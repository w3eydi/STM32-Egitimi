# STM32 Eğitimi - 000 Başlangıç

STM32 Platformu için Gömülü Sistem Programlama

----------------------------

## Başlarken

Bu ilk bölümde STM32 mikrodenetleyicileri programlamak için gerekli ortamların kurulmasını göstereceğim. Birincil kaynak olarak her zaman geliştiriciyi tercih ediyoruz. Bu dokümanlara nasıl ulaşılacağı konusunda bağlantılarıyla birlikte bilgi vereceğim. İkincil ve üçüncül kaynaklar olarak kitap, blog yazıları youtube, udemy, vb. gibi platformları tercih edebilirsiniz. Son olarak diğer bölümlerde kullanabileceğimiz şekilde temel, başlangıç bir arm programlama ortamı oluşturacağız.

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