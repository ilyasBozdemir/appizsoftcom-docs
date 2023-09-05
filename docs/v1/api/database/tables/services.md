## Hizmetler Tablosu
### Tablo adı : `services`

Bu tablo, sunulan hizmetlerin bilgilerini saklamak için kullanılır. Her bir hizmetin detaylarını içerir.


| Alan Adı        | Tür       | Açıklama                  | Örnek Değer                              |
| --------------- | --------- | ------------------------- | ---------------------------------------- |
| `id`             | serial    | Servis kimliği (benzersiz)| unique id, sistem belirler                |
| `slug`           | varchar   | Servis URL'si             | "web-development-service" gibi            |
| `title`          | varchar   | Servis Başlığı            | "Web Geliştirme Hizmeti"                 |
| `img`            | varchar   | Servis İkon URL'si        | "/path/to/icon.png" gibi                 |
| `metaDesc`       | text      | Meta Açıklama             | "Web geliştirme hizmetleri sunuyoruz."    |
| `content`        | text      | Servis İçeriği            | "Web geliştirme hizmetimiz ... detaylar."|
| `serviceCategory`| varchar | Servis Kategorisi         | "Web Development" gibi                  |

## Kullanım Alanları

1. **Servis Detayları Görüntüleme**: Müşteriler veya kullanıcılar, sunulan hizmetlerin detaylarını incelemek için bu tabloyu kullanabilirler. `slug` alanıyla servisin benzersiz URL'sine erişebilirler.

2. **Servis Kategorilerine Göre Listeleme**: Kullanıcılar, belirli bir hizmet kategorisine ait tüm servisleri listelemek için `serviceCategory` alanını kullanabilirler.

3. **Servis Arama**: Kullanıcılar, belirli bir anahtar kelimeye göre servisleri arayabilirler. `title` veya `metaDesc` alanlarını kullanarak arama yapılabilir.

## Data Fetching Kullanım Alanları

1. **Servis Listesi Getirme**: Tüm servisleri veya belirli bir kategoriye ait servisleri getirmek için, `/api/v1/services` endpointi kullanılır.

2. **Servis Detaylarını Getirme**: Belirli bir servisin detaylarını getirmek için, `/api/v1/services/{slug}` endpointi kullanılır. `{slug}` URL içinde belirtilmelidir.

3. **Yeni Servis Ekleme**: Yeni bir servis eklemek için, `/api/v1/services` endpointine POST isteği gönderilir. İstek gövdesinde servis bilgileri bulunur.

4. **Servis Güncelleme**: Mevcut bir servisi güncellemek için, `/api/v1/services/{slug}` endpointine PUT isteği gönderilir. `{slug}` URL içinde belirtilmelidir.

5. **Servis Silme**: Bir servisi silmek için, `/api/v1/services/{slug}` endpointine DELETE isteği gönderilir. `{slug}` URL içinde belirtilmelidir.

Bu kullanım alanları ve data fetching işlemleri, `services` tablosunu kullanarak hizmetlerin yönetilmesi ve sunulması için rehberlik eder.
