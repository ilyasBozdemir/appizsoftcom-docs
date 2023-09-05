## Kullanıcı Rol Tablosu

### Tablo adı : `user_roles`

| Alan Adı      | Tür       | Zorunluluk | Açıklama                        | Örnek Değer                   |
| ------------- | --------- | ---------- | ------------------------------- | ----------------------------- |
| `role_id`     | int       | Zorunlu    | Rol kimliği (benzersiz)       | unique id, sistem belirler bunu |
| `name`        | varchar   | Zorunlu    | Rolün adı                       | "Admin" veya "Kullanıcı"      |
| `description` | varchar   | Opsiyonel  | Rolün açıklaması                | "Sistem yöneticisi"           |
