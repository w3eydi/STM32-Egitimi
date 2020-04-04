# STM32 Eğitimi - 000 Başlangıç

STM32 Platformu için Gömülü Sistem Programlama

----------------------------

## Başlarken

Bu ilk bölümde STM32 mikrodenetleyicileri programlamak için gerekli ortamların kurulmasını göstereceğim. Birincil kaynak olarak her zaman üreticinin sitesini tercih ediyoruz. Bu dokümanlara nasıl ulaşılacağı konusunda bağlantılarıyla birlikte bilgi vereceğim. İkincil ve üçüncül kaynaklar olarak kitap, blog yazıları youtube, udemy, vb. gibi platformları tercih edebilirsiniz. Son olarak diğer bölümlerde kullanabileceğimiz şekilde temel, başlangıç bir arm programlama ortamı oluşturacağız.

---

## IDE

Aşağıda bağlantısı adresini yazdığım doküman genel olarak mevcut IDE (Geliştirme Ortamları) hakkında bilgi vermektedir. Ben içerisinde CubeMX ve diğer ST-LINK yazılımlarının kurulu bir şekilde gelmesi, tamamen ücretsiz olması ve üreticinin IDE'si olması nedeniyle **STM32CubeIDE** 'yi tercih edeceğim.
- Getting started with STM32 Nucleo board software development tools (User Manual) - [UM1727](https://www.st.com/resource/en/user_manual/dm00105928-getting-started-with-stm32-nucleo-board-software-development-tools-stmicroelectronics.pdf)
> Mikrodenetleyici ile ilgili tüm detaylı bilgilere, üreticinin sitesinden Datasheet diye tabir edilen bilgi kağıtlarından ulaşıyoruz. 'User Manuel' de bunlardan biri. STM32F446RE kullandığım için [www.st.com](https://www.st.com/) ST firmasının mikrodenetleyici kataloglarından kendi kartımla ilgili bilgilere ulaşabiliyorum.

### STM32CubeIDE

Programı kullandığım Mayıs 2020 tarihi itibariyle şu anda 1.3.0 Windows versiyonunu kullanmaktayım. Kurulum da yapmanız gereken tek şey Next -> Next demek. Nucleo veya Discovery Board kullanıyorsanız içerisinde ST-LINK/V2 programlayıcısı tümleşik halde olduğu için ek bir donanıma gerek kalmıyor. Yazılım kısmında ise zaten programlayıcı yükleme kısmında kutucuk tik işaretli bir şekilde karşımıza çıkıyor. Ayarları değiştirmeden yüklediğimizde bağladığımız USB girişi üzerinden mikrodenetleyicimizi programlayabiliyoruz. CubeMX yazılımı da içerisinde tümleşik olarak IDE'yle birlikte gelmektedir. STM32CubeIDE kullanacaksanız ayrıca yüklemenize gerek yok.
- [STM32CubeIDE İndirme Linki](https://www.st.com/en/development-tools/stm32cubeide.html) Get Software diyerek işletim sisteminize uygun bağlantıdan indirebilirsiniz. [STM32CubeIDE Databrief](https://www.st.com/resource/en/data_brief/stm32cubeide.pdf)

### Farklı Bir IDE Kullanmak

Diğer ide'lerde (geliştirme ortamı) STM32 HAL kütüphanesinden yararlanmak için STM32CubeMX programını kurmanız gerekmektedir.
- [STM32CubeMX İndirme Linki](https://www.st.com/en/development-tools/stm32cubemx.html) Get Software butonu ile indirebilirsiniz. [STM32CubeMX Databrief](https://www.st.com/resource/en/data_brief/stm32cubemx.pdf)
> CubeMX ile ilgili asıl göz atmamız gereken User Manuel dosyasıdır. İçerisinde tüm bölümleri en başından ide'niz için C kodu üretmeye kadar detaylı bir şekilde anlatmaktadır.
STM32CubeMX for STM32 configuration and initialization C code generation (User Manuel) - [UM1718](https://www.st.com/content/ccc/resource/technical/document/user_manual/10/c5/1a/43/3a/70/43/7d/DM00104712.pdf/files/DM00104712.pdf/jcr:content/translations/en.DM00104712.pdf)

##### ST-LINK/V2
Aslında aşağıdaki idelerle birlikte içerisinde yüklendiğini hatırlıyorum ama tam emin değilim. STM32CubeMX 'le birlikte yükleniyorda olabilir. Neyse, ST-LINK/V2 normalde ayrı bir aparat olarak satılan bir programlayıcıdır. Yani; bizim sahip olduğumuz mikrodenetleyiciyi programlamaya yarar. Fakat **NUCLEO veya DISCOVERY** kullanıyorsanız ayrıca bu aparatı satın almanıza gerek yoktur. Zaten kartla birlikte tümleşik olarak gelmektedir. Dik tuttuğumuzda üstteki alttakine göre ufak olan kısım bizim programlayıcımızdır. Bir kaç ayar yaparsanız başka kartları programlamak için bile kullanabilirsiniz. Genellikle M3 Cortex bir çekirdek mevcuttur. USB aracılığıyla aldığı verilerle alttaki asıl mikrodenetleyicimiz olan M4 çekirdeğine (kendi kartım için konuşuyorum - STM32F446-RE) programlanmasını sağlar. USB ile ST-LINK/V2 kullanmak için birde sürücüsüne ihtiyacımız vardır. STM32CubeIDE kullanıyorsanız Next -> Next kısmında ierlerken tikli olduğunu görmüş olmalısınız. Ama alttaki idelerde olmama ihtimaline karşı linki yazıyorum.
- [ST-LINK/V2](https://www.st.com/en/development-tools/stsw-link009.html#get-software)
- [STM32 ST-LINK Utility](https://www.st.com/en/development-tools/stsw-link004.html#get-software)
> Utility ise memory takibi yapmamıza, doğruluyabilmemize, silmemize kısacası elimizdeki kartın içeriğine erişip, HEX dosyalarını görüntülemek için kolay ve verimli bir yardımcımızdır. Daha profesyonel kullanımlarda tercih edilse de bir bakmanızda fayda olacağını düşünüyorum. Bu programlarla ilgili bütün bağlantıların yer aldığı sayfayada [ST-LINK/V2 in-circuit debugger/programmer for STM8 and STM32](https://www.st.com/en/development-tools/st-link-v2.html#tools-software) adresinden ulaşabilirsiniz.

##### Keil µVision

Arm firmasının resmi programlama ortamıdır. Ücretsiz sürüm de 32kB kod limiti vardır.
- [Keil µVision İndirme Linki](https://www.keil.com/download/product/)

##### IAR Embedded Workbench for Arm

IAR firmasının Arm işlemciler için programlama ortamıdır. Özellikle mikrodenetleyici kullanmadan 'Simülasyon' özelliğiyle kullanabilirsiniz. Ücretsiz sürüm de 32kB kod limiti vardır.
- [IAR Embedded Workbench for Arm](https://www.iar.com/iar-embedded-workbench/#!?currentTab=free-trials)

##### Atollic TrueSTUDIO

ST firması Atollic TrueSTUDIO firmasını satın aldı ve üzerine kendi STM32CubeIDE yazılımını geliştirdi. Bende artık bu ide'yi kullanmanızı tavsiye etmiyorum. Aslında gereksiz bir genel kültür oldu. Zaten sitenin anasayfasında uyarı olarak yeni versiyonları çıkmayacağı ve STM32CubeIDE kullanılması tavsiye edilmektedir. STMCubeIDE 'nin 1.3.0 'dan önceki versiyonlarında bende bir kaç kez kullanmıştım. Fakat yeni versiyonla bir çok yeni özellik geliştirildiği için artık Atollic programına gerek kalmadı. Youtube, Udemy gibi bazı video ortamlarında dersler Atollic programıyla çekildiği için denemek isteyenler olursa diye ilgili bağlantıyı aşağıya bırakıyorum. 
- [Atollic TrueStudio](https://atollic.com/resources/download/)

##### System Workbench for STM32

Açık kaynak mimarisini kullanarak oluşturulan bir topluluk ide'sidir.
- [SW4STM32](https://www.openstm32.org/HomePage)

---

## Donanımlarımız için Gerekli Bilgi Kağıtları (Datasheets / User Manuals)

Örneklerimi ben kendi kartım **STM32F446RE - NUCLEO** için yapacağım. Siz de aynı yolları izleyerek hangi kartı kullanıyorsanız üreticinin sitesinden kendi kartınızın bilgilerine erişebilirsiniz. Zaten google dahil kartınızı arattığınız da yine reklamsızlarda ilk sırada çıkıyor.

https://www.st.com/en/microcontrollers-microprocessors/stm32f446re.html - Benim kartımız adresi burada yer almaktadır ve kartımla ilgili tüm bilgilere **KEY FEATURES** içeriğinden ulaşabiliyorum. Üstte bahsettiğim URL'ye girdiğinizde kırmızı çerçeveli [Download datasheet](https://www.st.com/resource/en/datasheet/stm32f446re.pdf) kısmına baktığımızda genel pin yapısı, regülatör bağlantıları, block diyagramı gibi bilgilere erişebiliyoruz. Burada bizim için block diyagramın ekran görüntüsünü çekip, saklamamız faydalı olacaktır. Bazı konularda kullanacağımız özelliğin hangi veriyoluna bağlı olduğunu bilmemiz gerekebiliyor.

**[ EKRAN GORUNTUSU GELECEK ]**

[Tools & Software](https://www.st.com/en/microcontrollers-microprocessors/stm32f446re.html#tools-software) dediğimizde daha önce verdiğimiz programların da dahil olduğu kartımızla birlikte kullanabileceğimiz kocaman bir program listesi çıkıyor.

[Resources](https://www.st.com/en/microcontrollers-microprocessors/stm32f446re.html#resource) İşte nihayet asıl mekanımıza geldik. Kartımızla alakalı bol bol doküman mevcut. Nasıl kullanabileceğimizden tutun da örneklere kadar bir çok veri bulunmaktadır.
- [RM0390 - Reference manual](https://www.st.com/resource/en/reference_manual/dm00135183-stm32f446xx-advanced-armbased-32bit-mcus-stmicroelectronics.pdf) Aslında en çok uğrayacağımız bölümdür. Mikrodenetleyicinize ait her yapının registers(yazmaçları) ve bitleri yer almaktadır. En önemlisi de bunların nasıl programlanması gerektiği anlatılmaktadır.
- [PM0214 - Programming manual](https://www.st.com/resource/en/programming_manual/dm00046982-stm32-cortexm4-mcus-and-mpus-programming-manual-stmicroelectronics.pdf) Bu kaynakla birlikte aslında mikrodenetleyici programlamak için temel dokümanlara sahip oluyoruz.

##### STM32 HAL(Hardware Abstraction Layer) Libraries

Bizim yazılımlarımızda kullanacağımız donanım soyutlama katmanlarına da aşağıdaki bağlantılardan erişebiliriz. Hangi işlemci çekirdeğini kullanıyorsanız onunla ilgili kütüphaneye bakabilirsiniz. Benim işlemci çekirdeğim Cortex - M4 olduğu için **STM32F4 HAL and low-layer drivers** kısmına bakacağım.

- Description of STM32F0 HAL and low-layer drivers [UM1785](https://www.st.com/content/ccc/resource/technical/document/user_manual/2f/77/25/0f/5c/38/48/80/DM00122015.pdf/files/DM00122015.pdf/jcr:content/translations/en.DM00122015.pdf)
- Description of STM32F1 HAL and low-layer drivers [UM1850](https://www.st.com/content/ccc/resource/technical/document/user_manual/72/52/cc/53/05/e3/4c/98/DM00154093.pdf/files/DM00154093.pdf/jcr:content/translations/en.DM00154093.pdf)
- Description of STM32F2 HAL and low-layer drivers [UM1940](https://www.st.com/content/ccc/resource/technical/document/user_manual/56/32/53/cb/69/86/49/0e/DM00223149.pdf/files/DM00223149.pdf/jcr:content/translations/en.DM00223149.pdf)
- Description of STM32F3 HAL and low-layer drivers [UM1786](https://www.st.com/content/ccc/resource/technical/document/user_manual/a6/79/73/ae/6e/1c/44/14/DM00122016.pdf/files/DM00122016.pdf/jcr:content/translations/en.DM00122016.pdf)
- Description of STM32F4 HAL and low-layer drivers [UM1725](https://www.st.com/content/ccc/resource/technical/document/user_manual/2f/71/ba/b8/75/54/47/cf/DM00105879.pdf/files/DM00105879.pdf/jcr:content/translations/en.DM00105879.pdf)
- Description of STM32L4 HAL and low-layer drivers [UM1884](https://www.st.com/content/ccc/resource/technical/document/user_manual/63/a8/8f/e3/ca/a1/4c/84/DM00173145.pdf/files/DM00173145.pdf/jcr:content/translations/en.DM00173145.pdf)
- Description of STM32F7 HAL and low-layer drivers [UM1905](https://www.st.com/content/ccc/resource/technical/document/user_manual/45/27/9c/32/76/57/48/b9/DM00189702.pdf/files/DM00189702.pdf/jcr:content/translations/en.DM00189702.pdf)
- Description of STM32H7 HAL and low-layer drivers [UM2217](https://www.st.com/content/ccc/resource/technical/document/user_manual/group0/40/ee/88/53/f6/1e/4c/87/DM00392525/files/DM00392525.pdf/jcr:content/translations/en.DM00392525.pdf)

Kendi işlemcinizi göremiyor veya bağlantı adresleri bozulmuş olma ihtimaline karşı [buradan](https://www.st.com/en/embedded-software/stm32cube-mcu-mpu-packages.html?querycriteria=productId=LN1897#overview) geliştirici sitesine gidip, [Product selector](https://www.st.com/en/embedded-software/stm32cube-mcu-mpu-packages.html?querycriteria=productId=LN1897#products) seçeneğinden kendi mikrodenetleyicinize ait HAL dokümanına ulaşabilirsiniz.

---

## Temel HAL Projesi Oluşturma

---

**MIT Lisansı**

[Telif Hakkı](https://github.com/w3eydi/STM32-Egitimi/blob/master/LICENSE) (Copyright) (c) 2020 Eydi Gözeneli - github.com/w3eydi