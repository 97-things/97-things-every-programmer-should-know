# İki Yanlış Bir Doğru Yapabilir (ve Düzeltilmesi Zordur)

Kod asla yalan söylemez ama kendi kendisiyle çelişebilir. Bazı çelişkiler "Bu nasıl olabilir?" sorusuna yol açar. anlar.

Bir [röportajda](http://www.netjeff.com/humor/item.cgi?file=ApolloComputer), Apollo 11 Ay Modülü yazılımının baş tasarımcısı Allan Klumpp, motorları kontrol eden yazılımın, iniş aracını kararsız hale getirmesi gereken bir hata içerdiğini açıkladı. Ancak, başka bir hata ilkini telafi etti ve yazılım, hata bulunmadan veya düzeltilmeden önce hem Apollo 11 hem de 12 Ay inişleri için kullanıldı.

Bir tamamlanma durumu döndüren bir işlev düşünün. true döndürmesi gerektiğinde false döndürdüğünü hayal edin. Şimdi(now) çağıran fonksiyonun dönüş değerini kontrol etmeyi ihmal ettiğini hayal edin. Bir gün biri eksik çeki fark edip onu yerleştirene kadar her şey yolunda gider.

Veya durumu bir XML belgesi olarak depolayan bir uygulamayı düşünün. Düğümlerden birinin, belgelerin olması gerektiği gibi, `TimeToDie` yerine `TimeToLive` olarak yanlış yazıldığını hayal edin. Hem yazar kodu hem de okuyucu kodu aynı hatayı içeriyorken her şey yolunda görünüyor. Ancak birini düzeltin veya aynı belgeyi okuyan yeni bir uygulama ekleyin ve simetri ve kod bozulur.

Koddaki iki kusur, tek bir görünür hata oluşturduğunda, hataları düzeltmeye yönelik metodik yaklaşım kendi kendine çökebilir. Geliştirici bir hata raporu alır, hatayı bulur, düzeltir ve yeniden test eder. Bildirilen hata yine de ortaya çıkıyor, çünkü ikinci bir hata çalışıyor. Böylece ilk düzeltme kaldırılır, ikinci temel kusur bulunana kadar kod incelenir ve bunun için bir düzeltme uygulanır. Ancak ilk hata geri döndü, bildirilen hata hala görülüyor ve bu nedenle ikinci düzeltme geri alındı. Süreç tekrar ediyor, ancak şimdi geliştirici iki olası düzeltmeyi reddetti ve asla işe yaramayacak bir üçüncüsü yapmak istiyor.

Görünür bir hata olarak görünen iki kod hatası arasındaki etkileşim, yalnızca sorunu çözmeyi zorlaştırmakla kalmaz, aynı zamanda geliştiricileri çıkmaz sokaklara sürükler, yalnızca doğru yanıtları erkenden denediklerini bulmak için.

Bu sadece kodda olmaz: Sorun yazılı gereksinim belgelerinde de mevcuttur. Ve viral olarak bir yerden diğerine yayılabilir. Koddaki bir hata, yazılı açıklamadaki bir hatayı telafi eder.

İnsanlara da yayılabilir: Kullanıcılar, uygulama Sol dediğinde Sağ anlamına geldiğini öğrenir ve davranışlarını buna göre ayarlar. Hatta bunu yeni kullanıcılara iletiyorlar: "Unutmayın, uygulamalar sol düğmeyi tıklayın diyorsa, bu gerçekten sağdaki düğme anlamına gelir." Hatayı düzeltin ve aniden kullanıcıların yeniden eğitilmesi gerekir.

Tek bir yanlışın fark edilmesi ve düzeltilmesi kolay olabilir. Çözülmesi daha zor olan, birden çok nedeni olan, birden çok değişikliğe ihtiyaç duyan sorunlardır. Kısmen, kolay problemler o kadar kolay çözülür ki, insanlar onları nispeten hızlı bir şekilde düzeltmeye ve daha zor problemleri daha sonraki bir tarihe saklamaya eğilimlidir.

Sempatik kusurlardan kaynaklanan arızaların nasıl ele alınacağı konusunda verilecek basit bir tavsiye yoktur. Olasılığın farkında olmak, açık bir kafa ve tüm olasılıkları değerlendirmeye istekli olmak gereklidir.

[Allan Kelly](http://programmer.97things.oreilly.com/wiki/index.php/Allan_Kelly) Tarafından