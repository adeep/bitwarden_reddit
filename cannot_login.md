_Bu belgenin en güncel sürümü 
[GitHub'da bulunmaktadır](https://github.com/djasonpenney/bitwarden_reddit/blob/main/cannot_login.md)_.

Eğer iyileştirmeler veya düzeltmeler yapmak istiyorsanız, lütfen
[bir pull request oluşturmayı](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) düşünün.

# İçindekiler

TBD

# Giriş

Ah hayır! Kasanıza giriş yapamıyorsunuz. Sorun ne olabilir?

Önce kötü haber: Sorunun ne olduğunu öğrenmek için bazı deneyler yapmanız gerekecek. Birçok olasılık var ve ne olduğunu anlamak için biraz araştırma yapmanız gerekecek.

Daha da kötüsü, kasanızın içeriğini tamamen kaybetmiş olma ihtimaliniz var. Eğer önceden hazırlık yapmadıysanız, 
[kasanızı silmeye](https://bitwarden.com/help/forgot-master-password/) ve 
[yeniden başlamaya](https://github.com/djasonpenney/bitwarden_reddit/blob/main/getting_started.md) zorlanabilirsiniz.

Eğer bunu okuyorsanız ve hâlâ erişiminiz varsa, lütfen bir
[acil durum sayfası](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md) oluşturun.
Daha da ileri gidip gerçek bir
[tam yedekleme](https://github.com/djasonpenney/bitwarden_reddit/blob/main/backups.md) oluşturabilirsiniz.
Bu daha fazla iş; eğer bunaldıysanız, lütfen en azından acil durum sayfasını oluşturun.

# Yedek Yapın!

> Nereye gidiyoruz ve neden bu sepetteyim?

Deneyeceğiniz bazı şeyler potansiyel olarak yıkıcı olabilir. Bu nedenle - mümkünse - herhangi bir şey yapmadan önce yedeğiniz olmalıdır.

Bir [Acil Durum Sayfası](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md)
birçok basit durumda kurtuluşunuzdur:

* Ana şifrenizi unutursunuz (evet doğru; beyninin _hiçbir şeyi_ hatırlayacağına güvenemezsiniz);
* Kasanız [TOTP](https://en.wikipedia.org/wiki/Time-based_one-time_password) ile güvenlidir, TOTP uygulaması telefonunuzdadır ve telefonunuz kayıp geçen bir otobüsün tekerlekleri altında kalmıştır;
* Kasanız FIDO2 güvenlik anahtarı ile güvenlidir, ancak güvenlik anahtarınız kaybolmuş veya bozulmuştur.
* Siz _ÖLÜ_sünüz ve kocanızın elektrik faturasını ödemek için kasanıza girmesi gerekir

...ve bunun gibi. Acil durum sayfası, kimlik bilgilerinizin bozulmamış olduğunu ancak açıp kullanamadığınızı varsayar.

Bir [tam yedekleme](https://github.com/djasonpenney/bitwarden_reddit/blob/main/backups.md) 
bir adım daha ileri gider: kimlik bilgilerinizin bulut kopyası kaybolur veya bozulursa ne olur?
Bu nasıl olabilir?

* Bir kasa girişini güncellerken elleriniz titrer, onu zarar verir veya silersiniz ve aylar geçene kadar fark etmezsiniz;
* Kötü niyetli bir eski sevgili veya genç, Bitwarden yedekleme e-postasına anlık erişim sağlar ve açıkça 
  [kasanızı siler](https://bitwarden.com/help/forgot-master-password/).
  (Birçok kişi bu yedekleme e-postasının güvenliğinin bu küçük Aşil topuğunu bıraktığını duymaktan şaşırır.
  Bu, hesabınızdaki olağandışı etkinlik gibi Bitwarden'dan gelen kritik mesajlara ek olarak.)
* Dünya açılır ve Bitwarden veri merkezlerini yutar, böylece hiçbir bulut sunucusunda kelimenin tam anlamıyla kopya kalmaz.

Bitwarden kasanıza giriş yapamıyorsanız ve zaten yedeğiniz yoksa, _felaket kurtarmada_sınız.
İlk önceliğiniz mümkün olduğunca çok veri kurtarmak ve kaydetmek olmalıdır.

Sonraki bölümde bunun nasıl yapılacağını özetleyeceğiz.
Bu sizin ilk önceliğinizdir ve bu belgenin geri kalanı yapabildiğiniz kadar yedek aldığınızı varsayacaktır.

## Dışa Aktarma Yapma (eğer yapabiliyorsanız)!

Bitwarden'in bir
[dışa aktarma işlevi](https://bitwarden.com/help/export-your-data/) vardır.
Bu, yedekleme yapmanın önemli bir parçasıdır. 
Genel olarak dışa aktarmalar hakkında dikkat etmeniz gereken bazı şeyler vardır:

* Bitwarden dışa aktarımı, en az bir istemcide Bitwarden'a hâlâ giriş yapmış olmanızı gerektirir.

* Bitwarden dışa aktarımı ana şifreyi bilmenizi gerektirir. 
Giriş sorunlarınız ana şifrenizle ilgili bir sorunu içeriyorsa, dışa aktarma işlevini kullanamazsınız. Yine, her şeyi manuel olarak dışa aktarmanız gerekir. 

* Bitwarden dışa aktarımı [Gönderimler](https://bitwarden.com/products/send/) veya çöp kutusundaki hiçbir öğeyi içermez.

Bitwarden dışa aktarımları CSV veya JSON formatındadır.

* CSV dışa aktarımları dosya eklerini, kartları, kimlikleri ve geçiş anahtarlarını içermez. Bitwarden ekosisteminden ayrılmayı seçerseniz en iyisidir. JSON dışa aktarımı kadar eksiksiz değildir.

* JSON dışa aktarımları en eksiksizdir.
  Mümkünse, şifre korumalı şifreli olanları kullanın. _"Kısıtlı" dışa aktarma formatını kullanmayın._
  "Şifrelenmemiş JSON" dışa aktarımları bu durumda kabul edilebilir, çünkü zaten felaket kurtarmaddasınız.

* Bir kuruluş kullanıyorsanız ve Koleksiyonlarınız varsa, bunları web kasasındaki
  [yönetici konsolu](https://bitwarden.com/help/export-your-data/#export-an-organization-vault) aracılığıyla ayrı ayrı dışa aktarmanız gerekir.

## Zor Yoldan Yapma

Bitwarden dışa aktarma işlevini kullanamazsanız, _ancak kilidi açılmış bir Bitwarden istemcisine hâlâ erişiminiz varsa_:

* _O cihazı ağdan çıkarın_. 
  Mobil cihazsa, "Uçak Modu"na alın.
  Masaüstüyse, Ethernet kablonuzu çıkarın veya başka bir şekilde dünyanın geri kalanından bağlantısını kesin.
  Risk, bir Bitwarden istemcisinin sunucuyla konuşurken garip davranması ve sizi çıkarması olabilir.

* Kalem ve kağıt alın. Sessiz özel bir yerde, kilidi açık kasanızdaki her girişi tek tek gözden geçirin.
* Her girişi kağıdınıza kopyalayın.
* Düzgün yazın.
* "0" (sıfır) ile "O" (büyük oh), "1" (bir) ile "l" (küçük ell),
  "5" (beş) ile "S" (büyük ess) arasındaki farklara çok dikkat edin.
* Acele etmeyin! Çalışmanızı iki kez kontrol edin.
* [Geçiş anahtarlarını](https://bitwarden.com/passwordless-passkeys/) elle kopyalayamazsınız.
* Ekstra çalışma gerektirecek birçok öğe vardır.
  Bunlar arasında dosya ekleri, 
  [özel URI eşleştirme algılama](https://bitwarden.com/help/uri-match-detection/) ve herhangi bir kuruluş kasası bulunur.

Her şeyi kopyalamaya çalıştıktan sonra, geri dönün ve dışa aktardığınız kopyanın tam olduğundan emin olmaya çalışın.

Bu kılavuzun geri kalanı için, yapabildiğiniz kadar yedek aldığınızı varsayıyoruz.

# Bir Başlangıç: Çıkış Yapmış, Giriş Yapmış ve Kilitli

Bitwarden kasanız her zaman _üç_ durumdan birindedir:

* _Çıkış Yapmış_ -- erişim yok. 
  Buradan yapabileceğiniz tek şey giriş yapmaya çalışmaktır. Bu kullanıcı adınızı,
  ana şifrenizi ve 2FA'nızı gerektirir. Ayrıca
  [yeni cihaz doğrulaması](https://bitwarden.com/help/new-device-verification/) geçmeyi de gerektirebilir.
* _Giriş Yapmış_ -- kasanız açık. Buradan açıkça çıkış yapabilirsiniz. Ayrıca kasayı "kilitlemek" de mümkündür,
  genellikle zaman aşımı nedeniyle. Ayrıntılar Bitwarden istemcinizin seçenekleri tarafından kontrol edilir.
* _Kilitli_ -- kasanız Bitwarden sunucusu tarafından kimlik doğrulamasından geçmiştir, ancak yerel erişim yoktur.
  Kasanızın kilidini açmak PIN, biyometri veya hatta ana şifreyi yeniden girmeyi gerektirebilir.
  Bu seçenekler Bitwarden istemcinizin seçenekleri tarafından kontrol edilir.

Tüm bunlar hakkında daha fazla bilgi [burada](https://bitwarden.com/help/unlock-with-pin/#understanding-unlock-vs-log-in).

_Kilidi Açma Sorunları_

Eğer sadece "kilitli"yseniz, mevcut Bitwarden istemcinizin kilidini açmanız gerekir.
Sunucu dahil değildir; bu Bitwarden istemcinizle yerel bir sorundur.
Burada dört yaygın olasılık vardır:

*   [PIN ile Kilidi Açma](https://bitwarden.com/help/unlock-with-pin/) -- bunu önceden kurmuş olmanız gerekir;
*   [Biyometri ile Kilidi Açma](https://bitwarden.com/help/biometrics/) -- bunu önceden kurmuş olmanız gerekir;
*   Ana şifrenizle kilidi açma -- bu her zaman izin verilir.
*   Ayrıca bir [geçiş anahtarı](https://bitwarden.com/help/login-with-passkeys/) aracılığıyla erişiminiz olabilir.

Dikkatle bakın; istemciniz sizden _ana şifrenizi_ mi
yoksa _PIN'inizi_ mi (sadece kilidi açarken geçerli) istiyor? 
Bunlar birbirinin yerine kullanılamaz; ana şifreniz istendiğinde PIN çalışmaz (ve tersi de geçerlidir), ve PIN'iniz tek başına _asla_ giriş yapamazsınız.

Ana şifrenizle kilidi açmak işe yaramazsa, ya Bitwarden istemciniz yana gitmiştir (yaygın değil ama mümkün), ya da (korkunçlu!) ana şifrenizi unutmuşsunuzdur.

# İlk Adımlar: "Web kasası"nı test edin

⚠️ [Yedek](#yedek-yapın) yaptınız mı?

Peki burada ne oluyor? En baştan başlayalım: Bitwarden istemcinizi tamamen eleyim.
Tarayıcınızda kasa web sayfasına gidin
([ABD sunucusu](https://vault.bitwarden.com), [AB sunucusu](https://vault.bitwarden.eu),
veya muhtemelen kendi barındırdığınız bir örnek).

Web sayfası _yüklenmiyorsa_, ya bilgisayarınızda ağ sorunu var ya da sunucu hatası var.

* Hesabınızın hangi sunucuda olduğundan emin değilseniz, ikisini de deneyin. Sunucular _birbirinin yerine kullanılamaz_.
* _Farklı tarayıcılarla_ giriş yapmaya çalışın.
* _Özel/gizli tarayıcı oturumu_ kullanmayı deneyin.
* _Tarayıcı önbelleğini silmeyi_ deneyin.

️️️⚠️ Sadece önbelleğe alınmış tarayıcı içeriğini silin.
  _Tarayıcı çerezlerinizi silmeyin_.
  Bu noktada tarayıcı çerezlerinizi kaybetmek Bitwarden'ın cihazınızı "bilinen cihaz" olarak "unutmasına" neden olabilir, bu da
  [yeni cihaz doğrulaması](https://bitwarden.com/help/new-device-verification/) 
  veya hesabınızda 2FA'ya ihtiyaç duymanıza yol açabilir.

️⚠️ "Çok sık" giriş yapmaya çalışırken: Bitwarden sunucuları
[9 başarısız giriş girişiminden sonra CAPTCHA doğrulaması gerektirecektir](https://bitwarden.com/help/security-faqs/#q-how-can-i-protect-my-bitwarden-account-from-brute-force-attacks)
bilinmeyen bir cihazdan, bu yüzden denemelerinizde dikkatli olun.

Bu deneylerden en az biri başarılı olursa, bunun bir sunucu sorunu olmadığını bilirsiniz ve Bitwarden istemci(ler)inizin işleyişine odaklanabilirsiniz.

# Bitwarden sunucusuna bağlanamıyor

⚠️ [Yedek](#yedek-yapın) yaptınız mı?

[Web kasasına bağlanmayı](#ilk-adımlar-web-kasasını-test-edin) deneyip sorun yaşadınız mı?
Sunucunun kendisi veya bağlantınız olabilir:

* _Diğer cihazlar ve diğer ağlar_ aracılığıyla (yani Wi-Fi'ye karşı hücresel) giriş yapmayı deneyin.

* Mobil cihazlarda: _Wi-Fi'yi geçici olarak kapatmayı_ deneyin, yani hücresele geçin. 
  Veya tam tersi.
  Bu bazı ağ ve/veya IP adresi sorunlarını "çözebilir".

* Yerel ağınızdaki tüm cihazlar için: yönlendiriciyi kapatın, 30 saniye bekleyin, sonra tekrar açın.
  Bu bazı ağ adresleme sorunlarını çözebilir.

* VPN kullanıyorsanız, onu kapatın (veya açın), (en azından geçici olarak).

Bitwarden sunucusuna bağlanamıyor gibi görünüyorsanız (ancak diğer siteler doğru bağlanıyor gibi görünüyor):

* [Bitwarden durum sayfasına](https://status.bitwarden.com) bakarak başlayın.
  Belki bu bilinen bir sorun veya planlı bir kesinti.
* _Bitwarden (ABD/AB) sunucuları geçici olarak kapalı mı_?
  [Downdetector](https://downdetector.com/status/bitwarden/) diğer kullanıcıların da sorunu yaşayıp yaşamadığını görmek için iyi bir çapraz kontrol.

* _Kendi barındırıyorsanız_, kendi sunucunuzun _doğru çalıştığını doğrulayın_.  Giriş sorunlarınızın kendi barındırdığınız Bitwarden sunucunuzun yerel hataları yanlış yapılandırmaları nedeniyle olması mümkün.
Bu sorunlar bu kılavuzun kapsamı dışındadır). Ancak lütfen _en son sunucu sürümünün_
yüklü olduğunu doğrulayın. "Yeni" istemci sürümleri 
"eski" sunucu sürümleriyle iletişim kurmakta sorun yaşayabilir.

Bitwarden sunucunuz kapalıysa, yapabileceğiniz çok fazla şey yok -- yine, henüz yapmadıysanız yedek yapmak dışında.

Web kasası aracılığıyla giriş yapabiliyorsanız, ancak yerel Bitwarden istemcinizi (veya tarayıcı uzantısını) kullanamıyorsanız, Bitwarden istemci sorununuz var.

Web kasası aracılığıyla giriş yapamıyorsanız, kullanıcı adı/şifre sorununuz olabilir.

# Bitwarden İstemci Sorunları

Web kasası aracılığıyla başarıyla giriş yapabiliyorsanız, ancak Bitwarden istemciniz aracılığıyla sorun yaşıyorsanız, iyi haberle başlayın: kimlik bilgileriniz kaybolmadı!

Ancak soru şu ki, sorununuz tek bir Bitwarden istemcisi, tek ana makine, hatta belki belirli bir ağla mı ilgili.

⚠️ [Yedek](#yedek-yapın) yaptınız mı?

* _Bitwarden istemcisini kaldırıp taze bir sürüm yüklemeyi_ deneyin. 
  Mevcut bir Bitwarden istemcisinin yükseltmeden sonra kafasının karışabileceği birden fazla durum var gibi görünüyor. O istemciyle şu anda giriş yaptıysanız,
  _[yedek yapmadan](#yedek-yapın) istemciyi kaldırmayın_.

* [Diğer Bitwarden istemcileri](https://bitwarden.com/download/) aracılığıyla giriş yapmayı deneyin.

* Farklı bir cihazda Bitwarden istemcisi kullanmayı deneyin.
  Bu bir OS sorunu,
çakışan tarayıcı uzantısı veya diğer çevresel faktörler olup olmadığını gösterebilir.

* Yine, mümkünse, farklı bir ağ deneyin.
Dizüstü bilgisayarınızı bir kafeye götürün. 
Wi-Fi'yi kapatın (veya açın) böylece İnternet'e farklı bir bağlantı kullanacaksınız.
VPN'inizi etkinleştirin veya devre dışı bırakın.
VPN'iniz için farklı bir çıkış düğümü deneyin.

Bu deneylerin arkasındaki nokta, zincirdeki kırık bağlantıyı tespit etmek ve araştırmanızı daha yakından yönlendirmektir.

## KDF Sorunları

⚠️ [Yedek](#yedek-yapın) yaptınız mı?

Bitwarden artık
[KDF ayarlarınızı](https://bitwarden.com/help/kdf-algorithms/) kasanızı ilk oluşturduğunuzda aldığınız
varsayılan ayarlardan farklı olacak şekilde değiştirmenizi öneriyor.
Bu değişikliği yaptığınızda bazı Bitwarden istemcilerinin kötü davranma olasılığı var. 
Web kasası aracılığıyla giriş yapabiliyorsanız, ancak bir
veya daha fazla Bitwarden istemciniz çalışmıyorsa,

* İstemcinizi _Tamamen_ çıkarın ve tekrar girin.
* KDF ayarlarınızı geçici olarak varsayılana geri döndürmeyi düşünün ve tekrar deneyin.

> Özellikle iOS'ta, Argon2 ayarları "çok yüksek" olabilir: bunları varsayılan değerlere değiştirin (en azından
> "bellek" için).
> Bitwarden'a göre: "iOS, otodoldurma için uygulama belleğini sınırlar. Belleği varsayılan 64 MB'den artırmak, otodoldurmayla kasanın kilidini açarken hatalara neden olabilir."

## Uygulama donuyor veya çöküyor, veya başka şekilde açıklanamaz davranıyor

Bir Bitwarden istemcisi tutarlı bir şekilde çökerse veya başka açıklanamaz davranışları varsa, tam kaldırma ve yeniden yükleme yapmayı düşünün.

⚠️ Bitwarden mobil uygulamasını, masaüstü uygulamasını ve tarayıcı uzantısını kaldırmanın bu uygulamaları
Bitwarden için tekrar "bilinmeyen cihazlar" yapacağını unutmayın, 
[yeni cihaz doğrulaması](https://bitwarden.com/help/new-device-verification/) ve giriş koruması nedeniyle e-posta giriş doğrulama kodu gerektirecektir. 
Kasanızda 2FA'yı etkinleştirmeyi başaramadıysanız bu kritiktir; e-posta doğrulama kodlarını alacağınız e-posta hesabınıza erişiminiz olduğundan emin olun.

1. Uygulamayı kaldırın. Kaldırmadan önce "çıkış" yapamıyorsanız endişe etmeyin.
2. Uygulamanın yerel depolamasını silin--kaldırmanın sistemde uygulamadan iz bırakmadığından emin olun.
   Kaldırıcıya güvenmeyin; kaldırıcının kaçırmış olabileceği başka [yerel depolama](https://bitwarden.com/help/data-storage/) olup olmadığını görün.
3. Cihazınızı yeniden başlatın,
4. Uygulamayı taze indirmeden yeniden yükleyin.
5. Tekrar giriş yapmayı deneyin.

Bu özel Bitwarden istemcisi kötü davranmaya devam ederse, ancak kullanıcı adı/şifre sorunu olmadığını dışladıysanız, daha fazla yardım almak için yeni bir gönderi oluşturabilirsiniz. Sorunu mümkün olduğunca ayrıntılı açıklamaya çalışın,
hangi tam hata mesajını aldığınız (ideal olarak ekran görüntüsüyle, ancak kişisel ve
hassas verileri bulanıklaştırdığınızdan emin olun), belki de zaten neyi denediğiniz (ve işe yaramadığı) vb.

Ayrıca [Bitwarden destek](https://bitwarden.com/contact/) ile iletişime geçip yeni bir sorun bileti oluşturabilirsiniz.

Bir hata bulduğunuza inanıyorsanız--"diğer" veya "garip" hata mesajlarınız var--bunu
GitHub'da rapor edebilirsiniz (tarayıcı uzantısı, masaüstü uygulaması,
web kasası ve CLI için [buraya](https://github.com/bitwarden/clients/issues), Android mobil uygulaması ve
Android Authenticator uygulaması için [buraya](https://github.com/bitwarden/android/issues), ve iOS mobil uygulaması ve
iOS Authenticator uygulaması için [buraya](https://github.com/bitwarden/ios/issues)…)

## E-posta ve/veya Ana Şifre

Peki web kasası _düzgün çalışıyor gibi görünüyorsa_, yine de oraya (veya başka hiçbir yere) giriş yapamıyorsanız ne olacak?
Sonra ne yapacaksınız?
Bu noktada, kullanıcı adınız, ana şifreniz veya her ikisiyle ilgili bir sorunu şüphelenmeli.z

️⚠️ "Çok sık" giriş yapmaya çalışırken: Bitwarden sunucuları
[9 başarısız giriş girişiminden sonra CAPTCHA doğrulaması gerektirecektir](https://bitwarden.com/help/security-faqs/#q-how-can-i-protect-my-bitwarden-account-from-brute-force-attacks)
bilinmeyen bir cihazdan, bu yüzden denemelerinizde dikkatli olun.

* Yanlış web kasasında mısınız, [ABD kasası](https://vault.bitwarden.com) mı [AB kasası](https://vault.bitwarden.eu) mı)?
Bunlar _birbirinin yerine kullanılamaz_.
Bunu daha önce denemediyseniz, devam edin ve diğer web sunucusu aracılığıyla giriş yapmayı deneyin.

_E-postanızı kontrol edin._

* _Gerçekten hesabınız var mı?_
  [Bitwarden'a gidin](https://bitwarden.com/pricing/) ve yeni hesap oluşturmayı deneyin.
  Eğer _zaten_ hesabınız varsa, gelen kutunuzda mesaj _almayacaksınız_.
  Eğer e-posta mesajı _alırsanız_, ya e-postayı yanlış hatırlamışsınız ya da biri (kötü niyetli
  aile üyesi?) onu silmiş.
  Yanlışlıkla yeni kasa oluşturduysanız, lütfen şimdi [silmeyi](https://bitwarden.com/help/forgot-master-password/) düşünün.)

> E-posta adresi için, Bitwarden küçük harf veya büyük harf kullanmanız umurunda değil,
> dolayısıyla example@example.com veya EXAMPLE@EXAMPLE.COM ile giriş yapmaya çalışırsanız – ikisi de tam olarak aynı şekilde çalışmalıdır. Bu ana şifre için geçerli değil!

_Ana şifrenizi kontrol edin_

* _E-posta adresinizi ve ana şifrenizi doğrulayın_
  [acil durum sayfanıza](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md) başvurarak.
* "Ana şifre ipucu" belirlediniz mi? Öyleyse, [talep etme](https://vault.bitwarden.com/#/hint) zamanı.

> Pro ipucu: birçok kişi ana şifre ipucunu acil durum sayfalarını nerede sakladıklarını hatırlatmak için kullanır.

* Belki _yakın zamanda e-posta adresinizi ve/veya ana şifrenizi değiştirdiniz_?
  Ve daha kötüsü, acil durum sayfanızı güncellemediniz mi?
  Bir adım geri çekilin, rahatın, yürüyüşe çıkın, bir fincan kahve alın.
  Belki bir anda aklınıza gelir.

_Yazım hatalarını arayın_

* _E-posta adresinizde ve/veya ana şifrenizde herhangi bir yazım hatası arayın_, özellikle aptalca yazım hataları veya daha belirgin
  olanlar như _0 (sıfır) ile O (büyük harf "oh")_, _l (küçük "L") ile I (büyük harf "i")_,
  veya _| (özel karakter "dikey çubuk")_.
* _Eklenen veya eksik boşlukları arayın_: sondaki boşluklar, başlangıç boşlukları veya ana şifrenizde çift boşluklar. Şifredeki boşluk kritiktir!
  Tutarsızlık ya onu yazarken ya da ana
  şifreyi oluştururken olabilir.

_"Özel" Karakterler_

Ana şifrenizde _sorunlu özel karakterler_ var mı?
ASCII olmayan, Unicode veya Emoji karakterler bir sistemde çalışabilir ancak diğer sistemlerde çalışmayabilir.
Ana şifreniz sadece "güvenli" 95 karakterli
[yazdırılabilir ASCII karakter setini](https://commons.wikimedia.org/wiki/File:ASCII-Table-wide.svg) kullanmalıdır

Ana şifreniz _şu anda_ çalışsa bile, sistem yükseltmesi gelecekte başarısız olmasına neden olabilir! 

Karakter seti sorununuz olabileceğinin güçlü bir işareti, web kasanız veya bazı Bitwarden istemcilerinden giriş yapabilmeniz ancak diğerlerinden yapamamanızdır.
Bu durumda, ana şifrenizi değiştirmeyi düşünün,
ancak yine, önce [yedek yaparak](#yedek-yapın) başlayın!

Birçok kişi şifreye garip karakterler koymanın onu "daha güvenli" hale getirdiğini düşünür. Güvenlik açısından, garip karakter bazılarının umduğu kadar yardımcı olmaz: `MyDögHàŝFlèaß` neredeyse 
güvenlik ("rastgelelik" veya "entropi") katmaz
sadece biraz daha uzun ama çok daha idare edilebir [parola öbeği](https://xkcd.com/936/) kullanmak kadar, örneğin
`polka-fame-curled-either-passover` veya `WinnerPlasmaKabobSinuous`.

Dahası da var, noktalama işaretleri ve
özel karakterler ana şifreyi hatırlamayı ve yazmayı zorlaştırır.

Ana şifrenizi güncellemeyi seçerseniz, Bitwarden'ın kendisi tarafından oluşturulan 4 kelimelik parola öbeği kullanın.
Ekstra güvenlik istiyorsanız,
Bitwarden'ın parola öbeğine başka bir kelime (hatta iki kelime) eklemesini sağlayın.

Sorunlu özel karakterlere geri dönersek, "en güvenli" karakterler, "yazdırılabilir ASCII karakter seti",
ana şifrede kullanmanız gereken tek karakterler şunlardan oluşur:

* büyük harfler A-Z
* küçük harfler a-z
* rakamlar 0-9
* boşluk karakteri
* ! (ünlem işareti)
* " (çift tırnak)
* \# (octothorpe, "pound", "hashtag" veya "sharp" olarak da bilinir)
* $ (dolar işareti)
* % (yüzde)
* & (ampersand)
* ' (apostrof)
* ( (sol parantez)
* ) (sağ parantez)
* \* (yıldız işareti, "star" veya "splat" olarak da bilinir)
* \+ (artı)
* , (virgül)
* \- (tire)
* . (nokta, veya "dot")
* / (slash)
* : (iki nokta)
* ; (noktalı virgül)
* < ("küçüktür")
* = (eşittir)
* \> ("büyüktür")
* ? (soru işareti)
* @ (at işareti)
* ^ (carat)
* _ (alt çizgi)
* \` (geri tik)
* ~ (tilde)

> Bu karakterlerin tümü Bitwarden ana şifresinde kabul edilebilir olsa da,
> diğer web sitelerinin bazılarıyla sorun yaşayabileceğini unutmayın.

_Otomatik Düzeltme Sorunları_

Ana şifrenizin klavyeniz, cihazınız veya hatta istemci (tarayıcı) tarafından bozulması mümkündür. Yani, bu bir otomatik düzeltme sorunu olabilir.
Özellikle şifre girişi genellikle gizlendiği için bunu kolayca fark etmeyebilirsiniz. 
Bahsedilen güvenli karakterlerle bile,
bazı karakterler klavyeniz, istemciniz veya cihazınız tarafından otomatik düzeltilebilir:

* Bazı sistemler düz tırnakları (`'` veya `"`) kıvrık tırnaklarla değiştirir 
  (yani, "akıllı tırnaklar", örneğin "&ldquo;", "&rdquo;",
  "&lsquo;" ve "&rsquo;"). MacOS bu konuda özellikle ünlüdür.
* "." (nokta/tam durma) ve/veya "boşluk tuşu"na bastıktan sonra görünmez boşluklar eklemiş olabilirsiniz.
* Bazı sistemler otomatik olarak
  girdi küçük harfini büyük harfe veya tam tersine değiştirir.
* iOS'ta: _akıllı noktalamayı devre dışı bırakın_, çünkü bu yazdığınız karakterleri "otomatik düzeltebilir". 
  Ayarlar->Genel->Klavye altına bakın ve _Akıllı Noktalama_yı kapatın.
* Genel olarak, her türlü apostrof ve tırnak işareti (', ", `, ´, ', ', ‛, ", ", ‟) kullandığınız cihaz veya uygulama tarafından tercih edilen farklı bir forma otomatik düzeltilebilir.

Girdiğiniz doğru şifreyi bulmak veya sisteminizde doğru şifreyi yazmak için ne deneyebilirsiniz?

* Mümkünse _otomatik düzeltmeyi kapatın_.
  iOS'ta, Ayarlar->Genel->Klavye'ye gidin ve hem _Otomatik Büyük Harf_ hem de _Otomatik Düzeltme_yi devre dışı bırakın.
* _(Sanal veya fiziksel) klavyenizi değiştirmeyi_ deneyin.
* Mümkünse _klavye girişinizi görünür yapın_.
* Daha dikkatli yazın (ellerinize bakın!).
* Windows'taki [Karakter Haritası](https://support.microsoft.com/en-us/topic/how-to-use-special-characters-in-windows-documents-ec1a4e84-706e-67a5-e52b-e3ebab90313f) gibi _ekran klavyesini kullanın_.
* Şifreyi `Notepad` veya `TextEdit` gibi bir metin düzenleyicide yazmayı ve sonra giriş formunuza yapıştırmayı düşünün.

## Kayıp Şifre veya Kayıp 2FA

> Bunların hiçbiri işe yaramıyor! Web kasası orada, ama giriş yapmama izin vermiyor.

Şifrenizi gerçekten kaybettiyseniz, ne yazık ki kasanıza geri girmeniz için süper gizli bir arka kapı yoktur.
Bitwarden ne ana şifrenizi sıfırlayabilir ne de herhangi bir şekilde "atlatabilir".
Bitwarden ana şifresi sizi "kimlik doğrulamak"tan fazlasını yapar; aynı zamanda kasanızın şifrelenmesinde büyük bir faktördür.
_Ana şifreniz kasanızın şifresini çözmek için gerekli bir girdimdir ve
ana şifreniz asla cihazınızı terk etmez._

Bu sizin korunmanız içindir. Bu, Bitwarden sunucusu kötü niyetli kişiler tarafından ele geçirilse bile, kasanızın şifresini çözmek için gerekli sırrı ellerinde bulundurmayacağı anlamına gelir. Ana şifre mevcut olmadığı sürece, başka biri tarafından sıfırlanamaz veya değiştirilemez.

⚠️ Mümkünse, [yedeğiniz](#yedek-yapın) var mı?

Tek kalan umudunuz ana şifreyi hatırlayabilmeniz veya hatta "tahmin edebilmenizdir".
Hatırlama şansı olduğuna inanıyorsanız, zaman ayırın--hatta birkaç gün--ve belki hatırlarsınız.
Bazen oturup odaklanmak iyidir.
Ya da belki birkaç gün düşünmemek iyidir…

⚠️ "Çok sık" giriş yapmaya çalışırken: Bitwarden sunucularının
"bilinmeyen bir cihazdan 9 başarısız giriş girişiminden sonra CAPTCHA doğrulaması gerektireceğini" unutmayın.
Dikkatli olun ve denemelerinizde mümkün olduğunca doğru olun.
Aksi takdirde her şifre tahmininizden önce ek CAPTCHA
zorluklarıyla karşılaşmaya başlayacaksınız.

_Bitwarden hesabınızı gerçekten kaybettiyseniz_,
kullandığınız e-posta adresine erişiminiz olduğu sürece [Bitwarden hesabınızı silebilirsiniz](https://bitwarden.com/help/forgot-master-password/).

Hesap silme geri alınamaz!
Yine, [yedeğiniz](#yedek-yapın) var mı?
Sonra, [yeni hesap oluşturabilir](https://github.com/djasonpenney/bitwarden_reddit/blob/main/getting_started.md)
ve ideal olarak en son yedeğinizi/dışa aktarmanızı içe aktarabilir/geri yükleyebilirsiniz.

## "Hacklendim" mi?

Bazen biri şifre yöneticisine giriş yapamayınca, "hacklenmiş olmalıyım" diye düşünürler.
Bunun naif olduğuna inanıyorum:

Güçlü bir ana şifreniz (benzersiz, karmaşık ve rastgele oluşturulmuş) ve kasanızda iyi 2FA'nız (FIDO2 donanım güvenlik belirteci veya TOTP uygulaması) olduğunu varsayıyorum. 
Cihazınıza kötü amaçlı yazılım indirmediğinizi varsayıyorum: "hack", "crack" veya "hile" yok; cihazınızda güncel OS yamaları var (ve güncel yamalar yoksa veya güncellenemiyorsa kullanmıyorsunuz); başka kimsenin klavyeye veya hatta USB portlarına erişimine izin vermiyorsunuz, vb.

Bu durumda ezici olasılık bunu _kendinizin yaptığıdır_. Evet, orada karşı koyamayacağınız egzotik saldırlar var, ama bunlar son derece nadir. Bir rapor, bu sofistike saldırıları kullanan varlıkların _kişi başına_ 250.000 dolar aldığını gösteriyor.

Gerçekten kötü amaçlı yazılımınız varsa, ezici olasılık _onu indirip yüklediğinizdir_. Bu kötü bir uygulama indirmek (veya yan yükleme yapmak), kasıtlı olarak "hack" veya "crack"li oyun indirmek, ya da belki garip veya beklenmedik e-posta ekini dikkatsizce açmak olabilir.

_Neden şifre yöneticisi?_

Bir saldırgan banka hesaplarınızı ve diğer varlıklarınızı yağmalamak isteseydi, ihlali keşfetmenizin mümkün olduğunca uzun sürmesini sağlarlardı. Kötü işlerini yapmak için mümkün olduğunca çok zamana ihtiyaçları var.
Şifre yöneticinizin girişini değiştirmek yapacakları şeylerin listesinin neredeyse en altındadır.

Tabii, istisnalar vardır. Kötü bir aktör örneğin Amazon hesabınızı ele geçirip bırakma konumuna mal göndermek veya [brushing dolandırıcılığı](https://www.uspis.gov/news/scam-article/brushing-scam) başlatmak için kullanabilir.

Yasadışı içerik yayınlamak (ve yasadışı içeriği kaldırmanızı geciktirmek) için sosyal medya hesabının girişini değiştirebilirler.

Bunun tek istisnası, _kendi sırlarınıza erişiminizi reddederek_ size keder vermek isteyen kinci eski eş veya asi genç olabilir. Bunun gibi gerçek köşe durum dışında, saldırganın kasanızı değiştirmesi olası bir senaryo değildir.

## Bir Önlem

> Ahır kapısı? Kapatılması gerekiyor?

Özel olarak konu hakkında değil, bunun tekrar olmasını önlemeye çalışmak için bazı ek düşünceler.

_Acil Durum Sayfası_

Bir [acil durum sayfası](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md) her kullanıcının düşünmesi gereken minimal bir önlemdir.

_Yedeklemeler_

_Kasanızın düzenli [yedeklemelerini](https://github.com/djasonpenney/bitwarden_reddit/blob/main/backups.md) yapın.

Benim düşüncem, yedekleme acil durum sayfasının uygun bir üst kümesidir. Acil durum sayfası çevrimiçi kimlik bilgilerinizin bozulmadığını varsayar. Yedekleme bunun ötesine geçer ve başka yerde kullanabileceğiniz kimlik bilgilerinizin tam kopyasını oluşturur: [kendi barındırma](https://bitwarden.com/help/self-host-an-organization/) veya hatta farklı bir şifre yöneticisine geçmek.

Yedekleme "çıkarma senaryosunu" _kendi başına_ engellemez, ancak başka bir yedek sağlar.
Bitwarden kasanıza erişimi kaybederseniz, o zaman önemli verilerinizin çoğuna veya tümüne sahip olacaksınız ve bu verileri yeni kasaya geri yükleyebileceksiniz.

Yedeklemelerin periyodik olarak güncellenmesi gerekir. Her üç, altı, hatta on iki ayda bir kasanızın yedeklemesini yapmak için yinelenen takvim hatırlatıcısı oluşturmayı düşünün.
Ben yıldızda bir kez yedekleme yaparım ve bunu bir sonraki kasabadaki ailemizle görüşmek için bir bahane olarak kullanırım, şifreli USB bellek çiftini taze kopyayla değiştirmek için.

_Şimdi İki Faktörlü Kimlik Doğrulamayı Kurun._

Akıllı siber güvenlik önlemi olmasının yanı sıra, 2FA kurarısanız "dairesel çıkarma" sorununa neden olabilecek potansiyel Bitwarden "yeni cihaz doğrulaması" sorunlarını atlayacaktır. Sadece 2FA kurtarma bilgilerinizi tam yedeğinize dahil ettiğinizden emin olun.

_Acil Erişim_

Bitwarden [Acil Erişim](https://bitwarden.com/help/emergency-access/) de yardımcı olabilir.
Bunun ücretli Bitwarden aboneliği gerektirdiğini ve birinin kasanıza erişim sağlamadan önce zorunlu bir bekleme süresi olduğunu unutmayın.

_Geçiş Anahtarı ile Giriş_

"Geçiş anahtarı ile giriş"-geçiş anahtarları aracılığıyla Bitwarden hesabı için yedek giriş yöntemi ekleyebilirsiniz, ideal olarak "şifrelemeyle.
Bu ana şifreyi girmeden ve 2FA'nız veya "yeni cihaz doğrulaması" kodu olmadan giriş yapmayı mümkün kılar.
Şifrelemeli bu giriş-geçiş anahtarları PRF özellikli tarayıcıya, "geçiş anahtarı-cüzdana"
(yani o geçiş anahtarını nerede sakladığınıza) ve OS'nin oluşturulmasını desteklemesine bağlıdır.
Şu anda, "geçiş anahtarı ile giriş" hâlâ Beta'dadır ve sadece web kasasına giriş için mümkündür.

⚠️ Ancak, Bitwarden hesabınıza/kasanıza ek giriş-geçiş anahtarları ne kadar güzel olsa da: şu anda, bu
Bitwarden-giriş-geçiş anahtarları ana şifrenizi değiştirmez. Bazı kritik eylemler hâlâ ana şifre onayı gerektirir (ana şifreyi değiştirmek ve kasayı dışa aktarmak gibi). (Şimdilik) sadece Bitwarden-giriş-geçiş anahtarlarına güvenmeyin.

## Teşekkürler

Bu kılavuz https://community.bitwarden.com/t/guide-i-cant-login-some-tips-for-login-problems-issues/82188/4 temel alınmıştır.

Bu sürüm [başka eski gönderi](https://community.bitwarden.com/t/how-to-master-password-problems-and-best-practices/43282) temel alınmıştır.

[Topluluk Forumu](https://community.bitwarden.com/t/guide-i-cant-login-some-tips-for-login-problems-issues/82188)'ndaki katkıları bu gönderiye ilham kaynağı olarak hizmet etmiş olan [@grb](https://community.bitwarden.com/u/grb), [@DenBesten](https://community.bitwarden.com/u/denbesten), [@Neuron5569](https://community.bitwarden.com/u/neuron5569) ve [@dh024](https://community.bitwarden.com/u/dh024)'e teşekkürler!

[Nail1684](https://community.bitwarden.com/u/Nail1684/summary)'e övgüler; herhangi bir hata şüphesiz benim, onun değil.
