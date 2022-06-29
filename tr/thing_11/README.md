# Domain Dilindeki Kod

İki kod tabanını hayal edin. Karşılaştığınız birinde:

```
if (portfolioIdsByTraderId.get(trader.getId())
  .containsKey(portfolio.getId())) {...}
```
  
Bu kodun ne işe yaradığını merak ederek kafanı kaşıyorsun. Bir tüccar nesnesinden bir kimlik alıyor gibi görünüyor, bunu görünüşte bir haritadan harita çıkarmak için kullanıyor ve ardından iç haritada bir portföy nesnesinden başka bir kimliğin olup olmadığını görüyor. Kafanı biraz daha kaşıyorsun. portfolioIdsByTraderId tanımına baktığınızda şunu keşfedersiniz:

```
Map<int, Map<int, int>> portfolioIdsByTraderId;
```

Yavaş yavaş, bunun bir tüccarın belirli bir portföye erişimi olup olmadığıyla ilgili olabileceğini anlayacaksınız. Ve elbette, bir yatırımcının belirli bir portföye erişimi olup olmadığını umursayan bir şey olduğunda, aynı arama parçasını veya daha büyük olasılıkla benzer ama çok farklı bir kod parçasını bulacaksınız.

Diğer kod tabanında bununla karşılaşırsınız:

```
if (trader.canView(portfolio)) {...}
```

Kafa kaşımak yok. Bir tüccarın nasıl bildiğini bilmenize gerek yok. Belki de bu haritalardan biri içeride bir yere gizlenmiştir. Ama bu tüccarın işi, senin değil.

Şimdi bu kod tabanlarından hangisinde çalışmayı tercih ederdiniz?

Bir zamanlar sadece çok temel veri yapılarımız vardı: bitler, baytlar ve karakterler (gerçekten sadece baytlar ama biz bunları harfler ve noktalama işaretleriymiş gibi yapardık). Ondalık sayılar biraz zordu çünkü 10 tabanlı sayılarımız ikili sistemde pek iyi çalışmıyor, bu yüzden birkaç boyutta kayan nokta tipimiz vardı. Ardından diziler ve dizeler geldi (gerçekten sadece farklı diziler). Sonra yığınlar, kuyruklar, karmalar ve bağlantılı listeler, atlama listeleri ve *gerçek dünyada olmayan* pek çok başka heyecan verici veri yapısı vardı. "Bilgisayar bilimi", gerçek dünyayı kısıtlayıcı veri yapılarımızla eşleştirmek için çok çaba harcamakla ilgiliydi. Gerçek gurular bunu nasıl yaptıklarını bile hatırlayabiliyorlardı.

Sonra kullanıcı tanımlı türlerimiz var! Tamam, bu haber değil ama oyunu biraz değiştiriyor. Alan adınız tüccarlar ve portföyler gibi kavramlar içeriyorsa, bunları örneğin Tüccar ve Portföy adı verilen türlerle modelleyebilirsiniz. Ancak bundan daha da önemlisi, etki alanı terimlerini kullanarak *aralarındaki ilişkileri* modelleyebilirsiniz.

Etki alanı terimlerini kullanarak kodlama yapmazsanız, buradaki *this* int'nin bir yatırımcıyı tanımlamanın yolu anlamına geldiğini, oysa oradaki *that* int'nin bir portföy tanımlamanın yolu anlamına geldiğini anlayan bir gizli okuma oluşturursunuz. (Karıştırmamak en iyisi!) Ve algoritmik bir snippet ile bir iş konseptini ("Bazı yatırımcıların bazı portföyleri görüntülemesine izin verilmez - bu yasa dışıdır") temsil ediyorsanız, diyelim ki bir anahtar haritasında bir varlık ilişkisi var, denetim ve uyumluluk adamlarına herhangi bir iyilik yapmıyorsunuz demektir. .

Sıradaki yazılımcı sırrın içinde olmayabilir, o halde neden bunu açıklığa kavuşturmuyorsunuz? Bir anahtarın varlık kontrolü yapan başka bir anahtarı aramak için kullanılması çok açık değildir. Çıkar çatışmasını önleyen iş kurallarının burada uygulandığını birisi nasıl sezebilir?

Etki alanı kavramlarını kodunuzda açık hale getirmek, diğer yazılımcıların, bir etki alanı hakkında anladıklarına bir algoritmayı güçlendirmeye çalışmaktan çok daha kolay bir şekilde kodun *niyetini* elde edebilecekleri anlamına gelir. Bu aynı zamanda, etki alanı modeli geliştiğinde ki bu, etki alanına ilişkin anlayışınız arttıkça artacaktır, kodu geliştirmek için iyi bir konumdasınız demektir. İyi bir kapsülleme ile birleştiğinde, kuralın yalnızca bir yerde var olma ve bağımlı kodlardan herhangi biri daha akıllıca olmadan değiştirebilme şansınız yüksektir.

Birkaç ay sonra kod üzerinde çalışmak için gelen yazılımcı size teşekkür edecek. Birkaç ay sonra gelen yazılımcı siz olabilirsiniz.

[Dan North](http://programmer.97things.oreilly.com/wiki/index.php/Dan_North) Tarafından