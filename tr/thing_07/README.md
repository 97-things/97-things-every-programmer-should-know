# Paylaşıma Dikkat Edin

Şirketteki ilk projemdi. Derecemi yeni bitirmiştim ve her gün geç saatlere kadar mevcut kodu inceleyerek kendimi kanıtlamak için can atıyordum. İlk değişiklik üzerinde çalışırken, öğrendiğim her şeyi - yorum yapmak, günlüğe kaydetmek, mümkünse ortak kodu kütüphanelere çekmek işlerini - uygulamaya koymak için ekstra özen gösterdim. Kendimi çok hazır hissettiğim kod incelemesi kaba bir uyanış olarak geldi - yeniden kullanım hoş karşılanmadı!

Bu nasıl olabilir? Üniversite boyunca yeniden kullanım, kaliteli yazılım mühendisliğinin özü olarak kabul edildi. Okuduğum tüm makaleler, ders kitapları, bana öğreten deneyimli yazılım uzmanları. Hepsi yanlış mıydı?

Kritik bir şeyi kaçırdığım ortaya çıktı.

Bağlam.

Sistemin çılgınca farklı iki parçasının aynı şekilde bazı mantık yürütmeleri, düşündüğümden daha az şey ifade ediyordu. Bu paylaşılan kod kitaplıklarını çıkarana kadar, bu parçalar birbirine bağımlı değildi. Her biri bağımsız olarak gelişebilir. Her biri, sistemin değişen iş ortamının ihtiyaçlarına göre mantığını değiştirebilir. Bu dört satırlık benzer kod tesadüfiydi - zamansal bir anormallik, bir tesadüf. Yani ben gelene kadar.

Oluşturduğum ortak kod kitaplıkları her ayağın bağcıklarını birbirine bağladı. Bir iş etki alanına göre adımlar, önce diğeriyle senkronize edilmeden yapılamaz. Bu bağımsız işlevlerdeki bakım maliyetleri ihmal edilebilir düzeydeydi, ancak ortak kitaplık, çok daha fazla test gerektiriyordu.

Sistemdeki mutlak kod satırı sayısını azaltırken, bağımlılık sayısını artırdım. Bu bağımlılıkların bağlamı kritiktir - yerelleştirilmiş olsalardı, haklı olabilirdi ve bazı olumlu değerlere sahip olabilirdi. Bu bağımlılıklar kontrol altında tutulmadığında, kodun kendisi gayet iyi görünse bile, eğilimleri sistemi daha büyük endişelere bulaştırır.

Bu hatalar sinsidir, özünde iyi bir fikir gibi görünürler. Doğru bağlamda uygulandığında bu teknikler değerlidir. Yanlış bağlamda, değerden çok maliyeti artırırlar. Çeşitli bölümlerin kullanılacağı bağlam hakkında hiçbir bilgim olmadan mevcut bir kod tabanına geldiğimde, bugünlerde nelerin paylaşıldığı konusunda çok daha dikkatli oluyorum.

Paylaşıma dikkat edin. Bağlamınızı kontrol edin. Ancak o zaman devam edin.

[Udi Dahan](http://programmer.97things.oreilly.com/wiki/index.php/Udi_Dahan) Tarafından