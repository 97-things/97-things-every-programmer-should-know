# IDE'nizi Bilin

1980'lerde programlama ortamlarımız tipik olarak yüceltilmiş metin editörlerinden daha iyi değildi... eğer şanslıysak. Bugünlerde hafife aldığımız sözdizimi vurgulama, kesinlikle herkesin erişemeyeceği bir lükstü. Kodumuzu güzel bir şekilde biçimlendirmek için güzel yazıcılar, genellikle boşluklarımızı düzeltmek için çalıştırılması gereken harici araçlardı. Hata ayıklayıcılar aynı zamanda kodumuzda adım adım ilerleyen, ancak çok sayıda şifreli tuş vuruşuyla çalışan ayrı programlardı.

1990'larda şirketler, programcıları daha iyi ve daha kullanışlı araçlarla donatmaktan elde edebilecekleri potansiyel geliri fark etmeye başladılar. Entegre Geliştirme Ortamı (IDE), önceki düzenleme özelliklerini bir derleyici, hata ayıklayıcı, güzel yazıcı ve diğer araçlarla birleştirdi. Bu süre zarfında menüler ve fare de popüler hale geldi, bu da geliştiricilerin editörlerini kullanmak için artık şifreli tuş kombinasyonlarını öğrenmeleri gerekmediği anlamına geliyordu. Menüden komutlarını kolayca seçebilirler.

21. yüzyılda IDE'ler o kadar yaygın hale geldi ki, diğer alanlarda pazar payı kazanmak isteyen şirketler tarafından ücretsiz olarak dağıtılıyor. Modern IDE, inanılmaz bir dizi özellikle donatılmıştır. En sevdiğim, otomatik yeniden düzenleme, özellikle bir kod yığınını seçip bir yönteme dönüştürebildiğim *Çıkarma Yöntemi*. Yeniden düzenleme aracı, yönteme geçirilmesi gereken tüm parametreleri alır ve bu da kodu değiştirmeyi son derece kolaylaştırır. IDE'm, bu yöntemle değiştirilebilecek diğer kod parçalarını bile algılayacak ve onları da değiştirmek isteyip istemediğimi soracak.

Modern IDE'lerin bir başka şaşırtıcı özelliği de bir şirket içinde stil kurallarını uygulama yeteneğidir. Örneğin, Java'da bazı programcılar tüm parametreleri nihai hale getirmeye başladılar (bence bu bir zaman kaybıdır). Ancak, böyle bir stil kuralına sahip oldukları için, bunu takip etmek için tek yapmam gereken, onu IDE'mde ayarlamak: Son olmayan herhangi bir parametre için bir uyarı alırdım. Stil kuralları, örneğin, referans nesnelere otomatik kutulanmış ilkel değerler üzerinde `==` kullanmak gibi, otomatik kutulanmış nesneleri referans eşitliği için karşılaştırmak gibi olası hataları bulmak için de kullanılabilir.

Ne yazık ki modern IDE'ler, onları nasıl kullanacağımızı öğrenmek için çaba harcamamızı gerektirmiyor. Unix'te C'yi ilk programladığımda, dik öğrenme eğrisi nedeniyle vi editörünün nasıl çalıştığını öğrenmek için biraz zaman harcamak zorunda kaldım. Önceden harcanan bu süre, yıllar içinde cömertçe karşılığını verdi. Hatta bu yazının taslağını *vi* ile yazıyorum. Modern IDE'lerin çok kademeli bir öğrenme eğrisi vardır ve bu, aracın en temel kullanımının ötesine asla geçemeyeceğimiz etkisine sahip olabilir.

Bir IDE öğrenmede ilk adımım klavye kısayollarını ezberlemektir. Kodumu yazarken parmaklarım klavyede olduğundan, bir değişkeni satır içi yapmak için *Ctrl+Shift+I* tuşlarına basmak akışı bozmaktan tasarruf sağlarken, faremle bir menüde gezinmeye geçmek akışı keser. Bu kesintiler gereksiz bağlam geçişlerine yol açıyor ve her şeyi tembel bir şekilde yapmaya çalışırsam beni çok daha az üretken yapıyor. Aynı kural klavye becerileri için de geçerlidir: Yazıya dokunmayı öğrenin, önceden harcadığınız zamana pişman olmayacaksınız.

Son olarak, programcılar olarak, kodumuzu değiştirmemize yardımcı olabilecek, zamanı kanıtlanmış Unix akış araçlarına sahibiz. Örneğin, bir kod incelemesi sırasında, programcıların birçok sınıfı aynı adlandırdığını fark edersem, *find*, *sed*, *sort*, *uniq* ve *grep* araçlarını kullanarak bunları çok kolay bulabilirim, bunun gibi:

```
find . -name "*.java" | sed 's/.*\///' | sort | uniq -c | grep -v "^ *1 " | sort -r
```

Evimize gelen bir tesisatçının el fenerini kullanabilmesini bekliyoruz. IDE'mizle nasıl daha etkili olabileceğimizi incelemek için biraz zaman harcayalım.

[Heinz Kabutz](http://programmer.97things.oreilly.com/wiki/index.php/Heinz_Kabutz) Tarafından