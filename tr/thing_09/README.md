# Başkalarını Suçlamadan Önce Kodunuzu Kontrol Edin

Geliştiriciler — hepimiz! — genellikle kendi kodumuzun bozulduğuna inanmakta güçlük çekeriz. O kadar ihtimal dışı ki, bir kez olsun, bozuk olan derleyici olmalı.

Ancak gerçekte kodun derleyici, yorumlayıcı, işletim sistemi, uygulama sunucusu, veritabanı, bellek yöneticisi veya başka herhangi bir sistem yazılımı parçasındaki bir hata tarafından kırılması çok (çok) olağandışıdır. Evet, bu hatalar var, ancak inanmak isteyebileceğimizden çok daha az yaygınlar.

Bir zamanlar bir döngü değişkenini optimize eden bir derleyici hatasıyla ilgili gerçek bir sorunum vardı, ancak derleyicimde veya işletim sistemimde birçok kez bir hata olduğunu hayal ettim. Her seferinde benim hatam olduğu ortaya çıktığında kendimi biraz aptal hissetmek için süreçte çok zamanımı, destek zamanımı ve yönetim zamanımı harcadım.

Araçların yaygın olarak kullanıldığını, olgunlaştığını ve çeşitli teknoloji yığınlarında kullanıldığını varsayarsak, kaliteden şüphe etmek için çok az neden vardır. Tabii ki, araç erken bir sürümse veya dünya çapında yalnızca birkaç kişi tarafından kullanılıyorsa veya nadiren indirilen bir sürüm (0.1), Açık Kaynaklı Yazılım parçasıysa, yazılımdan şüphelenmek için iyi bir neden olabilir. (Aynı şekilde, ticari yazılımın alfa sürümü de şüpheli olabilir.)

Derleyici hatalarının ne kadar nadir olduğu göz önüne alındığında, derleyicinin yanlış olduğunu kanıtlamaktansa, zamanınızı ve enerjinizi kodunuzdaki hatayı bulmaya harcamanız çok daha iyidir. Tüm olağan hata ayıklama tavsiyeleri geçerlidir, bu nedenle sorunu yalıtın, aramaları devre dışı bırakın, testlerle çevreleyin; arama kurallarını, paylaşılan kitaplıkları ve sürüm numaralarını kontrol edin; başkasına açıkla; yığın bozulmasına ve değişken tür uyumsuzluklarına dikkat edin; kodu farklı makinelerde ve hata ayıklama ve yayınlama gibi farklı yapı yapılandırmalarında deneyin.

Kendi varsayımlarınızı ve başkalarının varsayımlarını sorgulayın. Farklı satıcılara ait araçlarda farklı varsayımlar yerleşik olabilir - aynı satıcıdan farklı araçlar da olabilir. Başka biri tekrarlayamayacağınız bir sorunu bildirdiğinde, gidin ve ne yaptıklarına bakın. Belki de hiç düşünmediğiniz bir şeyi yapıyorlar ya da farklı bir sırayla bir şeyler yapıyorlar.

Kişisel bir kural olarak, sabitleyemediğim bir hatam varsa ve bunun derleyici olduğunu düşünmeye başlıyorum, o zaman yığın bozulması aramanın zamanı geldi. Bu, özellikle izleme kodunun eklenmesi sorunu hareket ettiriyorsa geçerlidir.

Çok iş parçacıklı sorunlar, saçları griye çeviren ve makinede çığlık atmaya neden olan başka bir hata kaynağıdır. Basit kodu destekleyen tüm öneriler, bir sistem çok iş parçacıklı olduğunda çoğalır. Hata ayıklama ve birim testleri, bu tür hataları herhangi bir tutarlılıkla bulmak için güvenilemez, bu nedenle tasarımın basitliği çok önemlidir.

Derleyiciyi suçlamak için acele etmeden önce, Sherlock Holmes'un tavsiyesini hatırlayın, "Bir kez imkansızı ortadan kaldırdığınızda, geriye kalan ne kadar imkansız olursa olsun, gerçek olmalı" ve bunu Dirk Gently'nin "Olası olmayanı bir kez ortadan kaldırdığınızda, geriye ne kaldıysa, ne kadar imkansız olursa olsun, gerçek olmalı."

[Allan Kelly](http://programmer.97things.oreilly.com/wiki/index.php/Allan_Kelly) Tarafından