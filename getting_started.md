[/u/cryoprof](https://www.reddit.com/user/cryoprof/)'un _Bitwarden™'de Doğru Ayakla Başlangıç Kılavuzu (Sürüm 3.0)_'dan arsızca kopyalanmış ve uyarlanmış, [burada](https://www.reddit.com/r/Bitwarden/s/nIwfXH9Sr7) yayınlanmış:

# SUNUCUNUZU SEÇİN

Bitwarden hesabınızın bulut sunucusu [bitwarden.com](https://vault.bitwarden.com) veya bitwarden.eu'da barındırılmasını isteyip istemediğinize karar verin; emin değilseniz, bitwarden.com'u seçin (yakın zamana kadar, bu tek mevcut sunucu seçeneğiydi).

# E-POSTA ADRESİNİZİ SEÇİN

Bitwarden kullanıcı adınız olarak kullanacağınız e-posta adresini seçin. Benzersiz bir e-posta adresi kullanmalısınız: başka hiçbir yerde kullanılmayan bir adres.

Birçok posta sunucusu (Gmail ve ProtonMail gibi) myname+randomstring@domain.com gibi "artı" adresini destekler. Kullanmadan önce kendinize test mesajı göndererek bu özelliği test ettiğinizden emin olun.

# ACİL DURUM SAYFANIZI BAŞLATIN

Bir kağıt alın ve üstüne "Acil Durum Sayfası" yazın. Sonra kullanmayı planladığınız Bitwarden bulut sunucusunu (bitwarden.com veya bitwarden.eu) ve Bitwarden girişiniz için kullanacağınız e-posta adresini yazın. Paranoyaksanız veya gizli ajan oynamayı seviyorsanız, kağıdı sert bir yüzeye (not defteri veya dergi üzerine değil) koyarak yazdığınızdan ve tüm perdeler kapalı, kapalı odada yalnız olduğunuzdan emin olun.

# ANA ŞİFRENİZİ SEÇİN

[Bu bağlantıya](https://passhelp.github.io/generator/#phrase:4) bir kez tıklayın ve görüntülenen ifadeyi kağıdınıza kopyalayın.

Bu sizin _ana şifreniz_ olacak. Tıbbi bir durumunuz yoksa, biraz pratikle bunu ezberleyebileceksiniz (posta adresinizi, telefon numaranızı, arkadaş ve akrabalarınızın isimlerini ve benzer bilgileri ezberlemeyi başardınız; ana şifrenizi ezberlemek çok daha zor değil — ancak biraz pratik yapmanız gerekeceğini unutmayın).

Çevrimiçi şifre oluşturucularının güvenliği konusunda endişeniz varsa, önce bağlantılı parola öbeği oluşturucu web sayfasını yerel .html dosyası olarak kaydedin, cihazınızın internet bağlantısını kesin ve bundan sonra parola öbeğinizi oluşturmak için yerel olarak kaydettiğiniz .html dosyasını açın.

# YENİ HESABINIZI KAYIT EDİN

[Bitwarden hesabınızı kayıt edin](https://bitwarden.com/help/create-bitwarden-account/) ya [bitwarden.com sunucusunda](https://vault.bitwarden.com) ya da [bitwarden.eu](https://vault.bitwarden.eu) sunucusunda. İsterseniz sahte isim kullanın ve Şifre İpucunu şimdilik boş bırakın.

Bitwarden'ın kayıt sürecinin bir parçası olarak e-posta adresinizi onaylamanızı gerektireceğini unutmayın.

Bu noktada Premium özelliklerini kullanmak istiyorsanız [aboneliğinizi Premium'a yükseltmeyi](https://bitwarden.com/go/start-premium/) düşünün.

# İKİ FAKTÖRLÜ KİMLİK DOĞRULAMA VE ŞİFRELEME

Hâlâ Web Kasası uygulamasında, Güvenlik ayarlarının ["İki Adımlı Giriş" bölümüne](https://vault.bitwarden.com/#/settings/security/two-factor) gidin ve Bitwarden hesabınız için 2FA yöntemini etkinleştirin.

## Donanım Güvenlik Anahtarı (FIDO2)

En iyi seçim [Yubikey Security Key NFC](https://www.yubico.com/product/security-key-nfc-by-yubico-black/) gibi donanım güvenlik anahtarıdır. Bitwarden'da bunu kurmak için, Geçiş anahtarı sağlayıcısı için "Yönet"e tıklayın ve Yubikey'lerinizi oraya kaydedin ("Yubico OTP Güvenlik Anahtarı" altında değil). Şahsen, üç güvenlik anahtarım var; birini yanımda taşıyorum, birini evde tutuyorum ve birini akrabamın evinde güvenli şekilde saklıyorum.

## TOTP ("Kimlik Doğrulayıcı uygulaması")

Donanım güvenlik anahtarı kullanmaya istekli veya hazır değilseniz, şimdi TOTP'yi etkinleştirin:

* [Ente Auth](https://ente.io/auth/)'u indirin.
* Hesap oluşturun. Bitwarden için e-posta gibi, bir e-posta adresi kullanmayı düşünün. Bunu acil durum sayfanıza yazın.
* [Bu bağlantıya](https://passhelp.github.io/generator/#phrase:4) bir kez tıklayın ve görüntülenen ifadeyi Ente Auth şifreniz olarak kağıdınıza kopyalayın.
* Hâlâ Bitwarden web sayfasındaki "İki Adımlı Giriş" bölümünde, Bitwarden hesabınızda 2FA'yı etkinleştirmek için talimatları takip edin.

## Temizlik

*ÖNEMLİ: "İki Adımlı Giriş" bölümünden ayrılmadan önce, "Kurtarma kodunu görüntüle" bağlantısına tıklayın. Bu kodu "Acil Durum Sayfanıza" doğru şekilde yazın*

Güvenlik ayarlarının "Anahtarlar" sekmesinde, KDF algoritmanızı Argon2id olarak değiştirin. iOS cihazları kullanmıyorsanız varsayılan ayarları koruyun, iOS cihazları kullanıyorsanız "bellek" ayarını 48 MB'ye düşürün ve "yinelemeler"i 4'e yükseltin.

# ŞİFRELERİNİZİ EKLEYİN

Başka yerde saklanan [şifreleri içe aktararak](https://bitwarden.com/help/import-data/) veya sıfırdan yeni kasa öğeleri oluşturarak kasanızı doldurun.

# BİTWARDEN İSTEMCİLERİNİ YÜKLEYIN (sonunda!)

Kullanmak istediğiniz Bitwarden istemci uygulamalarını ([tarayıcı](https://bitwarden.com/help/getting-started-browserext/) ve [mobil](https://bitwarden.com/help/getting-started-mobile/)) indirin ve yükleyin. Masaüstünde tarayıcı uzantısının hem güvenliği hem de kolaylığı artırdığını unutmayın. [Masaüstü uygulaması](https://bitwarden.com/help/getting-started-desktop/) da yararlıdır.

Her birinde ayarları yapılandırın. _Kasa Zaman Aşımı Eylemi_ni "Çıkış Yap" yerine "Kilitle" olarak ayarlamanızı ve nispeten kısa bir _Zaman Aşımı Süresi_ kullanmanızı öneririm. Ayrıca sistem panosunu kısa bir gecikmeden sonra temizleyen seçeneği etkinleştirin.

Windows masaüstü uygulamasında (kullanıyorsanız), Ayarlar'a gidin ve "Ekran görüntülerini devre dışı bırak" ayarını işaretleyin.

# BİRAZ TEMİZLİK

* Mobil olmayan Bitwarden uygulamalarından birinden (yani Web Kasası uygulaması, Masaüstü uygulaması veya tarayıcı uzantısı) kasa dışa aktarması oluşturarak ilk yedeğinizi yapın, dışa aktarma türü için ["Şifre Korumalı" seçeneğiyle şifreli .json dosya formatını](https://bitwarden.com/help/encrypted-export/#create-an-encrypted-export) seçtiğinizden emin olun. Yedekleme dosyanız için güçlü şifre oluşturmak için daha önce kullandığınız yöntemi kullanın, ancak bu sefer [6 kelimelik parola öbeği](https://passhelp.github.io/generator/#phrase:6) yapın; yedekleme dosyası şifresini "Acil Durum Sayfası" kağıdınıza yazın. Ayrıca, yedekleme dosyası şifresini kaydetmek için Bitwarden kasanızda bir giriş oluşturun (bu gelecekteki yedeklemeler oluşturduğunuzda şifreyi kullanmayı kolaylaştıracaktır).

* Kasanıza giriş yaparken veya kilidini açarken ana şifrenizi yazmak için Acil Durum Sayfanızı "kopya kağıdı" olarak kullanın, ta ki kalp hafızanızla yazmayı edinene kadar (yaklaşık bir hafta, fazla veya az). İlk hafta için PIN veya FaceId gibi hileler _KULLANMAYIN_: kendinizi günde en az bir kez ana şifreyi yazmaya zorlayın.

* Acil Durum Sayfanızı güvenlik zarfında (satın alabileceğiniz veya [kendiniz yapabileceğiniz](https://passwordbits.com/emergency-sheet-envelope/)) mühürleyin ve güvenli bir yerde saklayın.

* Sonunda Acil Durum Sayfasının bir veya daha fazla yedek kopyasını yapmalı ve yangın durumunda en az birini evinizin dışında saklamalısınız.

* İsteğe bağlı olarak, Şifre İpucunuzu Acil Durum Sayfanızın nerede gizlendiği hakkında ipucu içerecek şekilde güncelleyin. Şifre İpucunu değiştirmek için, Web Kasasına giriş yapın ve şifre değiştirme formunu kullanın, ancak _mevcut_ ana şifrenizi yeni şifre alanına yazın (böylece ana şifre değişmez) ve hesap şifreleme anahtarınızı döndürme seçeneğini _işaretlemeyin_.

* Bitwarden'ı masaüstünde kullanıyorsanız, [tarayıcı uzantısını kullanmalısınız](https://bitwarden.com/help/getting-started-browserext/). Uzantı simgesini tarayıcı pencerenizin üstüne sabitleyin ve tarayıcının yerleşik şifre yöneticisini devre dışı bırakın (ayrıca Bitwarden'a geçmeden önce yüklemiş olabileceğiniz 3. taraf şifre yöneticilerini de devre dışı bırakın).

İsteğe bağlı olarak, tarayıcı uzantısı ayarlarında aşağıdaki değişiklikleri yapın:

(a) Hesap Güvenliği seçeneği "PIN ile kilidi aç"ı etkinleştirin (ancak "Tarayıcı yeniden başlatıldığında ana şifre ile kilitle"yi _devre dışı bırakmayın_), PIN'i ana şifrenizden yazması daha kolay olan kısa parola öbeği veya şifre olarak tanımlayın.

(b) Otomatik Doldurma seçeneği "Form alanlarında otomatik doldurma menüsünü göster"i kapatın (otomatik doldurmak için beş başka yol vardır, bunların en iyisi Ctrl+Shift+L klavye kısayoludur — veya macOS'ta Cmd+Shift+L).

(c) Bildirim seçenekleri "Giriş eklemeyi sor" ve "Mevcut girişi güncellemeyi sor"u devre dışı bırakın (hesap kimlik bilgilerini önce doğrudan tarayıcı uzantısında oluşturarak ve sonra kimlik bilgilerini hesap kayıt formuna aktarmak için otomatik doldurmayı kullanarak girişler eklemek daha iyidir).

(d) Geçiş anahtarlarını Bitwarden kasanızda saklamak istediğinizden emin değilseniz "Geçiş anahtarlarını kaydet ve kullan" Bildirim seçeneğini devre dışı bırakın (geçiş anahtarları kullanıcı deneyimi optimize edilmeden önce biraz daha olgunlaşma zamanına ihtiyaç duyabilecek "son teknoloji" bir teknolojidir).

(e) Gizlilik endişeleri sizin için önemliyse ve biraz bozulmuş UI görsellerini umursamıyorsanız, Görünüm seçeneği "Web sitesi simgelerini göster"i devre dışı bırakın.

# SON DÜŞÜNCELER

Bitwarden'da sayısız ek seçenek ve gelişmiş işlev vardır, ancak yukarıdakiler tüm temelleri kapsar! Adım 12'deki yöntemi kullanarak yedekleme dışa aktarmanızı düzenli olarak güncelleyin. Ana şifrenizi veya yedekleme şifrenizi başka hiçbir yerde kullanmayın ve bu şifrelerin ne olduğunu kimsenin bilmesine izin vermeyin. Cihazlarınızı güvenli ve kötü amaçlı yazılımdan uzak tutun, o zaman her şey yolunda olmalı.
