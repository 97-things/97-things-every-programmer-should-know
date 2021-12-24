# Akıllı Kodlama

Yazılımın doğruluğu hakkında elle akıl yürütmeye çalışmak, koddan daha uzun ve koddan daha fazla hata içerme olasılığı daha yüksek olan resmi bir kanıtla sonuçlanır. Otomatik araçlar tercih edilir, ancak her zaman mümkün değildir. Aşağıdakiler bir orta yolu tanımlar: doğruluk hakkında yarı resmi olarak akıl yürütme.

Temel yaklaşım, incelenen tüm kodu kısa bölümlere, örneğin bir fonksiyon çağrısı gibi tek bir satırdan on satırdan daha az bloklara bölmek ve bunların doğruluğunu tartışmaktır. Argümanların yalnızca şeytanın avukatlığını yapan içindeki yazılımcıyı ikna edecek kadar güçlü olması gerekir.

Her uç noktada *programın durumu*(yani, program sayacı ve tüm "canlı" nesnelerin değerleri) kolayca açıklanan bir özelliği karşılayacak ve o bölümün işlevselliğinin (durum dönüşümü) tek bir görev olarak tanımlanması kolay olacak şekilde bir bölüm seçilmelidir, bunlar akıl yürütmeyi kolaylaştırır. Bu tür uç nokta özellikleri, fonksiyonlar için *önkoşul*, *sonkoşul*, döngüler ve sınıflar için (örneklerine göre) *değişmez* gibi kavramları genelleştirir. Bölümlerin mümkün olduğunca birbirinden bağımsız olması için çabalamak, akıl yürütmeyi kolaylaştırır ve bu bölümler değiştirileceği zaman vazgeçilmezdir.

İyi bilinen (belki de daha az takip edilen) ve 'iyi' kabul edilen kodlama uygulamalarının çoğu, akıl yürütmeyi kolaylaştırır. Bu nedenle, yalnızca kodunuz hakkında akıl yürütme niyetiyle, daha iyi bir stil ve yapı düşünmeye başlarsınız. Şaşırtıcı olmayan bir şekilde, bu uygulamaların çoğu statik kod analizörleri tarafından kontrol edilebilir:

- Uzak bölümleri son derece birbirine bağımlı hale getirdikleri için goto deyimlerini kullanmaktan kaçının.
- Değiştirilebilir global değişkenleri kullanmaktan kaçının çünkü bunları kullanan tüm bölümleri bağımlı hale getirir.
- Her değişken mümkün olan en küçük kapsama sahip olmalıdır. Örneğin, yerel bir nesne, ilk kullanımından hemen önce bildirilebilir.
- İlgili olduğunda nesneleri *değişmez(immutable)* yapın.
- Hem yatay hem de dikey boşluk kullanarak kodu okunabilir hale getirin. Örneğin, ilgili yapıları hizalamak ve iki bölümü ayırmak için boş bir çizgi kullanmak.
- Nesneler, türler, fonksiyonlar vb. için açıklayıcı (ancak nispeten kısa) adlar seçerek kodu kendi kendine belgeleyin.
- İç içe bir bölüme ihtiyacınız varsa, onu bir fonksiyon yapın.
- Fonksiyonlarınızı kısa tutun ve tek bir göreve odaklanın. Eski *24 satırlık sınır* hâlâ geçerlidir. Ekran boyutu ve çözünürlüğü değişse de, 1960'lardan bu yana insan bilişinde hiçbir şey değişmedi.
- Fonksiyonların birkaç parametresi olmalıdır (dört iyi bir üst sınırdır). Bu, işlevlere iletilen verileri kısıtlamaz: İlgili parametreleri tek bir nesnede gruplamak, *nesne değişmezlerinden* yararlanır ve tutarlılık ve tutarlılık gibi akıl yürütmeden tasarruf sağlar.
- Daha genel olarak, bir bloktan bir kitaplığa kadar her bir kod birimi *dar bir arayüze* sahip olmalıdır. Daha az iletişim, gerekli muhakemeyi azaltır. Bu, dahili durumu döndüren *alıcıların* bir yükümlülük olduğu anlamına gelir, çalışmak için bir nesneden bilgi istemeyin. Bunun yerine, nesneden zaten sahip olduğu bilgilerle işi yapmasını isteyin. Başka bir deyişle, *kapsülleme* tamamen ve yalnızca *dar arayüzler* ile ilgilidir.
- *değişmezler(invariants)* sınıfını korumak için, *ayarlayıcılar(setters)* bir nesnenin durumunu yöneten değişmezlerin kırılmasına izin verme eğiliminde olduğundan, *ayarlayıcıların* kullanılması önerilmez.

Doğruluğu hakkında akıl yürütmenin yanı sıra, kodunuz hakkında tartışmak size onu anlamanızı sağlar. Kazandığınız bilgileri herkesin yararına iletin.

[Yechiel Kimchi](http://programmer.97things.oreilly.com/wiki/index.php/Yechiel_Kimchi) Tarafından
