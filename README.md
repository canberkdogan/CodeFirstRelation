# CodeFirstRelation

# Code First Relation - Entity Framework Core

Bu proje, Entity Framework Core kullanarak **Code First** yaklaşımı ile bir veritabanı ve tablolar oluşturmayı amaçlamaktadır.

## Veritabanı Tabloları

### 1. User Tablosu
- **Id**: `int` (Birincil anahtar ve otomatik artan)
- **Username**: `string` (Kullanıcının kullanıcı adı)
- **Email**: `string` (Kullanıcının e-posta adresi)

### 2. Post Tablosu
- **Id**: `int` (Birincil anahtar ve otomatik artan)
- **Title**: `string` (Gönderinin başlığı)
- **Content**: `string` (Gönderinin içeriği)
- **UserId**: `int` (Gönderiyi oluşturan kullanıcı)

Bir kullanıcının birden fazla gönderisi olabilir ancak her gönderi sadece bir kullanıcıya aittir.

## Entity Sınıfları

### User.cs

```csharp
public class User
{
    public int Id { get; set; }
    public string Username { get; set; }
    public string Email { get; set; }

    // Bir kullanıcının birden fazla gönderisi olabilir.
    public ICollection<Post> Posts { get; set; }
}
