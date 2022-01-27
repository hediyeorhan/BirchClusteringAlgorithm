<h1 align="center" style="color:red;">BIRCH KÜMELEME ALGORİTMASI</h1>


<h2>Kümeleme Nedir?</h2>
Clustering ( Kümeleme ) bir veri setinde benzer özellikler gösteren verilerin gruplara ayrılmasına denir. Aynı küme içinde benzerlikler fazla, kümeler arası benzerlikler azdır. Unsupervised Learning ( Gözetimsiz öğrenme ) vardır yani önceden herhangi bir bilgi verilmez.
Kümelemenin amacı, bir grup etiketlenmemiş veride içsel gruplamayı belirlemektir.

<h2>Birch Kümeleme Algoritması</h2>
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

<h2>Örnek bir veri seti üzerinden birch kümeleme algoritmasının çalışma mantığını adım adım inceleyelim : </h2>

![image](https://user-images.githubusercontent.com/59260491/151447305-40dfdeeb-a222-4860-9d71-e6d9fd476dd9.png)

![image](https://user-images.githubusercontent.com/59260491/151447339-44cc8b5c-df14-45f9-a9fe-014b34b5ceea.png)

![image](https://user-images.githubusercontent.com/59260491/151447364-e14b7bad-c715-4100-954b-b6cfcb69e6b2.png)

![image](https://user-images.githubusercontent.com/59260491/151447400-c6a8e095-d1a9-4b7b-9d64-46cd1890ac8c.png)

![image](https://user-images.githubusercontent.com/59260491/151447421-a6a62e3c-2e24-423a-a8d0-b5d297a26037.png)

![image](https://user-images.githubusercontent.com/59260491/151447437-1abb2832-86bd-4bb8-bf2b-1d86c6b3a389.png)

![image](https://user-images.githubusercontent.com/59260491/151447463-748cbb5e-d9e3-45c2-a667-c80e48f81342.png)

<h2>KAYNAKÇA :</h2> 

•	Zhang T., Ramakrishman R., Livny M., BIRCH: An Effective Data Clustering Method for Very Large Databases, ACM SIGMOD Record, Vol. 25, No. 2, pages 103-114, 1996.

•	(Lecture Notes in Computer Science 4165 _ Information Systems and Applications, incl. Internet_Web, and HCI) Chao Yao, Lingyu Wang, Sean X. Wang, Sushil Jajodia (auth.), Willem Jonker, Milan Petković

•	https://scikit-learn.org/stable/modules/generated/sklearn.cluster.Birch.html

•	http://dspace.kocaeli.edu.tr:8080/xmlui/bitstream/handle/11493/973/197927.pdf?sequence=1&isAllowed=y

•	https://www.geeksforgeeks.org/ml-birch-clustering/

•	http://acikerisim.pau.edu.tr/xmlui/bitstream/handle/11499/1219/Mustafa%20Se%C3%A7kin%20Durmu%C5%9F.pdf?sequence=1&isAllowed=y



