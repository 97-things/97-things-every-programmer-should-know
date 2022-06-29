# Mesaj Geçişi, Paralel Sistemlerde Daha İyi Ölçeklenebilirlik Sağlar

Yazılımcılara, hesaplama çalışmalarının en başından itibaren, eşzamanlılığın ve özellikle eşzamanlılığın özel bir alt kümesi olan paralelliğin zor olduğu, yalnızca en iyilerin onu doğru yapmayı umabileceği ve hatta yanlış anlayabileceği öğretilir. İplikler, semaforlar, monitörler ve iş parçacığı açısından güvenli olmak için değişkenlere eşzamanlı erişim sağlamanın ne kadar zor olduğu konusunda her zaman büyük bir odak vardır.

Doğru, birçok zor problem var ve çözülmesi çok zor olabilir. Ama sorunun kökü nedir? Paylaşılan hafıza. İnsanların üzerinde durup durduğu hemen hemen tüm eşzamanlılık sorunları, paylaşılan değişebilir belleğin kullanımıyla ilgilidir: yarış koşulları, kilitlenme, canlı kilit, vb. Cevap açık görünüyor: Ya eşzamanlılıktan vazgeç ya da paylaşılan bellekten kaçın!

Devam eden eşzamanlılık neredeyse kesinlikle bir seçenek değildir. Bilgisayarlar neredeyse üç ayda bir giderek daha fazla çekirdeğe sahip olduğundan, gerçek paralellikten yararlanmak giderek daha önemli hale geliyor. Uygulama performansını iyileştirmek için artık artan işlemci saat hızlarına güvenemeyiz. Yalnızca paralellikten yararlanarak uygulamaların performansı iyileşir. Açıkçası, performansı iyileştirmemek bir seçenektir, ancak kullanıcılar tarafından kabul edilmesi pek olası değildir.

Öyleyse paylaşılan hafızadan kaçınabilir miyiz? Kesinlikle.

Programlama modelimiz olarak iş parçacıklarını ve paylaşılan belleği kullanmak yerine, süreçleri ve mesaj geçişini kullanabiliriz. Buradaki işlem, mutlaka bir işletim sistemi işlemi değil, yalnızca yürütme koduyla korunan bağımsız bir durum anlamına gelir. Erlang (ve ondan önceki occam) gibi diller, süreçlerin eşzamanlı ve paralel sistemleri programlamak için çok başarılı bir mekanizma olduğunu göstermiştir. Bu tür sistemler, paylaşılan bellek, çok iş parçacıklı sistemlerin sahip olduğu tüm senkronizasyon streslerine sahip değildir. Ayrıca, bu tür sistemlerin mühendisliğinin bir parçası olarak uygulanabilecek resmi bir model Haberleşme Sıralı Süreçler (CSP - Communicating Sequential Processes) vardır.

Daha ileri gidebilir ve bir bilgi işlem yolu olarak veri akışı sistemlerini tanıtabiliriz. Bir veri akışı sisteminde, açıkça programlanmış bir kontrol akışı yoktur. Bunun yerine, veri yolları ile bağlanan operatörlerin yönlendirilmiş bir grafiği kurulur ve ardından sisteme veri beslenir. Değerlendirme, sistem içindeki verilerin hazır olup olmadığı ile kontrol edilir. Senkronizasyon sorunu kesinlikle yoktur.

Tüm bunları söyledikten sonra, C, C++, Java, Python ve Groovy gibi diller sistem geliştirmenin başlıca dilleridir ve bunların hepsi programcılara paylaşımlı bellek, çok kanallı sistemler geliştirme dilleri olarak sunulur. Peki ne yapılabilir? Cevap, paylaşılan değiştirilebilir belleğin tüm kullanımından kaçınarak süreç modelleri ve mesaj geçişi sağlayan kitaplıklar ve çerçeveler kullanmak veya yoksa, oluşturmaktır.

Sonuç olarak, paylaşılan bellekle programlama değil, bunun yerine mesaj iletimini kullanmak, bilgisayar donanımında yaygın olan paralellikten yararlanan sistemleri uygulamanın en başarılı yolu olabilir. Tuhaf bir şekilde, süreçler bir eşzamanlılık birimi olarak iş parçacıklarından önce gelse de, gelecek süreçleri uygulamak için iş parçacıklarını kullanmak gibi görünüyor.

[Russel Winder](http://programmer.97things.oreilly.com/wiki/index.php/Russel_Winder) Tarafından