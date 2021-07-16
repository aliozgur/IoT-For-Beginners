# Donanım

IoT ibaresinin kısaltmasındaki **T** İngilizce `Things` Türkçe `Nesne` olup fiziksel dünya ile etkileşimde bulunan cihazları ifade eder. Müfredatta yer alan her bir proje öğrenci ve amatörlerin rahatlıkla erişebileceği donanımlar kullanılarak hazırlanmıştır. Kişisel tercihler, programlama dili bilgisi ve tercihi, öğrenme hedefleri ve erişim imkanlarına göre iki tip IoT donanımı seçeneği sunuyoruz. Bu iki seçeneğe ilave olarak IoT donanımına erişimi olmayanlar veya donanım satın almadan önce tecrübe kazanmak isteyenler için de 'sanal donanım' seçeneği sunuyoruz.

> 💁 Ödevleri yapmak için IoT donanımına sahip olmanız gerekmez. Sanal IoT donanımını kullanarak da ödevlerinizi tamamlayabilirsiniz.

Derslerde fiziksel donanım olarak Arduino veya Raspberry Pi kullanabilirsiniz. Her bir platformun kendine göre güçlü ve zayıf yönleri var. Bu yönler ilk derslerden birinde ayrıntılı bir şekilde ele alınmaktadır. Henüz hangi donanımı kullanmak istediğinize karar vermediyseniz [ikinci dersin ilk projesini](./1-getting-started/lessons/2-deeper-dive/README.tr.md) inceleyip hangi donanımı kullanmak istediğinize karar verebilirsiniz.  

Derslerin karmaşıklığını azaltmak için belirli bir donanım kullanımı tercih edilmiştir. Dersleri takip etmek için farklı donanımlar da kullanabilirsiniz ancak ödevlerinizi bu donanımlar ile ilave bileşenlere gerek kalmadan yapabileceğinizi garanti edemiyoruz. Örneğin, Arduion cihazlarının çoğunda WiFi modülü bulunmaz. Ancak, bizim bulut servislerini kullanmak için ağ erişimine ihtiyacımız olacak, bu nedenle spesifik olarak Wio terminali tercih ettik.    

Dersleri takip ederken yazılım ve donanım gibi teknolojik bileşenlere ilave olarak teknik olmayan toprak, saksı, meyve ve sebze gibi nesnelere de ihtiyacınız olacak.

## Donanım Satın Alma

![The Seeed studios logo](./images/seeed-logo.png)

Seed Studios derste kullanacağımız donanımları hızlıca kullanabileceğiniz birer kit olarak sizin için hazırladı: 


### Arduino - Wio Terminal

**[IoT for beginners with Seeed and Microsoft - Wio Terminal Starter Kit](https://www.seeedstudio.com/IoT-for-beginners-with-Seeed-and-Microsoft-Wio-Terminal-Starter-Kit-p-5006.html)**

[![The Wio Terminal hardware kit](./images/wio-hardware-kit.png)](https://www.seeedstudio.com/IoT-for-beginners-with-Seeed-and-Microsoft-Wio-Terminal-Starter-Kit-p-5006.html)

### Raspberry Pi

**[IoT for beginners with Seeed and Microsoft - Raspberry Pi 4 Starter Kit](https://www.seeedstudio.com/IoT-for-beginners-with-Seeed-and-Microsoft-Raspberry-Pi-Starter-Kit.html)**

[![The Raspberry Pi Terminal hardware kit](./images/pi-hardware-kit.png)](https://www.seeedstudio.com/IoT-for-beginners-with-Seeed-and-Microsoft-Raspberry-Pi-Starter-Kit.html)

## Arduino

Arduion üzerinde çalışan yazılımlar C++ programlama dili ile geliştirilir. Tüm ödevleri tamamlayabilmek için aşağıdakilerine ihtiyacınız olacak:

### Arduino donanımı

* [Wio Terminal](https://www.seeedstudio.com/Wio-Terminal-p-4509.html)
* *Opsiyonel* - USB-C kablosu veya `USB-A to USB-C` adaptörü. Wio terminalinin USB-C portu vardır ve `USB-C to USB-A` kablosu ile birlikte gelir. Eğer masaüstü bilgisayarınızda sadece USB-C portu varsa USB-C kablosuna veya `USB-A to USB-C` adaptörüne ihtiyacınız olacak.

### Arduino'ya özel sensör ve aktüatörler

Aşağıdaki bileşenler Wio terminal Arduino'ya özeldir, Raspberry Pi kullanıyorsanız bu bileşenlere ihtiyacınız olmayacak.

* [ArduCam Mini 2MP Plus - OV2640](https://www.arducam.com/product/arducam-2mp-spi-camera-b0067-arduino/)
* [ReSpeaker 2-Mics Pi HAT](https://www.seeedstudio.com/ReSpeaker-2-Mics-Pi-HAT.html)
* [Breadboard Jumper Wires](https://www.seeedstudio.com/Breadboard-Jumper-Wire-Pack-241mm-200mm-160mm-117m-p-234.html)
* 3.5mm girişi(jack) olan kulaklık veya hoparlör, veya şunun gibi bir JST hoparlör:
  * [Mono Enclosed Speaker - 2W 6 Ohm](https://www.seeedstudio.com/Mono-Enclosed-Speaker-2W-6-Ohm-p-2832.html)
  * [Grove speaker plus](https://www.seeedstudio.com/Grove-Speaker-Plus-p-4592.html)
* *Opsiyonel* - Görüntü yakalama için 16GB veya daha düşük kapasiteli microSD kart. microSD kartı bilgisayarınıza takmak için, eğer yoksa, bir bağlantı aparatına da ihtiyacınız olacak. **NOT** - Wio Terminal maksimum 16GB'a kadar kapasitesi olan SD kartları destekler, daha yüksek kapasiteli SD kartlar Wio terminal tarafından desteklenmez.

## Raspberry Pi

Raspberry Pi üzerinden çalışan yazılımlar Python programlama dili ile geliştirilir.Tüm ödevleri tamamlayabilmek için aşağıdakilerine ihtiyacınız olacak:


### Raspberry Pi donanımı

* [Raspberry Pi](https://www.raspberrypi.org/products/raspberry-pi-4-model-b/)
  > 💁 Versions from the Pi 2B and above should work with the assignments in these lessons.
* microSD kart (microSD kart da içeren Raspberry Pi kiti satın alabilirsiniz) ve microSD kartı bilgisayarınıza takmak için, eğer yoksa, bir bağlantı aparatı.
* USB güç kaynağı (Güç kaynağı da olan Raspberry Pi 4 kiti satın alabilirsiniz). Raspberry Pi 4 kullanacaksanız USB-C güç kaynağına ihtiyacınız olacak, daha eski Raspberry Pi versiyonları için ise micro-USB güç kaynağına ihtiyacınız olacak.

### Raspberry Pi özel sensör ve aktüatörler

Aşağıdaki bileşenler Raspberry Pi'ye özeldir, Arduino kullanıyorsanız bu bileşenlere ihtiyacınız olmayacak.

* [Grove Pi base hat](https://www.seeedstudio.com/Grove-Base-Hat-for-Raspberry-Pi.html)
* [Raspberry Pi Camera module](https://www.raspberrypi.org/products/camera-module-v2/)
* Mikrofon ve hoparlör:

  Aşağıdakilerden birini kullanabilirsinizi (veya mudallerini):
  * Herhangi bir USB mikrofon ve USB hoparlör veya 3.5mm kablolu girişi (jask) olan hoparlör, veya Raspberry Pi'niz HDMI üzerinden bir monitör veya televizyona bağlayabilirsiniz
  * Dahili mikrofonu olan USB headset
  * [ReSpeaker 2-Mics Pi HAT](https://www.seeedstudio.com/ReSpeaker-2-Mics-Pi-HAT.html) ile birlikte
    * 3.5mm girişi (jack) olan kulaklık veya hoparlör, veya aşağıdakibe benzer bir JST hoparlör:
    * [Mono Enclosed Speaker - 2W 6 Ohm](https://www.seeedstudio.com/Mono-Enclosed-Speaker-2W-6-Ohm-p-2832.html)
  * [USB Speakerphone](https://www.amazon.com/USB-Speakerphone-Conference-Business-Microphones/dp/B07Q3D7F8S/ref=sr_1_1?dchild=1&keywords=m0&qid=1614647389&sr=8-1)
* [Grove Light sensor](https://www.seeedstudio.com/Grove-Light-Sensor-v1-2-LS06-S-phototransistor.html)
* [Grove button](https://www.seeedstudio.com/Grove-Button.html)

## Sensörler ve aktüatörler

Aşağıdaki sensörlerin çoğu Arduino ve Raspberry Pi donanımı ile kullanabilirsiniz:

* [Grove LED](https://www.seeedstudio.com/Grove-LED-Pack-p-4364.html) x 2
* [Grove nem ve sıcaklık sensörü](https://www.seeedstudio.com/Grove-Temperature-Humidity-Sensor-DHT11.html)
* [Grove kapasitif toprak nem sensörü](https://www.seeedstudio.com/Grove-Capacitive-Moisture-Sensor-Corrosion-Resistant.html)
* [Grove röle](https://www.seeedstudio.com/Grove-Relay.html)
* [Grove GPS (Air530)](https://www.seeedstudio.com/Grove-GPS-Air530-p-4584.html)
* [Grove Zaman ve Mesafe Sensörü](https://www.seeedstudio.com/Grove-Time-of-Flight-Distance-Sensor-VL53L0X.html)

## Opsiyonel Donanım

Otomatik sulama ile ilgili derslerde röle kullanılır. Bu röleyi USB güç beslemeli su pompasına bağlamak için şu bileşenlere ihtiyacınız olacak.


* [6V water pump](https://www.seeedstudio.com/6V-Mini-Water-Pump-p-1945.html)
* [USB terminal](https://www.adafruit.com/product/3628)
* Silicone pipes
* Red and black wires
* Small flat-head screwdriver

## Sanal donanım

Sanal donanım kullanıyorsanız Pyhton ile geliştirilmiş sensör ve aktüatör simulatörlerini kullanabilirsiniz. Sanal donanımı kendi bilgisayarınızda (PC veya Mac) kullanabileceğiniz gibi, elinizde olmayan donanımları simüle etmek için Raspberry Pi üzerinden de kullanabilirsiniz. Örneğin, Raspberry Pi için kameranız varsa ancak Grove sensörlerine sahip değilseniz sanal donanım kodunu Pi üzerinde çalıştırarak Grove sensörlerini simüle edebilirsiniz. 

Sanal donanım simülatörü olarak [CounterFit](https://github.com/CounterFit-IoT/CounterFit) kullanacağız.

Dersleri tamamlamak için bir web kameranız, mikrofonunuz ve kulaklık veya hoparlörünüz olmalı. Bunlar dahili veya harici bileşenler olabilir ve işletim sisteminiz  bileşenlerin tüm uygulamalardan kullanılmasına izin verecek şekilde konfigüre edilmiş olmalıdır.
