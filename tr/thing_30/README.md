# Kendinizi Tekrar Etmeyin (Don't Repeat Yourself - DRY)

Programlamanın tüm ilkeleri arasında, Kendini Tekrar Etme (DRY) belki de en temellerinden biridir. İlke, Andy Hunt ve Dave Thomas tarafından *The Pragmatic Programmer*'da formüle edilmiştir ve diğer birçok iyi bilinen yazılım geliştirme en iyi uygulamalarının ve tasarım modellerinin temelini oluşturur. Tekrarlamayı tanımayı öğrenen ve uygun uygulama ve doğru soyutlama yoluyla bunu nasıl ortadan kaldıracağını anlayan geliştirici, uygulamayı sürekli olarak gereksiz tekrarlarla bulaştıran birinden çok daha temiz kod üretebilir.

Tekrarlamak israftır
---

Bir uygulamaya giren her kod satırı korunmalıdır ve gelecekteki hataların potansiyel bir kaynağıdır. Tekrarlama, kod tabanını gereksiz yere şişirir, bu da hatalar için daha fazla fırsat sağlar ve sisteme kazara karmaşıklık ekler. Tekrarlamanın sisteme eklediği şişkinlik, sistemle çalışan geliştiricilerin tüm sistemi tam olarak anlamasını veya bir yerde yapılan değişikliklerin mantığı kopyalayan başka yerlerde yapılması gerekmediğinden emin olmasını da zorlaştırır. DRY, "her bilgi parçasının bir sistem içinde tek, açık ve yetkili bir temsile sahip olmasını" gerektirir.

Süreçte tekrar, otomasyon gerektirir
---

Yazılım geliştirmedeki birçok süreç tekrarlanır ve kolayca otomatikleştirilir. DRY ilkesi, bu bağlamlarda ve uygulamanın kaynak kodunda geçerlidir. Manuel test yavaştır, hataya açıktır ve tekrarlanması zordur, bu nedenle mümkünse otomatik test paketleri kullanılmalıdır. Yazılımı entegre etmek, manuel olarak yapıldığında zaman alıcı ve hataya açık olabilir, bu nedenle bir oluşturma işlemi, ideal olarak her check-in ile mümkün olduğunca sık çalıştırılmalıdır. Otomatikleştirilebilen zahmetli manuel süreçler nerede olursa olsun, bunlar otomatikleştirilmeli ve standartlaştırılmalıdır. Amaç, görevi tamamlamanın tek bir yolu olduğundan ve mümkün olduğu kadar acısız olduğundan emin olmaktır.

Mantıkta tekrar, soyutlamayı gerektirir.
---

Mantıkta tekrar birçok biçim alabilir. Kopyala-yapıştır *if-then* veya *switch-case* mantığı, tespit edilmesi ve düzeltilmesi en kolay olanlardan biridir. Birçok tasarım deseni, bir uygulama içinde mantıkta tekrarlamayı azaltmak veya ortadan kaldırmak gibi açık bir amaca sahiptir. Bir nesne, kullanılmadan önce tipik olarak birkaç şeyin olmasını gerektiriyorsa, bu bir Abstract Factory veya Factory Yöntemi ile gerçekleştirilebilir. Bir nesnenin davranışında birçok olası varyasyon varsa, bu davranışlar büyük *if-then* yapıları yerine Strategy kalıbı kullanılarak enjekte edilebilir. Aslında, tasarım kalıplarının formülasyonu, ortak sorunları çözmek ve bu çözümleri tartışmak için gereken çabanın tekrarını azaltma girişimidir. Ek olarak, veritabanı şeması gibi yapılara DRY uygulanarak normalizasyon sağlanır.

Prensip meselesi
---

Diğer yazılım ilkeleri de DRY ile ilgilidir. Yalnızca kodun işlevsel davranışı için geçerli olan Bir Kez ve Yalnızca Bir Kez ilkesi, DRY'nin bir alt kümesi olarak düşünülebilir. "Yazılım varlıklarının genişletilmeye açık, ancak değiştirilmeye kapalı olması gerektiğini" belirten Açık/Kapalı(Open/Closed) İlkesi, pratikte yalnızca DRY'ye uyulduğunda çalışır. Benzer şekilde, iyi bilinen Tek Sorumluluk(Single Responsibility) İlkesi, bir sınıfın "değişmek için tek bir nedeni" olmasını gerektirir, DRY'ye dayanır.

Yapı, mantık, süreç ve işlev açısından izlendiğinde, DRY ilkesi yazılım geliştiricilere temel rehberlik sağlar ve daha basit, daha sürdürülebilir, daha yüksek kaliteli uygulamaların oluşturulmasına yardımcı olur. Performansı veya diğer gereksinimleri karşılamak için tekrarlamanın gerekli olabileceği senaryolar olsa da (örneğin, bir veritabanında veri denormalizasyonu), yalnızca hayali bir sorundan ziyade gerçek bir sorunu doğrudan ele aldığı durumlarda kullanılmalıdır.

[Steve Smith](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Smith) Tarafından