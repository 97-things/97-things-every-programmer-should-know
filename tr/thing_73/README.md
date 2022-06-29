# Singleton Modelin Cazibesine Kapılma

Singleton modeli, sorunlarınızın çoğunu çözer. Sadece tek bir örneğe ihtiyacınız olduğunu biliyorsunuz. Bu örneğin kullanılmadan önce başlatılacağına dair bir garantiniz var. Küresel bir erişim noktasına sahip olarak tasarımınızı basit tutar. Hepsi iyi. Bu klasik tasarım deseninde sevilmeyen şey nedir?

Oldukça fazla, ortaya çıkıyor. Cazip olabilirler, ancak deneyimler çoğu singleton'ın gerçekten yarardan çok zarar verdiğini gösteriyor. Test edilebilirliği engeller ve sürdürülebilirliğe zarar verirler. Ne yazık ki, bu ek bilgelik olması gerektiği kadar yaygın değildir ve singleton'lar birçok programcı için karşı konulmaz olmaya devam etmektedir. Ama direnmeye değer:

- Tek örnek gereksinimi çoğu zaman hayal edilir. Çoğu durumda, gelecekte ek bir örneğe gerek olmayacağı tamamen spekülasyondur. Bir uygulamanın tasarımı boyunca bu tür spekülatif özelliklerin yayınlanması, bir noktada acıya neden olacaktır. Gereksinimler değişecek. İyi tasarım bunu benimser. Singleton'lar yapmaz.

- Singleton'lar, kavramsal olarak bağımsız kod birimleri arasında örtük bağımlılıklara neden olur. Bu, hem gizli oldukları için hem de birimler arasında gereksiz bağlantı oluşturdukları için sorunludur. Bu kod kokusu, gevşek bağlantıya ve sahte bir uygulamayı gerçek bir uygulamayla seçici olarak değiştirme yeteneğine bağlı olan birim testleri yazmaya çalıştığınızda keskinleşir. Singletons, bu tür basit alaycılığı önler.

- Singleton'lar ayrıca, birim testini yine engelleyen örtük kalıcı durum taşır. Birim testi, testlerin birbirinden bağımsız olmasına bağlıdır, bu nedenle testler herhangi bir sırada çalıştırılabilir ve program, her birim testinin yürütülmesinden önce bilinen bir duruma ayarlanabilir. Değişken duruma sahip tekilleri tanıttıktan sonra, bunu başarmak zor olabilir. Ek olarak, bu tür küresel olarak erişilebilir kalıcı durum, özellikle çok iş parçacıklı bir ortamda kod hakkında akıl yürütmeyi zorlaştırır.

- Çoklu iş parçacığı, singleton desene başka tuzaklar getirir. Erişimi doğrudan kilitleme çok verimli olmadığı için, sözde çift kontrol kilitleme modeli (DCLP) popülerlik kazanmıştır. Ne yazık ki, bu ölümcül çekiciliğin başka bir şekli olabilir. DCLP'nin birçok dilde iş parçacığı için güvenli olmadığı ve olduğu yerde bile, onu kurnazca yanlış anlama fırsatları olduğu ortaya çıktı.

Singletonların temizlenmesi son bir zorluk sunabilir:

- Bazı bağlamlarda ciddi bir sorun olabilen, Singleton'ları açıkça öldürmek için destek yoktur. Örneğin, bir eklentinin yalnızca tüm nesneleri temizlendikten sonra güvenli bir şekilde kaldırılabileceği bir eklenti mimarisinde.

- Program çıkışında singleton'ların örtülü temizliğine yönelik bir düzen yoktur. Bu, karşılıklı bağımlılıkları olan tekiller içeren uygulamalar için zahmetli olabilir. Bu tür uygulamaları kapatırken, bir singleton, zaten yok edilmiş olan diğerine erişebilir.

- Bu eksikliklerin bir kısmı, ek mekanizmalar getirilerek aşılabilir. Ancak bu, alternatif bir tasarım seçerek önlenebilecek ek kod karmaşıklığı pahasına gelir.

Bu nedenle, Singleton deseni kullanımınızı, gerçekten hiçbir zaman birden çok kez somutlaştırılmaması gereken sınıflarla sınırlayın. Bir singleton'ın global erişim noktasını rastgele koddan kullanmayın. Bunun yerine, singleton'a doğrudan erişim, arayüzü aracılığıyla diğer koda geçirilebileceği yalnızca birkaç iyi tanımlanmış yerden olmalıdır. Bu diğer kod habersizdir ve bu nedenle, bir singleton'un veya başka bir sınıfın arabirimi uygulayıp uygulamadığına bağlı değildir. Bu, birim testini engelleyen bağımlılıkları kırar ve sürdürülebilirliği iyileştirir. Bu nedenle, bir dahaki sefere bir singleton uygulamayı veya ona erişmeyi düşündüğünüzde, umarım durup tekrar düşünürsünüz.

[Sam Saariste](http://programmer.97things.oreilly.com/wiki/index.php/Sam_Saariste) Tarafından