# Projenizi temizleyin

Projelerinizi tamamladıktan sonra bulutta kullandığınız kaynakları silmeniz iyi olacaktır.

Derste yer alan her bir proje için aşağıdaki bulut kaynaklarından bazılarını oluşturmuş olabilirsiniz

* Bir Kaynak Grubu (Resource Group)
* Bir IoT Hub
* IoT cihaz kaydı (device registration)
* Bir depolama hesabı (Storage Account)
* Bir fonksiyon uygulaması (Functions App)
* Bir Azure Harita hesabı (Azure Maps account)
* Özel bir görüntü projesi (custom vision project)
* Bir Azure Container Registry
* Bir bilişsel servis kaynağı (cognitive services resource)

Bu kaynaklardan çoğu ücretsiz olduğu için veya ücretsiz katmanda yer alacağınız için size bir maliyeti olmayacaktır. Ödeme gerektiren servisleri ücretsiz katmanda yer alıyorsanız hesabınız için tanımlanan ücretsiz kullanım kotası kadar veya ücretli katmanda yer alıyorsanız çok düşük (birkaç lira) bir ücret karşılığında kullanabilirsiniz.

Ücretsiz olmalarına veya çok düşük ücretli olmalarına rağmen bu kaynakları işiniz bittiğinde silmeniz iyi olacaktır. Örneğin, ücretsiz katmanda yer alıyorsanız sadece bir adet `IoT Hub` tanımlayabilirsiniz, ikincisini tanımlamak isterseniz ücret ödemeniz gerekir.

Kullanacağınız tüm servisler bir "Kaynak Grubu" (Resource Group) altında oluşturulur ve bu sayede kaynaklarınızı daha kolay yönetebilirsiniz. Kaynak grubunu sildiğinizde bu grubun altındaki tüm servisler de otomatik olarak silinecektir.


Kaynak grubunu silmek için komut satırından aşağıdaki komutu çalıştırabilirsiniz:

```sh
az group delete --name <kaynak-grubu-adı>
```

`<kaynak-grubu-adı>` ibaresinin yerine silmek istediğiniz kaynak grubunun adını yazınız.

Karşınıza aşağıdakine benzer bir onay mesajı çıkacak:

```output
Are you sure you want to perform this operation? (y/n): 
```

Kaynak grubunun silinmesini onaylamak için `y` yazın.

Kaynak grubu altındaki servislerin hepsinin silinmesi biraz zaman alacaktır.

> 💁 Kaynak gruplarının silinmesi ile ilgili daha fazla ayrıntıya [Azure Resource Manager resource group and resource deletion documentation on Microsoft Docs](https://docs.microsoft.com/azure/azure-resource-manager/management/delete-resource-group?tabs=azure-cli&WT.mc_id=academic-17441-jabenn) sayfasından erişebilirsiniz.