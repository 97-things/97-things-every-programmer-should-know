# Araçlarınızı Özenle Seçin

Modern uygulamalar çok nadiren sıfırdan oluşturulur. Birkaç iyi nedenden dolayı mevcut araçlar (bileşenler, kitaplıklar ve çerçeveler) kullanılarak birleştirilirler:

- Uygulamaların boyutu, karmaşıklığı ve karmaşıklığı artarken bunları geliştirmek için mevcut süre kısalır. Daha fazla iş alanı kodu ve daha az altyapı kodu yazmaya odaklanabilirlerse, geliştiricilerin zamanını ve zekasını daha iyi kullanır.

- Yaygın olarak kullanılan bileşenler ve çerçevelerin, şirket içinde geliştirilenlerden daha az hata içermesi muhtemeldir.

- Web'de ücretsiz olarak sunulan çok sayıda yüksek kaliteli yazılım vardır, bu da daha düşük geliştirme maliyetleri ve gerekli ilgi ve uzmanlığa sahip geliştiricileri bulma olasılığının artması anlamına gelir.

- Yazılım üretimi ve bakımı yoğun bir iştir, bu nedenle satın almak inşa etmekten daha ucuz olabilir.

Ancak, uygulamanız için doğru araç karışımını seçmek, biraz düşünmeyi gerektiren zor bir iş olabilir. Aslında bir seçim yaparken aklınızda bulundurmanız gereken birkaç şey var:

- Farklı araçlar, bağlamları hakkında farklı varsayımlara dayanabilir (ör. çevreleyen altyapı, kontrol modeli, veri modeli, iletişim protokolleri vb.), bu da uygulama ile araçlar arasında mimari uyumsuzluğa yol açabilir. Böyle bir uyumsuzluk, kodu gereğinden fazla karmaşık hale getirecek saldırılara ve geçici çözümlere yol açar.

- Farklı araçların farklı yaşam döngüleri vardır ve yeni işlevler, tasarım değişiklikleri ve hatta hata düzeltmeleri diğer araçlarla uyumsuzluklara neden olabileceğinden, bunlardan birini yükseltmek son derece zor ve zaman alıcı bir görev haline gelebilir. Araç sayısı arttıkça sorun daha da kötüleşebilir.

- Bazı araçlar, genellikle çok hızlı bir şekilde kontrolden çıkabilen bir veya daha fazla XML dosyası aracılığıyla oldukça fazla yapılandırma gerektirir. Uygulama, tamamı XML'de ve bazı programlama dillerinde birkaç garip kod satırında yazılmış gibi görünebilir. Konfigürasyonel karmaşıklık, uygulamanın bakımını ve genişletilmesini zorlaştıracaktır.

- Satıcı kilitlenmesi, büyük ölçüde belirli satıcı ürünlerine bağlı olan kodlar, onlar tarafından birkaç açıdan kısıtlandığında ortaya çıkar: sürdürülebilirlik, performans, gelişme yeteneği, fiyat, vb.

- Özgür yazılım kullanmayı planlıyorsanız, bunun o kadar da özgür olmadığını keşfedebilirsiniz. Mutlaka ucuz olmayacak olan ticari destek satın almanız gerekebilir.

- Lisans koşulları, özgür yazılım için bile önemlidir. Örneğin, bazı şirketlerde viral doğası nedeniyle GNU lisans koşulları kapsamında lisanslanan yazılımların kullanılması kabul edilemez - yani, onunla geliştirilen yazılım kaynak koduyla birlikte dağıtılmalıdır.

Bu sorunları azaltmak için kişisel stratejim, yalnızca kesinlikle gerekli araçları kullanarak küçük bir başlangıç yapmaktır. Genellikle ilk odak noktası, örneğin dağıtılmış uygulamalar için hassas soketler kullanmak yerine bazı ara katman yazılımları kullanarak, düşük seviyeli altyapı programlaması (ve sorunları) ile meşgul olma ihtiyacını ortadan kaldırmaktır. Ve sonra gerekirse daha fazlasını ekleyin. Arayüzler ve katmanlama yoluyla harici araçları iş alanı nesnelerimden ayırma eğilimindeyim, böylece aracımı biraz zahmetle değiştirmem gerekirse değiştirebilirim. Bu yaklaşımın olumlu bir yan etkisi, genellikle başlangıçta tahmin edilenden daha az harici araç kullanan daha küçük bir uygulama ile sonuçlanmasıdır.

[Giovanni Asproni](http://programmer.97things.oreilly.com/wiki/index.php/Giovanni_Asproni) Tarafından