# Kodu Kaldırarak İyileştirin

*Az* ama öz. Bu oldukça basmakalıp küçük bir özdeyiş, ama bazen gerçekten de doğru.

Son birkaç hafta içinde kod tabanımızda yaptığım iyileştirmelerden biri, onun parçalarını kaldırmak.

Yazılımı, YAGNI (yani, İhtiyacınız Olmayacak(You Aren't Gonna Need It)) dahil olmak üzere XP ilkelerini izleyerek yazdık. İnsan doğası ne ise, kaçınılmaz olarak birkaç yerde yetersiz kaldık.

Ürünün belirli görevleri yerine getirmesinin çok uzun sürdüğünü gözlemledim, neredeyse anında olması gereken basit görevlerdi. Bunun nedeni, aşırı uygulanmış olmalarıydı; Gerekmeyen ekstra çan ve ıslıklarla süslenmişti, ama o zamanlar iyi bir fikir gibi görünüyordu.

Bu nedenle, kodu basitleştirdim, ürün performansını iyileştirdim ve yalnızca rahatsız edici özellikleri kod tabanından kaldırarak global kod entropisi seviyesini düşürdüm. Yararlı bir şekilde, birim testlerim bana operasyon sırasında başka hiçbir şeyi kırmadığımı söylüyor.

Basit ve tamamen tatmin edici bir deneyim.

Öyleyse neden gereksiz kod ilk etapta orada kaldı? Neden bir yazılımcı fazladan kod yazma ihtiyacı hissetti ve bu, gözden geçirme veya eşleştirme sürecini nasıl geçti? Neredeyse kesinlikle şöyle bir şey:

- Eğlenceli ekstra bir şeydi ve yazılımcı bunu yazmak istedi. *(İpucu: Kod yazın, sizi eğlendirdiği için değil değer kattığı için yazın.)*
- Birisi gelecekte gerekli olabileceğini düşündü, bu yüzden şimdi kodlamanın en iyisi olduğunu düşündü. *(İpucu: Bu YAGNI değil. Şu anda ihtiyacınız yoksa hemen yazmayın.)*
- O kadar büyük bir "ekstra" gibi görünmüyordu, bu yüzden gerçekten gerekli olup olmadığını görmek için müşteriye geri dönmek yerine uygulamak daha kolaydı. *(İpucu: Fazladan kod yazmak ve korumak her zaman daha uzun sürer. Ve müşteriye aslında oldukça ulaşılabilir. Fazladan küçük bir kod parçası zamanla kartopu yaparak bakım gerektiren büyük bir iş parçasına dönüşür.)*
- Yazılımcı, ek özelliği haklı çıkaran ne belgelenmiş ne de tartışılmış ek gereksinimler icat etti. Gereksinim aslında sahteydi. *(İpucu: Sistem gereksinimlerini yazılımcılar belirlemez; müşteri yapar.)*

Şu an ne üzerinde çalışıyorsunuz? Hepsi gerekli mi?

[Pete Goodliffe](http://programmer.97things.oreilly.com/wiki/index.php/Pete_Goodliffe) Tarafından
