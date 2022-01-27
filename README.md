BIRCH KÜMELEME ALGORİTMASI


Kümeleme Nedir?
Clustering ( Kümeleme ) bir veri setinde benzer özellikler gösteren verilerin gruplara ayrılmasına denir. Aynı küme içinde benzerlikler fazla, kümeler arası benzerlikler azdır. Unsupervised Learning ( Gözetimsiz öğrenme ) vardır yani önceden herhangi bir bilgi verilmez.
Kümelemenin amacı, bir grup etiketlenmemiş veride içsel gruplamayı belirlemektir.

Birch Kümeleme Algoritması
BIRCH (Balanced Iterative Reducing and Clustering using Hierarchies) algoritması özellikle büyük boyutlu verilerin kümelenmesi için tasarlanmıştır.Hiyerarşik kümeleme gerçekleştirmek için kullanılan denetimsiz bir veri madenciliği algoritmasıdır. Artımlı ve sıradüzensel bir teknik kullanılmaktadır. Kümeleme için gerekli bilgiyi yakalama amacıyla bir ağaç oluşturulur. BIRCH iki önemli kavram üzerine kurulmuştur: Küme niteleyici (clustering feature) ve küme niteleyici ağacı (clustering feature tree).  Hem bellek, hem de zaman bakımından doğrusaldır. Algoritmanın etkili çalışmasında eşik değerinin seçimi çok önemlidir. Eğer eşik değeri uygun değilse ağacın tekrar tekrar baştan oluşturulması gerekebilir. 
Birch Algoritma Karmaşıklığı : O(n)
Küme niteleyici, küçük gruplar halindeki veri nesnelerinden oluşturulan alt kümeleri ana bellekte temsil edecek olan üç adet parametreden oluşan yapıdır. 
Kullandığımız formüller : 
![image](https://user-images.githubusercontent.com/59260491/151447008-59883def-6b7d-4387-a061-fc209cd7dd05.png)

BIRCH algoritmasının çalışması iki aşamada gerçekleşir: 
1) Birinci aşamada bütün veritabanı taranarak birleştirici hiyerarşik algoritmalardaki gibi önceden belirlenen N sayısı kadar veri içeren küçük alt kümeler oluşturulur. Bu alt kümelerin her biri için CF değeri hesaplanır. Bu CF değerleri veritabanına oranla çok daha az yer kapladığı için ana bellekte tutulur. Bulunan CF değerleri kullanılarak CF ağaçları oluşturulur. CF ağaçları için iki parametre söz konusudur: Dallanma katsayısı (branching factor) ağaçta en fazla kaç adet yaprak olacağını belirtir, eşik (threshold) değeri ise yapraklarda oluşturulacak küme sayısının çapının en fazla ne kadar olacağını belirler. 
2) Ana bellekte oluşturulan CF ağacı gerçek veritabanının küme yapısını yansıttığı için CF nesneleri üzerinde herhangi bir bölümleme ya da hiyerarşik algoritma kullanılarak kümeleme işlemi kolaylıkla gerçekleştirilebilir.
![image](https://user-images.githubusercontent.com/59260491/151447053-9231e7ec-aaef-4537-b1c8-bfd37ad1c788.png)

BIRCH tek başına bir kümeleme algoritması değil, verinin ana belleğe sığmayacak kadar büyük boyutlarda olduğu durumlarda veritabanının ana belleğe sığacak bir modelini oluşturmaya imkan veren bir algoritmadır. Bu yüzden BIRCH algoritması diğer kümeleme yöntemleri için ön işlem aşaması olarak da kullanılır. 
BIRCH algoritmasının avantajları: Veritabanı yapısını ana belleğe sığdırdığı için I/O miktarını azaltarak performansı arttırır, tek bir tarama ile veritabanının modelini oluşturabilir, hesaplanabilir karmaşıklığı O(n) olduğu için çok fazla işlem gücü gerektirmez. 
Dezavantajları: Yalnızca sayısal verilerde kullanılabilir, verilerin okunma sırasına duyarlıdır, tüm hiyerarşik algoritmalarda olduğu gibi sadece dairesel kümeleri bulabilir.
