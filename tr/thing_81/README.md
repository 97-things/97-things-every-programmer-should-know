# Kesin ve Somut Test Edin

Belirli bir uygulamanın tesadüfi davranışını test etmek yerine, bir kod biriminin istenen, temel davranışını test etmek önemlidir. Ancak bu, belirsiz testler için bir bahane olarak alınmamalı veya yanlış anlaşılmamalıdır. Testlerin doğru *ve* kesin olması gerekir.

Denenmiş, test edilmiş ve test edilmiş klasik sıralama rutinlerinden bir şey açıklayıcı bir örnek sunar. Sıralama algoritması uygulamak, bir programcı için mutlaka günlük bir görev değildir, ancak sıralama o kadar tanıdık bir fikirdir ki, çoğu insan ondan ne bekleyeceğini bildiğine inanır. Ancak bu sıradan aşinalık, geçmiş belirli varsayımları görmeyi zorlaştırabilir.

Programcılara "Neyi test edersiniz?" diye sorulduğunda açık ara en yaygın yanıt "Sıralamanın sonucu, sıralanmış bir öğe dizisidir." Bu doğru olsa da, gerçeğin tamamı bu değildir. Daha kesin bir koşul istendiğinde, birçok programcı, ortaya çıkan dizinin orijinaliyle aynı uzunlukta olması gerektiğini ekler. Doğru olmasına rağmen, bu hala yeterli değil. Örneğin, aşağıdaki sıra verilir:

```
3 1 4 1 5 9
```

Aşağıdaki dizi, azalan düzende sıralanmama ve orijinal diziyle aynı uzunluğa sahip olma son koşulunu karşılar:

```
3 3 3 3 3 3
```

Spesifikasyonu karşılasa da, kastedilen kesinlikle bu değil! Bu örnek, gerçek üretim kodundan alınan bir hataya dayanmaktadır (neyse ki yayınlanmadan önce yakalanmıştır), burada verilen dizi basit bir tuş vuruşu kayması veya anlık bir mantık hatası, tüm sonucun ilk öğeyle doldurulması için ayrıntılı bir mekanizmaya yol açmıştır.

Tam son koşul, sonucun sıralanması ve orijinal değerlerin bir permütasyonuna sahip olmasıdır. Bu, gerekli davranışı uygun şekilde kısıtlar. Sonuç uzunluğunun, yıkamada çıkan giriş uzunluğu ile aynı olması ve yeniden ayarlanmasına gerek olmaması.

Son koşulu tarif edilen şekilde belirtmek bile size iyi bir test vermek için yeterli değildir. İyi bir test okunabilir olmalıdır. Doğru (ya da değil) olduğunu kolayca görebileceğiniz kadar anlaşılır ve basit olmalıdır. Bir dizinin sıralandığını ve bir dizinin diğerinde bir değer permütasyonu içerdiğini kontrol etmek için halihazırda bir kodunuz yoksa, test kodunun test edilen koddan daha karmaşık olması muhtemeldir. Tony Hoare'nin gözlemlediği gibi:

> Bir yazılım tasarımı oluşturmanın iki yolu vardır: Bir yol, onu *açıkça* hiçbir eksiklik olmayacak kadar basit hale getirmek, diğeri ise onu bariz eksiklikler olmayacak kadar karmaşık hale getirmektir.

Somut örnekler kullanmak, bu tesadüfi karmaşıklığı ve kaza olasılığını ortadan kaldırır. Örneğin, aşağıdaki sıra verilir:

```
3 1 4 1 5 9
```

Sıralamanın sonucu aşağıdaki gibidir:

```
1 1 3 4 5 9
```

Başka hiçbir cevap işe yaramayacak. Yedek kabul etmeyin.

Somut örnekler, genel davranışı erişilebilir ve açık bir şekilde göstermeye yardımcı olur. Boş bir koleksiyona öğe eklemenin sonucu, yalnızca boş olmaması değildir: Koleksiyonun artık tek bir öğeye sahip olmasıdır. Ve tutulan tek öğe, eklenen öğedir. İki veya daha fazla öğe boş değil olarak nitelendirilir. Ve ayrıca yanlış olurdu. Farklı bir değere sahip tek bir öğe de yanlış olur. Bir tabloya bir satır eklemenin sonucu sadece tablonun bir satır daha büyük olması değildir. Ayrıca, eklenen satırı kurtarmak için satırın anahtarının kullanılabileceğini de gerektirir. Ve benzeri.

Davranışı belirlerken testler basitçe doğru olmamalıdır: Ayrıca kesin olmalıdırlar.

[Kevlin Henney](http://programmer.97things.oreilly.com/wiki/index.php/Kevlin_Henney) Tarafından