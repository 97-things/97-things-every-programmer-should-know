# Görünmezi Daha Görünür Hale Getirin

Görünmezliğin birçok yönü, desteklenmesi gereken yazılım ilkeleri olarak haklı olarak övülür. Terminolojimiz, görünmezlik metaforları bakımından zengindir. Mekanizma şeffaflığı ve bilgi gizleme, bunlardan ikisi. Douglas Adams'ın deyişiyle, yazılım ve onu geliştirme süreci *çoğunlukla görünmez* olabilir:

- Kaynak kodun doğuştan gelen bir varlığı, doğuştan gelen bir davranışı yoktur ve fizik yasalarına uymaz. Bir düzenleyiciye yüklediğinizde görünür, ancak düzenleyiciyi kapattığınızda kaybolur. Bunu çok uzun süre düşünün ve kimsenin duymadığı bir ağacın devrilmesi gibi, gerçekten var mı diye merak etmeye başlıyorsunuz.
- Çalışan bir uygulamanın varlığı ve davranışı vardır, ancak oluşturulduğu kaynak koddan hiçbir şey göstermez. Google'ın ana sayfası hoş bir şekilde minimaldir; arkasında olup bitenler kesinlikle önemli.
- %90'ını bitirdiysen ve son %10'da hata ayıklamaya çalışırken durmadan takılıp kaldıysan, %90'ını bitirmedin, değil mi? Hataları düzeltmek ilerleme kaydetmiyor. Hata ayıklamak için size ödeme yapılmaz. Hata ayıklama israftır. Atığı daha görünür kılmak iyidir, böylece ne olduğunu görebilir ve ilk etapta onu yaratmamaya çalışmayı düşünmeye başlayabilirsiniz.
- Eğer projeniz yolunda gidiyorsa ve bir hafta sonra altı ay geciktiyse sorunlarınız var, bunların en büyüğü muhtemelen altı ay gecikmiş olması değil, ancak görünmezlik güç alanları altı aylık gecikmeyi gizleyecek kadar güçlü! Görünür ilerleme eksikliği, ilerleme eksikliği ile eş anlamlıdır.

Görünmezlik tehlikeli olabilir. Düşüncelerinizi bağlayacak somut bir şeyiniz olduğunda daha net düşünürsünüz. Onları gördüğünüzde ve sürekli değiştiğini gördüğünüzde işleri daha iyi yönetirsiniz:

- Birim testleri yazmak, kod biriminin birim testi için ne kadar kolay olduğuna dair kanıt sağlar. Kodun sergilemesini istediğiniz gelişimsel niteliklerin varlığını (veya yokluğunu) ortaya çıkarmaya yardımcı olur; düşük bağlantı ve yüksek kohezyon gibi nitelikler.
- Çalışan birim testleri, kodun davranışı hakkında kanıt sağlar. Uygulamanın sergilemesini istediğiniz niteliklerin çalışma zamanının varlığını (veya yokluğunu) ortaya çıkarmaya yardımcı olur; sağlamlık ve doğruluk gibi nitelikler.
- Bülten tahtaları ve kartları kullanmak ilerlemeyi görünür ve somut hale getirir. Görevler, gizli bir proje yönetim aracına başvurmadan ve kurgusal durum raporları için programcıları kovalamak zorunda kalmadan *Başlamadı*, *Devam Ediyor* veya *Bitti* olarak görülebilir.
- Kademeli geliştirme yapmak, geliştirme kanıtlarının sıklığını artırarak geliştirme ilerlemesinin (veya eksikliğinin) görünürlüğünü artırır. Serbest bırakılabilir yazılımın tamamlanması gerçeği ortaya çıkarır; tahminler öyle değil.

Bol miktarda düzenli görünür kanıt içeren bir yazılım geliştirmek en iyisidir. Görünürlük, ilerlemenin gerçek olduğuna ve bir yanılsama olmadığına, kasıtlı ve kasıtsız olmadığına, tekrarlanabilir olduğuna ve tesadüfi olmadığına dair güven verir.

[Jon Jagger](http://programmer.97things.oreilly.com/wiki/index.php/Jon_Jagger) Tarafından