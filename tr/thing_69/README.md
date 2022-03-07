# Fareyi Yere Bırakın ve Klavyeden Uzaklaşın

Saatlerdir amansız bir soruna odaklandınız ve görünürde bir çözüm yok. Bacaklarınızı uzatmak veya otomatlara çarpmak için ayağa kalkıyorsunuz ve dönüş yolunda cevap aniden ortaya çıkıyor.

Bu senaryo tanıdık geliyor mu? Neden olduğunu hiç merak ettiniz mi? İşin püf noktası şu ki, kod yazarken beyninizin mantıksal kısmı aktiftir ve yaratıcı taraf kapalıdır. Mantıksal taraf bir mola verene kadar size hiçbir şey sunamaz.

İşte gerçek hayattan bir örnek: Bazı eski kodları temizliyordum ve 'ilginç' bir yöntemle karşılaştım. *ss:dd:ss xx* biçimini kullanarak bir dizenin geçerli bir zaman içerdiğini doğrulamak için tasarlanmıştır; burada *hh* saati, *mm* dakikayı, *ss* saniyeyi ve *xx* bunlardan birini temsil eder *ÖÖ(AM)* veya *ÖS(PM)*.

Yöntem, iki karakteri (saati temsil eden) bir sayıya dönüştürmek ve uygun aralıkta olduğunu doğrulamak için aşağıdaki kodu kullandı:

```
try {
    Integer.parseInt(time.substring(0, 2));
} catch (Exception x) {
    return false;
}

if (Integer.parseInt(time.substring(0, 2)) > 12) {
    return false;
}
```

Dakikaları ve saniyeleri test etmek için karakter ofsetinde ve üst limitte uygun değişikliklerle aynı kod iki kez daha ortaya çıktı. Yöntem, AM ve PM'yi kontrol etmek için şu satırlarla sona erdi:

```
if (!time.substring(9, 11).equals("AM") &
    !time.substring(9, 11).equals("PM")) {
    return false;
}
```

Bu karşılaştırma dizilerinin hiçbiri başarısız olursa, false döndürülürse, yöntem true değerini döndürür.

Yukarıdaki kod endişeli ve takip edilmesi zor görünüyorsa, endişelenmeyin. Ben de öyle düşündüm, bu da temizlemeye değer bir şey bulduğum anlamına geliyordu. Yeniden düzenledim ve hala çalıştığından emin olmak için birkaç birim testi yazdım.

Bitirdiğimde, sonuçlardan memnun hissettim. Orijinal kod saat, dakika ve saniye için yalnızca üst sınırı test ettiğinden, yeni sürümün okunması kolay, yarı boyutunda ve daha doğruydu.

Ertesi gün işe hazırlanırken kafamda bir fikir belirdi: Neden dizeyi normal bir ifade kullanarak doğrulamıyorsunuz? Birkaç dakika yazdıktan sonra, yalnızca bir kod satırında çalışan bir uygulamam oldu. İşte burada:

```
public static boolean validateTime(String time) {
    return time.matches("(0[1-9]|1[0-2]):[0-5][0-9]:[0-5][0-9] ([AP]M)");
}
```

Bu hikayenin amacı, sonunda otuzdan fazla kod satırını tek bir kodla değiştirmiş olmam değil. Mesele şu ki, bilgisayardan uzaklaşana kadar ilk denememin soruna en iyi çözüm olduğunu düşündüm.

Bu yüzden bir daha kötü bir problemle karşılaştığınızda kendinize bir iyilik yapın. Sorunu gerçekten anladığınızda, beyninizin yaratıcı tarafını içeren bir şey yapın - sorunu çizin, biraz müzik dinleyin ya da sadece dışarıda yürüyüşe çıkın. Bazen bir sorunu çözmek için yapabileceğiniz en iyi şey, fareyi bırakıp klavyeden uzaklaşmaktır.

[BurkHufnagel](http://programmer.97things.oreilly.com/wiki/index.php/BurkHufnagel) Tarafından