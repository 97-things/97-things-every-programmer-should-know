# Fonksiyonel Programlama İlkelerini Uygulayın

Fonksiyonel programlama, son zamanlarda ana akım programlama topluluğunun yeniden ilgisini çekti. Bunun bir nedeni, fonksiyonel paradigmanın *ortaya çıkan özelliklerinin*, sektörümüzün çoklu çekirdeğe geçişinin getirdiği zorlukların üstesinden gelmek için iyi bir konumda olmasıdır. Ancak, bu kesinlikle önemli bir uygulama olsa da, bu parçanın size *fonksiyonel programlamanızı bilmenizi* tavsiye etmesinin nedeni bu değildir.

Fonksiyonel programlama paradigmasına hakim olmak, diğer bağlamlarda yazdığınız kodun kalitesini büyük ölçüde artırabilir. Fonksiyonel paradigmayı derinlemesine anlar ve uygularsanız, tasarımlarınız çok daha yüksek derecede *referans şeffaflığı* sergileyecektir.

Referans şeffaflığı çok istenen bir özelliktir: Fonksiyonların, nerede ve ne zaman çağrıldıklarına bakılmaksızın, aynı girdi verildiğinde tutarlı bir şekilde aynı sonuçları verdiğini ifade eder. Yani, fonksiyon değerlendirmesi değişken durumun yan etkilerine daha az bağlıdır - ideal olarak, hiç değil.

Zorunlu koddaki hataların önde gelen bir nedeni de değiştirilebilir değişkenlere bağlanabilir. Bunu okuyan herkes, belirli bir durumda bazı değerlerin neden beklendiği gibi olmadığını araştırmış olacaktır. Görünürlük semantiği, bu sinsi kusurları hafifletmeye veya en azından konumlarını büyük ölçüde daraltmaya yardımcı olabilir, ancak bunların asıl suçlusu aslında aşırı değişkenlik kullanan tasarımların tutumu olabilir.

Ve bu konuda kesinlikle sektörden pek bir yardım alamıyoruz. Nesne yönelimine girişler, bu tür tasarımı kısmen destekler, çünkü genellikle, birbirleri üzerinde mutlu bir şekilde mutatör yöntemlerini çağıran ve tehlikeli olabilen, nispeten uzun ömürlü nesnelerin grafiklerinden oluşan örnekler gösterirler. Ancak, zekice teste dayalı tasarımla, özellikle de ["Mock Roles, not Objects"](http://www.jmock.org/oopsla2004.pdf) yapıldığından emin olunduğunda, gereksiz değişkenlik ortadan kaldırılabilir.

Net sonuç, değiştirilebilir üye değişkenlere başvurmak bulunmak yerine, kendilerine iletilen argümanlar üzerinde hareket eden daha çok sayıda, daha küçük işlevlerle tipik olarak daha iyi sorumluluk dağılımına sahip bir tasarımdır. Daha az kusur olacak ve ayrıca hata ayıklamak genellikle daha kolay olacak, çünkü bu tasarımlarda sahte bir değerin nerede ortaya çıktığını bulmak, aksi takdirde hatalı bir atamayla sonuçlanan belirli bağlamı çıkarmaktan daha kolaydır. Bu, çok daha yüksek derecede bir referans şeffaflığı ekler ve pozitif olarak hiçbir şey bu fikirleri, bu hesaplama modelinin norm olduğu fonksiyonel bir programlama dili öğrenmek kadar derine inemez.

Tabii ki, bu yaklaşım her durumda optimal değildir. Örneğin, nesne yönelimli sistemlerde bu tarz, genellikle etki alanı modeli geliştirmede (yani işbirliklerinin iş kurallarının karmaşıklığını yıkmaya hizmet ettiği yerlerde) kullanıcı arayüzü geliştirmeye göre daha iyi sonuçlar verir.

Öğrenilen dersleri diğer alanlara mantıklı bir şekilde uygulayabilmek için fonksiyonel programlama paradigmasında ustalaşın. Nesne sistemleriniz (biri için) referans şeffaflığı iyiliği ile yankılanacak ve işlevsel benzerlerine pek çok kişinin inandığından çok daha yakın olacaktır. Hatta bazıları, fonksiyonel programlama ve nesne yöneliminin zirvesinin *yalnızca birbirinin bir yansıması*, bir hesaplamalı yin ve yang biçimi olduğunu bile iddia edebilir.

[Edward Garson](http://programmer.97things.oreilly.com/wiki/index.php/Edward_Garson) Tarafından