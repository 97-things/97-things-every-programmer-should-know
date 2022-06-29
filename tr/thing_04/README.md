# Kodlama Standardınızı Otomatikleştirin

Muhtemelen sen de orada bulunmuşsundur. Bir projenin başlangıcında herkesin birçok iyi niyeti vardır - bunlara "yeni projenin kararları" diyebiliriz. Oldukça sık olarak, bu kararların çoğu belgelere yazılır. Kodla ilgili olanlar projenin kodlama standardında yer alır. Başlangıç toplantısında, baş geliştirici belgeyi gözden geçirir ve en iyi durumda, herkes onları takip etmeye çalışacaklarını kabul eder. Ancak proje başladığında, bu iyi niyetler birer birer terk edilir. Proje sonunda teslim edildiğinde, kod bir karmaşa gibi görünüyor ve kimse bu hale nasıl geldiğini bilmiyor.

İşler ne zaman ters gitti? Muhtemelen başlangıç toplantısında. Bazı proje üyeleri dikkat etmedi. Diğerleri konuyu anlamadı. Daha da kötüsü, bazıları aynı fikirde değildi ve zaten kodlama standart isyanını planlıyorlardı. Sonunda bazıları konuyu anladı ve kabul etti, ancak projedeki baskı çok arttığında bir şeyleri bırakmak zorunda kaldılar. İyi biçimlendirilmiş kod, daha fazla işlevsellik isteyen bir müşteriyle size puan kazandırmaz. Ayrıca, bir kodlama standardını takip etmek, otomatikleştirilmemişse oldukça sıkıcı bir görev olabilir. Kendiniz bulmak için sadece dağınık bir sınıfı elle girintilemeye çalışın.

Ama eğer böyle bir problemse, neden ilk etapta bir kodlama standardına sahip olmak istiyoruz? Kodu tek tip bir şekilde biçimlendirmenin bir nedeni, hiç kimsenin bir kod parçasına yalnızca kendi özel yöntemiyle biçim vererek "sahip olmaması"dır. Bazı yaygın hatalardan kaçınmak için geliştiricilerin belirli anti-kalıpları kullanmasını önlemek isteyebiliriz. Toplamda, bir kodlama standardı projede çalışmayı kolaylaştırmalı ve baştan sona geliştirme hızını korumalıdır. Bundan sonra herkesin kodlama standardı üzerinde hemfikir olması gerekir - bir geliştiricinin kodu girintilemek için üç boşluk kullanması ve diğerinin dört boşluk kullanması yardımcı olmaz.

Kod kalitesi raporları oluşturmak ve kodlama standardını belgelemek ve sürdürmek için kullanılabilecek çok sayıda araç vardır, ancak tüm çözüm bu değildir. Mümkünse otomatikleştirilmeli ve uygulanmalıdır. İşte birkaç örnek:

- Kod biçimlendirmenin derleme sürecinin bir parçası olduğundan emin olun, böylece herkes kodu her derlediğinde bunu otomatik olarak çalıştırır.
- İstenmeyen anti-kalıplara karşı kodu taramak için statik kod analiz araçlarını kullanın. Herhangi biri bulunursa, yapıyı bozun.
- Kendi, projeye özgü anti-kalıplarınızı tarayabilmeniz için bu araçları yapılandırmayı öğrenin.
- Yalnızca test kapsamını ölçmekle kalmayın, sonuçları da otomatik olarak kontrol edin. Yine, test kapsamı çok düşükse yapıyı bozun.

Bunu önemli olduğunu düşündüğünüz her şey için yapmaya çalışın. Gerçekten önemsediğiniz her şeyi otomatikleştiremezsiniz. Otomatik olarak işaretleyemeyeceğiniz veya düzeltemeyeceğiniz şeylere gelince, bunları otomatikleştirilmiş kodlama standardına tamamlayıcı bir dizi yönerge olarak düşünün, ancak sizin ve iş arkadaşlarınızın bunları özenle takip edemeyeceğinizi kabul edin.

Son olarak, kodlama standardı statik değil dinamik olmalıdır. Proje geliştikçe, projenin ihtiyaçları değişir ve başlangıçta akıllıca görünen şey, birkaç ay sonra mutlaka akıllı olmak zorunda değildir.

[Filip van Laenen](http://programmer.97things.oreilly.com/wiki/index.php/Filip_van_Laenen) Tarafından