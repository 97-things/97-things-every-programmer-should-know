# Geri Adım Atın ve Otomatikleştirin, Otomatikleştirin, Otomatikleştirin

Bir modülde kod satırlarının sayısını üretmesi istendiğinde, dosyaları bir kelime işlemciye yapıştıran ve onun "satır sayısı" özelliğini kullanan programcılarla çalıştım. Ve haftaya tekrar yaptılar. Ve sonraki hafta. Kötüydü.

Kod imzalamayı ve sonucu bir sunucuya taşımayı içeren, çok sayıda fare tıklaması gerektiren, hantal bir dağıtım süreci olan bir proje üzerinde çalıştım. Birisi bunu otomatikleştirdi ve komut dosyası, son test sırasında, beklenenden çok daha sık olarak yüzlerce kez çalıştı. İyiydi.

Öyleyse, neden insanlar geri adım atmak ve otomatikleştirmek için zaman ayırmak yerine aynı görevi tekrar tekrar yapıyorlar?

## Yaygın yanlış anlama #1: Otomasyon yalnızca test amaçlıdır.

Elbette, test otomasyonu harika, ama neden orada dursun? Herhangi bir projede tekrarlanan görevler bol miktarda bulunur: sürüm kontrolü, derleme, JAR dosyaları oluşturma, belge oluşturma, dağıtım ve raporlama. Bu görevlerin çoğu için komut dosyası fareden daha güçlüdür. Sıkıcı görevleri yürütmek daha hızlı ve daha güvenilir hale gelir.

## Yaygın yanlış anlama #2: Bir IDE'm var, bu yüzden otomatikleştirmem gerekmiyor.

Makinemde hiç "Ama bu (kontrol eder|derlenir|testleri geçer)" oldu mu? takım arkadaşlarınızla tartışır mısınız? Modern IDE'lerin binlerce potansiyel ayarı vardır ve tüm ekip üyelerinin aynı konfigürasyonlara sahip olmasını sağlamak esasen imkansızdır. Ant veya Autotools gibi otomasyon sistemleri oluşturun, size kontrol ve tekrarlanabilirlik sağlar.

## Yaygın yanlış anlama #3: Otomatikleştirmek için egzotik araçlar öğrenmem gerekiyor.

İyi bir shell dili (bash veya PowerShell gibi) ve bir yapı otomasyon sistemi ile uzun bir yol kat edebilirsiniz. Web siteleriyle etkileşim kurmanız gerekiyorsa, iMacros veya Selenium gibi bir araç kullanın.

## Yaygın yanlış anlama #4: Bu dosya formatlarıyla baş edemediğim için bu görevi otomatikleştiremiyorum.

Sürecinizin bir kısmı Word belgeleri, elektronik tablolar veya resimler gerektiriyorsa, bunu otomatikleştirmek gerçekten zor olabilir. Ama bu gerçekten gerekli mi? Düz metin kullanabilir misiniz? Virgülle ayrılmış değerler? XML? Bir metin dosyasından çizim oluşturan bir araç mı? Çoğu zaman, süreçteki hafif bir ince ayar, sıkıcılıkta önemli bir azalma ile iyi sonuçlar verebilir.

## Yaygın yanlış anlama #5: Bunu çözecek zamanım yok.

Başlamak için tüm bash veya Ant'ı öğrenmeniz gerekmez. Gittikçe öğren. Otomatikleştirilebileceğini ve otomatikleştirilmesi gerektiğini düşündüğünüz bir göreviniz olduğunda, bunu yapmak için araçlarınız hakkında yeterince bilgi edinin. Ve bunu, zaman bulmanın genellikle daha kolay olduğu bir projede erken yapın. Başarılı olduğunuzda, siz (ve patronunuz) otomasyona yatırım yapmanın mantıklı olduğunu göreceksiniz.

[Cay Horstmann](http://programmer.97things.oreilly.com/wiki/index.php/Cay_Horstmann) Tarafından
