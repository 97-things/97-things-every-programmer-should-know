# İzci Kuralı

İzcilerin bir kuralı vardır: "Kamp alanını her zaman bulduğunuzdan daha temiz bırakın." Yerde bir pislik bulursanız, pisliği kimin yapmış olabileceğine bakmaksızın onu temizlersiniz. Bir sonraki kampçı grubu için kasıtlı olarak çevreyi iyileştirirsiniz. Aslında bu kuralın orijinal şekli, izciliğin babası Robert Stephenson Smyth Baden-Powell tarafından yazılmış, "Bu dünyayı bulduğunuzdan biraz daha iyi bir şekilde terk etmeye çalışın" idi.

Kodumuzdaki benzer bir kuralı izlesek ne olur: "Bir modülü her zaman teslim aldığınızdan daha temiz bir şekilde kontrol edin." Orijinal yazarın kim olduğu önemli değil, ya ne kadar küçük olursa olsun, modülü geliştirmek için her zaman biraz çaba gösterseydik. Sonuç ne olurdu?

Sanırım hepimiz bu basit kuralı izleseydik, yazılım sistemlerimizdeki amansız bozulmanın sonunu görürdük. Bunun yerine, sistemlerimiz geliştikçe yavaş yavaş daha iyi hale gelecekti. Ayrıca, sadece kendi küçük parçalarıyla ilgilenen bireylerden ziyade, sistemi bir bütün olarak önemseyen *ekipler* görürdük.

Bu kuralın çok fazla sorulacağını sanmıyorum. Kontrol etmeden önce her modülü mükemmel hale getirmek zorunda değilsiniz. Kontrol ettiğiniz zamandan *biraz daha iyi* hale getirmeniz yeterlidir. Elbette bu, bir modüle *eklediğiniz* herhangi bir kodun temiz olması gerektiği anlamına gelir. Ayrıca, modülü tekrar kontrol etmeden önce en az bir şeyi daha temizlediğiniz anlamına gelir. Basitçe bir değişkenin adını iyileştirebilir veya uzun bir işlevi iki küçük işleve bölebilirsiniz. Döngüsel bir bağımlılığı kırabilir veya ilkeyi ayrıntıdan ayırmak için bir arabirim ekleyebilirsiniz.

Açıkçası, bu bana sıradan bir nezaket gibi geliyor - tuvaleti kullandıktan sonra ellerinizi yıkamak veya çöpü yere atmak yerine çöp kutusuna atmak gibi. Gerçekten de, kodda bir karışıklık bırakma eylemi, *çöp atmak* kadar sosyal olarak kabul edilemez olmalıdır. *Yapılmamış* bir şey olmalı.

Ama bundan daha fazlası. Kendi kodumuzu önemsemek bir şeydir. Takımın kodunu önemsemek oldukça başka bir şey. Takımlar birbirlerine yardım eder ve birbirlerini temizlerler. İzci kuralına uyuyorlar çünkü bu sadece kendileri için değil herkes için iyi.

[Uncle Bob](http://programmer.97things.oreilly.com/wiki/index.php/Uncle_Bob) Tarafından