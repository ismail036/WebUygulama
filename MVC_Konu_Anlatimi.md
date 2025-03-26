# MVC Konu Anlatımı

## 1. MVC Nedir? (Model-View-Controller Mimari Yapısı)
MVC (Model-View-Controller) bir yazılım mimarisi desenidir ve uygulamaları modüler halinde bölerek geliştirmenin bir yolunu sunar.

- **Model:** Veri katmanı, iş mantığını içerir ve veritabanı ile etkileşim kurar.
- **View:** Kullanıcı arayüzü sunum katmanıdır. HTML, CSS ve Razor kodlarından oluşur.
- **Controller:** Kullanıcı isteklerini ele alan ve Model ile View arasında bir köprü oluşturan bölüm.

## 2. Model Katmanı (Entity, DTO, İş Mantığı, Veri Erişimi)
- **Entity Sınıfları:** Veritabanındaki tabloları temsil eden sınıflardır.
- **DTO (Data Transfer Object):** Veri transferi için kullanılan nesnelerdir.
- **Veri Erişim:** Entity Framework kullanılarak DbContext sınıfları yardımıyla gerçekleştirilir.

## 3. View Katmanı (Razor Syntax, HTML Helpers, Partial Views)
- **Razor Syntax:** Dinamik HTML oluşturmak için kullanılır (@ ile başlayan kod blokları).
- **HTML Helpers:** Form elementleri ve linkler gibi HTML içeriğini programatik olarak oluşturur (@Html.TextBox, @Html.DropDownList vb.).
- **Partial Views:** Tekrarlayan arayüz bölümlerini (header, footer vb.) parçalara ayırarak yeniden kullanım sağlar.

## 4. Controller Katmanı (Routing, Action Metodları, Model Binding)
- **Routing:** Kullanıcı isteklerinin doğru controller'a ve action'a yönlendirilmesini sağlar.
- **Action Metodları:** HTTP isteklerini karşılayan metodlardır (GET, POST, PUT, DELETE).
- **Model Binding:** Kullanıcıdan gelen verilerin otomatik olarak Model nesnelerine dönüştürülmesini sağlar.

## 5. Form İşlemleri ve Veri Bağlama (asp-for Kullanımı, Form Validasyonları)
- **asp-for:** HTML formlarındaki input alanlarını model property'leriyle bağlamak için kullanılır.
- **Validasyonlar:** `[Required]`, `[MaxLength]` gibi attribute'larla veri doğrulama kuralları belirlenir.

## 6. Dependency Injection ve Servis Kullanımı (Scoped, Singleton, Transient)
- **Scoped:** Her HTTP isteği için yeni bir instance oluşturur.
- **Transient:** Her kullanıldığında yeni bir nesne oluşur.
- **Singleton:** Uygulama boyunca tek bir instance kullanılır.

## 7. Önbellekleme Stratejileri (Client-Side, Server-Side, Database Caching)
- **Client-Side Caching:** Tarayıcı tarafında veri saklanır.
- **Server-Side Caching:** Sunucu tarafında veri saklanarak performans arttırılır.
- **Database Caching:** Sorgu sonuçlarının önbelleğe alınması.

## 8. DbContext ve Veritabanı İşlemleri (Entity Framework Core, Migration)
- **DbContext:** Veritabanı bağlantısını yönetir.
- **Migration:** Veritabanında yapılan değişikliklerin takip edilmesini sağlar (`Add-Migration`, `Update-Database`).

## 9. Generic Repository Pattern ve Dependency Injection ile Kullanımı
- **Generic Repository:** Veri erişim için tekrar eden kodların önüne geçmek için kullanılır.
- **Dependency Injection ile Repository Kullanımı:** Repository'ler servisler aracılığıyla enjekte edilir.

## 10. Redis Cache Kullanımı (Servis Implementasyonu ve Hataları)
- **Redis Cache:** Anahtar-değer yapısında hızlı veri saklama yöntemidir.
- **Bağlantı ve Kullanım:** `ConnectionMultiplexer.Connect` metodu ile Redis sunucusuna bağlanılır.
- **Kod Hataları:** Interface implementasyonu hataları, Şifreleme hataları gibi durumlar Redis implementasyonlarında yaygındır.
