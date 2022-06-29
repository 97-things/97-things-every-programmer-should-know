# Yapıya Sahip Olun (ve Yeniden Düzenleyin)

It is not uncommon for teams that are otherwise highly disciplined about coding practices to neglect build scripts, either out of a belief that they are merely an unimportant detail or from a fear that they are complex and need to be tended to by the cult of release engineering. Unmaintainable build scripts with duplication and errors cause problems of the same magnitude as those in poorly factored code.

Kodlama uygulamaları konusunda son derece disiplinli olan ekiplerin, bunların yalnızca önemsiz bir ayrıntı oldukları inancıyla veya karmaşık oldukları ve serbest bırakma mühendislik kültü tarafından yönlendirilmeleri gerektiği korkusuyla komut dosyalarını oluşturmayı ihmal etmeleri nadir görülen bir durum değildir. Yinelenen ve hatalar içeren sürdürülemez yapı komut dosyaları, kötü çarpanlara ayrılmış koddakilerle aynı büyüklükte sorunlara neden olur.

Yanlış deyimler kullanılarak yazılmış derleme komut dosyalarının bakımı ve daha da önemlisi iyileştirmesi zordur. Bir değişiklik yapmanın doğru yolunu anlamak için biraz zaman ayırmaya değer. Bir uygulama bir bağımlılığın yanlış sürümüyle oluşturulduğunda veya derleme zamanı yapılandırması yanlış olduğunda hatalar görünebilir.

Geleneksel olarak test etme, her zaman "Kalite Güvencesi" ekibine bırakılan bir şey olmuştur. Artık, kod yazarken test etmenin, değeri tahmin edilebilir bir şekilde sunabilmek için gerekli olduğunun farkındayız. Aynı şekilde, oluşturma sürecinin geliştirme ekibine ait olması gerekir.

Yapıyı anlamak, tüm geliştirme yaşam döngüsünü basitleştirebilir ve maliyetleri azaltabilir. Yürütülmesi kolay bir yapı, yeni bir geliştiricinin hızlı ve kolay bir şekilde başlamasına olanak tanır. Yapıdaki yapılandırmayı otomatikleştirmek, birden fazla kişi bir proje üzerinde çalışırken tutarlı sonuçlar elde etmenizi sağlayabilir ve "benim için çalışıyor" konuşmasından kaçınabilir. Birçok derleme aracı, kod kalitesiyle ilgili raporlar çalıştırmanıza izin vererek olası sorunları erkenden algılamanıza olanak tanır. Yapıyı nasıl kendinize ait yapacağınızı anlamak için zaman harcayarak kendinize ve ekibinizdeki diğer herkese yardımcı olabilirsiniz. Kodlama özelliklerine odaklanabilir, paydaşlarınıza fayda sağlayabilir ve çalışmayı daha keyifli hale getirebilirsiniz.

Ne zaman ve nasıl değişiklik yapacağınızı bilmek için oluşturma sürecinizi yeterince öğrenin. Derleme komut dosyaları koddur. Uygulama inşa edilene kadar tamamlanmadığı için başka bir nedenden dolayı başka birine bırakılamayacak kadar önemlidirler. Çalışan yazılımı teslim edene kadar programlama işi tamamlanmış sayılmaz.

[Steve Berczuk](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Berczuk) Tarafından