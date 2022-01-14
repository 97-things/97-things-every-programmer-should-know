# O Koda Dokunma!

Hepimizin başına bir noktada gelmiştir. Kodunuz, sistem testi için hazırlama sunucusuna alındı ve test yöneticisi bir sorunla karşılaştığını yazar. İlk tepkiniz "Çabuk, bunu düzeltmeme izin verin neyin yanlış olduğunu biliyorum."

Daha geniş anlamda, yanlış olan şey, bir geliştirici olarak hazırlama sunucusuna erişiminizin olması gerektiğini düşünmenizdir.

Çoğu web tabanlı geliştirme ortamında, mimari şu şekilde bölünebilir:

- Geliştiricinin makinesinde yerel geliştirme ve birim testi
- Manuel veya otomatik entegrasyon testinin yapıldığı geliştirme sunucusu
- QA ekibinin ve kullanıcıların kabul testi yaptığı aşamalandırma sunucusu
- Üretim sunucusu

Evet, kaynak kodu kontrolü ve biletleme gibi oraya serpiştirilmiş başka sunucular ve hizmetler var, ancak siz anladınız. Bu modeli kullanan bir geliştirici hatta kıdemli bir geliştirici bile geliştirme sunucusunun ötesine asla erişememelidir. Çoğu geliştirme, bir geliştiricinin yerel makinesinde, en sevdikleri IDE'ler, sanal makineler ve iyi şanslar için üzerine serpilmiş uygun miktarda kara büyü karışımı kullanılarak yapılır.

Otomatik veya manuel olarak SCC'ye kontrol edildikten sonra, her şeyin birlikte çalıştığından emin olmak için test edilebileceği ve gerekirse ince ayar yapılabileceği geliştirme sunucusuna aktarılmalıdır. Ancak bu noktadan itibaren, geliştirici sürecin bir izleyicisidir.

Hazırlama yöneticisi, kodu QA ekibi için hazırlama sunucusuna paketlemeli ve yuvarlamalıdır. Tıpkı geliştiricilerin geliştirme sunucusunun ötesinde herhangi bir şeye erişmesine gerek olmaması gerektiği gibi, QA ekibinin ve kullanıcıların geliştirme sunucusunda herhangi bir şeye dokunmasına gerek yoktur. Kabul testi için hazırsa, bir yayın kes ve yuvarla, kullanıcıdan geliştirme sunucusunda "Gerçekten hızlı bir şeye bak" deme. Unutmayın, projeyi kendiniz kodlamıyorsanız, diğer insanların orada kodu vardır ve kullanıcının görmesi için hazır olmayabilirler. Sürüm yöneticisi, her ikisine de erişimi olması gereken tek kişidir.

Hiçbir koşulda, hiçbir zaman bir geliştiricinin bir üretim sunucusuna erişimi olmamalıdır. Bir sorun varsa, destek personeliniz sorunu çözmeli veya sizden düzeltmenizi istemelidir. SCC'de kontrol edildikten sonra oradan bir yama yayınlayacaklar. Parçası olduğum en büyük programlama felaketlerinden bazıları, birinin \**öksürük*\*ben\**öksürük\** bu son kuralı ihlal etmesiyle gerçekleşti. Bozulursa, onu tamir etmenin yeri üretim değildir.

[Cal Evans](http://programmer.97things.oreilly.com/wiki/index.php/Cal_Evans) Tarafından