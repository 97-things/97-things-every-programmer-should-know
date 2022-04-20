# Durumlarda Düşünmek

Gerçek dünyadaki insanların durumla tuhaf bir ilişkisi var. Bu sabah kafeini koda dönüştürmek için başka bir güne hazırlanmak için yerel mağazaya uğradım. Bunu yapmanın en sevdiğim yolu latte içmek olduğundan ve hiç süt bulamadığım için görevliye sordum.

"Üzgünüm, süper kandırıldık, sütüm bitti."

Bir programcı için bu garip bir ifade. Ya sütünüz bitmiştir ya da bitmemiştir. Sütün bitmesi söz konusu olduğunda ölçek yoktur. Belki de bana bir hafta sütlerinin biteceğini söylemeye çalışıyordu ama sonuç benim için aynıydı, espresso günü.

Çoğu gerçek dünya durumunda, insanların duruma karşı rahat tavırları bir sorun değildir. Ne yazık ki, birçok programcı durum konusunda da oldukça belirsizdir ve bu bir problemdir.

Bu yöntemi içeren bir `Order` sınıfıyla, yalnızca kredi kartlarını kabul eden ve müşterilere fatura kesmeyen basit bir web mağazasını düşünün:

```
 public boolean isComplete() {
     return isPaid() && hasShipped();
 }
```

Makul, değil mi? Eh, ifade her yere kopyala yapıştır yerine güzel bir şekilde bir yönteme ayıklansa bile, ifade hiç var olmamalıdır. Gerçek şu ki, bir sorunu vurgular. Niye? Çünkü bir sipariş, ödemesi yapılmadan kargoya verilemez. Bu nedenle, `isPaid` doğru olmadığı sürece `hasShipped` doğru olamaz, bu da ifadenin bir kısmını gereksiz kılar. Yine de kodda netlik için `isComplete` isteyebilirsiniz, ancak o zaman şöyle görünmelidir:

```
 public boolean isComplete() {
     return hasShipped();
 }
```

İşimde her zaman hem eksik hem de gereksiz çek görüyorum. Bu örnek küçük, ancak iptal ve geri ödemeyi eklediğinizde, daha karmaşık hale gelecek ve iyi durum işleme ihtiyacı artar. Bu durumda, bir sipariş yalnızca üç farklı durumdan birinde olabilir:

- *Devam ediyor(In progress):* Öğe ekleyebilir veya kaldırabilir. Gönderilemiyor.
- *Ücretli(Paid):* Öğe eklenemez veya kaldırılamaz. Sevk edilebilir.
- *Gönderildi(Shipped):* Bitti. Daha fazla değişiklik kabul edilmedi.

Bu durumlar önemlidir ve işlem yapmadan önce beklenen durumda olduğunuzu ve bulunduğunuz yerden sadece yasal bir duruma geçtiğinizi kontrol etmeniz gerekir. Kısacası eşyalarınızı dikkatli bir şekilde, doğru yerlerde korumalısınız.

Ama durumlarda düşünmeye nasıl başlarsınız? İfadeleri anlamlı yöntemlere çıkarmak çok iyi bir başlangıç, ancak bu sadece bir başlangıç. Temel, durum makinelerini anlamaktır. CS sınıfından kötü anıların olabileceğini biliyorum ama onları geride bırak. Durum makineleri özellikle zor değildir. Kolay anlaşılır ve konuşulması kolay hale getirmek için onları görselleştirin. Geçerli ve geçersiz durumları ve geçişleri ortaya çıkarmak ve bunları doğru tutmak için kodunuzu test edin. Durum modelini inceleyin. Kendinizi rahat hissettiğinizde, Sözleşmeye Göre Tasarım'ı okuyun. Her genel yöntemin giriş ve çıkışında gelen verileri ve nesnenin kendisini doğrulayarak geçerli bir durum sağlamanıza yardımcı olur.

Durumunuz yanlışsa, bir hata vardır ve iptal etmezseniz verileri çöpe atma riskiniz vardır. Durum kontrollerini parazit olarak bulursanız, bunları gizlemek için bir aracın, kod oluşturmanın, dokumanın veya yönlerin nasıl kullanılacağını öğrenin. Hangi yaklaşımı seçerseniz seçin, durumlar halinde düşünmek kodunuzu daha basit ve daha sağlam hale getirecektir.

[Niclas Nilsson](http://programmer.97things.oreilly.com/wiki/index.php/Niclas_Nilsson) Tarafından