# Programınızı Dik Konumda Çivilemeyin

Bir keresinde, istisna işleme için aşağıdaki stratejiyi hicivli bir şekilde önerdiğim bir sahte C++ sınavı yazdım:

> Kod tabanımızdaki çok sayıda `try...catch` yapısı sayesinde, bazen uygulamalarımızın iptal edilmesini önleyebiliriz. Ortaya çıkan durumu "cesedi dik pozisyonda çivilemek" olarak düşünürüz.

Alaysızlığıma rağmen, aslında Dame Bitter Experience'ın dizinin dibinde aldığım bir dersi özetledim.

Kendi ev yapımı C++ kitaplığımızda temel bir uygulama sınıfıydı. Yıllar boyunca pek çok yazılımcının parmaklarını dürttü: Kimsenin eli temiz değildi. Diğer her şeyden kaçan istisnalarla başa çıkmak için kod içeriyordu. Catch-22'de Yossarian'dan yola çıkarak, bu sınıfın bir örneğinin sonsuza kadar yaşaması veya bu girişimde ölmesi gerektiğine karar verdik veya daha doğrusu hissettik (*karar verdi* bu canavarın inşasına girmekten daha fazla düşünce anlamına gelir).

Bu amaçla, birden çok istisna işleyicisini iç içe geçirdik. Windows'un yapılandırılmış özel durum işlemesini yerel türle karıştırdık (C++'da '__try...__except'i hatırla? Ben de yokum). Beklenmedik bir şekilde işler ters gittiğinde, parametrelere daha sert basarak onları tekrar çağırmayı denedik. Geriye dönüp baktığımda, bir başkasının catch cümlesi içinde içsel bir 'try...catch' işleyicisi yazarken, iyi uygulama otoyolundan kazara bir kayma yolu seçmiş olabileceğime dair bir tür farkındalığın üzerime çöktüğünü düşünmek hoşuma gidiyor, aromatik ama sağlığa zararlı delilik şeridi. Ancak, bu muhtemelen geriye dönük bir bilgeliktir.

Söylemeye gerek yok, ne zaman bu sınıfa dayalı uygulamalarda bir şeyler ters gitse, rıhtımdaki Mafya kurbanları gibi ortadan kayboldular ve felaketi kaydetmek için çağrıldığı varsayılan çöplük rutinlerine rağmen, arkalarında ne olduğunu gösteren hiçbir yararlı kabarcık izi bırakmadılar. Sonunda, uzun bir süre sonra yaptıklarımızın hesabını yaptık ve utanç duyduk. Tüm karmaşayı minimal ve sağlam bir raporlama mekanizmasıyla değiştirdik. Ancak bu, çizgide birçok kaza oldu.

Seni bununla rahatsız etmem, kesinlikle başka kimse bizim kadar aptal olamaz ama geçenlerde, akademik iş unvanı daha iyi bilmesi gerektiğini söyleyen bir adamla çevrimiçi bir tartışma yaptım. Uzak bir işlemde Java kodunu tartışıyorduk. Kodun başarısız olması durumunda, *in situ* istisnasını yakalaması ve engellemesi gerektiğini savundu. ("Peki onunla *ne* yapacaksın?" diye sordum. "Akşam yemeği için pişirelim mi?")

UI tasarımcılarının kuralından alıntı yaptı: KULLANICININ ASLA İSTİSNA RAPORU GÖRMESİNE İZİN VERMEYİN, sanki bu meseleyi çözmüş gibi, ne büyük harflerle ve her şeyle. Fotoğrafları daha zayıf blogları süsleyen mavi ekranlı ATM'lerden birindeki koddan sorumlu olup olmadığını ve kalıcı olarak travmatize olup olmadığını merak ediyorum. Her neyse, eğer onunla karşılaşırsan, başını salla ve gülümse ve kapıya doğru yan yan dönerken aldırma.

[Verity Stob](http://programmer.97things.oreilly.com/wiki/index.php/Verity_Stob) Tarafından