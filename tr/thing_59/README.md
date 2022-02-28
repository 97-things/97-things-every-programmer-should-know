# Polimorfizm için Kaçırılan Fırsatlar

Polimorfizm, OO(Object Oriented) için temel olan büyük fikirlerden biridir. Yunancadan gelen sözcük, birçok (*poli*) biçim (*morf*) anlamına gelir. Programlama polimorfizmi bağlamında, belirli bir nesne veya yöntem sınıfının birçok biçimine atıfta bulunur. Ancak polimorfizm sadece alternatif uygulamalarla ilgili değildir. Dikkatli kullanıldığında, polimorfizm, ayrıntılı *if-then-else* bloklarına ihtiyaç duymadan çalışmamıza izin veren küçük yerelleştirilmiş yürütme bağlamları oluşturur. Bir bağlamda olmak, doğru şeyi doğrudan yapmamızı sağlarken, o bağlamın dışında olmak bizi onu yeniden inşa etmeye zorlar, böylece doğru şeyi yapabiliriz. Alternatif uygulamaların dikkatli kullanımıyla, daha okunaklı daha az kod üretmemize yardımcı olabilecek bağlamı yakalayabiliriz. Bu, aşağıdaki (gerçekçi olmayan) basit alışveriş sepeti gibi bazı kodlarla en iyi şekilde gösterilir:

```
public class ShoppingCart {
    private ArrayList<Item> cart = new ArrayList<Item>();
    public void add(Item item) { cart.add(item); }
    public Item takeNext() { return cart.remove(0);  }
    public boolean isEmpty() { return cart.isEmpty(); }
}
```

Diyelim ki web mağazamız indirilebilecek ürünler ve gönderilmesi gereken ürünler sunuyor. Bu işlemleri destekleyen başka bir nesne oluşturalım:

```
public class Shipping {
    public boolean ship(Item item, SurfaceAddress address) { ... }
    public boolean ship(Item item, EMailAddress address) { ... }
}
```

Bir müşteri ödemeyi tamamladığında malları göndermemiz gerekir:

```
while (!cart.isEmpty()) {
    shipping.ship(cart.takeNext(), ???);
}
```

*???* parametresi yeni bir fantezi elvis operatörü değil, öğeyi e-postayla mı göndermeliyim yoksa salyangozla postalamalı mıyım? Bu soruyu cevaplamak için gereken bağlam artık mevcut değil. Sevkiyat yöntemini bir boolean veya enumda yakalayabilir ve ardından eksik parametreyi doldurmak için bir *if-then-else* kullanabilirdik. Başka bir çözüm, her ikisi de Öğeyi genişleten iki sınıf oluşturmak olacaktır. Bunları DownloadableItem ve SurfaceItem olarak adlandıralım. Şimdi biraz kod yazalım. Öğeyi tek bir yöntemi destekleyen bir arayüz olarak tanıtacağım, ship. Sepetin içeriğini göndermek için 'item.ship(shipper)' adını vereceğiz. "DownloadableItem" ve "SurfaceItem" sınıflarının her ikisi de ship'i uygulayacaktır.

```
public class DownloadableItem implements Item {
    public boolean ship(Shipping shipper) {
        shipper.ship(this, customer.getEmailAddress());
    }
}

public class SurfaceItem implements Item {
    public boolean ship(Shipping shipper) {
        shipper.ship(this, customer.getSurfaceAddress());
    }
}
```

Bu örnekte, `Shipping` ile çalışma sorumluluğunu her bir Öğeye devrettik. Her ürün, en iyi nasıl gönderileceğini bildiğinden, bu düzenleme, bir *if-then-else*'e ihtiyaç duymadan ürünle devam etmemizi sağlar. Kod ayrıca, genellikle birlikte iyi çalışan iki kalıbın kullanımını da gösterir: Komut ve Çift Gönderim. Bu kalıpların etkin kullanımı, polimorfizmin dikkatli kullanımına bağlıdır. Bu olduğunda, kodumuzdaki *if-then-else* bloklarının sayısında bir azalma olacaktır.

Polimorfizm yerine *if-then-else* kullanmanın çok daha pratik olduğu durumlar olsa da, daha çok polimorfik bir kodlama stilinin daha küçük, daha okunabilir ve daha az kırılgan bir kod tabanı sağlaması daha sık görülür. Kaçırılan fırsatların sayısı, kodumuzdaki *if-then-else* ifadelerinin basit bir sayımıdır.

[Kirk Pepperdine](http://programmer.97things.oreilly.com/wiki/index.php/Kirk_Pepperdine) Tarafından
