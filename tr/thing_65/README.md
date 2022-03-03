# Domain Alanına Özgü Türleri İlkel Türlere Tercih Edin

23 Eylül 1999'da 327,6 milyon dolarlık Mars Climate Orbiter, Dünya'daki bir yazılım hatası nedeniyle Mars'ın yörüngesine girerken kayboldu. Hata daha sonra *metrik karışıklık* olarak adlandırıldı. Uzay aracı Newton'u beklerken yer istasyonu yazılımı pound cinsinden çalışıyordu ve yer istasyonunun uzay aracının iticilerinin gücünü 4,45 kat hafife almasına yol açtı.

Bu, daha güçlü ve alana özgü yazma uygulanmış olsaydı önlenebilecek birçok yazılım hatası örneğinden biridir. Aynı zamanda, birincil tasarım hedeflerinden biri gömülü güvenlik açısından kritik yazılımı uygulamak olan Ada dilindeki birçok özelliğin ardındaki mantığın bir örneğidir. Ada, hem ilkel türler hem de kullanıcı tanımlı türler için statik denetime sahip güçlü yazmaya sahiptir:

```
type Velocity_In_Knots is new Float range 0.0 .. 500.00;

type Distance_In_Nautical_Miles is new Float range 0.0 .. 3000.00;

Velocity: Velocity_In_Knots;

Distance: Distance_In_Nautical_Miles;

Some_Number: Float;

Some_Number:= Distance + Velocity; -- Will be caught by the compiler as a type error.
```

Daha az talepkar etki alanlarındaki geliştiriciler, aksi takdirde dil tarafından sunulan ilkel veri türlerini ve dizeler ve kayan noktalar gibi kitaplıklarını kullanmaya devam edebilecekleri daha fazla alana özgü yazma uygulamasından da yararlanabilir. Java, C++, Python ve diğer modern dillerde soyut veri türü sınıf olarak bilinir. `Velocity_In_Knots` ve `Distance_In_Nautical_Miles` gibi sınıfların kullanılması, kod kalitesine göre çok fazla değer katar:

1. Kod, yalnızca Float veya String değil, bir etki alanı kavramlarını ifade ettiği için daha okunabilir hale gelir.
- Kod, kolayca test edilebilir davranışı içine aldığından, kod daha test edilebilir hale gelir.
- Kod, uygulamalar ve sistemler arasında yeniden kullanımı kolaylaştırır.

Yaklaşım, hem statik hem de dinamik olarak yazılan dillerin kullanıcıları için eşit derecede geçerlidir. Tek fark, statik olarak yazılan dilleri kullanan geliştiricilerin derleyiciden biraz yardım alırken, dinamik olarak yazılan dilleri benimseyenlerin birim testlerine güvenme olasılıklarının daha yüksek olmasıdır. Kontrol tarzı farklı olabilir, ancak motivasyon ve ifade tarzı değildir.

Buradaki ahlak, kaliteli yazılım geliştirmek amacıyla alana özgü türleri keşfetmeye başlamaktır.

[Einar Landre](http://programmer.97things.oreilly.com/wiki/index.php/Einar_Landre) Tarafından