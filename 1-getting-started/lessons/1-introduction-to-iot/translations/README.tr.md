# IoT'ye Giriş

![Dersin eskiz notları olarak özeti](../../../sketchnotes/lesson-1.jpg)

> Eskiz [Nitya Narasimhan](https://github.com/nitya) tarafından hazırlanmıştır. Yüksek çözünürlüklü versiyon için resme tıklayınız.

## Ders öncesi kısa sınav

[Kısa sınav](https://brave-island-0b7c7f50f.azurestaticapps.net/quiz/1)

## Giriş

Bu derste Nesnelerin İnterneti (IoT-Internet of Things) ile ilgili giriş seviyesindeki konular ve donanım kurulumunu nasıl yapacağınız ele alınmatadır.

Bu derste şunları ele alacağız:

* [Nesnelerin İnterneti Nedir?](#nesnelerin-interneti-nedir)
* [Iot Cihazları](#iot-cihazları)
* [Donanım Kurulumu](#donanım-kurulumu)
* [IoT Uygulamaları](#iot-uygulamaları)
* [Etrafınızda bulunan IoT cihazlarına örnekler](#entrafınızda-bulunan-iot-cihazlara-örnekler)


## Nesnelerin interneti nedir?

'Internet of Things' (Nesnelerin İnterneti) terimi 1999 yılında [Kevin Ashton](https://wikipedia.org/wiki/Kevin_Ashton) tarafından interneti sensörler vasıtasıyla fiziksel dünyaya bağlama fikrini tanımlamak için ortaya atılmıştır. O günden bugüne bu terim çevresindeki fiziksel dünya ile, sensörlerden veri toplayabilen veya aktüatörler ile fiziksel dünya ile etkileşimde bulunabilen ( elektriksel bir anahtarı veya LED'i açıp kapatabilen cihazlar gibi) ve genelde diğer cihazlar ile bağlantı kurabilen tüm cihazları tanımlamak için kullanılmaktadır.

> **Sensörler** hız, sıcaklık ve konum bilgisi gibi verileri toplayabilen bileşenlerdir
>
> **Aktüatörler** ise elektriksel sinyalleri anahtarı açma/kapama, ışıkları açma/kapama, ses veya güç kaynağı gibi diğer donanımlara kontrol sinyali gönderme gibi fiziksel dünya etkileşimini tetikleyen bileşenlerdir.

Teknoloji olarak IoT sadece sensörler ve aktüatörler gibi bileşenler ve fiziksel cihazlardan oluşmaz. IoT aynı zamanda sensörlerden gelen veriyi işleyen, aktüatörler vasıtasıyla cihazlara sinyal gönderilmesini sağlayan bulut bilişim hizmetlerini de kapsar. IoT, ilave olarak internete doğrudan bağlı olmayan ve uç bileşenler (edge device) olarak adlandırılan cihazları da kapsar. Uç bileşenler, bulut bilişim hizmetleri ile eğitilmiş hazır AI modellerini kendi üzerlerinde çalıştırarak sensör verilerini internet bağlantısına ihtiyaç duymadan kendileri işleyebilirler.

IoT çok hızlı büyüyen bir teknoloji alanıdır. 2025 yılı sonu itibariyle 30 milyar IoT cihazının aktif ve internete bağlı olacağı öngörülmektedir. 2025 yılı itibariyle ise IoT cihazlarının 80 zettabyte veya 80 trilyon gigibyte veri toplayacağı tahmin edilmektedir. Bu çok fazla veri demek!

![Zaman içindeki aktif IoT cihazlarını gösteren grafik. 2015 yılında 5 milyarın altında olan cihaz sayısının yükselen bir trend ile 2025 yılında 30 milyar olacağı tahmin ediliyor.](../../../images/connected-iot-devices.svg)

✅ Ufak bir araştırma yapın: IoT cihazları tarafından toplanan veya üretilen verinin ne kadarı gerçekten kullanılıyor ve ne kadarı kullanılmadan göz ardı ediliyor? Neden bu kadar çok veri göz ardı ediliyor?


Bahsettiğimiz veri IoT'nin başarısı için anahtar görevi görmektedir. Başarılı bir IoT geliştiricisi olmak için toplamanız gereken verinin ne olduğunu, bu veriyi nasıl toplayacağınızı, topladığınız veri ile nasıl kararlar alabileceğinizi ve bu kararları fiziksel dünya ile etkileşime geçmek için nasıl kullanabileceğinizi çok iyi anlamanız gerekir

## IoT Cihazları

IoT ibaresinin kısaltmasındaki **T** İngilizce `Things` Türkçe `Nesne` olup fiziksel dünya ile etkileşimde bulunan cihazları ifade eder.

Akıllı saatler, endüstriyel makina kontrollürleri gibi endüstriyel ve tüketici cihazları genelde özel yapım cihazlardır. Bu tür özel yapım cihazlar yerine getirecekleri göreve uygun olarak, çalışma koşulları (yüksek sıcaklık, yüksek titreşim veya yüksek basınçta çalışabilme) ve ergonomileri (bileğe takılarak kullanım) de dikkate alınarak üretilmiş özel devre kartları ve hatta özel yapım işlemciler kullanılarak üretilirler.

Geliştirici olarak ister IoT hakkında kendinizi geliştirmeye çalışın isterseniz de bir cihaz prototipi hazırlamak isteyin mutlaka bir geliştirici kiti ile çalışmaya başlamalısınız. Bu geliştirici kitleri, sensör ve aktüatörleri bağlamak için pinler, hata ayıklamayı destekleyen donanım bileşenleri veya diğer ilave kaynaklar gibi yukarıda bahsettiğimiz özel yapım cihazlarda bulunmayan bileşenleri de içeren genel kullanım amaçlı IoT cihazlarıdır. İlave pinler ve hata ayıklama donanımı gibi ilave bileşenler seri üretimi olan akıllı saat gibi cihazlar için ekstra maaliyet demektir.

Geliştirici donanım kitleri iki kategoriye ayrılır - microcontroller (mikrokontrolörler) ve single-board (kart bilgisayarlar). Bu iki kategoriyi kabaca bu kısımda ele alıp sonraki derste ayrıntılarını ele alacağız.

> 💁 Cep telefonunz da dahili sensör ve aktüatörleri barındıran ve bu bileşenleri kullanan uygulamaların yer aldığı ve bulut bilişim hizmetlerini kullanabilen genel kullanım amaçlı bir IoT cihazı olarak adlandırılabilir. Akıllı telefon uygulamalarının IoT cihaz olarak kullanıldığı eğitim içerikleri olduğunu da görebilirsiniz.


### Mikrokontrolörler

Mikrokontrolör (microcontroller unit olarak isimlendirilip MCU olarak da kısaltılmaktadır) aşağıdaki bileşenleri barındıran küçük bir bilgisayardır:

🧠 Bir veya daha fazla sayıda merkezi işlem birimi (CPU). Merkezi işlem birimi programınızı çalıştırı ve MCU'nun beynidir.

💾 Bellek (RAM ve program belleği). Programınız, veriniz ve değişkenleriniz bellekte saklanır.

🔌 Programlanabilir giriş/çıkış (I/O - input/output) bağlantıları veya pinleri. Bu pinler vasıtasıyla MCU sensörler ve aktüatörler ile konuşabilir.


MCU'lar genelde düşük maliyetli cihazlardır. Özel yapım donanımlar için MCU fiyatları US$0.50 civarında olabilmektedir, hatta bazı cihazların fiyatı US$0.03 civarındadır. Geliştirici kitlerinini fiyatı US$4'dan başlayıp ilave bileşenler eklendikçe artmaktadır. [Seeed studios](https://www.seeedstudio.com) tarafından üretilen ve üzerinde sensörler, aktüatörler, WiFi ve ekranı olan [Wio Terminal](https://www.seeedstudio.com/Wio-Terminal-p-4509.html) MCU geliştirici kitinin fiyatı US$30 civarındadır.

![Wio Terminal](../../../images/wio-terminal.png)

> 💁 Internette mikrokontrolör araması yaparken, **MCU** ifadesini arma teriminize dahil etmemeye dikkate edin. MCU ibaresi ile arama yaparsanız mikrokontrolörler ile ilgisi olmayan Marvel Cinematic Universe ile ilgili bir çok arama sonucu ile karşılaşabilirsiniz.


Mikrokontrolörler, genel kullanım yerine (PC veya Mac bilgisayarlar gibi) çok spesifik ve sınırlı sayıda görevi yerine getirmek için programlanmışlardır.
İstisnai bazı durumlar haricinde mikrokontrolörlere monitör, klavye ve fare takarak genel amaçlı işlemler için kullanamazsınız.

Mikrokontrolör geliştirici kitleri çoğunlukla ilave dahili (on board) sensörler ve aktüatörler ile birlikte satılırlar. Çoğu kartta programlanabilir bir veya daha fazla sayıda LED, birçok ürericiden temin edebileceğiniz ilave sensör ve aktüatörleri takmak için çevre bağlantı birimleri ve dahili sensörler ( çoğunlukla sıcaklık sensörü gibi sensörler) vardır. Bazı MCU'larda Bluetooth ve WiFi gibi dahili kablosuz bağlantı bileşenleri veya bu bileşenleri takabileceğiniz ilave mikrokontrolörleri de vardır.

> 💁 Mikrokontrolörler çoğunlukla C/C++ programlama dilleri kullanılarak programlanır.

### Single-board bilgisayarlar (kart bilgisayar)

Single-board bilgisayar, normal bir bilgisayardaki tüm bileşenlerin küçük bir kart üzerinde birleştirilmiş halidir. Bu bilgisayarlar PC ve Mac gibi klasik masaüstü veya dizüstü bilgisayarların özelliklerine sahiptir, ancak masaüstü veya dizüstü bilgisayarlar ile karşılaştırıldıklarında daha küçüktürler, daha az elektrik harcarlar ve oldukça ucuzdurlar.

![Raspberry Pi 4](../../../images/raspberry-pi-4.jpg)

Raspberry Pi single-board bilgisayarlar içinde en popüler olanıdır.

Single-board bilgisayarların da mikrokontrolörler gibi CPU'su, belleği ve giriş/çıkış pinleri vardır. Bu bilgisayarlara monitör takılmasını sağlayan grafik kartı, ses çıkışı, klavye ve fare bağlantısı, web kamerası ve harici depolama cihazları gibi diğer standart USB cihazların da bağlanmasını sağlayan ilave özellikleri vardır. Bu bilgisayarlarda çalışan programlar entegre bellek çipinden çalıştırılmaz, bunun yerine bu bilgsayarlarda çalışan progamlar işletim sistemi ile birlikte SD kart veya sabit disk (hard disk) üzerindedir.

> 🎓 Single-board bilgisayarları, sensör ve aktüatörler ile bağlantı yapılmasını sağlayan GPIO (genel amaçlı giriş/çıkış) pinleri olan klasik bir PC veya Mac'in küçük ve daha ucuz versiyonu olarak düşünebilirsiniz.

Single-board bilgisayarlar, tam donanımlı bilgisayarlardır ve herhangi bir programlama dili kullanılarak programlanabilirler. IoT cihazlar genelde Python ile programlanırlar.

### Dersin geri kalanı için donanım tercihleri

Takip eden tüm derslerde fiziksel dünya ve bulut hizmetleri ile etkileşimde bulunabilen IoT cihazların kullanımını gerektiren ödevler yer almaktadır. Her bir derste 3 cihaz seçeneği desteklenmektedir - Arduino (Seeed Studios Wio Terminal kullanarak), fiziksel bir single-borad bilgisayar (Raspberry Pi) veya PC veya Mac'inizde çalışan sanal bir single-board bilgisayar.

Tüm ödevleri tamamlamak için ihtiyaç duyulan donanım ile ilgili daha fazla bilgiye [donanım rehberinden](../../../hardware.tr.md) erişebilirsiniz.

> 💁 Dersteki ödevleri fiziksel bir donanım satın almanıza gerek kalmadan, sanal single-board bilgisayar kullanarak tamamlayabilirsiniz.


Hangi donanımı kullanacağınız tamamen sizin terchinize bırakılmıştır. Bu tercih, evde veya okulda hangi donanıma sahip olduğunuza ve hangi programlama dilini bildiğiniz veya öğrenmek istediğinize bağlıdır. İki donanım seçeneğinden hangisini tercih ederseniz edin iki seçenek için de aynı sensörler kullanılacaktır, bu nedenle hangi seçenek ile başlarsanız başlayın geliştirme kitinizdeki çoğu bileşeni değiştirmeden terchinizi sonradan da değiştirebilirsiniz. Örneğin, sanal single-board bilgisayar Raspberry Pi ile birebir aynıdır. Sanal kit ile geliştireceğiniz kodları, ileride Raspberry Pi satın almaya karar verirseniz, değiştirmeden doğrudan Raspberry Pi üzerinde de çalıştırabilirsiniz.

### Arduino geliştirici kiti

Mikrokontrolörler ile geliştirme yapmak istiyorsanız derste yer alan ödevleri Arduino ile yapabilirsiniz. Bunun için basit seviyede C/C++ bilgisine sahip olmanız gerekir. Ders içeriğinde C/C++ programlama ile ilgili ayrıntılar yer almaz. Derste sadece Arduino'ya özel kod parçaları, kullanılan sensörler ve aktüatörler hakkında bilgiler ile bulut hizmetlerine erişim için kullanılan kütüphanelerin referanslarına yer verilmektedir.

Ödevlerde [Visual Studio Code](https://code.visualstudio.com/?WT.mc_id=academic-17441-jabenn) ve [PlatformIO extension for microcontroller development](https://platformio.org) eklentisi kullanılmaktadır. Arduino tecrübeniz varsa Arduino IDE'yi de kullanabilirsiniz, ancak ders içeriğinde Arduino IDE kullanımı ile ilgili ayrıntılar yer almamaktadır.

### Single-board bilgisayar geliştirici kiti

Single-board bilgisayarlar ile IoT geliştirmek istiyorsanız Raspberry Pi veya bilgisayarınızda çalıştıracağınız sanal single-board bilgisayarı kullanabilirsiniz.

Bunun için temel seviyede Python programlama dili bilmeniz gerekir. Ders içeriğinde Python programlama ile ilgili ayrıntılar yer almaz. Derste sadece kullanılan sensörler ve aktüatörler hakkında bilgiler ile bulut hizmetlerine erişim için kullanılan kütüphanelerin referanslarına yer verilmektedir.

> 💁 Pyhthon ile programlama öğrenmek istiyorsanız aşağıdaki iki video serisine başvurabilirsiniz.
> * [Python for beginners](https://channel9.msdn.com/Series/Intro-to-Python-Development?WT.mc_id=academic-17441-jabenn)
> * [More Python for beginners](https://channel9.msdn.com/Series/More-Python-for-Beginners?WT.mc_id=academic-7372-jabenn)

Ödevlerde [Visual Studio Code](https://code.visualstudio.com/?WT.mc_id=academic-17441-jabenn) kullanılacaktır.

Raspberry Pi kullanıyorsanız, doğrudan Raspberry Pi OS işletim sisteminin tam sürüm masaüstü versiyonunu kullanabilirsiniz ve tüm kodlarınızı [the Raspberry Pi OS version of VS Code](https://code.visualstudio.com/docs/setup/raspberry-pi?WT.mc_id=academic-17441-jabenn) kullanarak yazabilirsiniz veya alternatif olarak Raspberry Pi'yi işletim sistemi olmada (headless device olarak) kullanarak kodunuzu bilgisayarınıza kurulu olan VS Code ile geliştirip [Remote SSH extension](https://code.visualstudio.com/docs/remote/ssh?WT.mc_id=academic-17441-jabenn) eklentisi ile Raspberry Pi üzerine atarak çalıştırabilirsiniz.

Sanal cihaz seçeneği ile ilerlerseniz doğrudan kendi bilgisayarınızda kodlama yapacaksınız. Sensör ve aktüatörlere doğrudan erişim yerine, bu donanım bileşenlerini simüle eden bir araç kullanmanız gerekecek. Simülasyon için kullanacağınız araç sensör değerlerini tanımlamanızı ve aktüatörlerin sonuçlarını ekranınızda görmenizi sağlayacaktır.


## Donanım Kurulumu

IoT cihazınızı programlamaya başlamadan önce bazı ayarlamalar ve kurulumlar yapmanız gerekir. Kullandığınız cihaza bağlı olarak lütfen aşağıdaki kurulum yönergelerini takip edin.

> 💁 Henüz bir cihazınız yoksa cihaz seçimiminde ve ek donanım bileşenleri hakkında bilgilerin yer aldığı [donanım kılavuzuna](../../../hardware.tr.md) göz atabilirsiniz. Tüm projelerde sanal donanım seçeneği olduğu için fiziksel cihaz satın almanıza gerek olmadığını da hatırlatmak isteriz.

Kullanacağınız donanım ve araçların en güncel versiyonları hakkında bilgi sahibi olabilmeniz için yönergelerde donanımları üreten veya kullanacağınız araçları sağlayan şirketlerin sayfalarına linklere yer verilmiştir.

Seçtiniz donanım ile ilişkili yönergeleri takip ederek kurulumlarınızı tamamlayıp örnek bir "Merhaba Dünya" projesi yapın. Bu hazırlıklar bu bölümde yer alan 4 ders boyunca geliştireceğimiz IoT gece lambasının ilk adımlarını oluşturmaktadır.


* [Arduino - Wio Terminal](wio-terminal.tr.md)
* [Single-board bilgisayar - Raspberry Pi](pi.tr.md)
* [Single-board bilgisayar - Sanal cihaz](virtual-device.tr.md)

✅ Hem Arduino hem de single-board bilgisayarda kodlama için VS Code kullanacağız. Daha önce VS Code kullanmadıysanız daha fazla bilgi sahibi olmak için [VS Code sitesini](https://code.visualstudio.com?WT.mc_id=academic-17441-jabenn) ziyaret edebilirsiniz.


## IoT Uygulamaları

IoT birçok uygulama alanına sahiptir. Bu kullanım alanlarını birkaç başlık altında toplayabiliriz:

* Tüketiciler için IoT
* Ticari IoT
* Endüstriyel IoT
* Altyapı için IoT

✅ Küçük bir araştırma: Aşağıda ayrıntılı olarak açıklanan her bir alan için aşağıdaki metinde yer almayan birer örnek bulun.


### Tüketiciler için IoT

Tüketiciler için IoT denildiğinde, tüketicilerin satın alıp evlerinde kullanacağı IoT cihazlarından bahsediyoruz. bu cihazlarda akıllı hoparlörler, akıllı ısıtma sistemleri ve akıllı süpürgeler gibileri inanılmaz derecede kullanışlıdır. Sesli su muslukları gibi su açık iken kapatmak için sesinizi duyurmakta zorlanacağınız bazılarının ise kullanışlılığı hala sorgulanmaktadır.

Tüketici IoT cihazları insanların fiziksel çevrelerinde daha fazla işi/görevi yerine getirmelerini sağlamaktadır, özellikle 1 milyar engelli insan için. Örneğin, akıllı süpürgeler hareket kısıtlaması olan insanların evlerini temizleyebilir, ses kontrollü fırınlar görme veya motor becerilerinde engeli olan insanların fırınlarını ses ile ısıtmalarını sağlayabilir, sağlık monitörleri kronik hastalığı olanların durumlarını daha yakından ve düzenli bir şekilde takip etmelerini sağlayabilir. Bu cihazlar artık o kadar olağan hale gelmiştir ki örneğin öğrenciler online eğitimin devam ettiği COVID ortamında ders ve ödev teslim zamanlarını akıllı zamanlayıcı ve saatler ile hatırlatmalar kullanarak kolayca takip edebilmektedir.

✅ Kişisel olarak veya evinizde yukarıda bahsettiğimiz tüketici IoT cihazlarından hangisine sahipsiniz?

### Ticari IoT

Ticari IoT'nin kapsamı işeyerlerinde kullanılan cihazlardır. Örneğin, ofislerde hareket ve yoğunluk sensörleri kullanılarak ışık ve ısıtma sistemlerini dinamik olarak ayarlayan cihazlar bulunmaktadır. Bu cihazlar sayesinde hem maliyetler hem de karbon emisyonu azaltılabilmektedir. Fabrikalarda ise baret giyimeyen personeli tespit edebilen veya ses seviyesinin belirlenen eşik değerinin üstünde olduğunda alarm veren ve iş güvenliği alanında kullanılabilen cihazlar kullanılabilmektedir. Perakende sektöründe IoT cihazlar dolap sıcaklığını takip edip sıcaklık belirli bir seviyenin altında düştüğünde işletmecileri uyaran, raflardaki stok durumunu anlık olarak takip edip boş rafların zaman kaybetmeden doldurulmasını sağlayan sistemler vardır. Ulaşım sektörü IoT cihazları konum takibi, kilometre takibi, sürüş yapılan süre takibi ve depoya yaklaşan araçların bildirimi gibi işlevler için her geçen gün çok daha yoğun olarak kullanmakatadır.

> ✅  Çalıştığınız kurum veya okulunuzda hangi ticari IoT cihazları var?


### Industrial IoT (IIoT)

Endüstriyel IoT veya IIoT, makineleri büyük ölçekte kontrol etmek ve yönetmek için IoT cihazlarının kullanılmasıdır. Bu, fabrikalardan dijital tarıma kadar çok çeşitli kullanım durumlarını kapsar.

Industrial IoT, or IIoT, is the use of IoT devices to control and manage machinery on a large scale. This covers a wide range of use cases, from factories to digital agriculture.

Fabrikalar, IoT cihazlarını birçok farklı şekilde kullanır. Makinelerin sıcaklık, titreşim ve dönüş hızı gibi değerleri fazla sensörle izlenebilir. Bu veriler, değerlerin belirli toleransların dışına çıkması durumunda (anomali) makinenin durdurulmasını sağlamak için, örneğin normal çalışma sıcaklığının üstünde çalışan makineyi durdurmak için, kullanılır. Bu veriler ayrıca, yapay zeka (AI) modelleri kullanılarak makinedeki bir arıza ortaya çıkmadan önce arızayı tahmin eden kestirimci bakım uygulamalarında da kullanılır.

Gezegenimiz artan nüfusu besleyecekse, özellikle de 500 milyon hanede [geçimlik tarım](https://wikipedia.org/wiki/Subsistence_agriculture) ile hayatta kalan 2 milyar insan için dijital tarım önemlidir. Dijital tarım uygulamaları, birkaç dolarlık sensörden  tutun da devasa ticari donanım bileşenini barındıran cihazların olduğu geniş bir yelpazedir. Bir çiftçi en basit anlamda, mahsulünün hasat için ne zaman hazır olacağını tahmin etmek için sıcaklıkları izleyip [büyüme derecesi günlerinden](https://wikipedia.org/wiki/Growing_degree-day) faydalanarak endüstriyel IoT kullanımına başlayabilir. Çiftçiler, bitkilerin kurumasına neden olmadan ihtiyaç duydukları kadar su vermek için toprak nemi izlemeyi otomatik sulama sistemlerine bağlayabilirler. Çiftçileri bahsettiğimiz örneklerin daha da ileri götürerek devasa tarım arazilerindeki mahsul büyümesini, hastalıkları ve toprak kalitesini izlemek için dronları, uydu verilerini ve yapay zeka modellerini kullanıyor.

✅ Başka hangi IoT cihazları çiftçilere fayda sağlayabilir?

### Altyapı için IoT

Altyapı için IoT, insanların her gün kullandıkları yerel ve küresel altyapı hizmetlerini izlemek ve kontrol eden cihazları tarif eder.


### Infrastructure IoT

Infrastructure IoT is monitoring and controlling the local and global infrastructure that people use every day.

[Akıllı Şehirler](https://wikipedia.org/wiki/Smart_city), şehir hakkında veri toplamak için IoT cihazlarını kullanan ve bunu şehrin işleyişini iyileştirmek için kullanan kentsel alanlardır. Bu şehirler genellikle yerel yönetimler, akademi ve yerel işletmeler arasındaki işbirlikleri ile yönetiliyor, ulaşımdan park etmeye ve kirliliğe kadar birçok şeyi takip ediyor ve yönetiyor. Örneğin Danimarka, Kopenhag'da hava kirliliği yerel sakinler için önemlidir, bu nedenle hava kalitesi sürekli olarak ölçülür ve elde edilen bu veriler en temiz bisiklet ve koşu rotaları hakkında bilgi sağlamak için kullanılır.


[Akıllı elektrik şebekeleri](https://wikipedia.org/wiki/Smart_grid), bireysel evler düzeyinde kullanım verilerini toplayarak güç talebinin daha iyi analizine olanak tanır. Bu veriler, kullanıcılara ne kadar güç kullandıklarına, ne zaman kullandıklarına dair içgörüler ve hatta maliyetlerin nasıl azaltılacağına dair öneriler sunarak, yeni elektrik santrallerinin nerede kurulacağı da dahil olmak üzere ülke düzeyinde ve kişisel düzeyde (örneğin, elektrikli arabaları gece şarj etmek gibi) kararlara rehberlik edebilir.


✅ Yaşadığınız yerde herhangi bir şeyi ölçmek için IoT cihazları kullanma şansınız olsaydı yaşadığınız çevredeki hangi değeri veya değerleri ölçmek istedrdiniz?

## Entrafınızda bulunan IoT cihazlara örnekler

Etrafınızda ne kadar çok IoT cihazı olduğunu bilseydiniz eminim çok şaşırırdınız. Bu dersin içeriğini evde yazıyorum ve evimde internete bağlı ve akıllı özellikleri olan uygulamalar veya ses ile kontrol sağlayan veya telefonum basıtasıyla bana veri gönderebilen şu cihazlara sahibim:


* Birden fazla akıllı hoparlöt
* Buzdolabıi bulaşık makinesi, fırın ve mkrodalga fırın
* Güneş panelleri için enerji monitörü
* Akıllı prizler
* Görüntülü zil ve güvenlik kameraları
* Birden fazla akıllı sensör içeren akıllı termostat
* Otomatik garaj kapısı kumandası
* Ev eğlence sistemleri ve ses kontrollü televizyonlar
* Akıllı lambalar
* Egzersiz ve sağlık takibi yapabilen cihazlar


Yukarıda bahsettiğimiz cihazların hepsinin sensör ve aktüatörleri var ve İnternet'e bağlanabilirler. Garaj kapımın açık olup olmadığını telefonumdan kontrol edebilir ve akıllı hoparlörümden garaj kapısının kapatılmasını sağlayabilirim. Hatta bir zamanlayıcı ayarlayarak kapı gece açıksa otomatik olarak kapanmasını sağlayabilirim. Kapı zilim çaldığında, dünyanın neresinde olursam olayım telefonumdan kapıda kimin olduğunu görebilir ve kapı ziline yerleştirilmiş bir hoparlör ve mikrofon aracılığıyla onlarla iletişim kurabilirim. Daha sağlıklı olmak için sağlığıma ilişkin verilerdeki kalıpları tespit ederek kan şekerimi, kalp atış hızımı ve uyku düzenimi izleyebilirim. Işıklarımı bulut servisler üzerinden kontrol edeblir internet bağlantım kesildiğinde ise karanlıkta kalabilirim.

---

## 🚀 Görev
Evinizde, okulunuzda veya iş yerinizde bulunan IoT cihazlarını listeleyin. Çevrenizde düşündüğünüzden daha fazla sayıda IoT cihazı olabilir!

## Ders sonu kısa sınav

[Kısa sınavı cevaplamak için tıklayın.](https://brave-island-0b7c7f50f.azurestaticapps.net/quiz/2)

## Gözden Geçirme & Bireysel Çalışma

Tüketiciler için geliştirilen IoT projelerinin yararlarını ve başarısızlıklarını araştırın. Haber siteleri ve diğer kaynaklarıdan gizlilik sorunları, donanım sorunları veya bağlantı kopmasından kaynaklanan sorunlar ile ilgili haber ve makaleleri araştırıp tüketici IoT projelerinde nelerin ters gidebileceğini araştırın.

Bazı örnekler:

* Tüketici IoT projelerindeki güzel başarısızlık örnekleri için **[Internet of Sh*t](https://twitter.com/internetofshit)** *(küfürlü içerik uyarısı)* Twitter hesabına göz atabilirsiniz.
* [c|net - My Apple Watch saved my life: 5 people share their stories](https://www.cnet.com/news/apple-watch-lifesaving-health-features-read-5-peoples-stories/)
* [c|net - ADT technician pleads guilty to spying on customer camera feeds for years](https://www.cnet.com/news/adt-home-security-technician-pleads-guilty-to-spying-on-customer-camera-feeds-for-years/) *(rıza dışı röntgencilik içerik uyarısı)*

## Ödev

[Bir IoT projesini araştırın](assignment.tr.md)
