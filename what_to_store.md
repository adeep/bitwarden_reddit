İnsanlar şifre yöneticilerinden bahsettiklerinde, her zaman web siteleri için şifre saklamayı düşünürler. Bu önemli bir kullanım, ancak düşünmeniz gereken birçok başka şey de var.

Şifre yöneticinizde saklamAMAmanız gereken şeyler, şifre yöneticisinde saklamak İSTEYEBİLECEĞİNİZ şeyler (ancak belki de değil) ve düşünmemiş olabileceğiniz şifre yöneticinizde saklanacak şeyler hakkında size bazı fikirler vermeye çalışacağım.

Son bölümde şifre kasası girişini NASIL dolduracağınız hakkında bazı fikirlerden de bahsedeceğim. Elbette, istediğiniz şekilde yapabilirsiniz, ancak belki kasa organizasyonunuzu nasıl geliştireceğiniz konusunda size bazı fikirler verebilirim.

# Ama önce, risk yönetimi ve şifre yöneticinizin incelemesi

En üst düzeyde, kimlik bilgisi depolamanıza *iki* tehdit vardır. İlki, yetkisiz bir tarafın sırlarınıza erişim sağlayabileceği riski, herkesin düşündüğü şeydir. Bunu önlemek için adımlar arasında iyi şifreleme, iyi ana şifre ve cihazlarınızı kötü amaçlı yazılımlardan korumak yer alır.

İkinci tehdit de önemlidir. Şifre yöneticinizden kilitli kalmak istemezsiniz! Bitwarden ana şifresi artı 2FA'nız kimlik bilgisi depolamanızın kilidini açmak için "anahtarlarınızdır". Eğer bunları kaybederseniz, sırlarınız sonsuza kadar kaybolabilir.

Düşünceli risk yönetiminin temeli risklerinizi belirlemek, olasılıklarını önceliklendirmek ve bu tehditleri hafifletmek için kaynak ayırmaktır. Kimlik bilgisi depolamanızı düşünürken, kimsenin izniniz olmadan okuyamayacağından emin olmak, ancak ihtiyacınız olduğunda kullanılabilir olmasını istiyorsunuz.

Bunu nasıl yapmaMANIN iyi bir örneği, ana şifrelerini hiç yazmayan insanlardır. Rastgele, karmaşık ve benzersiz ana şifre seçtilerse, onu tamamen unutma riskiyle karşı karşıyadırlar. Bu teorik risk değil; insanlar ayda birkaç kez Reddit'te bu konuda gönderi yapıyorlar ve kasaya geri dönmek için süper gizli arka kapı arıyorlar. Kötü haber, tabii ki, şifre yöneticinizin arka kapısı varsa, kötü adamlar da bunu bilecektir.

Bu yüzden kimlik bilgisi depolamanızın içeriği söz konusu olduğunda, ona tehditlerini analiz eder ve bu tehditleri nasıl yöneteceğinize karar verirsiniz. Bu öznel değerlendirme haline gelir. En muhtemel tehditler nelerdir? Risk altında olan nedir? Bu riskleri hafifletmek için ne yapmaya isteklisiniz? Tehdit gerçekleşirse ödemeye istekli olduğunuz bedel nedir?

Burada bir örnek, belki kasanıza erişimi kaybederseniz her web sitesi için kurtarma iş akışlarını çalıştırmaya istekli olmanızdır. Bununla ilgili çok sorun var: web sitelerinin listesini nereden alacaksınız? "Kurtarma soruları" birden fazla web sitesinde aynı cevapları paylaşıyorsanız tehdit olabilir. Ve spor salonu dolabının kilit kombinasyonu gibi (veya olması gereken) çilingir ve hizmet ücreti içeren sırlarınız var. Gerçekten tüm bunlarla uğraşmaya istekli misiniz?

Sonuç olarak, şifre yöneticinize koymaktan rahat hissetmeyeceğiniz şeyler olduğuna karar verebilirsiniz. Bunlar için argümanlar vardır (mutlaka ikna edici değil). Ancak yine, bu öznel karar olacaktır.

# Şifre yöneticinizde saklamaMANız gereken şeyler

Bu bölüm açıkça kişisel görüşüme göredir. İtiraz etmekte özgürsünüz.

# Bitwarden Kurtarma Bilgileriniz

Kasanıza erişimi kaybedebilirsiniz. Ana şifreyi unutabilirsiniz. TOTP'niz ("Kimlik Doğrulayıcı Uygulamanız") başarısız olup sizi çıkmaza sokabilir. Keşke kullanıcı adına, ana şifreye ve 2FA kurtarma koduna sahip olsaydınız!

Sorun dairesellikdir. Kasadan kilitli kaldığınızda bu şeyleri bulmak için kasanızın içine bakamazsınız. Bunun yerine istediğiniz bir [acil durum sayfasıdır](https://www.reddit.com/r/Bitwarden/comments/1fknnbo/emergency_kit_20/).

# Diğer web siteleri için 2FA kurtarma kodları

Çoğu web sitesinin kurtarma iş akışı vardır. Kontrol ettiğiniz e-posta adresi kadar basit veya tek kullanımlık şifreler listesi kadar karmaşık olabilir. Bu iş akışlarının farkında olmanızı ve kayıt tutmanızı şiddetle tavsiye ederim. Felaket kurtarma söz konusu olduğunda, artıklık çok iyi bir şeydir.

Ancak şifre yöneticinizi açabilir ve 2FA'nıza erişiminiz varsa, herhangi bir 2FA kurtarma koduna ihtiyacınız yoktur. Şifre yöneticinize erişimi kaybettiyseniz, acil durum sayfanıza ihtiyacınız vardır. 2FA'nıza erişimi kaybettiyseniz (Yubikey'iniz veya TOTP uygulamanız gibi), [tam yedeğe](https://www.reddit.com/r/Bitwarden/comments/1f995wl/making_bitwarden_backups_version_20/) ihtiyacınız vardır. Ne mevcut kasa ne de acil durum sayfası sorununuzu çözer.

Eğer herhangi bir nedenle biri kasanıza erişim sağlarsa, bu kurtarma kodları tartışmalı olarak risk olabilir. Yubikey veya TOTP uygulaması kullansanız bile, bu kurtarma kodlarını kimlik bilgisi depolamanızda bulundurmak artık birinin erişim sağlamak için Yubikey'inize ihtiyacı olmadığı anlamına gelir.

Her iki durumda da, kurtarma kodlarını kimlik bilgisi depolamanızda saklamak anlamsız ile gereksiz tehdit yüzeyi arasında bir yerdedir.

# Güvenlik soruları ve cevapları

Bazı web siteleri hâlâ kurtarma iş akışı olarak "güvenlik soruları" listesi kullanır. Bunlar "ilk erkek arkadaşınızın adı" ve "katıldığınız ilk okulun adı" gibi cevaplardır. Bir düzeyde, bu 2FA kurtarma kodları gibidir. Bu soruları ve verdiğiniz cevapları kesinlikle kaydetmek istiyorsunuz. Kasanıza erişiminiz varsa, bu cevaplara ihtiyacınız yoktur. Ve bu cevapları bilen herkes muhtemelen web sitesine yetkisiz erişim sağlayabilir.

Yan not: bu sorulara doğru tutarlı cevaplar vermek *istemezsiniz*. Sizi hedef alan biri (metamfetamin çılgını eski kayınbirader gibi) kişisel bilgilerini size karşı kullanabilir. Veya cevaplarınızı saklayan bir web sitesi ihlal edilirse, saldırganlar cevaplarınızı diğer web sitelerinde kullanabilir. Sonuç olarak, bu soruların kaydına ve her web sitesine verdiğiniz benzersiz yalanların kaydına ihtiyacınız vardır.

# Kripto Tohum

Kripto para hesapları normal finansal hesaplar değildir. Kredi kartları, banka kartları ve banka kredilerinin hepsinin özel kontrol ve dengeleri vardır. Birinin sahte çek yapıp sizden çalması oldukça mümkündür. Ancak resmin geri kalanı, bankaların parayı GERİ almada ÇOK İYİ olmasıdır. Hesap verebilirlik zinciri hırsıza yol açacak, paranız iade edilecek ve hırsızın Çok Kötü Günü olacaktır.

Kripto para farklıdır. Bu kilitler mevcut değildir. Hesabın kontrolüne sahipseniz, fonlar üzerinde tam, engelsiz ve kontrol edilmemiş kontrolünüz vardır.

Bu nedenle, en iyi uygulama kripto tohumları çevrimdışı tutmaktır. Güvenli bir yerde kağıt üzerinde yazılı olabilir. Yangın durumunda iki yerde kopyası bile olabilir. Ancak çoğu uzman onu hiçbir zaman çevrimiçi bırakmamanızı tavsiye edecektir. Soyulmanızın çok fazla yolu vardır ve hiçbir başvuru hakkınız olmayacaktır.

# Şifre yöneticinizde UYGUN olabilecek şeyler?

Bu bölüm açıkça kişisel görüşüme göredir. İtiraz etmekte özgürsünüz.

# TOTP Anahtarları

[TOTP](https://en.wikipedia.org/wiki/Time-based_one-time_password) oldukça iyi 2FA mekanizmasıdır. Sizinle web sitesi arasında paylaşılan sır (TOTP anahtarı) ile mevcut tarihsaati birleştirerek zamanla değişen "jeton" üretmek için çalışır. Bu genellikle her 30 saniyede değişen altı haneli sayıdır.

Bu şekilde 2FA kimlik doğrulama protokolü sırasında hiçbir sır maruz kalmaz. "Ortadaki saldırgan"dan küçük risk vardır, burada yanıltılıp "Truva Atı" web sitesine götürülür ve yanlışlıkla şifrenizi ve mevcut TOTP jetonunu girersiniz. Saldırgan bu bilgiyi hemen web sitenize giriş yapmak ve tarayıcı oturum çerezlerinizi diğer sırlar arasında toplamak için kullanabilir. Ancak sadece FIDO2 donanım jetonu veya geçiş anahtarı daha güçlüdür. Genel olarak, makul 2FA biçimidir.

Endişe, bir saldırganın "bir şekilde" kimlik bilgisi depolamanıza erişim sağlaması durumunda, hem şifrenizi hem de TOTP anahtarınızı elde etmesidir. Endişe ayrımı bakış açısından, TOTP anahtarlarınızı...başka yerde; şifre kasanızda değil yerleştirmek tartışmalı olarak daha güçlüdür.

*Neden uygun olabilir*

Şifre kasanızın doğrudan ihlali olasılık dışı olduğunu; web sitelerinize diğer saldırıların daha muhtemel olduğunu düşünebilirsiniz. Benzetme olarak, yatağınızın altında dolu av tüfeği tutmakla evinizin kilit ve hırsız alarmını geliştirmek arasında hangisi sizi daha iyi korur?

Bazıları risk hafifletmenizin diğer yollarla daha iyi hizmet edildiğini düşünür. Harici TOTP uygulamanızdaki veri tabanının bütünlüğü ve güvenliğinin başka bir endişe haline geldiğini unutmayın. Ve her durumda, Bitwarden'ın kendisini güvence altına almak için TOTP kullanıyorsanız, bu harici uygulamaya zaten ihtiyacınız olduğu sonucuna varabilirsiniz--tüm TOTP anahtarlarınızı orada tutabileceğiniz gibi.

(Bu, bu subreddit'te sık tartışma konusudur: Bitwarden'daki dahili TOTP işlevini kullanmanın uygun olup olmadığı. Bu konuda fikir birliği yoktur. Güvenlikte önemli gelişme olup olmadığına veya yerleşik işlevin kolaylığının güvenlikte olası azalmayı aşıp aşmadığına karar vermeniz gerekecektir.)

# Bitwarden Ana Şifreniz

Belki?

Buradaki düşünce, operasyonel güvenlikte eksiklik yaşarsanız, biri kilidi açılmış cihazınıza ulaşır ve sonra kilidi açılmış kasanıza ulaşırsa, *o zaman* ana şifrenizi öğreneceklerdir. Bu, saldırganın şifrelerinizi daha sonraki tarihte edinmesi için önemli bir adım olabilir.

*Neden uygun olabilir*

Açıkça kasanız için kasa girişine bakıyorsanız, ana şifreyi kullandınız. En azından, yakın zamanda. Ve biri kasanızın içeriğini inceliyorsa, ana şifre artık amacına hizmet etmiyor.

Ve bu kasa girişi kasanıza yeniden erişim kazanmanıza yardımcı olmasa da, acil durum sayfanız veya tam yedeğiniz bunu yapardı. Bu yüzden belki burada önemli güvenlik kaybı olmadan ek kolaylık vardır.

# Yubikey FIDO2 PIN'iniz (vb.)

Kasanızdaki TOTP anahtarlarına benzer şekilde, biri Yubikey'inizi çalmışsa ancak PIN'inizi bilmiyorsa, web sitelerinizdeki 2FA kontrolünü geçmek için Yubikey'i kullanamazlar.

*Neden uygun olabilir*

Çoğumuz için, fiziksel saldırı yüksek olasılık riski değildir. Ana Yubikey'im anahtarlığımda ve saldırganlara müsait değil. Yedek Yubikey'lerim kilitli ve sadece eşim ve alternatif icracımız konumlarını biliyor.

Yanlış PIN'i çok fazla kez girerseniz Yubikey tüm sırlarını temizler. Unutursam kullanabileceğim o PIN'lerin yedeği olduğunu bilmenin verdiği biraz huzur var.

# "Önemli" Girişler

Bazı insanlar web girişlerini iki kategoriye ayırır: saldırganlardan daha yüksek risk hissettikleri--banka hesapları gibi--düşük savunmasız olanlar, ButtBook ve SickSuck gibi. Şifre yöneticilerinde sadece daha az kritik sırları saklar ve geri kalanı için alternatif yöntem kullanırlar.

*Neden uygun olabilir*

Büyük sorun o "alternatif yöntem"dir. İkinci şifre yöneticisi kullanıyorlarsa, bu nasıl daha az savunmasız ve neden her şey için onu kullanmıyorsunuz? Yoksa o "önemli" hesaplar için zayıf veya yeniden kullanılan şifreler mi kullanıyorsunuz? Bu açıkça başlangıç noktası değil. Ve her durumda, acil durum sayfanızın veya tam yedeğinizin karmaşıklığını iki katına çıkardınız.

Ayrıca, "önemli" giriş dediğiniz şeyden bahsedelim. Instagram yorumları Dark Web'de çocuk pornografisi bağlantıları yayınlamak için kullanıldı. IG hesabınızın ikiliği çifti kasvetli FBI ajanı kapınızı çaldığında ihlal edildiğini öğrenmek istemezsiniz. Sonuç olarak, belki TÜM girişleriniz önemlidir.

# Şifre yöneticinizde gerçekten saklaMANIZ gereken şeyler

Bu bölüm düşünmemiş olabileceğiniz şeylerin bir koleksiyonudur.

* *Web Sitesi Girişleri* -- Bu herkesin ilk düşündüğü şeydir. Önemli kullanım durumudur. Her girişinizin benzersiz, karmaşık ve rastgele oluşturulmuş şifreleri olmalıdır. Burada düşünülecek başka şeyler de vardır. Bunu daha sonra konuşacağız.
* *Garanti ve seri numaralarını saklayın* -- Önemli cihazlarınız için seri numaraları (Dell dizüstü bilgisayarınızın hizmet numarası gibi) yararlı olabilir.
* *Yazılım lisans anahtarları* -- O sinir bozucu yazılım lisans anahtarları...on yıl öncesine göre artık o kadar yaygın görünmüyor, ama hâlâ birkaç tane var. Bunlar için ne tür güvenli stabil depolama kullanabilirim? Ah bekle! Şifre yöneticim bunun için iyi bir yer.
* *Diğer insanlar için şifreler* -- Karım gerçekten harika bir insan: zeki, komik, ama özellikle bilgisayar okuryazarı değil. Yedeklemelere bakarım ve etkili olarak sistem yöneticisi olarak çalışırım. Bu nedenle, acil durumlarda kullanmak üzere ana şifresi, banka kartının PIN'i ve birkaç başka öğe dahil kendi kasamda birkaç temel sır tutarım.

Kayınbiraderim benzer. Çok daha teknik düşünceli, ama tıbbi profesyonel; bilgisayarlar sadece bilgi kapsamının geçici parçası. Tüm yedeklemelerini ve güvenliğini yönetirim.

Ailenin başka tarafında, zorlanan sevgili yeğenim var. Telefonunu kaybettikten sonra (ve lanet Google Authenticator veri tabanı), devreye girdim ve güvenliğini yükseltmesine yardım etti. Ben onun yedekleri ve yedeklemelerini yönetiyorum.

* *Kapı Şifreleri* -- Kayınbiraderim kapılı toplulukta yaşıyor; kapı şifresini orada saklarım. Sevgili arkadaşın ev kapısının alarm koduna sahibim, böylece tatile çıktığında evine girebilir, postasını toplayabilir ve benzeri.
* Spor Salonu Dolabı -- Spor salonunda kullandığım o ucuz MasterLock: çalışıyorsam elbiselerimi geri almama yardımcı olmasa da, kasa girişi cüzdanımı ve telefonumu geri almak için birini kilidi imha etmek için ödeme yapmaktan kurtaracaktır.

Envanter alırsanız, sizin de bu tür birçok sırrınız olduğuna bahse girerim.

* *Sürücü Belgesi(leri)* -- Sürücü belge bilgilerimi, belge numarası ve son kullanma tarihi ile birlikte kasa girişinde bulundururum. (Pro ipucu: belgenizi yenilemek için son kullanma tarihinden yaklaşık altmış gün önce takvim uygulamanızda hatırlatıcı oluşturun.) Şifre yöneticiniz dosya eklerini destekliyorsa, bir görüntüsünü de kaydedin. Görüntü araba kullanmak için yasal olmayabilir, ancak ne kadar sık yararlı olabileceğine şaşıracaksınız. Uygunsa, eşiniz ve çocuklar için kopyalar kaydedin.

*Motorlu araç bilgileri*

Her araç için,

* VIN
* plaka numarası
* plaka son kullanma tarihi

Ayrıca araç için notlarda Kelly Blue Book'taki gibi öğenin tam açıklamasını eklemeyi seviyorum, örneğin,

>2021 Toyota Venza LE, 4D Sport Utility, 2.5L 4-Silindirli DOHC 16V, Sürekli Değişken (ECVT), AWD, Ruby Flare Pearl, Boulder w/Kumaş Koltuk Döşemesi, 6 Hoparlör, ABS frenler, Aktif Cruise Control, Klima, AM/FM radyo: SiriusXM, Apple CarPlay/Android Auto, Otomatik Uzun Far, Otomatik sıcaklık kontrolü, Elektronik Stabilite Kontrolü, Dış Park Kamerası Arka, Kumaş Koltuk Döşemesi, Dört tekerlek bağımsız süspansiyon, Ön Kova Koltuklar, Ön çift bölge A/C, Tam otomatik farlar, Aydınlatmalı giriş, Deri Vites Topuzu, Deri direksiyon, Düşük lastik basıncı uyarısı, Güçlü kapı aynaları, Güçlü sürücü koltuğu, Güçlü Bagaj Kapağı, Güçlü pencereler, Arka cam buğu giderici, Arka cam silecek, Uzaktan anahtarsız giriş, Hız algılama direksiyonu, Bölünebilir katlanır arka koltuk, Direksiyon üstü ses kontrolleri, Çekiş kontrolü, Sinyal gösterge aynaları, Değişken aralıklı
