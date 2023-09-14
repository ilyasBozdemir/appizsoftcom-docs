## Kimlik Doğrulama İşlemleri (Auth)

# Auth Register

Bu endpoint, kullanıcıların kayıt olmasını sağlar.

**URL:** `/api/v1/auth/register`

**Yöntem:** POST

## İstek Parametreleri

| Sütun Adı     | Tür          | Açıklama                            |
| ------------- | ------------ | ----------------------------------- |
| `user_id`       | int          | Kullanıcının benzersiz kimliği      |
| `role_id`       | int          | örneğin, "Admin" rolü için 1, "Kullanıcı" rolü için 2, vb.     | // FK user_roles
| `username`      | varchar(50)  | Kullanıcının kullanıcı adı          |
| `email`         | varchar(100) | Kullanıcının e-posta adresi         |
| `password_hash` | varchar(255) | Kullanıcının şifresi (hash değeri)  |
| `name`     | varchar(100) | Kullanıcının adı                |
| `last_name`     | varchar(100) | Kullanıcının soyadı                |
| `created_at`    | datetime     | Kullanıcının hesap oluşturma tarihi |
| `updated_at`    | datetime     | Kullanıcının son güncelleme tarihi  |
| `last_login`    | datetime     | Son oturum açma tarihi              |

## Başarı Durumu (HTTP 200)

Başarılı bir kayıt işlemi sonrasında HTTP 200 başarı durumu döner ve kaydedilen kullanıcının bilgilerini içeren JSON yanıtı gönderir.

```json
  {
    "role_id": 2,// 2 = User 
    "username": "kullanici123",
    "email": "kullanici123@example.com",
    "name": "John",
    "last_name": "Doe",
    "created_at": "2023-09-11T12:30:00",
    "updated_at": "2023-09-11T14:45:00",
    "last_login": "2023-09-11T14:30:00"
}
```

## Hata Durumları
Eğer e-posta adresi zaten kayıtlıysa veya gerekli parametreler eksikse, hata durumu döner. 
Örneğin:


```json
{
  "error": "Kullanıcı zaten kayıtlı."
}

```


Bu bölümde, kimlik doğrulama işlemleri için kullanılan API endpointleri açıklanmaktadır.

### Giriş (Login)

Kullanıcı girişi yapmak için kullanılır.

- **Yöntem**: POST
- **Endpoint**: `/api/v1/auth/login`

Örnek Kullanım:

```http
POST /api/v1/auth/login

Content-Type: application/json

```
#### Gövde

```json
{
  "username": "kullanici123",
  "password": "mysecretpassword",
}
```


