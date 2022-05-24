# Unix Araçları Arkadaşlarınızdır

Issız bir adaya sürgüne giderken bir IDE ile Unix araç kutusu arasında seçim yapmak zorunda kalsaydım, hiç düşünmeden Unix araçlarını seçerdim. İşte Unix araçları konusunda uzman olmanız için nedenler.

Birincisi, IDE'ler belirli dilleri hedeflerken, Unix araçları metin biçiminde görünen her şeyle çalışabilir. Her yıl yeni dillerin ve notasyonların ortaya çıktığı günümüzün geliştirme ortamında, Unix tarzında çalışmayı öğrenmek, her zaman karşılığını verecek bir yatırımdır.

Ayrıca, IDE'ler yalnızca geliştiricilerinin tasarladığı komutları sunarken, Unix araçlarıyla hayal edebileceğiniz her görevi gerçekleştirebilirsiniz. Bunları (klasik Pre-Bionicle) Lego blokları olarak düşünün: Küçük ama çok yönlü Unix araçlarını birleştirerek kendi komutlarınızı yaratırsınız. Örneğin, aşağıdaki sıra, Cunningham'ın imza analizinin metin tabanlı bir uygulamasıdır, dosyanın içeriği hakkında çok şey ortaya çıkarabilen her dosyanın noktalı virgül, parantez ve tırnaklardan oluşan bir dizi.

```
for i in *.java; do 
    echo -n "$i: "
    sed 's/[^"{};]//g' $i | tr -d '\n'
    echo
done
```

Ayrıca öğrendiğiniz her IDE işlemi o göreve özeldir; örneğin, bir projenin hata ayıklama derleme yapılandırmasına yeni bir adım eklemek. Buna karşılık, Unix araç becerilerinizi geliştirmek sizi her görevde daha etkili kılar. Örnek olarak, birden çok işlemci mimarisinde çapraz derleme için bir projenin yapısını değiştirmek için önceki komut dizisinde kullanılan sed aracını kullandım.

Unix araçları, çok kullanıcılı bir bilgisayarın 128 kB RAM'e sahip olduğu bir çağda geliştirildi. Tasarımlarındaki ustalık, günümüzde devasa veri kümelerini son derece verimli bir şekilde işleyebilecekleri anlamına geliyor. Çoğu araç, filtreler gibi çalışır ve aynı anda yalnızca tek bir satırı işleyerek işleyebilecekleri veri miktarında bir üst sınır olmadığı anlamına gelir. Yarım terabaytlık İngilizce Wikipedia dökümünde saklanan düzenleme sayısını mı aramak istiyorsunuz? Basit bir çağırma

```
grep '<revision>' | wc –l 
```

cevabı ter dökmeden verecektir. Bir komut dizisini genel olarak yararlı bulursanız, verileri döngülere ve koşullara aktarma gibi bazı benzersiz güçlü programlama yapılarını kullanarak onu kolayca bir shell komut dosyasında paketleyebilirsiniz. Daha da etkileyici bir şekilde, önceki gibi ardışık düzen olarak yürütülen Unix komutları, yüklerini modern çok çekirdekli CPU'ların birçok işlem birimi arasında doğal olarak dağıtacaktır.

Unix araçlarının küçük güzeldir kaynağı ve açık kaynak uygulamaları, set üstü medya oynatıcım veya DSL yönlendiricim gibi kaynakları kısıtlı platformlarda bile onları her yerde kullanılabilir hale getirir. Bu tür cihazların güçlü bir grafik kullanıcı arabirimi sunmaları pek olası değildir, ancak genellikle en yaygın kullanılan araçları sağlayan BusyBox uygulamasını içerirler. Ve Windows üzerinde geliştirme yapıyorsanız, Cygwin ortamı size hem yürütülebilir dosyalar olarak hem de kaynak kodu biçiminde akla gelebilecek tüm Unix araçlarını sunar.

Son olarak, mevcut araçlardan hiçbiri ihtiyaçlarınızı karşılamıyorsa, Unix araçlarının dünyasını genişletmek çok kolaydır. Sadece birkaç basit kurala göre oynayan bir program yazın (istediğiniz herhangi bir dilde): Programınız sadece tek bir görevi yerine getirmelidir; verileri standart girdisinden metin satırları olarak okumalıdır; ve sonuçlarını standart çıktısında başlıklar ve diğer gürültüler tarafından süslenmeden göstermelidir. Aracın çalışmasını etkileyen parametreler komut satırında verilmiştir. Bu kuralları takip edin ve "Dünya ve içindeki her şey sizindir".

[Diomidis Spinellis](http://programmer.97things.oreilly.com/wiki/index.php/Diomidis_Spinellis) Tarafından