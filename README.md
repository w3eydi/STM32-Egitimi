# STM32-Eğitimi

### STM32 HAL kütüphane örneklerinin git markdown yöntemiyle dokümantasyon olarak anlatılmıştır.

----------------------------


## Başlarken

STM32 HAL dokümantasyonu elektronik ve Arm programlama konusunda az çok bilgi sahibi, en azından led yakıp, söndürmüş veya bu konuyla haşır neşir olan kişilere daha çok hitap etmektedir. Her ne kadar anlatımımızı elimizden geldiğince sade bir şekilde anlatmaya çalışacak olsak da hiç bir bilgisi olmayan kişiler başlangıç aşamasında zorlanabilirler. Bu yüzden internette bolca bulunan ve devamı gelmeyen Türkçe kaynaklardan başlangıç aşamasını atlatabilirsiniz. Asıl amaç; az kullandığımız için unutulan bazı STM32 HAL yöntemlerini dokümante etmek, hızlı bir şekilde kullanılabilmesini sağlamak ve her ne kadar ingilizceden çeviri yapabileceğimiz bir çok araç olsa da çalışmamak için öne sürülen 'Türkçe kaynak yok!', 'İngilizcem iyi değil!' şeklindeki söylemlerin(!) azalmasına bir nebze katkı da bulunmaktır. Sizden en başta sabırlı olmanızı istiyorum. Azimli ve sabırlı bir şekilde gayret gösterirseniz, üstesinden gelebileceğinizi düşünmekteyim. Başarılar dilerim.


## Gereksinimler

- C Programlama Bilgisi
- Temel Elektronik
- STM32CubeIDE ( CubeIDE içerisinde CubeMX mevcut, ekstra kurmanıza gerek yok. Keil, IAR, Atollic veya System Workbench for STM32 ile kullanmak istiyorsanız yanında STM32CubeMX kurmanız gerekmektedir. )
- STM32 F Serisi Geliştirme Kartı ( STM32F0-(F1, F3, F4, L4, F7, H7) kartlarından elinizde mevcut olan veya ihtiyacınıza göre almak istediğiniz herhangi bir kartı kullanabilirsiniz. )

Benim elimde **STM32F446-RE NUCLEO** geliştirme kartı bulunmaktadır ve uygulamalarımda bu kartı kullanacağım.


## STM32 Eğitimi - 000 Başlangıç

İçerik:
- IDE kurulum kılavuzları ve indirme linkleri.
- İşlemci kullanım kılavuz bağlantıları. (Datasheets)
- CubeMX ile temel kod yazım ortamı oluşturulması.

---

**MIT Lisansı**

Telif Hakkı (Copyright) (c) 2020 Eydi Gözeneli - github.com/w3eydi

>Hiçbir ücret talep edilmeden burada işbu yazılımın bir kopyasını ve belgelendirme dosyalarını (“Yazılım”) elde eden herkese verilen izin; kullanma, kopyalama, değiştirme, birleştirme, yayımlama, dağıtma, alt lisanslama, ve/veya yazılımın kopyalarını satma eylemleri de dahil olmak üzere ve bununla kısıtlama olmaksızın, yazılımın sınırlama olmadan ticaretini yapmak için verilmiş olup, bunları yapmaları için yazılımın sağlandığı kişilere aşağıdakileri yapmak koşuluyla sunulur:

>Yukarıdaki telif hakkı bildirimi ve işbu izin bildirimi yazılımın tüm kopyalarına veya önemli parçalarına eklenmelidir. 

>YAZILIM “HİÇBİR DEĞİŞİKLİK YAPILMADAN” ESASINA BAĞLI OLARAK, TİCARETE ELVERİŞLİLİK, ÖZEL BİR AMACA UYGUNLUK VE İHLAL OLMAMASI DA DAHİL VE BUNUNLA KISITLI OLMAKSIZIN AÇIKÇA VEYA ÜSTÜ KAPALI OLARAK HİÇBİR TEMİNAT OLMAKSIZIN SUNULMUŞTUR. HİÇBİR KOŞULDA YAZARLAR VEYA TELİF HAKKI SAHİPLERİ HERHANGİ BİR İDDİAYA, HASARA VEYA DİĞER YÜKÜMLÜLÜKLERE KARŞI, YAZILIMLA VEYA KULLANIMLA VEYA YAZILIMIN BAŞKA BAĞLANTILARIYLA İLGİLİ, BUNLARDAN KAYNAKLANAN VE BUNLARIN SONUCU BİR SÖZLEŞME DAVASI, HAKSIZ FİİL VEYA DİĞER EYLEMLERDEN SORUMLU DEĞİLDİR.