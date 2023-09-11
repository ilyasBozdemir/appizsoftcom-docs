## Kimlik Doğrulama İşlemleri (Auth)

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

### Oturumu Sonlandırma (Logout)

Kullanıcının oturumunu sonlandırmak için kullanılır.

- **Yöntem**: POST
- **Endpoint**: `/api/v1/auth/logout`

### Şifremi Unuttum (Forgot Password)

Şifre sıfırlama talebi için kullanılır.

- **Yöntem**: POST
- **Endpoint**: `/api/v1/auth/forgot-password`

### Şifre Sıfırlama (Reset Password)

Şifre sıfırlama talebi için kullanılır.

- **Yöntem**: POST
- **Endpoint**: `/api/v1/auth/reset-password`

--- devamı gelicek
