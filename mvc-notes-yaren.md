# ASP.NET MVC Notları

## HTTP Metodları

### HttpGet

- Kullanıcıdan veri almak için (öğrenci oluşturma formu, güncelleme formu)

### HttpPost

- Kullanıcının gönderdiği veriyi işlemek ve kaydetmek için (öğrenci oluşturma ve güncelleme işlemleri)

## Data Annotations ve Validasyon

- `[Required]` => Boş geçilemez demektir
- Data Annotations özellikleri veri doğrulama için kullanılmıştır
  - `[Required]`
  - `[MaxLength(40)]`
  - `[Length(8,8)]`

## Layout ve View Yapısı

### Layout

- Şablondur aslında web sayfasının genel yapısını belirler
- Uygulamanın her sayfasında ortak olan öğeleri içerir (örneğin başlık, footer)

### @ViewData["Title"]

- Bu her sayfa için farklı bir başlık görüntülenmesini sağlar

### @RenderBody()

- Şablonun içeriğine yer tutucu işlevi görür
- Şablon kullanıldığında sayfada dinamik olarak içeriklerin gösterir (özgün)

## Program.cs ve Routing

### Program.cs

- Program.cs dosyasındaki CreateBuilder() metodu ile program başlatılır
- Geleneksel yönlendirmeler program.cs içinde yapılır (Conventional routing)
- Default yönlendirme => Home/Index'tir
- Ana tanımlamada routeler ile bu yönlendirmeler değişebilir

## MVC Mimarisi Çalışma Mantığı

### Model (Veri Yönetimi)

- Veriyi temsil eder ve işler
- Veritabanından gelen bilgileri işler
- Controller ile haberleşerek veriyi View'e gönderir
- Veri doğrulama (validation) yapar
- İş mantığını yönetir

### View (Kullanıcı Arayüzü)

- Veriyi kullanıcıya gösterir
- Kullanıcıya gösterilecek arayüzü oluşturur
- HTML + Razor syntax ile dinamik sayfa oluşturur
- Controller'dan gelen model verisini işler

### Controller (İş mantığı ve yönlendirme)

- Kullanıcıdan gelen istekleri işler ve uygun yanıtı döndürür
- Modelden veri alıp View'e gönderir
- Get, post vb. isteklerini yönetir
- Kullanıcıdan gelen girişleri kontrol eder
- Controller'de metodlar Action'lar oluyor

## View Bileşenleri

### ViewBag

- Controller'dan View'e veri göndermemizi sağlar

### return View(students)

- students listesini View'e göndermektedir

## HTML Helpers

- Normalde HTML tagları arasına yazabileceğimiz HTML kodlarını Razor içinde dinamik olarak bağlar
- @Html.TextBox()
- @Html.TextArea()

### @RenderSection()

- Sayfalara özel içerik eklenmesini sağlar

## Entity Framework ve Veritabanı

### ORM (Object Relational Mapping)

- EF Core veritabanına erişimi kolaylaştıran ORM aracıdır

### DbContext

- Entity Framework Core'un veritabanı ile iletişimini sağlayan ana sınıftır
- CRUD işlemleri yapılmasını sağlar

### DbSet<>

- EF Core'da bir veritabanı tablosunu temsil eder

## View'da Model Kullanımı

- View dosyalarında model verisi kullanmak için @model ile Model tanımlanır
- Örnek: `@model Week1_2.Models.Student`
- Modelden gelen veriyi ekrana yazar

## Routing (Yönlendirme)

### route

- Yoldur

### attribute routing

- Özellik yönlendirme
- Controller veya metot seviyesinde route belirlemeye yarar
- Mesela HomeController: Controller üstüne yazarsak tüm action'lar o yolla çağrılır
- Home => Ev yada ne isim vermişsek o olur
