## Sayfa SEO ayar Tablosu
### Tablo adı :  ` mespage_seosages `

`page_seo` tablosu, web sitesinin sayfalarının SEO verilerini saklamak için kullanılır. Bu tablo, her sayfanın benzersiz URL kimliği (`page_slug`) ve dil kodu (`language_code`) ile ilişkilendirilmiş SEO verilerini içerir.


| Alan Adı             | Tür            | Açıklama                                                    |
|----------------------|----------------|-------------------------------------------------------------|
| `id`                 | serial         | Benzersiz kimlik (otomatik olarak artan)                   |
| `page_url`           | varchar(255)   | Sayfanın URL'si                                            |
| `language`           | varchar(2)     | Sayfanın dili (örn. 'tr' veya 'en')                       |
| `title`              | varchar(255)   | Sayfa başlığı                                              |
| `description`        | text           | Sayfa açıklaması                                           |
| `keywords`           | varchar(255)[] | Sayfa anahtar kelimeleri (dizi olarak)                     |
| `twitter_card_type`  | varchar(50)    | Twitter Kart Türü (örn. 'summary' veya 'summary_large_image')|
| `twitter_username`    | varchar(50)    | Twitter kullanıcı adı                                      |
| `facebook_app_id`    | varchar(255)   | Facebook Uygulama Kimliği                                  |
| `og_title`           | varchar(255)   | Open Graph başlık                                           |
| `og_description`     | text           | Open Graph açıklama                                        |
| `og_type`            | varchar(50)    | Open Graph türü (örn. 'website' veya 'article')            |
| `og_image_url`       | varchar(255)   | Open Graph resim URL'si                                    |
| `canonical_url`      | varchar(255)   | Sayfanın kanonik URL'si (isteğe bağlı)                    |
| `created_at`         | timestamp      | Oluşturulma tarihi (varsayılan olarak geçerli tarih/saat) |
| `updated_at`         | timestamp      | Güncellenme tarihi (varsayılan olarak geçerli tarih/saat) |

