# Sanal single-board bilgisayar

Sensörler ve aktüatörlerle birlikte fiziksel bir IoT cihazı satın almak yerine, IoT donanımını simüle etmek için bilgisayarınızı kullanabilirsiniz. [CounterFit projesi](https://github.com/CounterFit-IoT/CounterFit), sensörler ve aktüatörler gibi IoT donanımını simüle eden bir uygulamayı kendi bilgisayarınızda çalıştırmanıza ve sensörlere ve aktüatörlere, yazdığınız Python kodundan, fiziksel donanım kullanarak bir Raspberry Pi için yazacağınız kodla aynı şekilde, erişmenize olanak tanır.


## Kurulum

CounterFit'i kullanmak için bilgisayarınıza bazı ücretsiz yazılımlar yüklemeniz gerekir.

### Görev

Gerekli yazılımların kurulması.

1. Python'u kurun. Kurulum adımları için [Python downloads](https://www.python.org/downloads/) sayfasına başvurun.

1. Visual Studio Code (VS Code) kurun. VS Code sanal cihaz kodunu yazmak için kullanacağınız kod editörüdür. Kurulum adımları için [VS Code dokümantasyon](https://code.visualstudio.com?WT.mc_id=academic-17441-jabenn) sayfasına başvurun.

    > 💁 Python kodu yazmak için istediğiniz Python IDE'yi (entegre geliştirme ortamı) kullanabilirsiniz. Ancak, ders içerii VS Code kullanımı için hazırlanmıştır.

1. VS Code için Pylance eklentisini kurun. Pylance, VS Code için Python dil desteği (kod tamamlama, tanıma git vb işlevler) sunan bir eklentidir. Pylance kurulum adımları için  [Pylance dokümantasyon](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance&WT.mc_id=academic-17441-jabenn) sayfasına başvurun.


CounterFit uygulamasının kurulumu ile ilgili yönergeler, CounterFit proje bazlı kurulduğu için, zamanı geldiğinde her bir ödev için ayrıca size verilecektir.


## Merhaba dünya

Yeni bir programlama dili veya teknolojisi öğrenirken küçük bir 'Merhaba Dünya' uygulaması oluşturmak geleneksel bir ilk adımdır. Bu küçük uygulama, `"Merhaba Dünya"` şeklinde basit bir metin çıktısı üreterek tüm araçların ve bileşenlerin doğru şekilde kurulup yapılandırıldığını teyit etmemizi sağlar.

Sanal IoT cihazı için için oluşturacağımız "Merhaba dünya" uygulaması, Python ve Visual Studio Code'un doğru bir şekilde yüklendiğini ve yapılandırıldığını teyit etmemizi sağlayacak. Bu basit uygulama ayrıca CounterFit kullanarak sanal IoT sensörleri ve aktüatörlerine de bağlanacak. Bu uygulama fiziksel bir donanım kullanmayacak, sadece tüm bileşenlerin beklediğimiz gibi çalışıp çalışmadığını test etmemizi sağlayacak.


Örnek uygulamayı `nightlight` (gece lambası) adlı bir klasör içinde oluşturacağız. Bu uygulama bu bölümdeki ödevinizin farklı kısımlarında yeniden kullanacağınız kodları içerecektir.


### Configure a Python virtual environment

One of the powerful features of Python is the ability to install [pip packages](https://pypi.org) - these are packages of code written by other people and published to the Internet. You can install a pip package onto your computer with one command, then use that package in your code. You'll be using pip to install a package to talk to CounterFit.

By default when you install a package it is available everywhere on your computer, and this can lead to problems with package versions - such as one application depending on one version of a package that breaks when you install a new version for a different application. To work around this problem, you can use a [Python virtual environment](https://docs.python.org/3/library/venv.html), essentially a copy of Python in a dedicated folder, and when you install pip packages they get installed just to that folder.

#### Task - configure a Python virtual environment

Configure a Python virtual environment and install the pip packages for CounterFit.

1. From your terminal or command line, run the following at a location of your choice to create and navigate to a new directory:

    ```sh
    mkdir nightlight
    cd nightlight
    ```

1. Now run the following to create a virtual environment in the `.venv` folder

    ```sh
    python3 -m venv .venv
    ```

    > 💁 You need to explicitly call `python3` to create the virtual environment just in case you have Python 2 installed in addition to Python 3 (the latest version). If you have Python2 installed then calling `python` will use Python 2 instead of Python 3

1. Activate the virtual environment:

    * On Windows run:

        ```cmd
        .venv\Scripts\activate.bat
        ```

    * On macOS or Linux, run:

        ```cmd
        source ./.venv/bin/activate
        ```

1. Once the virtual environment has been activated, the default `python` command will run the version of Python that was used to create the virtual environment. Run the following to get the version:

    ```sh
    python --version
    ```

    The output should contain the following:

    ```output
    (.venv) ➜  nightlight python --version
    Python 3.9.1
    ```

    > 💁 Your Python version may be different - as long as it's version 3.6 or higher you are good. If not, delete this folder, install a newer version of Python and try again.

1. Run the following commands to install the pip packages for CounterFit. These packages include the main CounterFit app as well as shims for Grove hardware. These shims allow you to write code as if you were programming using physical sensors and actuators from the Grove ecosystem but connected to virtual IoT devices.

    ```sh
    pip install CounterFit
    pip install counterfit-connection
    pip install counterfit-shims-grove
    ```

    These pip packages will only be installed in the virtual environment, and will not be available outside of this.

### Write the code

Once the Python virtual environment is ready, you can write the code for the 'Hello World' application

#### Task - write the code

Create a Python application to print `"Hello World"` to the console.

1. From your terminal or command line, run the following inside the virtual environment to create a Python file called `app.py`:

    * From Windows run:

        ```cmd
        type nul > app.py
        ```

    * On macOS or Linux, run:

        ```cmd
        touch app.py
        ```

1. Open the current folder in VS Code:

    ```sh
    code .
    ```

    > 💁 If your terminal returns `command not found` on macOS it means VS Code has not been added to your PATH. You can add VS Code to your PATH by following the instructions in the [Launching from the command line section of the VS Code documentation](https://code.visualstudio.com/docs/setup/mac?WT.mc_id=academic-17441-jabenn#_launching-from-the-command-line) and run the command afterwards. VS Code is installed to your PATH by default on Windows and Linux.

1. When VS Code launches, it will activate the Python virtual environment. The selected virtual environment will appear in the bottom status bar:

    ![VS Code showing the selected virtual environment](../../../images/vscode-virtual-env.png)

1. If the VS Code Terminal is already running when VS Code starts up, it won't have the virtual environment activated in it. The easiest thing to do is kill the terminal using the **Kill the active terminal instance** button:

    ![VS Code Kill the active terminal instance button](../../../images/vscode-kill-terminal.png)

    You can tell if the terminal has the virtual environment activated as the name of the virtual environment will be a prefix on the terminal prompt. For example, it might be:

    ```sh
    (.venv) ➜  nightlight
    ```

    If you don't have `.venv` as a prefix on the prompt, the virtual environment is not active in the terminal.

1. Launch a new VS Code Terminal by selecting *Terminal -> New Terminal, or pressing `` CTRL+` ``. The new terminal will load the virtual environment, and the the call to activate this will appear in the terminal. The prompt will also have the name of the virtual environment (`.venv`):

    ```output
    ➜  nightlight source .venv/bin/activate
    (.venv) ➜  nightlight
    ```

1. Open the `app.py` file from the VS Code explorer and add the following code:

    ```python
    print('Hello World!')
    ```

    The `print` function prints whatever is passed to it to the console.

1. From the VS Code terminal, run the following to run your Python app:

    ```sh
    python app.py
    ```

    The following will be in the output:

    ```output
    (.venv) ➜  nightlight python app.py
    Hello World!
    ```

😀 Your 'Hello World' program was a success!

### Connect the 'hardware'

As a second 'Hello World' step, you will run the CounterFit app and connect your code to it. This is the virtual equivalent of plugging in some IoT hardware to a dev kit.

#### Task - connect the 'hardware'

1. From the VS Code terminal, launch the CounterFit app with the following command:

    ```sh
    CounterFit
    ```

    The app will start running and open in your web browser:

    ![The Counter Fit app running in a browser](../../../images/counterfit-first-run.png)

    It will be marked as *Disconnected*, with the LED in the top-right corner turned off.

1. Add the following code to the top of `app.py`:

    ```python
    from counterfit_connection import CounterFitConnection
    CounterFitConnection.init('127.0.0.1', 5000)
    ```

    This code imports the `CounterFitConnection` class from the `counterfit_connection` module, which comes from the `counterfit-connection` pip package you installed earlier. It then initializes a connection to the CounterFit app running on `127.0.0.1`, which is an IP address you can always use to access your local computer (often referred to as *localhost*), on port 5000.

    > 💁 If you have other apps running on port 5000, you can change this by updating the port in the code, and running CounterFit using `CounterFit --port <port_number>`, replacing `<port_number>` with the port you want to use.

1. You will need to launch a new VS Code terminal by selecting the **Create a new integrated terminal** button. This is because the CounterFit app is running in the current terminal.

    ![VS Code Create a new integrated terminal button](../../../images/vscode-new-terminal.png)

1. In this new terminal, run the `app.py` file as before. The status of CounterFit will change to **Connected** and the LED will light up.

    ![Counter Fit showing as connected](../../../images/counterfit-connected.png)

> 💁 You can find this code in the [code/virtual-device](code/virtual-device) folder.

😀 Your connection to the hardware was a success!
