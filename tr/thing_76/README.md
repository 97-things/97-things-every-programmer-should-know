# Tek Sorumluluk İlkesi(The Single Responsibility)

İyi tasarımın en temel ilkelerinden biri:

> Aynı nedenle değişenleri bir araya toplayın ve farklı nedenlerle değişenleri ayırın.

Bu ilke genellikle *Tek Sorumluluk İlkesi* veya SRP olarak bilinir. Kısacası, bir alt sistemin, modülün, sınıfın ve hatta bir fonksiyonun değişmesi için birden fazla nedeni olmaması gerektiğini söylüyor. Klasik örnek, iş kuralları, raporlar ve veritabanıyla ilgilenen yöntemlere sahip bir sınıftır:

```
public class Employee {
  public Money calculatePay() ...
  public String reportHours() ...
  public void save() ...
}
```

Bazı programcılar, bu üç işlevi aynı sınıfta bir araya getirmenin tamamen uygun olduğunu düşünebilir. Sonuçta, sınıfların ortak değişkenler üzerinde çalışan fonksiyonların koleksiyonları olması gerekiyordu. Ancak sorun, üç işlevin tamamen farklı nedenlerle değişmesidir. `calculatePay` işlevi, ödeme değişikliğini hesaplamak için iş kuralları her değiştiğinde değişecektir. Birisi rapor için farklı bir format istediğinde `reportHours` işlevi değişecektir. DBA'lar veritabanı şemasını her değiştirdiğinde kaydetme işlevi değişecektir. Değişimin bu üç nedeni, `Employee`i çok değişken hale getirmek için birleşir. Bu nedenlerden herhangi biri için değişecektir. Daha da önemlisi, `Employee`ye bağlı tüm sınıflar bu değişikliklerden etkilenecektir.

İyi sistem tasarımı, sistemi bağımsız olarak dağıtılabilen bileşenlere ayırmamız anlamına gelir. Bağımsız dağıtım, bir bileşeni değiştirirsek diğerlerini yeniden dağıtmamız gerekmediği anlamına gelir. Ancak, `Employee` diğer bileşenlerdeki diğer birçok sınıf tarafından yoğun bir şekilde kullanılıyorsa, o zaman `Employee`de yapılan her değişikliğin diğer bileşenlerin yeniden konuşlandırılmasına neden olması muhtemeldir; böylece bileşen tasarımının (veya daha popüler bir adı tercih ederseniz SOA) büyük bir faydasını reddeder.

```
public class Employee {
  public Money calculatePay() ...
}

public class EmployeeReporter {
  public String reportHours(Employee e) ...
}

public class EmployeeRepository {
  public void save(Employee e) ...
}
```

Yukarıda gösterilen basit bölümleme, sorunları çözer. Bu sınıfların her biri kendi bileşenine yerleştirilebilir. Daha doğrusu, tüm raporlama sınıfları raporlama bileşenine girebilir. Veritabanıyla ilgili tüm sınıflar depo bileşenine girebilir. Ve tüm iş kuralları, iş kuralı bileşenine girebilir.

Zeki okuyucu, yukarıdaki çözümde hala bağımlılıklar olduğunu görecektir. Bu `Employee` hala diğer sınıflar tarafından bağımlıdır. Dolayısıyla, `Employee` değiştirilirse, diğer sınıfların büyük olasılıkla yeniden derlenmesi ve yeniden konuşlandırılması gerekecektir. Bu nedenle, `Employee` değiştirilemez ve ardından bağımsız olarak konuşlandırılamaz. Ancak, diğer sınıflar değiştirilebilir ve bağımsız olarak dağıtılabilir. Bunlardan birinde yapılacak hiçbir değişiklik, diğerlerini yeniden derlenmeye veya yeniden dağıtılmaya zorlayamaz. `Employee` bile *Bağımlılığı Tersine Çevirme İlkesi(Dependency Inversion Principle)* (DIP) dikkatli bir şekilde kullanılarak bağımsız olarak konuşlandırılabilir, ancak bu [farklı bir kitabın](http://www.amazon.com/dp/0135974445/) konusu.

Farklı nedenlerle değişen şeyleri ayıran SRP'nin dikkatli bir şekilde uygulanması, bağımsız olarak konuşlandırılabilir bir bileşen yapısına sahip tasarımlar oluşturmanın anahtarlarından biridir.

[Uncle Bob](http://programmer.97things.oreilly.com/wiki/index.php/Uncle_Bob) Tarafından