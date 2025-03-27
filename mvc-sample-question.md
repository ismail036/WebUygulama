# ASP.NET Core MVC Örnek Sınav Soruları

## Soru 1

**Soru:** Aşağıdaki Razor syntax'ı ne işe yarar?

```csharp
@model List<Student>
```

**Şıklar:**

A) View'da kullanılacak model tipini belirtir

B) Veritabanından öğrenci listesini çeker

C) Yeni bir öğrenci listesi oluşturur

D) Controller'a model tipini bildirir

**Cevap:** A) View'da kullanılacak model tipini belirtir

**Açıklama:**

- View dosyasının başında model tipini belirtmek için kullanılır
- Strongly-typed view oluşturmayı sağlar
- IntelliSense desteği sağlar
- Compile-time type checking sağlar

## Soru 2

**Soru:** Tag Helper'ların avantajı nedir?

**Şıklar:**

A) Veritabanı bağlantısını hızlandırır

B) Server-side özellikleri HTML benzeri syntax ile kullanmayı sağlar

C) JavaScript kodlarını otomatik optimize eder

D) View component'leri otomatik oluşturur

**Cevap:** B) Server-side özellikleri HTML benzeri syntax ile kullanmayı sağlar

**Açıklama:**

- HTML-friendly syntax sunar
- IntelliSense desteği sağlar
- Daha okunabilir kod yazımı sağlar
- Server-side özellikleri HTML elementlerine ekler

## Soru 3

**Soru:** Aşağıdaki action method hangi HTTP metoduna yanıt verir?

```csharp
[HttpPost]
public IActionResult CreateStudent(StudentViewModel model)
```

**Şıklar:**

A) GET

B) POST

C) PUT

D) DELETE

**Cevap:** B) POST

**Açıklama:**

- [HttpPost] attribute'u POST isteklerini işler
- Genellikle form submit işlemlerinde kullanılır
- Veri oluşturma işlemleri için kullanılır
- Body içinde veri göndermeyi sağlar

## Soru 4

**Soru:** ViewBag ve ViewData arasındaki fark nedir?

**Şıklar:**

A) ViewBag dinamik tiplidir, ViewData dictionary kullanır

B) ViewBag kalıcı depolama sağlar, ViewData geçicidir

C) ViewBag sadece string değerler alır, ViewData her türlü veriyi alır

D) ViewBag ve ViewData aynı şeydir, sadece isimleri farklıdır

**Cevap:** A) ViewBag dinamik tiplidir, ViewData dictionary kullanır

**Açıklama:**

- ViewBag dynamic özelliğini kullanır
- ViewData bir dictionary'dir
- İkisi de controller'dan view'a veri taşır
- İkisi de tek request için geçerlidir

## Soru 5

**Soru:** Aşağıdaki routing tanımı ne anlama gelir?

```csharp
[Route("api/[controller]/[action]/{id?}")]
```

**Şıklar:**

A) Sadece API controller'ları için geçerli bir route tanımı

B) Controller ve action isimlerini otomatik olarak route'a ekler, id parametresi opsiyoneldir

C) Tüm controller'lar için varsayılan route tanımı

D) Sadece belirli bir controller için özel route tanımı

**Cevap:** B) Controller ve action isimlerini otomatik olarak route'a ekler, id parametresi opsiyoneldir

**Açıklama:**

- [controller] token'ı controller ismini alır
- [action] token'ı action method ismini alır
- {id?} opsiyonel bir route parametresidir
- api prefix'i API rotalarını belirtir

## Soru 6

**Soru:** Model validation için aşağıdaki attribute'lardan hangisi yanlıştır?

**Şıklar:**

A) [Required]

B) [StringValidation]

C) [MaxLength(50)]

D) [EmailAddress]

**Cevap:** B) [StringValidation]

**Açıklama:**

- [StringValidation] diye bir validation attribute yoktur
- Doğru attribute'lar:
  - [Required] - zorunlu alan
  - [MaxLength] - maksimum uzunluk
  - [EmailAddress] - email format kontrolü

## Soru 7

**Soru:** DbContext sınıfı için aşağıdakilerden hangisi doğrudur?

**Şıklar:**

A) Her request için yeni bir instance oluşturulmalıdır

B) Tüm uygulama için tek bir instance kullanılmalıdır

C) Her method için yeni bir instance oluşturulmalıdır

D) Instance oluşturmaya gerek yoktur, statik methodlar kullanılır

**Cevap:** A) Her request için yeni bir instance oluşturulmalıdır

**Açıklama:**

- DbContext Scoped lifetime ile kullanılmalıdır
- Her HTTP request için yeni instance oluşur
- Memory leak'leri önler
- Connection yönetimini optimize eder

## Soru 8

**Soru:** Aşağıdaki Layout tanımı ne işe yarar?

```csharp
@{
    Layout = "_MainLayout";
}
```

**Şıklar:**

A) Sayfanın CSS dosyasını belirler

B) Sayfanın master template'ini belirler

C) Sayfanın JavaScript dosyalarını yükler

D) Sayfanın meta tag'lerini ayarlar

**Cevap:** B) Sayfanın master template'ini belirler

**Açıklama:**

- Layout sayfası tüm sayfalarda ortak kullanılacak template'i belirler
- Header, footer gibi ortak alanları içerir
- @RenderBody() ile içerik alanını belirler
- Tutarlı sayfa yapısı sağlar

## Soru 9

**Soru:** Dependency Injection için aşağıdaki servis kayıt yöntemlerinden hangisi yanlıştır?

**Şıklar:**

A) services.AddScoped<IService, Service>()

B) services.AddSingleton<IService, Service>()

C) services.AddTransient<IService, Service>()

D) services.AddStatic<IService, Service>()

**Cevap:** D) services.AddStatic<IService, Service>()

**Açıklama:**

- AddStatic diye bir method yoktur
- Doğru servis kayıt methodları:
  - AddScoped - request bazlı
  - AddSingleton - tek instance
  - AddTransient - her inject'te yeni instance

## Soru 10

**Soru:** Action method'da return View(model) ile ne yapılır?

**Şıklar:**

A) Model'i JSON formatında döndürür

B) Model'i view'a paslar ve view'ı render eder

C) Model'i veritabanına kaydeder

D) Model'i başka bir action'a yönlendirir

**Cevap:** B) Model'i view'a paslar ve view'ı render eder

**Açıklama:**

- View() methodu bir ViewResult döndürür
- Model verisi view'a aktarılır
- View engine view'ı render eder
- HTML çıktısı oluşturulur

## Soru 11

**Soru:** Aşağıdaki controller kodunda kaç hata vardır?

```csharp
public class StudentController inherits Controller
{
    private StudentService _service;

    public StudentController()
    {
        _service = new StudentService();
    }

    public ActionResult Index()
    {
        var students == _service.GetAll();
        ViewBag.Count := students.Count;
        return View(students);
    }
}
```

**Şıklar:**

A) 2

B) 3

C) 4

D) 5

**Cevap:** C) 4

**Açıklama:**
Hatalar:

1. `inherits` yerine `:` kullanılmalı
2. Dependency Injection kullanılmamış (constructor injection yapılmalı)
3. `==` operatörü yerine `=` kullanılmalı
4. `:=` operatörü yerine `=` kullanılmalı

## Soru 12

**Soru:** View Component'in doğru kullanımı hangisidir?

**Şıklar:**

A) `@Component.InvokeAsync("CartSummary")`

B) `@await Component.InvokeAsync("CartSummary")`

C) `@Html.RenderComponent("CartSummary")`

D) `@RenderComponent("CartSummary")`

**Cevap:** B) `@await Component.InvokeAsync("CartSummary")`

**Açıklama:**

- View Component'ler asenkron çalışır
- await keyword'ü kullanılmalıdır
- InvokeAsync methodu kullanılır
- Component sınıfı üzerinden çağrılır

## Soru 13

**Soru:** Aşağıdaki model sınıfındaki hatalar nelerdir?

```csharp
public class ProductModel
{
    [Required, MinLength = 3]
    public string Name;

    [Range(0.0, 999.99)]
    private decimal Price { get; set; }

    [DataType("Date")]
    public DateTime CreatedDate { get; set; };
}
```

**Şıklar:**

A) 2 hata

B) 3 hata

C) 4 hata

D) 5 hata

**Cevap:** B) 3 hata

**Açıklama:**
Hatalar:

1. MinLength attribute'u parantez ile kullanılmalı: `[MinLength(3)]`
2. Name field olarak tanımlanmış, property olmalı
3. Price private tanımlanmış, public olmalı
4. CreatedDate sonundaki gereksiz noktalı virgül

## Soru 14

**Soru:** Aşağıdaki Cache implementasyonunda ne tür bir hata vardır?

```csharp
public class CacheService : IMemoryCache
{
    private MemoryCache _cache = new();

    public object Get(string key)
    {
        return _cache.Get(key);
    }

    public void Set(string key, object value)
    {
        _cache.Set(key, value, TimeSpan.FromMinutes(30));
    }
}
```

**Şıklar:**

A) Interface eksik method implementasyonları

B) MemoryCache yanlış instantiate edilmiş

C) TimeSpan kullanımı hatalı

D) Generic tip kullanılmamış

**Cevap:** A) Interface eksik method implementasyonları

**Açıklama:**

- IMemoryCache interface'i daha fazla method içerir
- TryGetValue, Remove gibi methodlar eksik
- Interface'in tüm methodları implement edilmeli
- Ya tüm methodlar implement edilmeli ya da kendi interface'imiz yazılmalı

## Soru 15

**Soru:** Aşağıdaki Middleware tanımında hangi hata vardır?

```csharp
app.Use(async (context, next) =>
{
    await context.Response.WriteAsync("Before");
    next();
    await context.Response.WriteAsync("After");
});
```

**Şıklar:**

A) Use methodu yanlış kullanılmış

B) async/await eksik kullanılmış

C) next() methodu await edilmemiş

D) WriteAsync yanlış kullanılmış

**Cevap:** C) next() methodu await edilmemiş

**Açıklama:**

- Middleware'de next delegate'i await edilmelidir
- Doğru kullanım: `await next();`
- Pipeline akışı için önemli
- Response sıralaması için kritik

## Soru 16

**Soru:** Aşağıdaki Route tanımında ne hatalıdır?

```csharp
[Route("[controller]/[action]/{id:int?}/{name}")]
```

**Şıklar:**

A) Controller token yanlış yazılmış

B) Action token yanlış yazılmış

C) Opsiyonel parametre sonra gelmeli

D) Route syntax'ı hatalı

**Cevap:** C) Opsiyonel parametre sonra gelmeli

**Açıklama:**

- Opsiyonel parametreler en sonda olmalıdır
- {name} zorunlu parametre opsiyonel parametreden sonra gelemez
- Doğru sıralama: zorunlu parametreler, sonra opsiyonel parametreler
- Route matching için önemli

## Soru 17

**Soru:** Model binding için aşağıdaki kodda ne hatalıdır?

```csharp
public IActionResult Update([FromForm]int id, [FromBody]ProductModel model)
```

**Şıklar:**

A) FromForm ve FromBody birlikte kullanılamaz

B) int için FromForm kullanılamaz

C) ProductModel için FromBody kullanılamaz

D) Action method adı hatalı

**Cevap:** A) FromForm ve FromBody birlikte kullanılamaz

**Açıklama:**

- Request body'si sadece bir kez okunabilir
- FromBody tek bir parametre için kullanılabilir
- FromForm ile FromBody aynı action'da kullanılamaz
- Ya form data ya da JSON/XML body kullanılmalı

## Soru 18

**Soru:** Aşağıdaki DbContext tanımında ne hatalıdır?

```csharp
public class ShopContext : DbContext
{
    public DbSet<Product> Products;
    public DbSet<Category> Categories { private get; set; }
    protected List<Order> Orders { get; set; }
}
```

**Şıklar:**

A) 1 hata

B) 2 hata

C) 3 hata

D) Hata yok

**Cevap:** C) 3 hata

**Açıklama:**
Hatalar:

1. Products field olarak tanımlanmış, property olmalı
2. Categories property'si private set olmamalı
3. Orders DbSet yerine List olarak tanımlanmış ve protected

## Soru 19

**Soru:** Aşağıdaki Validation attribute'u neden hatalıdır?

```csharp
public class CustomRangeAttribute : ValidationAttribute
{
    protected override ValidationResult IsValid(object value)
    {
        if (value is int val && val > 0 && val < 100)
            return ValidationResult.Success;
        return new ValidationResult("Invalid range");
    }
}
```

**Şıklar:**

A) Base class yanlış

B) Method signature eksik

C) Return type hatalı

D) Validation logic hatalı

**Cevap:** B) Method signature eksik

**Açıklama:**

- IsValid methodunun ikinci parametresi eksik
- Doğru signature: `IsValid(object value, ValidationContext context)`
- ValidationContext parameter önemli
- Custom validation için gerekli

## Soru 20

**Soru:** Aşağıdaki Action method'da ne hatalıdır?

```csharp
[HttpPost]
public async Task<ActionResult> Create(ProductModel model)
{
    if (!ModelState.IsValid)
        return View(model);

    var result = _service.AddProduct(model);
    return RedirectToAction("Index");
}
```

**Şıklar:**

A) async method içinde await kullanılmamış

B) ModelState kontrolü yanlış

C) Return type hatalı

D) RedirectToAction yanlış kullanılmış

**Cevap:** A) async method içinde await kullanılmamış

**Açıklama:**

- Async method tanımlanmış ama await kullanılmamış
- \_service.AddProduct muhtemelen async bir method olmalı
- Async method await edilmeli
- Ya async/await kaldırılmalı ya da await kullanılmalı
