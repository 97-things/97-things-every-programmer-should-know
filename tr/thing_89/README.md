# Doğru Algoritmayı ve Veri Yapısını Kullanın

> Çok sayıda şubesi olan büyük bir banka, veznedarlar için aldığı yeni bilgisayarların çok yavaş olduğundan şikayet etti. Bu, herkesin elektronik bankacılık kullandığı ve ATM'lerin şimdiki kadar yaygın olmadığı zamanlardaydı. İnsanlar bankayı çok daha sık ziyaret ediyorlardı ve yavaş bilgisayarlar insanları sıraya sokuyordu. Sonuç olarak, banka satıcıyla olan sözleşmesini bozmakla tehdit etti.

> Satıcı, gecikmelerin nedenini belirlemek için bir performans analizi ve ayar uzmanı gönderdi. Kısa süre sonra, terminalde çalışan ve neredeyse tüm CPU kapasitesini tüketen belirli bir program buldu. Bir profil oluşturma aracı kullanarak programı yakınlaştırdı ve suçlu olan işlevi görebildi. Kaynak kodu okuyun:

> ```
> for (i=0; i<strlen(s); ++i) {
>   if (... s[i] ...) ...
> }
> ```

> Ve string s ortalama olarak binlerce karakter uzunluğundaydı. (Banka tarafından yazılan) kod çabucak değiştirildi ve banka veznedarları sonsuza dek mutlu yaşadılar....

Programcının gereksiz yere ikinci dereceden ölçeklenen kodu kullanmaktan daha iyisini yapması gerekmez miydi?
strlen'e yapılan her çağrı, sonlandırıcı boş karakterini bulmak için dizgedeki binlerce karakterin her birini geçti. Ancak dizi hiç değişmedi. Programcı, uzunluğunu önceden belirleyerek, strlen'e binlerce çağrıyı (ve milyonlarca döngü yürütmesini) kaydedebilirdi:

```
n=strlen(s);
for (i=0; i<n; ++i) {
  if (... s[i] ...) ...
}
```

Herkes, mikro optimizasyonun tuzaklarından kaçınmak için "önce çalıştır, sonra hızlı çalıştır" atasözünü bilir. Ancak yukarıdaki örnek, programcının Machiavellian adagio'yu takip ettiğine neredeyse inandırırdı "önce yavaş çalışmasını sağlayın".

Bu düşüncesizlik, bir kereden fazla karşılaşabileceğiniz bir şey. Ve bu sadece "tekerleği yeniden icat etme" meselesi değil. Bazen acemi programcılar gerçekten düşünmeden yazmaya başlarlar ve aniden balon sıralamayı 'icat ederler'. Hatta bununla övünüyor olabilirler.

Doğru algoritmayı seçmenin diğer tarafı veri yapısı seçimidir. Büyük bir fark yaratabilir: Bir karma veri yapısı veya ikili bir ağaç ile karşılaştırıldığında, aramak istediğiniz bir milyon öğeden oluşan bir koleksiyon için bağlantılı bir liste kullanmak, kullanıcının programınızı takdir etmesi üzerinde büyük bir etkiye sahip olacaktır.

Programcılar tekerleği yeniden icat etmemeli ve mümkünse mevcut kitaplıkları kullanmalıdır. Ancak bankanınki gibi sorunlardan kaçınmak için algoritmalar ve nasıl ölçeklendikleri konusunda da eğitilmeleri gerekir. Onları 1980'lerdeki WordStar gibi eski tarz programlar kadar yavaş yapan şey, modern metin editörlerindeki göz kamaştırıcı şeyler mi? Birçoğu programlamada yeniden kullanımın çok önemli olduğunu söylüyor. Ancak hepsinden önemlisi, programcılar ne zaman, neyi ve nasıl yeniden kullanacaklarını bilmelidir. Bunu yapabilmek için problem alanı, algoritmalar ve veri yapıları hakkında bilgi sahibi olmaları gerekir.

İyi bir programcı, iğrenç bir algoritmayı ne zaman kullanacağını da bilmelidir. Örneğin, problem alanı asla beşten fazla öğe olamayacağını söylüyorsa (bir Yahtzee oyunundaki zar sayısı gibi), *her zaman* en fazla beş öğeyi sıralamanız gerektiğini bilirsiniz. Bu durumda, bubble sıralama aslında öğeleri sıralamanın en etkili yolu olabilir. Her şeyin bir zamanı vardır.

Bu nedenle, bazı iyi kitaplar okuyun ve onları anladığınızdan emin olun. Ve eğer Donald Knuth'un *Bilgisayar Programlama Sanatı* kitabını gerçekten iyi okuduysanız, şanslı bile olabilirsiniz: Yazarın bir hatasını bulun ve Don Knuth'un onaltılık dolar (2,56$) çeklerinden birini kazanın.

[JC van Winkel](http://programmer.97things.oreilly.com/wiki/index.php/JC_van_Winkel) Tarafından