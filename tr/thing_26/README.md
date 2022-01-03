# Hatayı Görmezden Gelmeyin!

> *Bir akşam barda arkadaşlarla buluşmak için sokakta yürüyordum. Bir süredir bira içmemiştik  ve onları tekrar görmeyi dört gözle bekliyordum. Acele içinde nereye gittiğime bakmıyordum. Bir kaldırımın kenarına takıldım ve yüz üstü kaldım. Eh, sanırım dikkat etmemem de bana hizmet ediyor.*

> *Bacağımı acıttı ama arkadaşlarımla buluşmak için acelem vardı. Bu yüzden kendimi toparladım ve devam ettim. Yürüdükçe ağrım artıyordu. Başta bunu şok olarak görmeme rağmen, bir şeylerin ters gittiğini çabucak fark ettim.*

> *Ama ne olursa olsun bara koştum. Geldiğimde acı içindeydim. Dışarıda harika bir gece geçirmedim çünkü dikkatim çok dağınıktı. Sabah doktora gittim ve kaval kemiğimin kırıldığını öğrendim. Acıyı hissettiğimde durmuş olsaydım, üzerinde yürüdüğüm bir çok ekstra hasarı önlemiş olurdum. Muhtemelen hayatımın en kötü ertesi sabahı.*

Çok fazla yazılımcı benim felaket gecem gibi kod yazıyor.

*Hata, ne hatası? Ciddi olmayacak. Açıkçası. Bunu görmezden gelebilirim.* Bu, katı kod için kazanan bir strateji değildir. Aslında, bu sadece basit tembellik. (Yanlış sıralama.) Kodunuzda bir hata olma ihtimali ne kadar düşük olursa olsun, her zaman onu kontrol etmeli ve her zaman onunla ilgilenmelisiniz. Her zaman. Bunu yapmazsanız zaman kazanmıyorsunuz: Gelecek için olası sorunları biriktiriyorsunuz.

Kodumuzdaki hataları aşağıdakiler dahil olmak üzere çeşitli şekillerde rapor ederiz:

- **Dönüş kodları**, "işe yaramadı" anlamına gelen bir işlevin sonuç değeri olarak kullanılabilir. Hata dönüş kodlarını görmezden gelmek çok kolaydır. Sorunu vurgulamak için kodda hiçbir şey görmezsiniz. Gerçekten de, bazı standart C işlevlerinin dönüş değerlerini yok saymak standart bir uygulama haline geldi. printf'ten dönüş değerini ne sıklıkla kontrol ediyorsunuz?

- **errno** tuhaf bir C sapmasıdır, hatayı bildirmek için ayrı bir global değişkendir. Yok saymak kolaydır, kullanması zordur ve her türlü kötü soruna yol açar - örneğin, aynı işlevi çağıran birden fazla iş parçacığınız olduğunda ne olur? Bazı platformlar sizi burada acıdan yalıtır; diğerleri yapmaz.

- **İstisnalar**, daha yapılandırılmış, dil destekli bir sinyal verme ve hataları işleme yöntemidir. Ve muhtemelen onları görmezden gelemezsiniz. Yoksa yapabilir misin? Bunun gibi birçok kod gördüm:

```
try {
    // ...do something...
}
catch (...) {} // ignore errors
```

Bu korkunç yapının kurtarıcı zarafeti, ahlaki olarak şüpheli bir şey yaptığınız gerçeğini vurgulamasıdır.

Bir hatayı görmezden gelirseniz, görmezden gelir ve hiçbir şey yolunda gitmemiş gibi davranırsanız, büyük riskler alırsınız. Bacağımın üzerinde yürümeyi bıraktığımdan daha kötü bir duruma gelmesi gibi, sürmeye devam etmek de çok karmaşık arızalara yol açabilir. Sorunlarla ilk fırsatta ilgilenin. Kısa bir hesap tutun.

Hataları ele almamak şunlara yol açar:

- **Kırılgan kod.** Heyecan verici, bulunması zor hatalarla dolu kod.
- **Güvensiz kod.** Çatlaklar, yazılım sistemlerine girmek için genellikle zayıf hata işlemeden yararlanır.
- **Kötü yapı.** Kodunuzda sürekli olarak uğraşılması sıkıcı hatalar varsa, muhtemelen kötü bir arayüze sahipsiniz demektir. Hatalar daha az müdahaleci olacak ve bunların ele alınması daha az zahmetli olacak şekilde ifade edin.

Kodunuzdaki tüm olası hataları kontrol etmeniz gerektiği gibi, arayüzlerinizdeki tüm olası hatalı koşulları ortaya çıkarmanız gerekir. Hizmetlerinizin her zaman işe yarayacağını iddia ederek onları saklamayın.

Neden hataları kontrol etmiyoruz? Bir dizi yaygın mazeret var. Bunlardan hangisine katılıyorsunuz? Her birine nasıl karşı koyarsınız?

- Hata işleme, kodun akışını karıştırır, okumayı zorlaştırır ve "normal" yürütme akışını tespit etmeyi zorlaştırır.
- Fazladan bir iş ve yaklaşan bir teslim tarihim var.
- Bu işlev çağrısının *asla* bir hata döndürmeyeceğini biliyorum (printf her zaman çalışır, malloc her zaman yeni bellek döndürür - başarısız olursa daha büyük sorunlarımız olur...).
- Bu sadece bir oyuncak programıdır ve prodüksiyona uygun bir seviyede yazılması gerekmez.

[Pete Goodliffe](http://programmer.97things.oreilly.com/wiki/index.php/Pete_Goodliffe) Tarafından