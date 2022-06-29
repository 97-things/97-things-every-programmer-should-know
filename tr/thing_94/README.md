# Örnekleri Kullanarak Küçük Fonksiyonlar Yazın

Doğru olan bir kod yazmak istiyoruz ve bunun doğru olduğuna dair elimizde kanıt var. Bir fonksiyonun "boyutu" hakkında düşünmek her iki konuda da yardımcı olabilir. Bir işlevi uygulayan kod miktarı anlamında değil bu ilginç olsa da daha çok kodumuzun gösterdiği matematiksel işlevin boyutu anlamında.

Örneğin, Go oyununda *atari* adı verilen ve oyuncunun taşlarının rakibi tarafından ele geçirilebileceği bir koşul vardır: Yanında iki veya daha fazla boş alan bulunan bir taş (*liberties* olarak adlandırılır) ataride değildir. Bir taşın ne kadar özgürlüğe sahip olduğunu saymak zor olabilir, ancak bu biliniyorsa atariyi belirlemek kolaydır. Bunun gibi bir fonksiyon yazarak başlayabiliriz:

```
boolean atari(int libertyCount)
    libertyCount < 2
```

Bu göründüğünden daha büyüktür. Matematiksel bir fonksiyon, bir küme, etki alanı (burada `int`) ve aralık (burada `boolean`) olan kümelerin Kartezyen çarpımının bir alt kümesi olarak anlaşılabilir. Bu değer kümeleri Java'dakiyle aynı boyutta olsaydı, `int×boolean` kümesinde `2L*(Integer.MAX_VALUE+(-1L*Integer.MIN_VALUE)+1L)` veya 8.589.934.592 üye olurdu. Bunların yarısı, işlevimiz olan alt kümenin üyeleridir, bu nedenle işlevimizin doğru olduğuna dair tam kanıt sağlamak için yaklaşık 4,3×10<sup>9</sup> örneği kontrol etmemiz gerekir.

Testlerin hataların yokluğunu kanıtlayamayacağı iddiasının özü budur. Yine de testler, özelliklerin varlığını gösterebilir. Ama yine de bu boyut sorunumuz var.

Sorun alanı bize yardımcı olur. Go'nun doğası, bir taşın özgürlük sayısının herhangi bir int değil, tam olarak {1,2,3,4}'den biri olduğu anlamına gelir. Yani alternatif olarak şunu yazabiliriz:

```
LibertyCount = {1,2,3,4} 
boolean atari(LibertyCount libertyCount)
    libertyCount == 1
```

Bu çok daha izlenebilir: Hesaplanan fonksiyon artık en fazla sekiz üyeden oluşan bir kümedir. Aslında, kontrol edilen dört örnek, işlevin doğru olduğuna dair tam bir kesinlik kanıtı teşkil edecektir. Program yazmak için yerel türler yerine sorun alanıyla yakından ilgili türleri kullanmanın iyi bir fikir olmasının bir nedeni budur. Etki alanından ilham alan türleri kullanmak genellikle işlevlerimizi çok daha küçük hale getirebilir. Bu türlerin ne olması gerektiğini bulmanın bir yolu, işlevi yazmadan önce sorunlu etki alanı terimlerini kontrol etmek için örnekler bulmaktır.

[Keith Braithwaite](http://programmer.97things.oreilly.com/wiki/index.php/Keith_Braithwaite) Tarafından