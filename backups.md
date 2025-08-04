u/aj0413, [bu gönderinin](https://www.reddit.com/r/Bitwarden/comments/y6d588/making_bitwarden_backups_one_approach) bir revizyonunu yapmamı önerdi. Geri dönüp baktığımda, baştan başlamanın daha iyi olacağına karar verdim. İşte güncellenmiş versiyonum!

# Giriş

Bitwarden'ın yeni kullanıcıları için, 
[bir acil durum sayfası](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md) oluşturmayı öneriyoruz. Acil durum sayfası bir felaket kurtarma azaltma önlemidir. Ana şifrenizi unutursanız, TOTP veri deponuza erişimi kaybederseniz veya başka bir şekilde Bitwarden sunucularından bağlantınız koparsa, erişimi yeniden kazanabilmenizi sağlar.

Yedekleme bunun bir adım ötesine geçer. Bitwarden sunucuları ortadan kaybolursa veya veri deponuzu bozarsa, verilerinizin yakın tarihli bir kopyasının hala kurtarılabilir olmasını sağlar.

# Yedeklemede neler var?

Bir yedekleme aşağıdaki parçalara ihtiyaç duyar:

## Acil Durum Sayfası
Benim düşünceme göre, tam bir yedekleme [acil durum sayfasının](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md) uygun bir üst kümesidir. Bitwarden kasanıza ve TOTP veri deponuza yeniden erişim kazanmanızı sağlayacak tek ve özlü bir dosyadır.

## Bitwarden Kasa Dışa Aktarımı

Bunun bir [JSON dışa aktarımı](https://bitwarden.com/help/export-your-data/) olması gerekir. "CSV" formatı yararlıdır ama Bitwarden ekosisteminden ayrılmak istemediğiniz sürece gerekli değildir. CSV formatı ayrıca kasanızın eksik bir temsilidir. Teknik nedenlerle, JSON dışa aktarımının "şifre korumalı" versiyonunu oluşturmalısınız. "Hesap kısıtlı" dışa aktarım formatını KULLANMAYIN.

## TOTP veri deposu

"Authenticator uygulamanız" o altı haneli sayıları günün şu anki saati artı sunucuyla paylaştığınız bir sır aracılığıyla üretir. O uygulamanın sırlarının bir dışa aktarımını da tutmanız en iyinize hizmet eder.

## Kurtarma Kodları
Tıpkı Bitwarden'ın bir [2FA kurtarma kodu](https://bitwarden.com/help/two-step-recovery-code/) olduğu gibi, güçlü kimlik doğrulamayı destekleyen çoğu web sitesinin de bir kurtarma iş akışı vardır. En iyi güvenlik için, bunları kasanızda kaydetmek istemezsiniz, ama kesinlikle felaket kurtarma için bunların mevcut olması en iyisidir.

## Bitwarden Organizasyon dışa aktarımları
Paylaşılan Koleksiyonlardaki veriler [ayrı ayrı dışa aktarılmalıdır](https://bitwarden.com/help/export-your-data/#export-an-organization-vault). Yine, JSON dışa aktarımının "şifre korumalı" versiyonunu kullanın.

## Dosya eklentileri
Premium aboneliği olan kasalar kasa girişlerine rastgele dosyalar ekleyebilir. Yedeğiniz için "şifrelenmiş ZIP formatını" seçerseniz, Bitwarden bunları dışa aktarımınıza dahil edecektir.

Şifrelenmiş Zip formatından akıllıca kaçınmayı seçerseniz, bunları tek tek elle indirmeniz gerekecektir. Ek olarak, hangi dosya eklerinin hangi kasa girişine ait olduğunu açıklayan bir metin dosyası yapmanız gerekir. (Bu son nokta hakkında daha sonra detay.)

## Acil Durum Sayfası

İyi bir Bitwarden yedeklemesi ayrıca her yedekleme için üst düzey bir `emergency_sheet.txt` olmalıdır. Bu tam olarak [acil durum sayfanızdır](https://github.com/djasonpenney/bitwarden_reddit/blob/main/emergency_kit.md).

# Yedeğinizi Oluşturmak

Bu rehberin önceki versiyonunda, yedeklemeyi oluşturmak ve sürdürmek için [VeraCrypt](https://veracrypt.fr/en/Home.html) kullanmayı önermiştim. Nasıl kullanılacağı konusunda acı verici detaylı talimatlarım vardı. Hala onu tercih ediyorum. Dinamik olarak okuyabileceğiniz ve güncelleyebileceğiniz şifrelenmiş bir zip arşivi gibidir. Dosyalarınızın şifresi çözülmüş versiyonunun diskinize hiç yazılmaması için ayarlayabilirsiniz.

Ancak, belirli bir sinirlilikle, [7-Zip](https://www.7-zip.org/) veya [Picocrypt](https://github.com/Picocrypt/Picocrypt) gibi bir şeyle idare edebileceğinizi düşünüyorum. Şeytan, şifresi çözülmüş sırların sabit diskinize hiç yazılmasına izin vermeden yeni bir arşiv oluşturmanın nasıl yapılacağında olacaktır. Eğer umursuyorsanız. Ama bu rehberin geri kalanında VeraCrypt kullandığınızı varsayacağım.

# Yedekleme Organizasyonu

Bu bölümde çok genel bir format özetliyorum. Kendiniz ve diğer aile üyeleri için yedekleme yapmanıza olanak tanır.

## Üst Düzey

USB sürücünüzdeki genel görüntü en dıştaki `AAAREADME.txt`'yi ve ardından şifrelenmiş arşivi içerecektir. Arşiv makul olarak `backup.hc` olarak adlandırılabilir. Ayrıca VeraCrypt için bazı yükleyiciler kaydedeceksiniz.

`AAAREADME.txt` yedeğin kendisi hakkında daha fazla bilgi içerir.
Bunun bir VeraCrypt yedeklemesi olduğunu açıklamak ve uygulama (VeraCrypt gibi) için yükleyiciler dahil etmek istiyorsunuz.
`AAAREADME.txt`'de hiçbir sır yoktur. Yedeğin içeriği için bir 4-1-1'dir. İçeriği şu şekilde basit olmalıdır:

```
Bu ailem için bir Bitwarden yedeklemesidir. Yedekleme VeraCrypt aracılığıyla şifrelenmiştir. (Umarım) uyumlu yükleyiciler dahil edilmiştir.

Bu yedeklemeyi açmak için şifreleme anahtarına zaten sahip olmalısınız.
```

`installers/` ihtiyaç duyabileceğiniz mimarilerde VeraCrypt için uygun kurulum uygulamalarına sahip bir klasör olmalıdır.

## `backup.hc` İçinde

Bu şifrelenmiş bir arşivdir (VeraCrypt ile olduğu gibi).

Her kasa veya Organizasyon koleksiyonu için bir klasör oluşturun. Her klasörün içinde:

### `emergency_sheet.txt`
Bu o kasa için tam acil durum sayfasıdır.

### `bitwarden_export.json` (veya benzer açık ad)
Bu kasa veya organizasyon Koleksiyonunun dışa aktarımıdır. Dışa aktarımı oluştururken seçtiğiniz şifreyi `emergency_sheet.txt`'ye eklediğinizden emin olun.

### `recovery_codes.txt`

Güçlü 2FA'yı etkinleştirdiğinizde, iyi web siteleri Yubikey'inizi veya TOTP uygulamanızı kaybetmeniz durumunda size bir kurtarma iş akışı verir. Biliyorum, burada yaptığınız diğer her şeyle birlikte, bu önemli olmamalı. Ama yedeklemelere gelince, fazlalık çok iyi bir şeydir. [Google](https://support.google.com/accounts/answer/1187538?hl=en&co=GENIE.Platform%3DDesktop), [Microsoft](https://support.microsoft.com/en-us/account-billing/microsoft-account-recovery-code-2acc2f88-e37b-4b44-99d4-b4419f610013), [Bitwarden](https://bitwarden.com/help/two-step-recovery-code/) ve diğerleri tipik olarak tek kullanımlık kod veya tek kullanımlık kodlar kümesi kullanır.

Bu kurtarma kodlarını kasanızda saklamanın pek anlamı yoktur. Yubikey'iniz ve Ente Auth girişiniz varsa, kasa depolaması gerekli değildir. Hatta bazıları kurtarma kodlarının kasanızın içinde olmasının TOTP kodlarını kasada saklamak gibi olduğunu, ki bu onlara göre anatema, tartışacaktır.

Peki ne yapmalı? Bu tam yedeğin bunun için doğru yer olduğunu öneriyorum. Her siteyi uygun şekilde adlandıran ve her biri için kurtarma kodlarının listesini veren bir metin dosyası yapın. Örneğin,

```text
Hotmail https://outlook.live.com/owa/

kurtarma kodu: 1234-5678-9012-3456-7890

-----
Best Buy https://www.bestbuy.com

1234 5678
2345 6789
3456 7890
4567 8901
5678 9012

-----
Docker Hub https://hub.docker.com/

Kurtarma kodu: 1234567890abc
```

# Yedekleme Organizasyonu

USB'nizin en dış düzeyinde şöyle bir şey görmelisiniz:

```text
    AAAREADME.txt
    VeraCrypt/
      VeraCrypt Setup 1.26.15.exe
      VeraCrypt_1.26.14.dmg
    backup.hc
```

Şifrelenmiş arşivi açtığınızda şöyle bir şey göreceksiniz:

    mom/
      emergency_sheet.txt
      vault.json
      ente_auth.json
      recovery_codes.txt
    dad/
      emergency_sheet.txt
      vault.json
      ente_auth.json
      recovery_codes.txt
    family_organization/
      family_organization.json

# Yedeğinizi Saklamak

Yedeğinizin iki parçası vardır: arşiv dosyasının kendisi ve şifreleme şifresi (VeraCrypt "volume şifresi"). Yedeğinizin güvenliği, yalnızca yetkili tarafların _her iki_ parçaya da erişimi olmasını sağlamaktan gelir.

*Online yedeklemeler ne durumda?*

Online yedeklemeler ekstra adımlar gerektirir ve ekstra risk yaratır. Online hizmete güveniyorsunuz. Ayrıca hala bulutun DIŞINDAki tutulması gereken sayısız ekstra sır vardır: arşiv dosyası için URL, kullanıcı adı, şifre, 2FA sırları ve 2FA kurtarma kodu. Ve tabii ki hala bulutun dışında saklanması gereken şifreleme şifresi de var.

Son olarak, yedeğinizin çok büyük olacağı gibi bir durum yok. Beni, karımı, kayınbiraderimi ve bir yeğenimi içeren yedeğim toplamda 80 megabayttan az. Bu çok küçük! Amazon size 1Gb flash bellek 10'lu paketini 20 dolardan az fiyata satacaktır.

Online yedeklemelerle uğraşmayın. Bunun yerine güvenli konumlarda, çevrimdışı, fiziksel kopyalara yatırım yapın.

*Çevrimdışı Depolama*

Arşiv dosyasının kendisini eski usul hava boşluklu çevrimdışı saklamanızı öneriyorum: birden fazla konumda birden fazla USB flash bellek. Flash belleklerin iklim kontrollü bir konumda olmasını istiyorsunuz (arabanızın torpido gözünde değil). Anahtarlığınızdaki gibi savurulup titreştirilmemelerini istiyorsuniz. Evinizin sessiz ve sakin bir köşesini bulmanız gerekiyor.

Her konumda, tercihen farklı üreticilerden, flash bellek çiftleri bulundurmayı seviyorum. Bu, flash belleklerdeki herhangi bir tekil tasarım veya üretim kusununun tüm yedeklerinizi etkileme riskini azaltır. Onları bir anahtarlığa koyuyorum ve flash bellekerle birlikte her anahtarlıkta kayıtlı bir Yubikey var.

Kesinlikle başka bir flash bellek çiftinin saha dışında olmasını istiyorsunuz. Yangın, sel, deprem varsa veya hükümet gelip tüm dosyalarınızı alırsa, başka bir yerde başka bir yedeğinizin olmasını istiyorsunuz.

# Peki ya o şifreleme anahtarı?

Daha önce dediğim gibi, buradaki numara bir saldırganın HEM arşiv dosyanıza HEM de şifreleme anahtarına erişim kazanmamasını sağlamaktır. Tek doğru cevap yoktur. Tam durumunuza bağlıdır.

*Kasa kiralama* -- Eğer hükümet bir tehdit yüzeyi değilse ve kasa kiralamalaya erişiminiz varsa, şifrelemeyi tamamen atlayıp flash bellekleri orada kaydetmeyi düşünebilirsiniz. Pek çok insana hitap edeceğinden emin değilim, ama bir düşünce. Hey, iklim kontrollü, yangın geçirmez ve hırsızlık geçirmez.

*Benim yaptığım* -- Karım Bitwarden kasasında şifreleme anahtarının bir kopyasına sahip. Eğer önce ben ölürsem, flash bellekleri artı Yubikey'i alıp açabilecek. Yasal miras icracısı olan oğlumuzun da evinde flash bellekler ve Yubikey var, kasasında şifreleme anahtarının bir kopyası var. Şehir dışındaysak ve kasamızdan kilitlenip kalırsak, yedek telefonlarımızı yeniden temin etmek ve tekrar giriş yapmak için gerekenleri yapabilir. Karım ve ben öldükten sonra, bu ona kasamıza erişim verecek. Ayrıca kendi kasamda şifreleme anahtarının bir kopyası var: bu felaket kurtarmaya yardımcı olmaz, ama kendi arşivimi açmama ve onu periyodik olarak güncellememeni sağlar.

*Akıllı bir Redditor* -- her flash bellek setinin yanında şifreleme anahtarının bir kopyasına sahip! Numara şu ki bu bir bulmaca şeklinde ve sadece aile üyeleri bulmacayı çözecek kadar biliyor. Benim çözümüm gibi, bu da kendisinin, eşinin, kardeşlerinin, hatta ebeveynlerinin gerektiğinde yedeklemeyi açacak kadar bildiğini garanti eder.

*Kimseye Güvenme* -- Bunu gündeme getirmekten neredeyse nefret ediyorum, ama [Shamir'in Sır Paylaşımı](https://en.wikipedia.org/wiki/Shamir%27s_secret_sharing) hakkında bilmeniz gerekiyor. Sır, seçilen bir grubun yeteri kadarı bilgilerini birleştirmek için birlikte hareket etmedikçe açığa çıkarılamaz." Sırrı kaç parçaya böleceğinizi ve sırrı yeniden oluşturmak için kaç parçanın bir araya getirilmesi gerektiğini siz karar veriyorsunuz. Bu arada, bunun gerçekten güzel bir [web uygulaması](https://simon-frey.com/s4/) var. Sadece parçaları birleştirmeye başlamadan önce tarayıcınızın çevrimdışı olduğundan emin olun.

Bunu "gündeme getirmekten neredeyse nefret ediyorum" diyorum, çünkü bu son yaklaşımın operasyonel karmaşıklığı zorlayıcıdır. Grubun her üyesi kendi parçasını dikkatli tutmalıdır. Bir araya gelebilmek için birbirlerini bilmeleri gerekir, onlara uygunsuz şekilde işbirliği yapmayacak kadar güvenmeniz ama gerektiğinde işbirliği yapabilecek kadar güvenmeniz gerekir.
