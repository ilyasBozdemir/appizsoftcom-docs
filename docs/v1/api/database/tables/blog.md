## Blog Tablosu
### Tablo adı : `blog `

Bu tablo, blog makalelerinin bilgilerini saklamak için kullanılır. Her bir makalenin başlık, içerik, yazar ve diğer ayrıntılarını içerir.


| Alan Adı           | Tür             | Açıklama                                                   |
|--------------------|-----------------|------------------------------------------------------------|
| `id`               | int             | Benzersiz kimlik                                           |                           
| `title`            | varchar(255)    | Blog makalesinin başlığı                                   | 
| `slug`             | varchar(255)    | URL dostu başlık                                           |
| `authorName`       | varchar(100)    | Yazarın adı ve soyadı                                      |
| tags	             |text[]      |	Blog makalesinin etiketleri (dizi olarak)	["DevOps", "Süreç Otomasyonu"]  |   
| `content`          | text            | Blog makalesinin içeriği                                   |
| `imageUrl`         | varchar(255)    | Görsel URL                                                 | 
| `category`         | varchar(50)     | Blog makalesinin kategorisi                                |
| `publishDate`      | datetime        | Makalenin yayınlandığı tarih ve saat (ISO 8601 formatında) | 
| `modifyDate`       | datetime        | Makalenin son düzenleme tarihi (ISO 8601 formatında)       | 

## Kullanım Alanları

1. **Makale Okuma**: Kullanıcılar, makalelerin içeriğini görüntülemek ve okumak için bu tabloyu kullanabilirler. `slug` alanıyla makalenin benzersiz URL'sine erişebilirler.

2. **Etiketlere Göre Listeleme**: Kullanıcılar, belirli bir etikete sahip makaleleri listelemek için `tags` alanını kullanabilirler.

3. **Kategoriye Göre Listeleme**: Makaleleri belirli bir kategoriye göre filtrelemek için `category` alanını kullanabilirler.

4. **Yayın Tarihine Göre Sıralama**: Kullanıcılar, makaleleri yayın tarihine göre sıralayabilirler. `publishDate` alanını kullanarak bu işlemi gerçekleştirebilirler.

5. **Görsel İçeriğe Sahip Makaleler**: Kullanıcılar, görsel içeriğe sahip makaleleri belirlemek için `imageUrl` alanını kullanabilirler.

