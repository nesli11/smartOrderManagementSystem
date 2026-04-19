# smartOrderManagementSystem

## 1. Koleksiyonların Gerçek Hayattaki Karşılıkları 

Genel olarak koleksiyonlar bize aynı türdeki veya birbiriyle ilişkili verileri bir arada tutma imkanı sağlar. Bu da tekrarlı işlemlerden kaçınmamıza yardımcı olur ve kodun okunabilirliğini artırır.

### Listeler (Lists)
Sıralıdırlar ve aynı eleman birden fazla kez bulunabilir. Marketten alınacaklar listesi gibidir; eleman eklenebilir, çıkarılabilir veya güncellenebilir.

### Sözlükler (Dictionaries)
Telefon rehberindeki isim-numara eşleşmesi veya bir otel koridorundaki oda-anahtar ilişkisi gibidir. Her anahtar (Key) benzersizdir ve bizi doğrudan bir değere (Value) götürür.

### Kümeler (Sets)
Bir çekiliş torbasındaki farklı isimler gibi eşsiz elemanlardan oluşur. Sırasızdır ve asla tekrar eden eleman barındırmaz.

### Demetler (Tuples)
En önemli özellikleri değiştirilemez (immutable) olmalarıdır. Program boyunca sabit kalması gereken, güvenli ve salt okunur veri gruplarını temsil eder. Örneğin; bir koordinat bilgisi veya bir kaydın oluşturulma tarihi.

## 2. List vs Set vs Tuple Farkları

| Özellik | List (Liste) | Set (Küme) | Tuple (Demet) |
| :--- | :---: | :---: | :---: |
| **Yazım Biçimi** | `[a, b, c]` | `{a, b, c}` | `(a, b, c)` |
| **Sıralama (Ordered)** | Evet (İndeksli) | Hayır (Sırasız) | Evet (İndeksli) |
| **Değiştirilebilirlik** | Değiştirilebilir (Mutable) | Değiştirilebilir (Mutable) | Değiştirilemez (Immutable) |
| **Tekrar Eden Eleman** | İzin Verir | İzin Vermez (Unique) | İzin Verir |
| **En Yaygın Kullanım** | Veri ekleme/silme | Tekrarları engelleme | Sabit veriler/Güvenlik |

## 3. Bool ve If Kontrollerinin Sistem Mantığındaki Rolü

Bir sistem kurarken var-yok, doğru-yanlış (Boolean) mekanizması sistemin karar merkezidir. Bu mantık, bir sonuca varmamızdaki en önemli etkendir. Örneğin akıllı ev sisteminde; "Hava karanlık mı?" sorusunun cevabı `True` ise ışıklar yanar, `False` ise sönük kalır. 

Bu mantığın otomasyonun temeli olduğu söylenebilir; çünkü bu değerler sistemin o anki durumunu hafızada tutar. Sonuç olarak; Bool değerler ve if kontrolleri, sistemin stratejik yol haritasını belirler. Bu yapı taşları olmadan, bir yazılımın dış dünyaya tepki vermesi ve otonom bir kimlik kazanması mümkün değildir.

## 4. Bu Projede Hangi Veri Yapısı Neden Seçildi?

Proje içerisinde her veri yapısı, sunduğu avantajlara ve verinin işlenme ihtiyacına göre belirli görevlerde kullanılmıştır:

* **Liste (List):** `orders` ve `musteri_listesi` değişkenlerinde tercih edilmiştir. Siparişler geldikçe listeye yeni veriler eklenmesi gerektiği için listelerin esnek ve güncellenebilir yapısından yararlanılmıştır.
* **Sözlük (Dictionary):** Her bir siparişin detaylarını (müşteri adı, ödeme durumu, tutar) saklamak amacıyla kullanılmıştır. Bu sayede veriler "anahtar-değer" (key-value) ilişkisiyle gruplandırılarak daha organize ve erişilebilir bir yapı kurulmuştur.
* **Küme (Set):** `temizlenmis_musteri_listesi` ve `temizlenmis_urunler` bölümlerinde tercih edilmiştir. Sistemdeki **tekrar eden kayıtları** (örneğin aynı müşterinin birden fazla görünmesi veya ürün çeşitlerinin tespiti) tek bir işlemle ayıklamak ve veri setini sadeleştirmek amacıyla kullanılmıştır.
* **Demet (Tuple):** `siparis_ozeti` değişkeninde kullanılmıştır. Müşteri ismi ve toplam tutar ikilisi birer "veri paketi" haline getirilmiş; demet yapısının değiştirilemez (immutable) özelliği sayesinde bu özet bilgilerin işlem sonunda korunması sağlanmıştır.
