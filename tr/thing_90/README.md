# Ayrıntılı Log Kaydı Uykunuzu Bozacak

Bir süredir geliştirme veya üretimde olan bir sistemle karşılaştığımda, gerçek sorunun ilk işareti her zaman kirli bir logdur. Ne hakkında konuştuğumu biliyorsun. Bir web sayfasındaki normal bir akışta tek bir bağlantıya tıklandığında, sistemin sağladığı logda bir mesaj akışına neden olur. Çok fazla log kaydı hiç olmadığı kadar işe yaramaz olabilir.

Sistemleriniz benimki gibiyse sizin işiniz bittiğinde başkasının işi yeni başlıyor demektir. Sistem geliştirildikten sonra, umarım müşterilere hizmet veren uzun ve müreffeh bir yaşam sürecektir tabi şanslıysan. Sistem üretimdeyken bir şeylerin ters gittiğini nasıl anlayacaksınız ve bununla nasıl başa çıkacaksınız?

Belki biri sizin yerinize sisteminizi izliyordur ya da belki siz kendiniz izleyeceksiniz. Her iki durumda da, loglar muhtemelen izlemenin bir parçası olacaktır. Bir şey ortaya çıkarsa ve bununla başa çıkmak için uyanmanız gerekiyorsa, bunun iyi bir nedeni olduğundan emin olmak istersiniz. Sistemim ölüyorsa, bilmek istiyorum. Ama sadece bir hıçkırık varsa, güzellik uykumun tadını çıkarmayı tercih ederim.

Birçok sistem için, bir şeylerin yanlış olduğunun ilk göstergesi, bir loga yazılan bir log mesajıdır. Çoğunlukla, bu hata logları olacaktır. Kendinize bir iyilik yapın: İlk günden itibaren, hata loglarına bir şey kaydedilirse, birisinin gecenin bir yarısında sizi bu konuda aramasını ve uyandırmasını istediğinizden emin olun. Sistem testi sırasında sisteminizdeki yükü simüle edebiliyorsanız, gürültüsüz bir hata günlüğüne bakmak da sisteminizin makul ölçüde sağlam olduğunun iyi bir ilk göstergesidir. Ya da değilse bir erken uyarı.

Dağıtılmış sistemler başka bir karmaşıklık düzeyi ekler. Başarısız bir dış bağımlılıkla nasıl başa çıkacağınıza karar vermelisiniz. Sisteminiz çok dağıtılmışsa, bu yaygın bir durum olabilir. Loga kaydetme politikanızın bunu dikkate aldığından emin olun.

Genel olarak, her şeyin yolunda olduğunun en iyi göstergesi, daha düşük öncelikli mesajların mutlu bir şekilde ilerliyor olmasıdır. Her önemli uygulama olayı için yaklaşık bir INFO düzeyinde günlük log istiyorum.

Dağınık bir kütük, üretime ulaştığında sistemin kontrol edilmesinin zor olacağının bir göstergesidir. Log kayıtlarında hiçbir şeyin görünmesini beklemiyorsanız, bir şey göründüğünde ne yapacağınızı bilmek çok daha kolay olacaktır.

[Johannes Brodwall](http://programmer.97things.oreilly.com/wiki/index.php/Johannes_Brodwall) Tarafından