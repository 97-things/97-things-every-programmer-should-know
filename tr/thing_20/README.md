# Erken ve Sıkça Dağıtın

Dağıtım ve kurulum süreçlerinde hata ayıklama, genellikle bir projenin sonuna kadar ertelenir. Bazı projelerde, kurulum araçları yazmak, görevi "gerekli bir kötülük" olarak üstlenen bir yayın mühendisine devredilir. Her şeyin çalıştığından emin olmak için el yapımı bir ortamda incelemeler ve gösteriler yapılır. Sonuç olarak ekip, değişiklik yapmak için çok geç olana kadar dağıtım süreci veya dağıtılan ortamla ilgili hiçbir deneyim elde edemez.

Kurulum/dağıtım süreci, müşterinin gördüğü ilk şeydir ve basit bir kurulum/dağıtım süreci, güvenilir (veya en azından hata ayıklaması kolay) bir üretim ortamına sahip olmanın ilk adımıdır. Dağıtılan yazılım, müşterinin kullanacağı şeydir. Dağıtımın uygulamayı doğru bir şekilde kurmasını sağlamazsanız, müşteriniz yazılımınızı tam olarak kullanmaya başlamadan önce onlara sorular yönelteceksiniz.

Projenize bir kurulum süreci ile başlamak, siz ürün geliştirme döngüsü boyunca ilerlerken süreci geliştirmeniz için size zaman ve kurulumu kolaylaştırmak için uygulama kodunda değişiklik yapma şansı verecektir. Kurulum sürecini düzenli aralıklarla temiz bir ortamda çalıştırmak ve test etmek, geliştirme veya test ortamlarına dayanan kodda varsayımlarda bulunmadığınızı da kontrol eder.

Dağıtımı en sona koymak, koddaki varsayımları çözmek için dağıtım sürecinin daha karmaşık olması gerekebileceği anlamına gelir. Bir ortam üzerinde tam kontrole sahip olduğunuz bir IDE'de harika bir fikir gibi görünen şey, çok daha karmaşık bir dağıtım süreci sağlayabilir. Tüm takasları bir an önce bilmek daha iyidir.

Bir geliştiricinin dizüstü bilgisayarında çalışan bir uygulama görmekle karşılaştırıldığında, "dağıtabilmenin" erken dönemde çok fazla iş değeri yok gibi görünse de, basit gerçek şu ki, uygulamanızı hedef ortamda gösterene kadar, iş değeri sunmadan önce yapılacak çok iş var. Bir dağıtım sürecini erteleme gerekçeniz bunun önemsiz olmasıysa, düşük maliyetli olduğu için yine de yapın. Çok karmaşıksa veya çok fazla belirsizlik varsa, uygulama koduyla yapacağınızı yapın: ilerledikçe dağıtım sürecini deneyin, değerlendirin ve yeniden düzenleyin.

Kurulum/dağıtım süreci, müşterilerinizin veya profesyonel hizmet ekibinizin üretkenliği için çok önemlidir; bu nedenle, devam ederken bu süreci test ediyor ve yeniden düzenlemelisiniz. Bir proje boyunca kaynak kodunu test eder ve yeniden düzenleriz. Dağıtım daha azını hak etmiyor.

[Steve Berczuk](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Berczuk) Tarafından