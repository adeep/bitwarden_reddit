Bu, "tek başarısızlık noktası" kavramı hakkında bir yazıdır. Modern veri yönetiminde kritik bir kavramdır ve şifre veritabanınızın bakımına doğrudan uygulanır.

## ACID İşlemleri

Üniversiteden yüksek lisans derecemle mezun olup yazılım geliştirici olarak çalışmaya başladığımda, çok sayıda radikal fikrim ve vizyonum vardı. Sadece birkaç yıl sonra, veritabanlarını yönetmeye radikal yeni yaklaşım geliştirmekle meydan okuyulduğumuz en büyüleyici alanda çalışmaya başladım.

Beni veritabanı güvenilirliğinin temellerinde çalıştıran çok sabırlı olan mükemmel bir mentörum (Alan) olduğum için çok şanslıydım. Kavram aslında oldukça basittir. Alice'in Bob'a latte için 10 dolar ödediğini varsayalım. Veritabanı işlemi bakış açısından, aşağıdakilerden tam olarak biri olmalıdır:

1. Alice 10 dolar daha fakir, Bob 10 dolar daha zengin olur -- bu mutlu yoldur.
2. Ödeme başarısız olmaz. Alice'in bakiyesi değişmez. Bob'un bakiyesi değişmez.

Asla OLMAMASI gereken bazı şeyler:

* Alice 10 dolarını tutar, Bob ödeme almaz, ancak Alice latte'sini alır.
* Alice 20 dolar ücretlendirilir ancak sadece bir latte alır.
* Bob sadece bir latte sattığı için 20 dolar ödeme alır.

Dahası, Cindy işlemleri izliyor olabilir. Herhangi bir noktada, sadece uçuşta 10 dolar görmelidir. Kimse para sahte yapmıyor, süreçte sadece 10 dolar var.

...ve bunun gibi. Daha sonraki yıllarda, bu kavram veritabanı işlemlerinin [ACID özelliği](https://en.wikipedia.org/wiki/ACID) olarak resmileştirildi:

_Atomicitiy_: İşlem tek, bölünmez birim olarak ele alınır. Ya işlem içindeki tüm operasyonlar başarıyla tamamlanır ve işlenir ya da hiçbiri işlenmez. İşlemin herhangi bir parçası başarısız olursa, tüm işlem önceki durumuna geri alınır, kısmi güncellemeleri engeller.

_Tutarlılık_: İşlem veritabanını bir geçerli durumdan başka bir geçerli duruma getirmelidir. Tüm veri bütünlüğü kısıtlamalarının (örneğin, birincil anahtar kısıtlamaları, yabancı anahtar kısıtlamaları) işlem öncesi ve sonrasında korunmasını sağlar.

_İzolasyon_: Eşzamanlı işlemler birbirinden izole edilir, yani bir işlemin ara sonuçları diğer eşzamanlı işlemlere görünmez. Bu girişimi engeller ve her işlemin tek çalışıyormuş gibi çalışmasını sağlar.

_Dayanıklılık_: İşlem bir kez işlendiğinde, değişiklikleri kalıcı olarak saklanır ve sistem arızalarına veya çökmelerine dayanır. Bu genellikle değişiklikleri geçici olmayan depolamaya yazarak elde edilir.

Her sabah Alan'ın ofisine taze bir fincan kahveyle gelir, veritabanımızı nasıl ACID yapacağımızı tartışırdık. Haftalar boyunca, o kadar destekliydi: "Bu harika, Jason! Ama ne olur eğer...", kuyruğum bacaklarımın arasına girer, yeni bir kıvrım veya köşe durumu cevaplamak için masamama döneridim.

_Spoiler: Bir-iki ay sürdü, ama çözdük._

## Tek Başarısızlık Noktası (SPOF)

Bu sonraki soruna yol açtı. Dostum, o adam benimle çok sabırlıydı. Ne olur eğer...

* Güncelleme ortasında bilgisayar çöker.
* Güncelleme sırasında ağ bağlantısı kesilir.
* Güncelleme sırasında disk çöker?

* Güncelleme sırasında birden fazla bilgisayar çöker?
* Güncelleme sırasında birden fazla disk çöker?
* Heck, tüm veri merkezi çevrimdışı olursa?

ACID temelinde, kullanıcı _en fazla_ tek günceleme kaybetmeyi bekler. Bu güncelmemin başarısız olduğu (veya başarılı olduğu) konusunda net mesaj almalılar. Alice Bob'a ödeme yaptıysa, latte'sini almalı. Ödemesi geçmediyse, Bob bunu bilecek ve ona latte vermeyecek.

## Şifre Yöneticisinde SPOF

Tüm bunlar doğrudan şifre veri tabanınıza uygulanır. Tam olarak nasıl?

_İstemci makineniz_

Bitwarden mimarisinde, telefonunuz veya tarayıcınız SPOF _değildir_. Sadece kasanızın önbelleğe alınmış kopyasını tutar.

Kasa girişini düzenlediğinizde, değişiklikler _sadece_ makinenizde olur. "Kaydet"e tıkladığınızda, güncelleme atomik olarak Bitwarden sunucularına kaydedilir. En kötü ihtimalle değişikliğin sunucu tarafından kabul edilip edilmediği konusunda belirsizlik penceresi vardır (isteği gönderdikten hemen sonra ağ bağlantınızın kesilmesi gibi). Ancak bu bile "idempotent" istek çerçevesiyle hafifletilir...ama konudan saptım.

_Bitwarden Sunucusu_

Yani istemci makineniz SPOF değil. Peki sunucu makinesi? Bitwarden sunucunuz kesinlikle MSSQL, PostgreSQL, MySQL veya SQLite dahil olmak üzere ACID özelliklerine sahip veritabanı kullanır. Bu, sunucu çökerse ve yeniden başlarsa, en fazla gönderilen son işlemi kaybedeceği anlamına gelir.

_Bitwarden Diskleri_

Bitwarden sunucunuz Azure veri merkezinde çalışır. Tüm disk başarısız olursa ne olur? Bu durumda, Azure'un kendisinin verilerinizi yönetmek için [disk artıklık seçenekleri](https://learn.microsoft.com/en-us/azure/virtual-machines/disks-redundancy) vardır. [Ayrıntılar](https://bitwarden.com/help/data-storage/) biraz belirsiz. Bitwarden'a güvenmenin yanı sıra [kendi yedeklerinizin olması](https://github.com/djasonpenney/bitwarden_reddit/blob/main/backups.md) her zaman iyi bir fikirdir.

_Azure Veri Merkezi_

Tüm veri merkezi çökerse ne olur? Bu disklerle tam olarak aynı soru. Zaman zaman tam yedeklemeler yapmalısınız.

## Şifre Yöneticisi kullanımınızda SPOF

Bu çok daha ilginç hale geliyor. Kimlik bilgisi veri tabanınızda SPOF'u önlemek kendi davranışınızın işlevidir.

* _Ana Şifreniz_ -- Ayda yaklaşık bir kez, /r/Bitwarden'da biri ana şifresini unuttuğu için süper gizli arka kapı aradığı için panik halinde gönderi yapar. Beyniniz tek başarısızlık noktasıdır! Ana şifre isteğe bağlı değildir ve hafızanız güvenilir değildir. Ana şifreyi yeniden kazanmak için kurtarma iş akışına ihtiyacınız vardır. En basit haliyle, [acil durum sayfasına](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md) ihtiyacınız vardır.
* _2FA'nız_ -- telefonunuz ölürse, Bitwarden'ın kendisi için bile bir veya daha fazla site için TOTP kaybedebilirsiniz. Sarhoş amcanız ceketinizin üstüne oturursa, Yubikey'inizi yok edebilir.
* _Acil durum sayfanız_ -- acil durum sayfasının sadece bir kopyası varsa, doğal (veya doğal olmayan) felaket tarafından yok edilebilir.
* _Yedeğiniz_ -- yedeğin kendisinin sadece bir kopyası varsa, okunmaz hale gelebilir; dijital medya güvenilmezdir. Yedeğin kopyaları sadece bir yerdeyse, ev yangını tüm kopyaları yok edebilir -- esasen tekrar tek başarısızlık noktası.
* _Yedeklemenizi veya acil durum sayfanızı okuyacak varlıklar_ -- yedeği sakladığınız Google Drive'a giriş, yedek için şifreleme şifresi, hatta bulut hizmetinin kendisi bile SPOF olabilir. Bu yüzden Eski Okul'a gidiyorum ve sadece birden fazla USB bellek diski birden fazla konumda kaydediyorum. Artı yedek için şifreleme anahtarı benzer şekilde dağıtılır -- _USB'den farklı yerlerde_.
* _Ölümünüz_ -- Hepimiz bir noktada bu fani hayattan ayrılırız. Bu olduğunda, başka birinin parçaları toplaması gerekecek. Mahkeme kararı, tüm fotoğraflarınızın üzerinde olduğu NAS'a girişi mutlaka yeniden kazanmayabilir. Mahkeme kararı varlıklarınızı kurtarmalarına yardımcı olmayabilir (o ev yangınından sonra yeni çatı, kim?). Evet, ölümünüz potansiyel olarak SPOF olabilir.

## Sizin İçin Meydan Okuma

Şifre yöneticinizde tek başarısızlık noktanız var mı? En azından muhtemel risklere karşı hâlâ savunmasız mısınız? Yani, yüz megaton füzyon bombasından bahsetmiyorum, ancak ev yangını mümkün olan şeylerin kapsamı dışında değil.

Burada riski yönetme şeklinizi düşünün. Acil durum sayfası, tam yedekleme ve muhtemelen biraz şifreleme makul cevaplardır. Risk modelinize bağlıdır.
