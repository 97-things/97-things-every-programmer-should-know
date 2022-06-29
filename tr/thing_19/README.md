# Kolaylık bir yetenek değildir

İyi API'ler tasarlamanın önemi ve zorlukları hakkında çok şey söylendi. İlk seferde doğruyu bulmak zordur ve daha sonra değiştirmek daha da zordur. Çocuk yetiştirmek gibi bir şey. Deneyimli programcıların çoğu, iyi bir API'nin tutarlı bir soyutlama düzeyi izlediğini, tutarlılık ve simetri sergilediğini ve ifade edici bir dil için kelime dağarcığını oluşturduğunu öğrenmiştir. Ne yazık ki, yol gösterici ilkelerin farkında olmak otomatik olarak uygun davranışa dönüşmez. Tatlı yemek zararlıdır.

Yukarıdan vaaz vermek yerine, defalarca karşılaştığım belirli bir API tasarım 'stratejisini' seçmek istiyorum: uygunluk argümanı. Genellikle aşağıdaki 'anlayışlardan' biriyle başlar:

- Bu tek şeyi yapmak için diğer sınıfların iki ayrı çağrı yapmasını istemiyorum.
- Bu yöntemle hemen hemen aynıysa neden başka bir yöntem yapayım? Sadece basit bir anahtar ekleyeceğim.
- Bak, çok kolay: İkinci string parametresi ".txt" ile bitiyorsa, metod otomatik olarak ilk parametrenin bir dosya ismi olduğunu varsayar, yani gerçekten iki metoda ihtiyacım yok.

İyi niyetli olsalar da, bu tür argümanlar API kullanılarak kodun okunabilirliğini azaltmaya eğilimlidir. Gibi bir yöntem çağırma

```
parser.processNodes(text, false);
```

uygulamayı bilmeden veya en azından belgelere danışmadan neredeyse anlamsızdır. Bu yöntem muhtemelen arayanın rahatlığının aksine uygulayıcının rahatlığı için tasarlanmıştır - "Arayanın iki ayrı arama yapmak zorunda kalmasını istemiyorum", "İki ayrı yöntemi kodlamak istemedim" olarak çevrilmiştir." Sıkıcılığın, hantallığın veya beceriksizliğin panzehiri olması amaçlanıyorsa, temelde yanlış bir şey yoktur. Bununla birlikte, bu konuda biraz daha dikkatli düşünürsek, bu semptomların panzehiri verimlilik, tutarlılık ve zarafettir, rahatlık değil. API'lerin temeldeki karmaşıklığı gizlemesi gerekiyor, bu nedenle gerçekçi bir şekilde iyi API tasarımının biraz çaba gerektirmesini bekleyebiliriz. Tek bir büyük yöntemin yazılması, iyi düşünülmüş bir dizi işlemden kesinlikle daha uygun olabilir, ancak kullanımı daha kolay olur mu?

Bir dil olarak API metaforu, bu durumlarda bizi daha iyi tasarım kararlarına yönlendirebilir. Bir API, faydalı soruları sormak ve yanıtlamak için yeterli kelime dağarcığının üstündeki sonraki katmanı veren, ifade edici bir dil sağlamalıdır. Bu, sorulmaya değer olabilecek her soru için tam olarak bir yöntem veya fiil sağlaması gerektiği anlamına gelmez. Farklı bir kelime dağarcığı, anlamdaki incelikleri ifade etmemizi sağlar. Örneğin, temelde aynı işlem olarak görülebilse de, sadece farklı hızlarda yürütülmüş olsa da, yürü(doğru) yerine koş demeyi tercih ederiz. Tutarlı ve iyi düşünülmüş bir API sözlüğü, bir sonraki katmanda kodun anlamlı ve anlaşılması kolay olmasını sağlar. Daha da önemlisi, şekillendirilebilir bir sözcük dağarcığı, diğer programcıların API'yi tahmin etmediğiniz şekillerde kullanmasına olanak tanır, API kullanıcıları için gerçekten büyük bir kolaylık! Bir dahaki sefere, birkaç şeyi tek bir API yönteminde toplamaya can attığınızda, bu kadar sık istenen bir işlem için gerçekten uygun görünse de, İngilizce dilinde 'MakeUpYourRoomBeQuietAndDoYourHomeWork' için tek bir kelime olmadığını unutmayın.

[Gregor Hohpe](http://programmer.97things.oreilly.com/wiki/index.php/Gregor_Hohpe) Tarafından