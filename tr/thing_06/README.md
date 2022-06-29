# Yeniden Düzenlemeden Önce

Bir noktada her yazılımcının mevcut kodu yeniden düzenlemesi gerekecek. Ancak bunu yapmadan önce lütfen aşağıdakileri düşünün, çünkü bu sizi ve diğerlerini büyük ölçüde zamandan (ve acıdan) kurtarabilir:

- *Yeniden yapılandırma için en iyi yaklaşım, mevcut kod tabanını ve bu koda karşı yazılan testleri değerlendirmekle başlar.* Bu, kodun mevcut haliyle güçlü ve zayıf yönlerini anlamanıza yardımcı olacaktır, böylece hatalardan kaçınırken güçlü noktaları korumanızı sağlayabilirsiniz. Hepimiz mevcut sistemden daha iyisini yapabileceğimizi düşünüyoruz... ta ki mevcut sistem hatalarından ders çıkaramadığımız için önceki üründen daha iyi olmayan - hatta daha kötü olmayan - bir şeyle sonuçlanıncaya kadar.

- *Her şeyi yeniden yazmanın cazibesinden kaçının.* Mümkün olduğu kadar çok kodu yeniden kullanmak en iyisidir. Kod ne kadar çirkin olursa olsun, zaten test edilmiş, gözden geçirilmiş vb. Eski kodu - özellikle de üretimdeyse - atmak, farkında olmadığınız belirli geçici çözümlere ve hata düzeltmelerine sahip olabilecek, aylarca (veya yıllarca) test edilmiş, savaşta sertleştirilmiş kodu attığınız anlamına gelir. Bunu hesaba katmazsanız, yazdığınız yeni kod, eski kodda düzeltilen aynı gizemli hataları gösterebilir. Bu, yıllar içinde kazanılan çok fazla zaman, çaba ve bilgi israfına neden olacaktır.

- *Birçok artımlı değişiklik, tek bir büyük değişiklikten daha iyidir.* Artımlı değişiklikler, geri bildirim yoluyla sistem üzerindeki etkiyi daha kolay ölçmenizi sağlar, örneğin testlerden. Bir değişiklik yaptıktan sonra yüzlerce test hatası görmek eğlenceli değil. Bu, kötü kararlarla sonuçlanabilecek hayal kırıklığına ve baskıya yol açabilir. Birkaç test hatasının üstesinden gelmek kolaydır ve daha yönetilebilir bir yaklaşım sağlar.

- *Her yinelemeden sonra mevcut testlerin geçmesini sağlamak önemlidir.* Mevcut testler yaptığınız değişiklikleri karşılamaya yetmiyorsa yeni testler ekleyin. Eski koddaki testleri, gerekli özeni göstermeden atmayın. İlk bakışta, bu testlerden bazıları yeni tasarımınıza uygulanabilir görünmeyebilir, ancak bu özel testin neden eklendiğini derinlemesine araştırmak çabaya değer.

- *Kişisel tercihler ve ego araya girmemeli.* Bir şey bozuk değilse, neden düzeltelim? Kodun stilinin veya yapısının kişisel tercihinizi karşılamaması, yeniden yapılandırma için geçerli bir neden değildir. Önceki yazılımcıdan daha iyi bir iş yapabileceğinizi düşünmek de geçerli bir sebep değil.

- *Yeni teknoloji, yeniden düzenleme yapmak için yetersiz bir nedendir.* Yeniden düzenleme yapmanın en kötü nedenlerinden biri, mevcut kodun bugün sahip olduğumuz tüm harika teknolojinin çok gerisinde olması ve yeni bir dil veya çerçevenin işleri çok daha zarif bir şekilde yapabileceğine inanıyoruz. Maliyet-fayda analizi, yeni bir dilin veya çerçevenin işlevsellik, sürdürülebilirlik veya üretkenlikte önemli gelişmelerle sonuçlanacağını göstermediği sürece, onu olduğu gibi bırakmak en iyisidir.

- *İnsanların hata yaptığını unutmayın.* Yeniden yapılandırma, her zaman yeni kodun daha iyi - hatta önceki deneme kadar iyi - olacağını garanti etmez. Birkaç başarısız yeniden yapılandırma girişimi gördüm ve bir parçası oldum. Güzel değildi ama insandı.

[Rajith Attapattu](http://programmer.97things.oreilly.com/wiki/index.php/Rajith_Attapattu) Tarafından