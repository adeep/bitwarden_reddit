# Bir Şifre Yolculuğu

## Giriş

Yazılım geliştirmede işe başladığım zamanda, şifreler oldukça farklı bir değer önerisiydi. Tüm işlerimizi büyük "zaman paylaşımlı" ana bilgisayarlarda yapıyorduk. Bu Digital Equipment Corporation, TOPS-20 ve benzer makinelerin çağıydı.

Bu çağda şifreler oldukça önemsizdi. Bilgisayarlarımız büyük kurumsal ofislerin içinde, birçok kilitli kapının yanı sıra 24x7 güvenlik görevlileriyle birlikte bulunuyordu. İki? üç? şifrem olabilirdi. Genellikle bunları bir kağıt parçasına yazıp cüzdanımda bırakırdım.

Cüzdanım kaybolur veya çalınırsa, şifreler bir hırsıza yarar sağlamazdı. Fiziksel erişim kontrollerinin yanı sıra, HANGI makinelere giriş yapacaklarını ve genellikle hangi kullanıcı adının kullanıldığını da bilmeleri gerekirdi. Şifremi de unutursam, nöbetçi BT yöneticisini ziyaret edebilir, o da mutlulukla şifremi sıfırlardı.

1980'ler, masaüstü bilgisayarların bir meraktan bilgi işlemin temel bir parçasına dönüştüğü bilgi işlemde bir devrim başlattı. Çok küçük IBM PC'lerle (DOS çalıştıran) başladık, on yılın sonunda SunOS ve MentorGraphics iş istasyonları çalıştırıyorduk. 1990'ların gelişiyle bile, güvenlik ve felaket kurtarma hemen hemen aynıydı. Yani, fiziksel erişim hâlâ tüm bilgi işlem kaynaklarınız için birincil korumaydi.

## Ve sonra...İNTERNET

1990'lar ilerledikçe işler çok daha karmaşık hale geldi. CompuServe, America Online ve ilgili hizmetler gibi çevirmeli bağlantılarımız vardı. İş yerlerim bile çevirmeli erişim sunmaya başladı: kendi evimin çalışma odasının konforunda, işteki iş istasyonuma hatta SPARCstation süper bilgisayarı gibi diğer iş istasyonları veya sunuculara çevirmeli bağlantı yapabilirdim. Cüzdanimdaki o kağıt parçasında artık yarım düzine veya daha fazla şifre vardı. Kullanıcı adları belirgin olmamaya başladı.

Cüzdanımı kaybetsem ne olurdu? O kağıt parçasında tam olarak hangi şifrelerin olduğunu nasıl hatırlardım? Daha da endişe verici olanı, bu şifrelerin bazıları, cüzdanı kapan biri tarafından bakılan şeyi anlıyor olsaydı, gerçekten yararlı olabilirdi. Bir şeylerin değişmesi gerekiyordu...

*Palm III'üm İmdada*

Mutlu bir tesadüfle, bu, ilk kişisel dijital asistanım olan Palm Computing [Palm III](https://en.wikipedia.org/wiki/Palm_III)'e yatırım yaptığım zamandı. Bilgi işlem açısından, Palm'ım çok sınırlı (ve sinir bozucu) bir cihazdi. Çok az depolaması vardı. OS'si zar zor çalışıyordu. O kadar yavaştı ki, ayağınızı kapıdan dışarı çıkarıp onu itmeye yardım etmek istiyordunuz.

Ancak yapabildiği şey...devrimciydi. İlk kez, adres defterim, takvimim, görev listem ve hatta e-postamın son kopyası cebimdeydi. (Palm'ı özel bir kürüğe koyuyor, bir düğmeye basıyor ve Outlook Express ile senkronize oluyordu.) Palm'ımı kaybetsem, verilerim hâlâ masaüstü cihazımda olurdu. Fiziksel günlük planlayıcısını kaybetme konusunda artık endişelenmem gerekmiyordu.

Peki bu şifrelere nasıl yardım etti? Şifrelerimi saklamama izin veren [bir uygulama buldum](https://splashid.com/). Her şey şifrelenmişti, bu yüzden Palm III'üm çalınırsa, hırsızın onu okumak için hâlâ özel bir şifreye ihtiyacı olurdu. (Palm III'ün masaüstü şifresi olmadığını unutmayın. Cihazı elinize geçirirseniz, her şeyi okuyabilirsiniz. Ancak bu uygulama sırlarınızın güvenli olmasını sağlıyordu.) Daha da iyisi, Outlook Express'teki senkronizasyonumla entegre oluyordu; diğer her şeyi senkronize ettiğimde, güncellemeleri koordine eder, sonra aynı veritabanını masaüstümden bile okuyabilirdim.

Modern standartlara göre, bu uygulama oldukça temeldi. Modern terimlerle, sadece "güvenli notlar" veritabanıydı. "AOL" adlı bir girişi açabilir ve örneğin çevrimiçi hesabınız için kullanıcı adı ve şifreyi içeren küçük bir metin belgesi görürdünüz.

Ancak her şeyin üstüne, oldukça hoştu. Kimlik bilgisi veri tabanımı güncelleseydim, takvim etkinliği ekleseydim veya kişi güncelleseydim, eve gelir gelmez Palm'ı senkronize etmek için zihinsel not alırdım. E-postam konusunda çok endişelenmezdim, çünkü çevirmeli hizmetim sunucularında kopyalar tutuyordu.

## Peki felaket kurtarma?

Bu yeni sistem çok daha iyi olsa da, köşe durumları hakkında düşünmeye başladım. Hâlâ sorunlarım olduğunu fark ettim.

İlk olarak, yedek kopyam Windows 98 makinemdeaki sabit disktí. Bu cihaz tüm aile tarafından paylaşılıyordu. Güvenlik ve yedeklemeler <ahem> sınırlıydı. Çocuklar yanlışlıkla OS'yi bozabilir veya daha kötüsü. Ve sonra...evim yardımcı ısı kaynağı olarak odun sobası kullanıyordu. Yangın muhtemel bir tehdiţti. (Ailemdeki herkes oldukça tedbirlı olsa da, kazalar olur.)

Bu yüzden bir adım ekledim: Palm'ımı senkronize ettikten sonra, Outlook Express veri tabanını 3.5" disket diskete kopyalar, işe götürür ve masadaki kilitli çekmecede --su geçirmez plastik torba içinde-- saklardım. Ofiste yangın söndürme sistemi olduğunu biliyordum ve hem evdeki masaüstü makineyi hem de ofisi kaybetme olasılığı uzaktı.

Daha sonra ikinci bir 3.5" disket ekledim ve onu yangına dayanıklı kutuda ([bunun gibi](https://www.amazon.com/SentrySafe-Resistant-Chest-Cubic-1160/dp/B008NHKWZU/ref=sr_1_6)) sakladım.

## Zaman ilerliyor...

2000'ler ilerledikçe, kimlik bilgisi mağazam boyut olarak büyüdü. Daha büyük sorun ise, kullandığım _cihaz sayısıydı_. PDA ve masaüstü makinesinden fazlaydı. Dizüstü bilgisayarım ve tabletim vardı (çünkü açgözlü bir okuyucuyum). Palm yerine [Samsung S III](https://en.wikipedia.org/wiki/Samsung_Galaxy_S_III)'üm vardı. Outlook Express artık o kadar ilginç değildi, ancak kimlik bilgisi veri tabanımın tüm bu cihazlarda olması gerekiyordu.

Şifre yöneticim oldukça olgunlaşmıştı. Hâlâ güvenli notlar uygulamasıydı, ancak onu yerel olarak-wifi aracılığıyla--ev intranetime senkronize edebiliyordum. Web'e maruz kalma yok, kablolu bağlantılar yok, yaşasın! Ancak başka bir sorun kutusu açtı. Samsung'umı evden uzaktayken güncelleseydim, _bunu hatırlamam gerekirdi_. Dizüstü bilgisayarımda başka bir değişiklik yaparsam, senkronize etmeye çalıştığımda bir güncellemeyi kaybederdim. Tekrar tek başarısızlık noktasına dönmüştüm ve yanlış yapsam kendi en kötü düşmanım olabilirdim. Bu zorlaşıyordu!

## Yaşasın, LastPass!

Başka bir çözüm aramaya başladım ve [LastPass](https://www.lastpass.com/)'a rastladım. Bu onların son tökezleme ve beceriksizlik serilerinden önceydi. Tüm cihazlarım için sorunsuz yüksek kullanılabilirlik ve veri kurtarma sağlayan bulut yedekleme deposu olarak çalışan--en azından o zamanlar--harika bir değer önerisi gibi görünen ücretsiz katmanları vardı.

LastPass ayrıca şifre güvenliğimi artırmama yardımcı oldu. Zayıf şifrelerinizi görmenizi ve hatta diğer LastPass kullanıcılarına karşı göreceli güvenlik sıralamanızı veren mükemmel [liderlık tabloları](https://www.lastpass.com/features/security-dashboard) var. Gittim ve tüm şifrelerimi güçlü (rastgele oluşturulmuş) olacak şekilde güncelledim ve kurumsal dizüstü bilgisayarım için [parola öbeği](https://xkcd.com/936/) kullandım.

Kayıp güncelleme sorunu hakkında endişelenmem gerekmiyordu. Her değişiklik yaptığımda, en son sürüm buluta itiliyordu ve kasayı her açtığımda en son sürümü alıyordum.

LastPass'taki tarayıcı entegrasyonu da benim için gerçek bir kültür şokuydu. Yüceltilmiş "güvenli notlar" uygulamama şifre bulmak için kazmak yerine, LastPass şifrelerin tarayıcımda "otomatik doldurulmasına" yardımcı olarak yardım ederdi.

Yedeklemeler LastPass veri tabanını--uygun zaman aralığında--çıkarılabilir medyaya kopyalamaktan ibaretti. Yine, evde bir kopya ve ofis masamda bir kopya tutardım. Ancak LastPass bulut depolaması sayesinde, eve varmadan telefonumun ölmesi konusunda endişelenmem gerekmiyordu. Heck, artık (çok fazla) ev yangını konusunda endişelenmem gerekmiyordu...belki?

## Ah-oh, ana şifrem...

Bu noktada yaklaşık on yıl boyunca sahip olduğum ana şifrenin <ahem> oldukça zayıf olduğunu itiraf etmeliyim. O zamanın çoğunda aynısını kullanmıştım. Unutmayın, başlangıçta tüm bu bilgisayarlar kilitli kapıların arkasındaydı. Ve sonunda, birinin Samsung telefonumun kilidini açması ve/veya evime girip Windows masaüstümün kilidini açması gerekirdi. Kasa şifresi gerçekten ikincilydi. `xyzzyxyzzy` veya `plughplugh` gibi çok basit ana şifreler kullanma eğilimindeyidim.

İnternette maruz kalmayla, açıkça daha iyisini yapmam gerekiyordu. Hiç saldırıya uğramadım, ancak şimdi yepyeni bir sorunum vardı! Ana şifremi unutursam ne olurdu? Bilgi Bilimi Yapay Zeka alanında yüksek lisans dereceme dayanarak, insan hafızasına güvenilemeyeceğini anlıyordum.

Bu noktada, çözüm belirgin di. E-posta adresini ve ana şifreyi bir aile üyesinin veya benim erişebileceğim yangına dayanıklı kasamdaki bir kağıt parçasına koydum.

## Günümüze geçiş...

LastPass 2015'te [tökezlediğinde](https://www.wired.com/2015/06/hack-brief-password-manager-lastpass-got-breached-hard/) başladı.

Şimdi, LastPass'ın operasyonel hata yapmasının bu _ilk_ kez olmadığını kabul edeceğim, ancak benim için son saman çöpüydü. Ücretli kullanıcı olmaya hazırlanmıştım ve bu beni alternatiflere bakmaya yönlendirdi. (Zaferin ağzından yenilgiyi kapma hakkında konuşmak!)

Neyse ki, neredeyse tam aynı zamanda, [açık kaynaklı sıfır bilgi alternatifi](https://en.wikipedia.org/wiki/Bitwarden) kullanılabilir hale geldi. Daha da iyisi, (ve hâlâ) ücretsizdi!

O zamandan beri yolculuğum 2FA ([TOTP](https://en.wikipedia.org/wiki/Time-based_one-time_password) ve [FIDO2](https://en.wikipedia.org/wiki/FIDO_Alliance)) ve [donanım güvenlik anahtarlarına](https://www.yubico.com/) ciddi dalışlar oldu.

Hâlâ hata toleransı ve yedeklemeler konusunda çok endişeleniyorum, ancak sorunu en azından daha iyi kavradığımı hissediyorum. Geçiş anahtarları hâlâ çok sarsıntılı. Geleceğin şifre paylaşımı ve güvenilirlik konusunda bazı ilginç değişimler içereceğini düşünüyorum. Gelecek ilginç olacak!
