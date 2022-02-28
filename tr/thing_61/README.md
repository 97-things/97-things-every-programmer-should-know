# Tek İkili

Yapının, her hedef ortam için özel bir ikili dosya oluşturmak üzere kodun bir bölümünü yeniden yazdığı birkaç proje gördüm. Bu her zaman işleri olması gerekenden daha karmaşık hale getirir ve ekibin her kurulumda tutarlı sürümlere sahip olmama riskini beraberinde getirir. Asgari olarak, her biri daha sonra doğru yere dağıtılması gereken, yazılımın birden çok, neredeyse aynı kopyasının oluşturulmasını içerir. Gerekenden daha fazla hareketli parça anlamına gelir, bu da hata yapmak için daha fazla fırsat anlamına gelir.

Bir keresinde, her özellik değişikliğinin tam bir inşa döngüsü için kontrol edilmesi gereken bir ekipte çalıştım, bu yüzden testçiler küçük bir ayarlamaya ihtiyaç duyduklarında beklemeye bırakıldılar (inşa etmenin de çok uzun sürdüğünü söylemiş miydim?). Ayrıca sistem yöneticilerinin üretim için sıfırdan yeniden oluşturma konusunda ısrar ettiği bir ekipte de çalıştım (bizimle aynı komut dosyalarını kullanarak), bu da üretimdeki sürümün testten geçen sürüm olduğuna dair hiçbir kanıtımız olmadığı anlamına geliyordu. Ve bunun gibi.

Kural basittir: *Yayın ardışık düzenindeki tüm aşamalarda tanımlayabileceğiniz ve tanıtabileceğiniz tek bir ikili dosya oluşturun.* Ortama özgü ayrıntıları ortamda tutun. Bu, örneğin bunları bileşen kapsayıcısında, bilinen bir dosyada veya yolda tutmak anlamına gelebilir.

Ekibiniz bir kod yönetme yapısına sahipse veya tüm hedef ayarları kodla birlikte depoluyorsa, bu, hiç kimsenin tasarımı, uygulamanın özü olan ve platforma özgü özellikleri ayırmak için yeterince dikkatli düşünmediğini gösterir. Ya da daha kötüsü olabilir: Ekip ne yapacağını biliyor ama değişikliği yapma çabasına öncelik veremiyor.

Elbette istisnalar vardır: Önemli ölçüde farklı kaynak kısıtlamalarına sahip hedefler için inşa ediyor olabilirsiniz, ancak bu, "veritabanını ekrana ve tekrar ekrana" yazan çoğumuz için geçerli değildir. Alternatif olarak, şu anda düzeltmesi çok zor olan bazı eski karışıklıklarla yaşıyor olabilirsiniz. Bu gibi durumlarda, kademeli olarak hareket etmeniz gerekir, ancak mümkün olan en kısa sürede başlayın.

Ve bir şey daha: Ortam bilgilerini de sürümlü tutun. Bir ortam yapılandırmasını bozmak ve neyin değiştiğini bulamamak kadar kötü bir şey yoktur. Çevresel bilgiler, farklı oranlarda ve farklı nedenlerle değişeceğinden, koddan ayrı olarak versiyonlanmalıdır. Bazı ekipler bunun için dağıtılmış sürüm kontrol sistemleri kullanır (pazar ve git gibi), çünkü üretim ortamlarında yapılan değişiklikleri - kaçınılmaz olarak olduğu gibi - depoya geri göndermeyi kolaylaştırır.

[Steve Freeman](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Freeman) Tarafından