Yaklaşık bir yıl önce bir [acil durum kiti](https://www.reddit.com/r/Bitwarden/comments/143zktj/you_need_an_emergency_kit/) oluşturmanın nedenini ve nasılını açıklayan bir gönderi yapmıştım. Son zamanlarda u/DozySquirrel'den o eski gönderim için bir iyileştirme önerisi aldım. Orijinal gönderime baktığımda, onu temizlemenin zamanının geldiğini fark ettim.

# Kasanıza yönelik ikinci tehdit

Şifre yöneticimizi düşündüğümüzde, aklımıza gelen ilk şey sırlarımızı yetkisiz ifşadan korumaktır. O metamfetamin bağımlısı eski kayınbiraderimizin banka hesaplarımızı boşaltmasını istemeyiz. Denizaşırı siber suçluların kredi kartımızı ve kimlik numaralarımızı çalmasını istemeyiz. Ve haklısınız! Bu son derece önemlidir.

Ama başka bir risk daha var. Kasanızdan kilitlenip kalabilirsiniz.

>Ana şifremi unuttum!

>Telefonum çöktü ve 2FA'mı kaybettim!

>Büyükannem öldü ve onun hesaplarını kapatıp evini satmam gerekiyor!

(Bu senaryoların hepsini daha sonra konuşacağız.)

Burada vurgulayacağım nokta şu: kasanızı yetkisiz erişimden korumak için tüm makul önlemleri aldıysanız bile, hala bu ikinci risk vardır.

>E ne olacak? Her web sitesine gidip şifrelerimi sıfırlayabilirim.

Şaşırtıcı cevap şu: hayır, yapamazsınız. İlk ve en belirgin sorun şu: *web sitelerinin listesini nereden alacaksınız*? 2024 yılındayız. Kredi kartınız için en son ne zaman kağıt ekstre aldınız? https://toothpicks-r-us.com'dan ne sıklıkla e-posta alıyorsunuz?

Ama bekleyin: daha da kötüleşiyor. Belirgin bir kurtarma iş akışı olmayan sırlarınız var. iPhone'unuzdaki PIN bunun bir örneği olabilir. Windows 11 masaüstünüzün giriş şifresi bir diğeri.

Ve sonra değiştirilmesi zor veya zaman alıcı olabilecek öğeler var...eğer onları hatırlayabilirseniz. Bu kategoride şunlar gibi şeyler var:

* arabanızın VIN'i ve plaka numarası,
* eşinizin ve çocuklarınızın sosyal güvenlik numaraları,
* arkadaşlarınızın WiFi şifreleri,
* eşinizin ve çocuklarınızın ehliyet numaraları, veya
* yazılım lisans anahtarları.

E-posta ile aldığınız banka ekstrelerinde güvenlik amacıyla hesap numaraları yok, bu yüzden bunları yeniden kazanmak için bankayı ziyaret etmeniz gerekecek. Zengin kayınvalidenizin kapılı topluluğuna giriş kodu nasıl? Ve tabii ki spor salonu dolabınızın kilit kombinasyonu; evet, sanırım kilidi kesmesi için birine ödeme yapabilirsiniz...

Bilimsel olmayan tahminim şu ki, eğer kasanızı istenmeyen ifşadan korumak için gerekli özeni gösterdiyseniz (iyi ana şifre, 2FA, iyi operasyonel güvenlik), sırlarınızı bu ikinci tehdit nedeniyle kaybetme olasılığınız yaklaşık yüz kat DAHA fazla. Çeşitli subreddit'lerde kasalarına geri dönmek için süper gizli bir arka kapı arayan insanlardan ayda iki ile dört gönderi görüyorum. Size haber vereyim: böyle bir geçici çözüm olsaydı, kötü adamlar bunu bilirdi ve Bitwarden'ın güvenli olmadığını haykırıyor olurdunuz.

>Bununla başa çıkabilirim! Ana şifremi ezberleyeceğim!

Hm.

İlk olarak, deneysel psikologlar 50 yıldır insan hafızasının güvenilir olmadığını biliyorlar. Bir gerçeği günlük, günde birden fazla kez, yıllarca hatırlayabilirsiniz, sonra bir sabah >PUF< gitmiş olur. Hafızanız güvenilir bir kayıt sistemi değildir.

İkinci olarak, yukarıdakiler bir yana, travmatik beyin hasarı veya felç riski vardır. Bunların hiçbiri yaşa bağlı değildir. Ve böyle bir bedensel yaralanmanız olursa sebze olacağınızı söyleyip geçmeyin. Büyük ihtimalle iyileşeceksiniz...çoğunlukla. Ama kasanız kalıcı olarak kaybolmuş olabilir.

Üçüncüsü, iyileşemeyeceğiniz bir kaza var ve %100 risk altındasınız: kendi ölümünüz. Umarım uzun ve mutlu bir yaşam sürersiniz, ama hepimiz eninde sonunda ölürüz; bu vücudumuzun tasarımına dahil edilmiş. Bir gün BAŞKA BİRİ son işlerinizi halletmek zorunda kalacak. Bencilce davranıp "bu benim problemim değil" diye tartışmayın. Bu güne hazırlanmazsanız, muhtemelen ölümünüzden dolayı yas tutan ve kasanızdaki verilere ihtiyaç duyan birine gereksiz bir yük bırakıyorsunuz. Reddit'te bu üzücü durumu yılda yaklaşık iki kez gördüğümü söyleyebilirim. Bu gerçek bir problem!

# Acil Durum Kiti Nedir?

En basit haliyle, bu açmazdan çıkmanın bir yoludur. Kasanıza yeniden erişim kazanmanızı sağlayacak kalıcı bir kayıttır (beyniniz DEĞİL). Varsayım şu ki kimlik bilgisi depolama alanınız sağlam ve çevrimiçi, ama ona erişiminizi kaybetmişsiniz. Bazı olasılıklar:

* Ana şifrenizi unuttunuz. Evet, bu olur.
* Telefonunuz çöktü veya kayboldu. Ve herhangi bir nedenle TOTP (Authenticator) uygulamanızın depolama alanının yedeği yok.
* Cep telefonunuzun PIN'ini unutuyorsunuz. Veya TouchId kullanıyorsunuz ve parmağınızda kötü bir kesik var, bu yüzden telefon PIN'ine geri dönüyorsunuz.
* Öldünüz ve yas tutan eşinizin elektrik faturasını ödeyebilmek için şifreye ihtiyacı var.

Acil durum kiti size kasanıza geri dönmek için gerekli her şeyi vermeli. Şunlar gibi şeyler olacak:

* Doğru Bitwarden URL'si (bitwarden.com versus bitwarden.eu)
* Kasanız için kayıtlı e-posta. Kasa girişi için e-posta takma adı veya "artı adresleme" kullanabileceğinizi unutmayın, bu yüzden bu bariz olmayabilir!
* Ana şifreniz
* [Bitwarden 2FA kurtarma kodunuz](https://bitwarden.com/help/two-step-recovery-code/)
* Şifrelerinizi "baharatlıyorsanız", baharatlama algoritmasının tam açıklaması

Ek olarak, kasanız için destek e-postası değerli kabul edilmelidir. Tam gerekli olmasa da yine de belirtmeye değer:

* E-posta hizmetinizin doğru URL'si
* E-posta posta kutusu (e-posta adresi)
* E-posta şifreniz
* E-posta 2FA kurtarma kodunuz

Bitwarden 2FA'nız için TOTP (authenticator uygulaması) kullanıyorsanız, başka bir bağımlılığınız olabilir. Bazı insanlar TOTP uygulamaları hakkında herhangi bir bilgiyi kasalarında saklamayı sevmezler. Tamam, peki. Ama bunu yaparsanız, o veri deposuna yeniden erişim için GEREKLİ HER ŞEYİ başka bir yerde bulundurmanız gerekir.

Örneğin, Ente Auth kullanıyorsanız, şunları kaydetmelisiniz:

* Ente kullanıcı adı
* Ente şifresi
* Ente kurtarma anahtarı

Hala Authy kullanıyorsanız (iğrenç!), şunlara ihtiyacınız olabilir:

* Authy için kayıtlı telefon numarası
* Cep telefonu numaranıza yeniden erişim kazanmak için mobil sağlayıcınızdan "ekipman dondurma" PIN'i
* Authy şifreleme şifresi

# Acil Durum Kiti versus Yedek

Acil Durum Kiti ile örtük bir varsayım, çevrimiçi kimlik bilgisi depolama alanınızın sağlam olmasıdır.

>Ne? Bulut mükemmel değil mi?

Evet, doğru. Bu işte 50 yıldır çalışıyorum (ne!), ve size haber vereyim. Öyle değil. Hepimiz elimizden geleni yapıyoruz, ama boktan şeyler oluyor. En sevdiğim örnek, birincil Azure veri merkezinin Microsoft'un yanında, batı Washington'da bulunması. [Cascadia Yıkım Zonu](https://en.wikipedia.org/wiki/Cascadia_subduction_zone) harekete geçtiğinde, Redmond çevresindeki her şeyin moloz olma ihtimali var. Ve belki, sadece eğlence için Mt. Rainier, Redmond'u modern bir Pompeii'ye çevirebilir.

Veya belki (korkunç!) bir yazılım hatası kasanızı Bitwarden sunucularında depolandığı şekliyle tamamen bozar. Not: [hesap şifreleme anahtarınızı döndürdüğünüzde](https://bitwarden.com/help/account-encryption-key) hala cam bir çene var. Evet, problem yaratmak mümkün.

Başka bir örnek olarak, kendinizi ayağınızdan vurabilir ve bir sır kaybedebilir, ya da bir sır için kötü bir değer saklayabilirsiniz. Bitwarden'ın "şifre geçmişi" özelliği var, ama bu kasanızdaki tüm sırları kapsamayabilir. Güvenli bir notta yanlışlıkla bir şeyi silerseniz ne olur?

Ve tabii ki, çoğu insan bir zamanlar "Bitwarden ortadan kaybolursa ne olur?" diye sormuştur. Garip bir şekilde, bu daha az olası risklerden biri. Özellikle, Bitwarden bir gecede ortadan kaybolmaz. Aylar öncesinden e-posta alırsınız, bu da size hazırlanmak için bolca önceden uyarı verir.

Ama her durumda, yedeklemeler bunun hakkındadır. İyi bir yedekleme acil durum sayfanızın yaptığı her şeyi yapmalı, ama kimlik bilgisi veri deponuzun tüm içeriğini kopyalayarak daha ileri gider:

* Güvenli dosya ekleri ve organizasyon kasaları dahil kasanızın dışa aktarımı;
* TOTP uygulamanızın veri deposunun dışa aktarımı
* TÜM web siteleriniz için tüm 2FA kurtarma kodları

Yedekleme acil durum kitinden çok daha karmaşıktır. Kesinlikle yeni başlayanlar için değil, ama herkesi sonunda yedekleme yapmaya başlamaya teşvik ediyorum. [Burada](https://github.com/djasonpenney/bitwarden_reddit/blob/main/backups.md) yakın zamanda yazdığım bir tane var.

# Acil durum kiti nasıl yaparım?

En basit haliyle, _tüm bunları bir kağıda yazın_. Şimdiye kadar ne önerdim?

* Bitwarden sunucu URL'niz (https://vault.bitwarden.com versus https://vault.bitwarden.eu)
* Bitwarden giriş kullanıcı adınız
* Bitwarden ana şifreniz
* Bitwarden 2FA "kurtarma kodunuz" -- bunun ana şifreyi _değiştirmediğini_ unutmayın
* Bitwarden'ın bildirim gönderdiği e-posta adresi
* O e-posta adresinin şifresi
* O e-posta adresinin 2FA kurtarma kodu
* FIDO2 donanım güvenlik jetonunuzun PIN'i
* Ente Auth hesabınızın e-posta adresi
* Ente Auth hesabınızın şifresi
* Ente Auth "kurtarma anahtarı"
* Şifrelerinizi "baharatlıyorsanız", kasanızı açtıktan sonra baharatlama algoritmasının tam açıklaması.

Bundan daha fazlası var mı? Tam durumunuza bağlı. Unutmayın, bir gün _başka biri_ bu sayfayı okuyup siz öldükten sonra son işlerinizi halletmek için kullanmak zorunda kalacak.

Okunaklı yazın! Ve tercihen bu kağıdın ikinci bir kopyasını yapın ve yangın veya başka afet durumunda güvenilir bir arkadaşın veya iş ortağınızın onu sahada saklamasını sağlayın.

# Son düşünceler

Passwordbits'in acil durum kiti yapma ve saklama konusunda [harika bir makalesi](https://passwordbits.com/password-manager-emergency-sheet/) var. Bitwarden'a özel değil, ama makale tamamen alakalı.

[Burada](https://community.bitwarden.com/t/i-created-a-bitwarden-emergency-kit/69523) ilginç olabilecek Topluluk sayfalarından ikinci bir yaklaşım var.

Passwordbits ayrıca bitirdiğinizde nasıl saklayacağınız konusunda iyi öneriler sunuyor. Yeterince vurgulamadıklarını düşündüğüm bir şey şu: *birden fazla kopya istiyorsunuz*. Yangın veya sel varsa -- evinizi taşıyorsanız ve bir kutu kaybolursa -- yedeğinizin yedeğini istiyorsunuz.
