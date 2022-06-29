# Sınırlarınızı Bilin

> *"İnsan sınırlarını bilmeli." — Dirty Harry*

Kaynaklarınız sınırlı. Bilginizi, becerilerinizi ve araçlarınızı güncel tutmak için gereken zaman ve para dahil, işinizi yapmak için yalnızca çok fazla zamanınız ve paranız var. Sadece çok sıkı, çok hızlı, çok akıllı ve çok uzun süre çalışabilirsin. Araçlarınız sadece çok güçlü. Hedef makineleriniz sadece çok güçlü. Bu yüzden kaynaklarınızın sınırlarına saygı göstermelisiniz.

Bu sınırlara nasıl saygı duyulur? Kendinizi tanıyın, çalışanlarınızı tanıyın, bütçelerinizi bilin ve eşyalarınızı bilin. Özellikle bir yazılım mühendisi olarak, veri yapılarınızın ve algoritmalarınızın uzay ve zaman karmaşıklığını, sistemlerinizin mimarisini ve performans özelliklerini bilin. İşiniz, yazılım ve sistemlerin optimal bir evliliğini yaratmaktır.

Uzay ve zaman karmaşıklığı, *O(f(n))* işlevi olarak verilir; bu, n için girdinin boyutuna eşit, asimptotik uzay veya n sonsuza kadar büyürken gereken zamandır. *f(n)* için önemli karmaşıklık sınıfları arasında *ln(n)*, *n*, *n ln(n)*, *n<sup>e</sup>* ve *e<sup>n< bulunur /sup>*. Bu fonksiyonların grafiğinin açıkça gösterdiği gibi, *n* büyüdükçe *O(ln(n))*, *O(n)* ve *O(n ln(n))*'den çok daha küçüktür, ki bunlar hep böyledir *O(n<sup>e</sup>)* ve *O(e<sup>n</sup>)*'dan çok daha küçüktür. Sean Parent'in belirttiği gibi, ulaşılabilir n için tüm karmaşıklık sınıfları sabite yakın, doğrusala yakın veya sonsuza yakındır.

![](http://programmer.97things.oreilly.com/wiki/images/c/c0/Clearly.jpeg)

|              | access time      |   capacity |
|--------------|-----------------:| ----------:|
| register     |  < 1 ns          |        64b |
| cache line   |                  |        64B |
| L1 cache     |  1 ns            | 64 KB      |
| L2 cache     |  4 ns            | 8 MB       |
| RAM          | 20 ns            | 32 GB      |
| disk         | 10 ms            | 10 TB      |
| LAN          | 20 ms            | > 1 PB     |
| internet     | 100 ms           | > 1 ZB     |

Karmaşıklık analizi, soyut bir makine açısından yapılır, ancak yazılım gerçek makinelerde çalışır. Modern bilgisayar sistemleri, dil çalışma zamanları, işletim sistemleri, CPU'lar, önbellek belleği, rastgele erişimli bellek, disk sürücüleri ve ağlar dahil olmak üzere fiziksel ve sanal makinelerin hiyerarşileri olarak düzenlenir. İlk tablo, tipik bir ağ bağlantılı sunucu için rasgele erişim süresi ve depolama kapasitesi üzerindeki sınırları gösterir.

Kapasite ve hızın birkaç büyüklük derecesine göre değiştiğini unutmayın. Önbelleğe alma ve ileriye dönük, bu varyasyonu gizlemek için sistemlerimizin her düzeyinde yoğun olarak kullanılır, ancak bunlar yalnızca erişim öngörülebilir olduğunda çalışır. Önbellek kayıpları sık olduğunda sistem çöker. Örneğin, bir sabit sürücüdeki her baytı rastgele incelemek 32 yıl sürebilir. RAM'deki her baytı rastgele incelemek bile 11 dakika sürebilir. Rastgele erişim tahmin edilemez. Nedir? Bu, sisteme bağlıdır, ancak son kullanılan öğelere yeniden erişmek ve öğelere sırayla erişmek genellikle bir kazançtır.

Algoritmalar ve veri yapıları, önbellekleri ne kadar etkili kullandıklarına göre değişir. Örneğin:
- Doğrusal arama, ileriye bakmayı iyi bir şekilde kullanır, ancak *O(n)* karşılaştırmaları gerektirir.
- Sıralanmış bir dizinin ikili araması yalnızca *O(log(n))* karşılaştırmalarını gerektirir.
- Bir van Emde Boas ağacının aranması *O(log(n))* ve önbellekten habersiz.


|Elements | Search time (ns)|       |         |
|:--------|-----------:|-----------:|--------:|
|         | **linear** | **binary** |	**vEB** |
| 8       | 50         | 90         | 40      |
| 64      | 180        | 150        | 70      |
| 512     | 1200       | 230        | 100     |
| 4096    | 17000      | 320        | 160     |


Nasıl seçilir? Son tahlilde, ölçerek. İkinci tablo, bu üç yöntemle 64 bit tamsayı dizilerini aramak için gereken süreyi gösterir. Bilgisayarımda:
- Doğrusal arama, küçük diziler için rekabetçidir, ancak daha büyük diziler için katlanarak kaybeder.
- Van Emde Boas, tahmin edilebilir erişim modeli sayesinde kesinlikle kazanıyor.

> *"Paranı ödüyorsun ve seçimini yapıyorsun." — [Punch](http://www.nytimes.com/1988/02/28/magazine/on-language-you-pays-yer-money.html?pagewanted=all)*

[Greg Colvin](http://programmer.97things.oreilly.com/wiki/index.php/Greg_Colvin) Tarafından
