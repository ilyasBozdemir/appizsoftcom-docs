# Kimlik Doğrulama İşlemleri (Auth)
## Özet

### Kullanıcı (User) Tablosu

Kullanıcılar için temel bilgilerin saklandığı tablodur.

| Sütun Adı     | Tür          | Açıklama                            |
| ------------- | ------------ | ----------------------------------- |
| `user_id`     | int          | Kullanıcının benzersiz kimliği      |
| `role_id`     | int          | Kullanıcının rol kimliği (örneğin, "Admin" rolü için 1, "Kullanıcı" rolü için 2, vb.)  |
| `username`    | varchar(50)  | Kullanıcının kullanıcı adı          |
| `email`       | varchar(100) | Kullanıcının e-posta adresi         |
| `password_hash`| varchar(255)| Kullanıcının şifresi (hash değeri)  |
| `name`        | varchar(100) | Kullanıcının adı                    |
| `last_name`   | varchar(100) | Kullanıcının soyadı                 |
| `created_at`  | datetime     | Kullanıcının hesap oluşturma tarihi |
| `updated_at`  | datetime     | Kullanıcının son güncelleme tarihi  |
| `last_login`  | datetime     | Son oturum açma tarihi              |

### Kullanıcı Auth Endpointleri

Kullanıcı kimlik doğrulama (auth) işlemleri için aşağıdaki endpointler kullanılabilir:


#### 1. Kullanıcı Kayıt (Register)

Bu endpoint, kullanıcıların kayıt olmasını sağlar.

- URL: `/api/v1/auth/register`
- Yöntem: POST
#### 2. Kullanıcı Girişi (Login)

Kullanıcıların hesaplarına giriş yapmalarını sağlar.

- URL: `/api/v1/auth/login`
- Yöntem: POST

#### 3. Oturumu Sonlandırma (Logout)

Kullanıcıların oturumlarını sonlandırmalarını sağlar.

- URL: `/api/v1/auth/logout`
- Yöntem: POST

#### 4. Şifremi Unuttum (Forgot Password)

Kullanıcıların şifrelerini sıfırlamalarını sağlar.

- URL: `/api/v1/auth/forgot-password`
- Yöntem: POST


#### 5. Token Yenileme (Refresh Token)

Geçerli bir erişim tokenini yeniler.

- URL: `/api/v1/auth/refresh-token`
- Yöntem: POST

####  6. Hesap Doğrulama (Verify Email)

Kullanıcıların e-posta adreslerini doğrulamalarını sağlar.

- URL: `/api/v1/auth/verify-email`
- Yöntem: POST

#### 7. İki Faktörlü Kimlik Doğrulama (Two-Factor Authentication)

# 1. Auth Register

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

##  2. Giriş (Login)

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
