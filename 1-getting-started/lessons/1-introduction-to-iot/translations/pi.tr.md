# Raspberry Pi

[Raspberry Pi](https://raspberrypi.org) single-board bir bilgisayardır. Raspberry Pi'ye çok çeşitli sensörler ve aktüatörler ekleyebilirsiniz.Derslerimiz için [Grove](https://www.seeedstudio.com/category/Grove-c-1003.html) adlı bir donanım ekosistemi kullanabilirsiniz. Derste   Raspberry Pi'yi kodlayıp Python programlama dilini kullanarak Grove sensörlerine erişeceksiniz.

![ Bir Raspberry Pi 4](../../../images/raspberry-pi-4.jpg)

## Kurulum

IoT donanımı olarak bir Raspberry Pi kullanıyorsanız, iki seçeneğiniz var - doğrudan Raspberry Pi üzerinde (işletim sistemi kurulu, monitör ve klavye takılı) kod yazabilirsiniz veya headless olarak tabir edilen ve herhangi bir çevre birimi takılı olmayan sadece ağ üzerinden erişebileceğin bir Raspberry Pi'ye bilgisayarınız üzerinden uzaktan bağlanıp kod yazabilirsiniz.

Başlamadan önce, Grove Base Hat'i Raspberry Pi'ye bağlamanız gerekir.

### Görev - kurulum

Grove Base Hat'i Raspberry Pi'ye bağlayarak Pi'yi konfigüre edin

1. Grove Base Hat'i Raspberry Pi'ye bağlayın. Hat'in soketleri Pi'ni GPIO pinlerine tam oturur. Hat, Pi'nin üstünü tamamen kaplar.

	![Grove Hat'in Takılması ](../../../images/pi-grove-hat-fitting.gif)

2. Pi'yi nasıl programlayacağınıza karar verin ve kararınıza bağlı olarak aşağıdaki iki bölümden birine devam edin

    * [Doğrudan Pi Üzerinde Kodlama](#doğrudan-pi-üzerinde-kodlama)
    * [Uzaktan bağlantı ile Pi'yi Kodlama](#uzaktan-bağlantı-ile-piyi-kodlama)



### Doğrudan Pi Üzerinde Kodlama

Doğrudan Raspberry Pi üzerinde çalışmak istiyorsanız, Raspberry Pi OS'nin masaüstü sürümünü kullanabilir ve ihtiyacınız olan tüm araçları Pi'ye yükleyebilirsiniz.

#### Görev - doğrudan Pi üzerinde kodlama

Pi'nizi geliştirme yapmak için ayarlayın.

Pi'nizi kurmak için [Raspberry Pi kurulum kılavuzundaki](https://projects.raspberrypi.org/en/projects/raspberry-pi-setting-up) talimatları izleyin. Pi'nizi bir klavyeye/fareye/monitöre bağlayın, WiFi veya ethernet ağınıza bağlayın ve yazılımı güncelleyin. Yüklemek istediğiniz işletim sistemi **Raspberry Pi OS (32 bit)**'dir, SD kartınıza işletim sistemini kurmak için Raspberry Pi Imager'ı kullanıyorsanız **Raspberry Pi OS (32 bit)**  varsayılan ilk seçenek olarak zaten işaretlidir.

Pi'yi Grove sensörlerini ve aktüatörlerini kullanarak programlamak için bir kod editörüne ve kodunuzun Grove donanımıyla etkileşime girmesini sağlayan çeşitli kütüphaneler ve araçları kurmanız gerekir.

1. Pi'niz yeniden başlatıldığında, üst menü çubuğundaki **Terminal** simgesine tıklayarak Terminal'i başlatın veya *Menu -> Accessories -> Terminal* seçeneğini kullanarak Terminal'i başlatın
1. İşletim sistemi ve diğer yazılımların güncel olup olmadığını kontrol etmek için aşağıdaki komutu çalıştırın:

    ```sh
    sudo apt update && sudo apt full-upgrade --yes
    ```
1. Grove donanımı ile etkileşim için gerekli olan tüm kütüphaneleri indirmek için aşağıdaki komutu çalıştırın:

    ```sh
    curl -sL https://github.com/Seeed-Studio/grove.py/raw/master/install.sh | sudo bash -s -
    ```
	Python'un güçlü özelliklerinden biri [pip paketleri](https://pypi.org) kurabilme yeteneğidir - bunlar başkaları tarafından yazılan ve İnternet'te yayınlanan kod kütüphaneleridir. Bir komutla bilgisayarınıza bir pip paketi yükleyebilir, ardından bu paketi kodunuzda kullanabilirsiniz. Yukarıdaki komut, Python kodunuzu Grove donanımıyla etkileşimde bulunabilmesi için kullanacağınız pip paketlerini kuracaktır.

1. Pi'nizi menüden veya aşağıdaki komutu kullanarak yeniden başlatın.

    ```sh
    sudo reboot
    ```
1. Pi yeniden başlatıldığında Terminal'i açıp aşağıdaki komutu çalıştırın. Bu komut ile Python kodu yazmanızı sağlayacak olan [Visual Studio Code (VS Code)](https://code.visualstudio.com?WT.mc_id=academic-17441-jabenn) kod editörünü Pi'nize kurmuş olacaksınız.

    ```sh
    sudo apt install code
    ```

	Kurulum tamamlandıktan sonra VS Code'u üst menüden seçerek çalıştırabilirsiniz.

    > 💁 Python kodu yazmak için istediğiniz Python IDE'yi kullanabilirsiniz. Ancak, biz derslerimizde kod yazmak için VS Code kullanacağızç

1. Pylance'ı yükleyin. Pylance, VS Code'da Python dil desteği sağlayan bir eklentidir. Bu eklentiyi VS Code'a yüklemek  için [Pylance extension documentation](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance&WT.mc_id=academic-17441-jabenn) sayfasındaki yönergeleri takip edin.


### Uzaktan bağlantı ile Pi'yi Kodlama

Doğrudan Raspberry Pi'de kodlamak yerine, bir klavyeye/fareye/monitöre bağlı olmayan 'headless' olarak konfigüre edilmiş bir Pi'ye kendi bilgisayarınızdan uzaktan bağlantı sağlayarak Visual Studio Code ile de kodlama yapabilirsiniz.

#### Pi OS kurulumu

Uzaktan bağlantı ile kodlama yapabilmek için Pi OS'u SD kart üzerine kurmalısınız.

##### Görev - Pi OS'un kurulması

`headless` yani monitör, klavye ve fare gibi çevre birimlerine bağlantısı olmayan Pi OS (OS - [İng] Operating System, [Tr] İşletim Sistemi) kurulumu.

1. **Raspberry Pi Imager**'ı [Raspberry Pi OS software page](https://www.raspberrypi.org/software/) sayfasından indirip kendi bilgisayarınıza kurun

1. Bilgisayarınıza bir SD kart takın, gerekirse bir adaptör kullanının

1. Raspberry Pi Imager uygulamasını bilgisayarınızda çalıştırın

1. Raspberry Pi Imager açıldığında **CHOOSE OS** (işletim sistemi seçimi) butonuna basın ve açılan sayfada önce *Raspberry Pi OS (Other)* seçin ardında da *Raspberry Pi OS Lite (32-bit)* seçin

    ![Raspberry Pi OS Lite seçeneği seçilmiş Raspberry Pi Imager görüntüsü](../../../images/raspberry-pi-imager.png)

    > 💁 Raspberry Pi OS Lite, aspberry Pi OS'un masaüstü kullanıcı arayüzünü (UI) ve arayüz araçlarını içermeyen versiyonudur. `headless` Pi kurulumlarında masaüstü arayüznü ve ilgili araçların kurulumuna gerek yoktur, bu araçların olmaması kurulumun daha küçük olmasını ve başlama süresinin çok kısa olmasını sağlar.

1. **CHOOSE STORAGE** (depolama alanı seçimi) butonuna basın ve ardından da bilgisayarınıza taktığınız SD kartı seçin

1. `Ctrl+Shift+X` tuş kombinasyonunu kullanarak **Advanced Options** (gelişmiş seçenekler) sayfasını açın. Bu sayfada Pi OS'un imajını SD karta yazmadan önce ön tanımlı bazı konfigürasyon değerlerini güncelleyebilirsiniz.
	1. **Enable SSH** (SSH'ı aktif hale getir) seçeneğini işaretleyin ve `pi` kullanıcısı için bir şifre belirleyin. `pi` kullanıcısı ve belirlediğiniz şifre ile daha sonra Pi'nize uzak bağlantı sağlayacaksınız, bu nedenle şifre bilgisini bir yere not edin veya aklınızda tutun.

	1. Pi'nize WiFi (kablosuz yerel ağ) üzerinden bağlanacaksanız **Configure WiFi** (WiFi'yi ayarla) butonuna basın. Açılan sayfada WiFi ağınızın SSID (görünen adı) bilgisini, şifresini ve WiFi ülkesi bilgilerini girin. Kablolu bağlantı (ethernet kablosu) kullanacaksanız bu ayarları yapmanıza gerek yok. İşlemleri tamamlamadan önce bilgisayarınız ile Pi'nizin aynı ağa bağlı olduklarından emin olun.

	1. **Set locale settings** (yerelleştirme ayarları) butonuna basın. Açılan sayfada ülkenizi ve saat diliminizi ayarlayın

	1. Son olarak **SAVE** (kaydet) butonun basın

1. Pi OS imajının SD karta yazılmasını sağlamak için **WRITE**  (yaz) butonuna basın. Eğer macOS kullanıyorsanız, yazma işlemini onaylamak için macOS kullanıcı şifrenizi girmeniz istenecektir.


Pi OS imajının SD kartınıza yazma işlemi tamamlandıktan sonra bilgisayarınızın işletim sistemi işlemin tamamlandığı ile ilgili size bir bilgilendirme gösterecektir. SD kartınızı kendi bilgisayarınızdan çıkarıp Raspberry Pi'nize takarak Pi'yi çalıştırın.

#### Pi'ye uzakten erişim sağlama

Bir sonraki adımınız, Pi'ye uzaktan erişmektir. Uzaktan erişim için macOS, Linux ve Windows işletim sistemlerinin son sürümlerinde yer alan `ssh` uygulamasını kullanabilirsiniz.

##### Görev - Pi'ye uzaktan erişim sağlama

Pi'ye uzaktan erişim sağlama.

1. Terminal veya Command Prompt (komut satırı) uygulamasını açarak aşağıdaki komutu girin

    ```sh
    ssh pi@raspberrypi.local
    ```

	`ssh` kurulu olmayan eski bir Windows sürümü kullanıyorsanız OpenSSH kurabilirsiniz. Kurulum yönergelerine  [OpenSSH installation documentation](https://docs.microsoft.com//windows-server/administration/openssh/openssh_install_firstuse?WT.mc_id=academic-17441-jabenn) sayfasından erişebilirsiniz.

1. Bu komut Pi'nize bağlanmanızı sağlamalıdır. Bağlantı sağlandığında şifre girmeniz istenecek.

	Ağınızdaki diğer bilgisayarlara bağlanmak için kullanabileceğiniz `<hostname>.local` şeklindeki isimlendirme Linux ve Windows'un son güncel sürümlerinde olan bir özelliktir. Bağlantı denemesi sırasında erişmeye çalıştığınız bilgisayarın (hostname) bulunamadığına dair bir hata alırsanız ZeroConf (Apple Bonjour olarak adlandırır) ağ bağlantısını aktif hale getirmek için ilave yazılımlar kurmanız gerekecektir.

    1. Linux kullanıyorsanız, aşağıdaki komutu kullanarak Avahi'yi kurun

        ```sh
        sudo apt-get install avahi-daemon
        ```

    1. Windows kullanıyorsanız, ZeroConf'u aktif hale getirmek için kolay yöntem [Bonjour Print Services for Windows](http://support.apple.com/kb/DL999) kurmaktır. Daha güncel versiyonu için ise [iTunes for Windows](https://www.apple.com/itunes/download/) kurabilirsiniz.

    > 💁 Raspberry Pi'nize `raspberrypi.local` şeklinde erişemiyorsanız, Pi'nizin IP adresini kullanarak erişim sağlayabilirsiniz. Pi'nizin IP adresini öğrenmek için [Raspberry Pi IP address documentation](https://www.raspberrypi.org/documentation/remote-access/ip-address.md) sayfasındaki yönergeleri takip edebilirsiniz.

1. Raspberry Pi Imager'ın Advanced Options (gelişmiş ayarlar) ekranında belirlediğiniz şifreyi girin

#### Pi üzerindeki yazılımların konfigürasyonu

Pi'ye uzak bağlantı sağladıktan sonra, işletim sisteminin güncel olduğundan emin olmanız ve Grove donanımıyla etkileşime giren çeşitli kütüphaneleri ve araçları kurmanız gerekir.

##### Görev - Pi üzerindeki yazılımların konfigürasyonu

Pi ve Grove yazılımlarının konfigüre edilmesi ve kurulması.

1. `ssh` oturumundan işletim sistemini güncellemek ve Pi'yi yeniden başlatmak için aşağıdaki komutu çalıştırın:

    ```sh
    sudo apt update && sudo apt full-upgrade --yes && sudo reboot
    ```

    Bu komut ile Pi güncellenip yeniden başlatılacaktır. Pi'niz yeniden başlatılırken `ssh` oturumunuz sonlandırılacaktır. 30 saniye kadar Pi'nizin yeninden başlaması için bekleyip `ssh` ile Pi'ye yeniden bağalanın.

1. Yeniden bağlanarak açtığınız `ssh` oturumundan aşağıdaki komutu çalıştırarak Grove için gerekli kütüphaneleri kurun:

    ```sh
    curl -sL https://github.com/Seeed-Studio/grove.py/raw/master/install.sh | sudo bash -s -
    ```

    Python'un güçlü özelliklerinden biri [pip paketleri](https://pypi.org) kurabilme yeteneğidir. Pip paketleri başkaları tarafından yazılan ve İnternet'te yayınlanan kod kütüphaneleridir. Bir komutla bilgisayarınıza bir pip paketi yükleyebilir, ardından bu paketi kendi kodunuzun içinden kullanabilirsiniz. Yukarıdaki komut, Python kodunuzdan Grove donanımıyla etkileşime geçebilmek için kullanacağınız pip paketlerini kuracaktır.

1. Aşağıdaki komut ile Pi'nizi yeniden başlatın:

    ```sh
    sudo reboot
    ```

    Pi'yi yeniden başlattığınızda `ssh` oturumunuz sonlanacaktır. Bu aşamadan sonra Pi'ye yeniden bağlanmanıza gerek olmayacak.


#### VS Code'u uzaktan erişim için yapılandırma

Pi yapılandırıldıktan sonra, bilgisayarınızdan ücretsiz Visual Studio Code (VS Code) kod editörünü kullanarak Pi'ye bağlanabilirsiniz.


##### Görev - VS Code'un uzaktan erişim için yapılandırılması

Gerekli yazılımların kurulumu ve Pi'ye uzaktan erişim sağlanması.

1. VS Code'u, [VS Code documentation](https://code.visualstudio.com?WT.mc_id=academic-17441-jabenn) sayfasındaki adımları takip ederek bilgisayarınıza kurun

1. [VS Code Remote Development using SSH documentation](https://code.visualstudio.com/docs/remote/ssh?WT.mc_id=academic-17441-jabenn) sayfasındaki yönergeleri takip ederek uzaktan erişim için gerekli VS Code eklentilerini ve diğer yazılımların kurulumunu yapın.

1. Kurulumu tamamladıktan sonra [eklentilerin yönetimi](https://code.visualstudio.com/docs/remote/ssh#_managing-extensions?WT.mc_id=academic-17441-jabenn) sayfasından faydalanarak  [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance&WT.mc_id=academic-17441-jabenn) eklentisini uzaktan Pi'nize kurun.


## Merhaba dünya

Yeni bir programlama dili veya teknolojisi öğrenirken küçük bir 'Merhaba Dünya' uygulaması oluşturmak geleneksel bir ilk adımdır. Bu küçük uygulama, `"Merhaba Dünya"` şeklinde basit bir metin çıktısı üreterek tüm araçların ve bileşenlerin doğru şekilde kurulup yapılandırıldığını teyit etmemizi sağlar.

Pi için oluşturacağımız "Merhaba dünya" uygulaması, Python ve Visual Studio Code'un doğru bir şekilde yüklendiğini ve yapılandırıldığını teyit etmemizi sağlayacak.

Örnek uygulamayı `nightlight` (gece lambası) adlı bir klasör içinde oluşturacağız. Bu uygulama bu bölümdeki ödevinizin farklı kısımlarında yeniden kullanacağınız kodları içerecektir.

### Görev - merhaba dünya

Merhaba dünya uygulamasını oluşturun.

1. VS Code'u başlatın. VS Code'u doğrudan Pi üzerinde başlatabilirsiniz veya alternatif olarak SSH üzerinden Pi'nize erişerek VS Code'u kullanabilirsiniz.

1. VS Code içinden *Terminal -> New Terminal* menüsünü kullanarak veya `` CTRL+` `` tuş kombinasyonu ile Terminal'i başlatın. Terminal başlatıldığında `pi` kullanıcısının ana klasörüne konumlanacaktır.

1. Aşağıdaki komutları Terminal'de çalıştırarak kodunuzun yer alacağı bir klasör ve `app.py` isimli bir Python kod dosyası oluşturun

  	```sh
    mkdir nightlight
    cd nightlight
    touch app.py
    ```

1. Oluşturduğunuz klasörü VS Code'dan *File -> Open...* menüsünü kullanarak ve *nightlight* klasörünü seçip **OK** butonuna basarak açın

    ![VS Code ile nightlight klasörünü açma diyaloğu](../../../images/vscode-open-nightlight-remote.png)


1. VS Code dosya gezgininden `app.py` dosyasını bulup açın ve aşağıdaki kodu dosyaya ekleyin:

    ```python
    print('Merhaba Dünya!')
    ```

	`print` fonksiyonu parametre olarak verilen değeri çıktı olarak konsolda gösterir.

1. Python uygulamanızı çalıştırmak için VS Code Terminal'den aşağıdaki komutu çalıştırın:

    ```sh
    python3 app.py
    ```

    > 💁 Raspberry Pi'nizde Python3'e (en güncel versiyon) ilave olarak Python2 de kurulu ise uygulamanızı `python3` ile çalıştırmanız gerekir. Pi'nizde sadece Python2 kurulu ise uygulamanızı `python` ile çalıştırabilirsiniz.

	Terminal'de aşağıdaki çıktı gösterilecektir:

    ```output
    pi@raspberrypi:~/nightlight $ python3 app.py
    Merhaba Dünya!
    ```

> 💁 Örnek kodu [code/pi](code/pi) klasörü altında bulabilirsiniz.

😀 'Merhaba dünya' programınızı başarılı bir şekilde kodladınız!
