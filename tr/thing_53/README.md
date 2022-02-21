# Bağlayıcı Sihirli Bir Program Değildir

Sık sık (bunu yazmadan hemen önce başıma geldi), birçok programcının kaynak koddan derlenmiş bir dilde statik olarak bağlantılı bir yürütülebilir dosyaya geçme süreciyle ilgili görüşü şudur:

1. Kaynak kodunu düzenleyin
2. Kaynak kodunu nesne dosyalarına derleyin
3. Sihirli bir şey olur
4. Yürütülebilir dosyayı çalıştırın

Adım 3, elbette, bağlama adımıdır. Neden böyle çirkin bir şey söyleyeyim ki? Onlarca yıldır teknik destek yapıyorum ve aşağıdaki soruları tekrar tekrar alıyorum:

- Bağlayıcı, def'in birden fazla kez tanımlandığını söylüyor.
- Bağlayıcı, abc'nin çözülmemiş bir sembol olduğunu söylüyor.
- Yürütülebilir dosyam neden bu kadar büyük?

Ardından "Şimdi ne yapacağım?" genellikle "görünüyor" ve "bir şekilde" ifadeleri birbirine karışmış ve tam bir şaşkınlık havası ile. Bağlama sürecinin büyülü bir süreç olarak görüldüğünü gösteren "görünüyor" ve "bir şekilde", muhtemelen yalnızca sihirbazlar ve büyücüler tarafından anlaşılabilir. Derleme süreci bu tür ifadeleri ortaya çıkarmaz, bu da programcıların genellikle derleyicilerin nasıl çalıştığını veya en azından ne yaptıklarını anladığını ima eder.

Bir bağlayıcı çok aptal, yaya, basit bir programdır. Tek yaptığı, nesne dosyalarının kod ve veri bölümlerini bir araya getirmek, sembollere referansları tanımlarıyla bağlamak, çözülmemiş sembolleri kitaplıktan çıkarmak ve bir yürütülebilir dosya yazmaktır. Bu kadar. Büyü yok! Sihir yok! Bir bağlayıcı yazmanın sıkıcılığı genellikle tamamen gülünç derecede karmaşık dosya biçimlerinin kodunu çözmek ve oluşturmakla ilgilidir, ancak bu bir bağlayıcının temel yapısını değiştirmez.

Diyelim ki bağlayıcı, def'in bir kereden fazla tanımlandığını söylüyor. C, C++ ve D gibi birçok programlama dilinin hem bildirimleri hem de tanımları vardır. Bildirimler normalde aşağıdaki gibi başlık dosyalarına girer:

```
extern int iii;
```

bu da `iii` sembolüne harici bir referans oluşturur. Öte yandan, bir tanım aslında sembol için depolamayı bir kenara bırakır, genellikle uygulama dosyasında görünür ve şöyle görünür:

```
int iii = 3;
```

Her bir sembol için kaç tanım olabilir? *Highlander* filminde olduğu gibi, sadece bir tane olabilir. Peki ya birden fazla uygulama dosyasında bir iii tanımı görünüyorsa?

```
// File a.c
int iii = 3;
```

```
// File b.c
double iii(int x) { return 3.7; }
```

Bağlayıcı, `iii`ün birden çok tanımlı olduğundan şikayet edecektir.

Sadece bir tane olamaz, bir tane olmalı. iii yalnızca bir bildirim olarak görünüyorsa, ancak asla bir tanım değilse, bağlayıcı, iii'ün çözülmemiş bir sembol olduğundan şikayet edecektir.

Bir yürütülebilir dosyanın neden bu boyutta olduğunu belirlemek için, bağlayıcıların isteğe bağlı olarak oluşturduğu harita dosyasına bakın. Bir harita dosyası, yürütülebilir dosyadaki tüm sembollerin adresleriyle birlikte bir listesinden başka bir şey değildir. Bu size kitaplıktan hangi modüllerin bağlandığını ve her modülün boyutunu söyler. Artık şişkinliğin nereden geldiğini görebilirsiniz. Genellikle, neden bağlantılı oldukları hakkında hiçbir fikriniz olmayan kitaplık modülleri olacaktır. Bunu anlamak için, şüpheli modülü kitaplıktan geçici olarak kaldırın ve yeniden bağlayın. Daha sonra oluşturulan tanımsız sembol hatası, o modüle kimin başvurduğunu gösterecektir.

Belirli bir bağlayıcı mesajını neden aldığınız her zaman hemen açık olmasa da, bağlayıcılarla ilgili sihirli bir şey yoktur. Mekanikler basittir; her durumda çözmeniz gereken ayrıntılardır.

[Walter Bright](http://creativecommons.org/licenses/by/3.0/us/) Tarafından