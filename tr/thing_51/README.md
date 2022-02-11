# "Merhaba Dünya" Demeyi Öğrenin

Daha yaygın olarak Hoppy olarak bilinen kullanıcı adı leep olan Paul Lee, programlama konularında yerel uzman olarak ün yapmıştır. Yardıma ihtiyacım vardı. Hoppy'nin masasına doğru yürüdüm ve benim için bir koda bakabilir mi? diye sordum.

Tabii, dedi Hoppy, bir sandalye çek. Arkasında piramit şeklinde yığılmış boş kola kutularını devirmemeye özen gösterdim.

Ne kodu?

Bir dosyadaki bir fonksiyonda, dedim.

Öyleyse bu fonksiyona bir göz atalım. Hoppy K&R'ın bir kopyasını kenara çekti ve klavyesini önüme kaydırdı.

IDE nerede? Görünüşe göre Hoppy'nin çalışan IDE'si yoktu, sadece çalıştıramadığım bir editör. Klavyeyi geri aldı. Birkaç tuşa bastıktan sonra dosyayı açtık, oldukça büyük bir dosyaydı ve işleve bakıyorduk, oldukça büyük bir işlevdi. Sormak istediğim koşullu bloğa çağrı yaptı.

'x' negatifse bu cümle gerçekte ne yapar? diye sordum. Elbette yanlış.

Bütün sabah "x"i negatif olmaya zorlamanın bir yolunu bulmaya çalışıyordum, ancak büyük dosyadaki büyük işlev büyük bir projenin parçasıydı ve deneylerimi yeniden derleme *sonra* yeniden çalıştırma döngüsü beni yıpratıyordu. Hoppy gibi bir uzman bana cevabı söyleyemez mi?

Hoppy emin olmadığını itiraf etti. Sürprizime göre, K&R'ye ulaşmadı. Bunun yerine, kod bloğunu yeni bir düzenleyici arabelleğine kopyaladı, yeniden girinti yaptı, bir işleve sardı. Kısa bir süre sonra, sonsuza kadar döngüye giren, kullanıcıdan giriş değerlerini isteyen, bunları işleve ileten ve sonucu yazdıran bir ana işlevi kodlamıştı. Tamponu yeni bir dosya olarak, tryit.c olarak kaydetti. Bütün bunları kendim için yapabilirdim, belki de o kadar çabuk olmasa da. Ancak bir sonraki adımı son derece basitti ve o zamanlar benim çalışma şeklime oldukça yabancıydı:

```
$ cc tryit.c && ./a.out
```

Bakmak! Sadece birkaç dakika önce tasarlanan asıl programı şimdi çalışır durumdaydı. Birkaç değer denedik ve şüphelerimi doğruladık (yani bir konuda haklıydım!) ve ardından K&R'nin ilgili bölümünü kontrol etti. Hoppy'ye teşekkür ettim ve yine kola piramidini bozmamaya özen göstererek ayrıldım.

Kendi masama döndüğümde IDE'mi kapattım. Büyük bir ürün içinde büyük bir proje üzerinde çalışmaya o kadar alışmıştım ki, yapmam gerekenin bu olduğunu düşünmeye başlamıştım. Genel amaçlı bir bilgisayar da küçük işler yapabilir. Bir metin düzenleyici açtım ve yazmaya başladım.

```
#include <stdio.h>

int main()
{
    printf("Hello, World\n");
    return 0;
}
```

[Thomas Guest](http://programmer.97things.oreilly.com/wiki/index.php/Thomas_Guest) Tarafından