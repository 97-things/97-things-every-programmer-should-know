# Hataları Önle

Hata mesajları, kullanıcı ile sistemin geri kalanı arasındaki en kritik etkileşimlerdir. Kullanıcı ve sistem arasındaki iletişim kopma noktasına yaklaştığında meydana gelirler.

Bir hatanın kullanıcıdan gelen yanlış bir girdiden kaynaklandığını düşünmek kolaydır. Ancak insanlar tahmin edilebilir, sistematik yollarla hata yaparlar. Böylece, tıpkı diğer sistem bileşenleri arasında yaptığınız gibi, kullanıcı ile sistemin geri kalanı arasındaki iletişimi 'hata ayıklamak' mümkündür.

Örneğin, kullanıcının izin verilen bir aralık içinde bir tarih girmesini istediğinizi varsayalım. Kullanıcının herhangi bir tarih girmesine izin vermek yerine, yalnızca izin verilen tarihleri ​​gösteren liste veya takvim gibi bir cihaz sunmak daha iyidir. Bu, kullanıcının aralığın dışında bir tarih girme olasılığını ortadan kaldırır.

Biçimlendirme hataları başka bir yaygın sorundur. Örneğin, bir kullanıcıya bir Tarih metin alanı sunulur ve "29 Temmuz 2012" gibi açık bir tarih girerse, tercih edilen bir biçimde olmadığı için ("GG/AA/YYYY" gibi) reddetmesi mantıksızdır. "). Fazladan boşluklar içerdiğinden "29 / 07 / 2012"yi reddetmek daha da kötüdür. Bu tür bir sorunu, tarih istenen biçimde göründüğü için özellikle kullanıcıların anlaması zordur.

Bu hata, tarihi reddetmenin en yaygın üç veya dört tarih biçimini ayrıştırmaktan daha kolay olması nedeniyle oluşur. Bu tür küçük hatalar kullanıcının hayal kırıklığına uğramasına neden olur ve bu da kullanıcı konsantrasyonunu kaybettiği için ek hatalara yol açar. Bunun yerine, kullanıcıların veri değil bilgi girme tercihine saygı gösterin.

Biçimlendirme hatalarından kaçınmanın bir başka yolu da ipuçları sunmaktır - örneğin, alan içinde istenen biçimi ("GG/AA/YYYY") gösteren bir etiketle. Başka bir ipucu, alanı iki, iki ve dört karakterden oluşan üç metin kutusuna bölmek olabilir.

İpuçları talimatlardan farklıdır: İpuçları ipucu olma eğilimindedir; talimatlar ayrıntılıdır. Etkileşim noktasında ipuçları oluşur; talimatlar etkileşim noktasından önce görünür. İpuçları bağlam sağlar; talimatlar kullanımı belirler.

Genel olarak, talimatlar hatayı önlemede etkisizdir. Kullanıcılar, arayüzlerin geçmiş deneyimlerine göre çalışacağını varsayma eğilimindedir ("29 Temmuz 2012"nin ne anlama geldiğini elbette herkes biliyor mu?"). Böylece talimatlar okunmaz. İpuçları, kullanıcıları hatalardan uzaklaştırır.

Hatalardan kaçınmanın başka bir yolu da varsayılanlar sunmaktır. Örneğin, kullanıcılar genellikle *bugün*, *yarın*, *doğum günüm*, *son teslim tarihim* veya *bu formu en son kullandığımda girdiğim tarihe* karşılık gelen değerleri girerler. Bağlama bağlı olarak, bunlardan birinin akıllı varsayılan olarak iyi bir seçim olması muhtemeldir.

Sebep ne olursa olsun, sistemler hatalara karşı toleranslı olmalıdır. Bunu, tüm eylemlere ve özellikle de kullanıcıların verilerini yok etme veya değiştirme potansiyeline sahip eylemlere birden fazla *geri alma* düzeyi sağlayarak yapabilirsiniz.

*Geri al* eylemlerinin günlüğe kaydedilmesi ve analiz edilmesi, arayüzün kullanıcıları sürekli olarak 'yanlış' düğmeye tıklamak gibi bilinçsiz hatalara çektiği yerleri de vurgulayabilir. Bu hatalara genellikle, daha fazla hatayı önlemek için yeniden tasarlayabileceğiniz yanıltıcı ipuçları veya etkileşim dizileri neden olur.

Hangi yaklaşımı seçerseniz seçin, hataların çoğu sistematiktir - kullanıcı ile yazılım arasındaki yanlış anlamaların sonucudur. Kullanıcıların nasıl düşündüğünü, bilgiyi nasıl yorumladığını, karar verdiğini ve veri girdisini anlamak, yazılımınız ve kullanıcılarınız arasındaki etkileşimlerde hata ayıklamanıza yardımcı olacaktır.

[Giles Colborne](http://programmer.97things.oreilly.com/wiki/index.php/Giles_Colborne) Tarafından