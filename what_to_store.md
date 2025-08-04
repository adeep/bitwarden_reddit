
# Şifre Yöneticisi Kullanım Rehberi

İnsanlar şifre yöneticilerinden bahsederken, genellikle web siteleri için şifre saklamayı düşünürler. Bu önemli bir kullanım alanıdır, ancak dikkate almanız gereken birçok başka şey de vardır.

Şifre yöneticinize **saklamamanız gereken şeyler**, **belki saklamak isteyebileceğiniz ama emin olunmayan şeyler** ve **şifre yöneticinize saklamak isteyebileceğiniz ama aklınıza gelmemiş olabilecek şeyler** hakkında konuşacağım.

Son bölümde ayrıca bir şifre kasası (vault) girişinin nasıl doldurulabileceği ile ilgili bazı fikirler vereceğim. Tabii, istediğiniz şekilde yapabilirsiniz; ama kasanızı daha iyi organize etmek için bazı önerilerim olabilir.

---

## Öncelikle, risk yönetimi ve şifre yöneticinizin gözden geçirilmesi

En üst düzeyde, kimlik bilgilerinizi saklamanızda *iki* tehdit vardır. İlk tehdit, yetkisiz bir kişinin gizli bilgilerinize erişmesidir. Bu herkesin düşündüğü tehdittir. Bunu önlemek için iyi şifreleme, güçlü bir ana şifre ve cihazlarınızı kötü amaçlı yazılımlardan korumak gerekir.

İkinci tehdit de önemlidir: Şifre yöneticinize erişimi kaybetmek istemezsiniz! Bitwarden ana şifreniz ve 2FA kodlarınız, kimlik bilgilerinizi açmak için kullandığınız "anahtarlar"dır. Bunları kaybederseniz, bilgileriniz sonsuza kadar kaybolabilir.

Düşünceli risk yönetimi; riskleri tanımlamak, olasılıklarını önceliklendirmek ve bu tehditleri azaltmak için kaynak ayırmaktır. Kimlik bilgilerinize kimsenin sizin izniniz olmadan erişemediğinden emin olmak ama gerektiğinde ulaşılabilir olması önemlidir.

En kötü örnek, ana şifresini hiç yazmayan kişilerdir. Rastgele, karmaşık ve benzersiz bir ana şifre seçmiş olabilirler, ancak onu tamamen unutma riski vardır. Bu teorik değil; Reddit’te ayda birkaç kez bu durumdan şikayet edenler görülür ve gizli bir yoldan kasaya tekrar girmeye çalışırlar. Ama kötü haber şu ki, eğer şifre yöneticinizde bir arka kapı varsa, kötü niyetli kişiler de bunu bilir.

Bu yüzden kimlik bilgilerinizi saklarken tehditleri analiz edip bunları nasıl yöneteceğinize karar vermelisiniz. Bu öznel bir değerlendirmedir. En olası tehditler neler? Risk altındaki şeyler neler? Riskleri azaltmak için neler yapmaya hazırsınız? Bir tehdit gerçekleşirse bunun bedeli nedir?

Örneğin, kasaya erişimi kaybederseniz, her web sitesinde kurtarma işlemini yapmaya razı olabilirsiniz. Ancak bu pek çok sorun yaratır: Web sitelerinin listesini nereden alacaksınız? "Kurtarma soruları" aynı cevaplar birden çok site için paylaşılıyorsa tehlike yaratabilir. Ayrıca spor salonundaki kilit şifreniz gibi gizli bilgileriniz, çilingir ve hizmet bedeli gerektirebilir. Tüm bunlarla gerçekten uğraşmaya değer misiniz?

Sonuç olarak, bazı şeyleri şifre yöneticinizde saklamaya rahat hissetmeyebilirsiniz. Bunun için geçerli (ama tam ikna edici olmayan) sebepler vardır. Ama yine de bu tamamen öznel bir karardır.

---

## Şifre yöneticinize SAKLAMAMANIZ GEREKENLER

Bu bölüm tamamen benim kişisel görüşümdür. Katılmayabilirsiniz.

### Bitwarden Kurtarma Bilgileriniz

Kasaya erişiminizi kaybedebilirsiniz. Ana şifrenizi unutabilirsiniz. TOTP (Authenticator Uygulaması) başarısız olabilir. O an kullanışlı olabilecek kullanıcı adı, ana şifre ve 2FA kurtarma koduna ihtiyacınız olabilir!

Problem şu ki, kasaya kilitlenmişseniz içine bakamazsınız. Bunun yerine bir [acil durum sayfası (emergency sheet)](https://www.reddit.com/r/Bitwarden/comments/1fknnbo/emergency_kit_20/) kullanmalısınız.

### Diğer Web Siteleri için 2FA Kurtarma Kodları

Çoğu web sitesi kurtarma sürecine sahiptir. Bu bazen kontrolünüzdeki bir e-posta adresi, bazen de bir dizi tek kullanımlık parola olabilir. Bu kurtarma süreçlerini bilin ve kayıt altına alın. Felaket kurtarma için yedeklilik önemlidir.

Ancak şifre yöneticinize erişiminiz varsa 2FA kurtarma kodlarına gerek yoktur. Şifre yöneticinize erişimi kaybettiyseniz acil durum sayfanız gerekir. 2FA erişiminizi kaybettiyseniz (Yubikey veya TOTP uygulaması gibi) [tam yedeğe](https://www.reddit.com/r/Bitwarden/comments/1f995wl/making_bitwarden_backups_version_20/) ihtiyacınız olur. Kasadaki ya da acil durum sayfasındaki kodlar sorununuzu çözmez.

Eğer biri kasanıza erişirse, bu kodlar risk yaratabilir. Yubikey veya TOTP kullanıyor olsanız bile, kurtarma kodlarını saklamak Yubikey olmadan erişim sağlanmasına yol açabilir.

Bu yüzden kurtarma kodlarını şifre yöneticinizde saklamak ya gereksiz ya da bir tehdit yüzeyidir.

### Güvenlik Soruları ve Cevapları

Bazı siteler hala kurtarma yöntemi olarak "güvenlik soruları" kullanır. Örneğin "ilk erkek arkadaşınızın adı" veya "gittiğiniz ilk okulun adı" gibi. Bunlar da 2FA kurtarma kodları gibi düşünülmeli. Soruları ve cevaplarınızı kayıt edin. Kasanıza erişiminiz varsa bunlara gerek yoktur. Ama bu cevapları bilen biri siteye izinsiz erişebilir.

Not: Bu sorulara gerçek ve tutarlı cevaplar vermek istemezsiniz. Size karşı hedeflenen biri (örneğin eski ve sinirli bir akraba) kişisel bilgilerinizi kullanabilir. Ya da bir sitenin güvenliği ihlal edilirse saldırganlar cevapları diğer sitelerde kullanabilir. En iyisi her siteye farklı ve yalan cevaplar vermektir.

### Kripto Tohumları (Crypto Seeds)

Kripto para hesapları normal finansal hesaplar değildir. Kredi kartları, banka hesapları belirli kontrol mekanizmalarına sahiptir ve çalınan para genellikle geri alınabilir. Ancak kripto parada böyle bir denetim zinciri yoktur. Hesabı kontrol eden, parayı da kontrol eder.

Bu nedenle en iyi uygulama kripto tohumlarını (seed) çevrimdışı tutmaktır. Kağıda yazılı ve güvenli bir yerde saklanabilir, hatta yangına karşı iki yerde tutulabilir. Ama çevrimiçi bırakmak uzmanlarca önerilmez. Çünkü çok fazla soygun yöntemi var ve kurtarma şansınız yok.

---

## Şifre yöneticinizde BULUNDURABİLECEĞİNİZ ŞEYLER? (Kişisel görüşüm)

### TOTP Anahtarları

[TOTP](https://tr.wikipedia.org/wiki/Zaman_tabanlı_tek_kullanımlık_parola) iyi bir 2FA yöntemidir. Sizin ve sitenin paylaştığı gizli anahtar ve güncel zamanla birlikte 30 saniyede bir değişen 6 haneli kod üretir.

Bu protokolde 2FA sırasında gizli bilgi açığa çıkmaz. Bir “ortadaki adam saldırısı” risk vardır: sizi sahte siteye yönlendirirler, şifrenizi ve o anki TOTP kodunu girersiniz, saldırgan bunları kullanır. Ancak FIDO2 donanım anahtarı veya passkey daha güçlüdür. Genel olarak iyidir.

Endişe şu: saldırgan şifre kasanıza erişirse hem şifrenizi hem de TOTP anahtarınızı elde eder. Ayrım için TOTP anahtarlarını başka bir yerde tutmak daha güvenlidir.

*Niye olabilir?*

Kasaya doğrudan saldırı az olasıdır; diğer web saldırıları daha yaygındır. Mesela, yatak altına yüklü bir pompalı tüfek koymak mı, kapı kilitlerinizi ve alarm sisteminizi iyileştirmek mi daha iyidir?

Bazıları risk azaltmayı başka yollardan sağlar. Unutmayın ki TOTP uygulamanızdaki veri bütünlüğü ve güvenliği de önemlidir. Ayrıca Bitwarden’da TOTP kullanıyorsanız, zaten o dış uygulamaya ihtiyacınız var demektir ve TOTP anahtarlarınızı orada tutabilirsiniz.

(Bitwarden içindeki TOTP fonksiyonunu kullanmak sık tartışılır. Karar size kalmıştır: güvenlik artışı mı, yoksa kullanım kolaylığı mı daha önemli?)

### Bitwarden Ana Şifreniz

Belki?

Düşünce şu: operasyonel güvenlikte bir zafiyetiniz varsa, biri kilitsiz cihazınıza ve kasanıza erişirse ana şifrenizi öğrenebilir. Bu ileride saldırgan için avantajdır.

*Niye olabilir?*

Eğer kasadaki giriş kaydınıza bakıyorsanız, ana şifreyi zaten kullandınız demektir. Ve kasanız açıksa ana şifre amacına hizmet etmiyor.

Ayrıca bu giriş ana şifreyi kurtarmaya yardımcı olmaz; acil durum sayfanız veya tam yedeğiniz bunu yapar. Yani ek bir kolaylık olabilir, ciddi güvenlik kaybı olmadan.

### Yubikey FIDO2 PIN’iniz (ve benzerleri)

Kasadaki TOTP anahtarları gibi, Yubikey’iniz çalındı ama PIN bilinmiyorsa 2FA geçemez.

*Niye olabilir?*

Çoğumuz için fiziksel saldırı düşük risklidir. Ana Yubikey anahtarlığımda, yedeklerim kilitli yerde. Yanımda sadece eşim ve yetkili kişi bilir.

Yubikey yanlış PIN girilirse tüm verileri siler. PIN yedeği olması rahatlatıcıdır.

### "Önemli" Girişler

Bazıları web girişlerini ikiye ayırır: banka gibi yüksek riskli ve daha az kritik olanlar (örneğin sosyal medya). Şifre yöneticisine sadece az kritik olanları koyar, diğerleri için farklı yöntemler kullanır.

*Niye olabilir?*

Asıl sorun o “farklı yöntem”. İkinci bir şifre yöneticisi kullanıyorsanız neden hepsini ona koymuyorsunuz? Ya da kritik hesaplar için zayıf ya da tekrar eden şifreler mi kullanıyorsunuz? Bu kabul edilemez.

Ayrıca acil durum sayfanız ve yedeğiniz karmaşıklaşır.

Son olarak, önemli hesabınızın ne olduğuna dikkat edin. Örneğin Instagram hesabınız ele geçirilip karanlık web’e yasadışı içerik yüklenmiş olabilir. FBI kapınızı çalabilir. Belki de TÜM hesaplarınız önemlidir.

---

## Şifre yöneticinizde MUTLAKA SAKLAMANIZ GEREKENLER

Bu bölümde aklınıza gelmemiş olabilecek çeşitli gizli bilgiler vardır.

- **Web sitesi girişleri** — Herkesin aklına gelen ilk şey budur. Her giriş için benzersiz, karmaşık ve rastgele oluşturulmuş şifreler olmalı. Başka konular da var, sonra konuşuruz.
- **Garanti ve seri numaraları** — Önemli cihazlarınızın seri numaraları (ör. Dell dizüstü servis numarası) faydalı olabilir.
- **Yazılım lisans anahtarları** — Lisans anahtarları azaldı ama hala var. Nerede güvenli saklayabilirsiniz? Şifre yöneticisi iyi bir yer.
- **Başka kişiler için şifreler** — Eşim bilgisayar kullanımı az bildiği için yedeklerini ve önemli şifrelerini yönetiyorum. Kardeşim teknik olsa da doktor, bilgisayar onun işinin küçük bir parçası. Onun yedeklerini de ben tutuyorum. Yeğenim ise teknolojiyle arası iyi değil, onun da güvenliğini sağlıyorum.
- **Site giriş şifreleri** — Örneğin kapı şifresi, spor salonu kilit şifresi gibi.
- **Ehliyet bilgileri** — Ehliyet numarası, son kullanma tarihi, varsa resmi fotoğraf. Yenileme hatırlatıcı takın.
- **Araç bilgileri** — Araç VIN, plaka, ruhsat, sigorta bilgileri, detaylı araç açıklaması gibi.
- **Sağlık sigortası bilgileri** — Kart görüntüleri ve detayları.
- **Pasaportlar** — Pasaport numarası, son kullanma ve sayfa kopyaları.
- **Sosyal güvenlik numaraları** — Sık ihtiyaç duyulur.
- **İlaç ve aşı listesi** — Kişisel sağlık geçmişiniz için önemli.
- **Evcil hayvan bilgileri** — Mikroçip ID ve aşı kayıtları.

---

## Hesap Dışı Şifreler

- Telefon PIN’leri
- Bilgisayar giriş şifreleri
- NAS giriş bilgileri (TOTP anahtarı dahil)
- Bitwarden yedekleme şifreleme anahtarı
- Kredi kartı bilgileri ve müşteri hizmetleri numaraları
- Banka hesap bilgileri (kart numarası, PIN, hesap numarası, yönlendirme kodu)
- Sesli mesaj şifresi
- Bitlocker şifreleri

---

## WiFi Şifreleri

Birçok kişi iPhone KeyChain’e güvenir ama Android cihaz kullanıyorsanız veya Apple hesabınız kapandıysa bu yetersiz kalabilir. En azından önemli WiFi şifrelerini kaydedin.

---

## Router Giriş Bilgileri

Router’ı değiştirmek zorunda kalabilirsiniz ve eski çalışmayabilir. Yeni router’a şu bilgiler gereklidir:

- Yönetici kullanıcı adı ve şifresi
- IP adresi (genelde 192.168.0.1)
- PPPoE kullanıcı adı ve şifresi
- DHCP ayarları
- WiFi ayarları (kanallar vs)
- Varsayılan ağ geçitleri

Evde statik IP atadığınız cihazların listesini not olarak saklayın.

---

## Personel Numarası

Büyük şirketlerde sık ihtiyaç duyabilirsiniz.

---

## Bitwarden Kasası Girişi Doldurma Düşünceleri

- **Bu girişi neden oluşturdunuz?**  
  Belirli bir amaç olabilir, örneğin McDonald’s promosyonu. Girişin geçerliliğini hatırlamak ve gerekirse silmek için not alın.

- **Neden web sitesini kullanmıyorsunuz?**  
  Kötü müşteri deneyimi veya daha iyi alternatif olabilir.

- **Hesabı ne zaman oluşturdunuz?**  
  Şifre yöneticisine ekleme tarihi değil, hesap açılış tarihidir.

- **Notlar**  
  Hangi e-posta ve kullanıcı adı kullanıldı?

- **2FA türü**  
  SMS, FIDO2/WebAuthn donanım anahtarı, güvenlik soruları vb.

- **İpuçları**  
  2FA için isim sonuna emoji ekleyin:  
  - 🗝 basit şifre  
  - ⏰ TOTP  
  - 📞 SMS  
  - 🔒 FIDO2/WebAuthn  
  - ❓ Güvenlik soruları  
  - ✉ E-posta 2FA  

>Passkey kullanmadım ama kullanmaya başlayınca 🩻 ekleyeceğim.

Yaratıcı olun! Bu sistemle emoji veya isimle arama yapabilirsiniz.
"""
