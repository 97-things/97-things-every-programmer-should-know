# WET Performans Darboğazlarını Azaltıyor

DRY ilkesinin (Don't Repeat Yourself - Kendini Tekrar Etme) önemi, bir sistemdeki her bilgi parçasının tekil bir temsile sahip olması gerektiği fikrini kodlamasıdır. Başka bir deyişle, bilgi tek bir uygulamada yer almalıdır. DRY'nin antitezi WET'tir (Write Every Time - Her Zaman Yaz). Bilgi birkaç farklı uygulamada kodlandığında kodumuz WET olur. Bir performans profili üzerindeki sayısız etkilerini göz önünde bulundurduğunuzda, DRY ve WET'in performans etkileri çok netleşir.

Sistemimizin bir özelliğini, örneğin *X*, yani CPU darboğazını ele alarak başlayalım. Diyelim ki *X* özelliği CPU'nun %30'unu tüketiyor. Diyelim ki *X* özelliğinin on farklı uygulaması var. Ortalama olarak, her uygulama CPU'nun %3'ünü tüketecektir. Hızlı bir kazanç arıyorsak bu CPU kullanımı seviyesi endişelenmeye değmeyeceğinden, bu özelliğin bizim darboğazımız olduğunu gözden kaçırmamız muhtemeldir. Ancak, bir şekilde *X* özelliğini bir darboğaz olarak gördüğümüzü varsayalım. Artık her bir uygulamayı bulma ve düzeltme sorunuyla karşı karşıyayız. WET ile bulmamız ve düzeltmemiz gereken on farklı uygulamamız var. DRY ile %30 CPU kullanımını açıkça görürdük ve kodun onda birini düzeltmemiz gerekirdi. Ve her uygulamayı aramak için zaman harcamak zorunda olmadığımızdan bahsetmiş miydim?

Genellikle DRY'yi ihlal etmekten suçlu olduğumuz bir kullanım durumu vardır: koleksiyon kullanımımız. Bir sorguyu uygulamak için yaygın bir teknik, koleksiyon üzerinde yineleme yapmak ve ardından sorguyu sırayla her bir öğeye uygulamaktır:

```
public class UsageExample {
    private ArrayList<Customer> allCustomers = new ArrayList<Customer>();
    // ...
    public ArrayList<Customer> findCustomersThatSpendAtLeast(Money amount) {
        ArrayList<Customer> customersOfInterest = new ArrayList<Customer>();
        for (Customer customer: allCustomers) {
            if (customer.spendsAtLeast(amount))
               customersOfInterest.add(customer);
        }
        return customersOfInterest;
    }
}
```

Bu ham koleksiyonu client'lara göstererek, kapsüllemeyi ihlal ettik. Bu, yalnızca yeniden düzenleme yeteneğimizi sınırlamakla kalmaz, kodumuzu kullananların her birinin potansiyel olarak aynı sorguyu yeniden uygulamasını sağlayarak DRY'yi ihlal etmeye zorlar. Bu durum, açıkta kalan ham koleksiyonları API'den kaldırarak kolayca önlenebilir. Bu örnekte, `CustomerList` adlı yeni, alana özgü bir toplu tür tanıtabiliriz. Bu yeni sınıf, alanımızla daha semantik olarak uyumludur. Tüm sorularımız için doğal bir yuva görevi görecek.

Bu yeni koleksiyon türüne sahip olmak, bu sorguların performans darboğazı olup olmadığını kolayca görmemizi sağlayacaktır. Sorguları sınıfa dahil ederek, `ArrayList` gibi temsil seçeneklerini müşterilerimize gösterme ihtiyacını ortadan kaldırıyoruz. Bu bize, client sözleşmelerini ihlal etme korkusu olmadan bu uygulamaları değiştirme özgürlüğü verir:

```
public class CustomerList {
    private ArrayList<Customer> customers = new ArrayList<Customer>();
    private SortedList<Customer> customersSortedBySpendingLevel = new SortedList<Customer>();
    // ...
    public CustomerList findCustomersThatSpendAtLeast(Money amount) {
        return new CustomerList(customersSortedBySpendingLevel.elementsLargerThan(amount));
    }
}

public class UsageExample {
    public static void main(String[] args) {
        CustomerList customers = new CustomerList();
        // ...
        CustomerList customersOfInterest = customers.findCustomersThatSpendAtLeast(someMinimalAmount);
        // ...
    }
}
```   

Bu örnekte, DRY'ye bağlılık, client'larımıızın harcama düzeyine göre ayarlanmış SortedList ile alternatif bir indeksleme şeması sunmamıza izin verdi. Bu özel örneğin belirli ayrıntılarından daha önemli olan, DRY'yi takip etmek, kodun WET olması durumunda bulunması daha zor olacak bir performans darboğazı bulmamıza ve onarmamıza yardımcı oldu.

[Kirk Pepperdine](http://programmer.97things.oreilly.com/wiki/index.php/Kirk_Pepperdine) Tarafından