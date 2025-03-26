# MVC ve Web Programlama Soruları ve Çözümleri

## Soru 1: Razor Syntax & View
**Soru:** Aşağıdaki Razor kod bloğunun amacı nedir?
```csharp
@{
    var students = ViewBag.Students as List<Student>;
}
<table>
    @foreach (var student in students)
    {
        <tr>
            <td>@student.Name</td>
            <td>@student.Grade</td>
        </tr>
    }
</table>
```

**Şıklar:**

A) Öğrenci verilerini JSON formatında göstermek

B) Öğrenci verilerini HTML tablo formatında listelemek

C) Öğrenci verilerini veritabanına kaydetmek

D) Öğrenci verilerini düzenlemek için form oluşturmak

**Cevap:** B) Öğrenci verilerini HTML tablo formatında listelemek

**Açıklama:**
- ViewBag'den alınan öğrenci listesi HTML tablo yapısında gösteriliyor
- @foreach döngüsü ile her öğrenci için bir tablo satırı oluşturuluyor
- Her öğrencinin adı ve notu ayrı hücrelerde gösteriliyor
- Bu yapı, verileri düzenli bir şekilde görüntülemek için kullanılan tipik bir Razor syntax örneğidir

## Soru 2: Partial Views
**Soru:** @Html.Partial() ve @await Html.PartialAsync() arasındaki temel fark nedir?

**Şıklar:**

A) Partial senkron çalışırken, PartialAsync asenkron çalışır

B) PartialAsync daha az bellek kullanır

C) Partial daha hızlı çalışır

D) İkisi arasında hiçbir fark yoktur

**Cevap:** A) Partial senkron çalışırken, PartialAsync asenkron çalışır

**Açıklama:**
- @Html.Partial() senkron olarak çalışır ve işlem tamamlanana kadar bekler
- @await Html.PartialAsync() asenkron çalışır ve diğer işlemlerin devam etmesine izin verir
- PartialAsync özellikle büyük partial view'lar için daha iyi performans sağlar
- Modern web uygulamalarında PartialAsync kullanımı önerilir

## Soru 3: ASP.NET Core Tag Helpers
**Soru:** Aşağıdaki tag helper kullanımlarından hangisi yanlıştır?

**Şıklar:**

A) `<a asp-controller="Home" asp-action="Index">Anasayfa</a>`

B) `<form asp-action="Save" method="post">`

C) `<input type="text" asp-for="@Model.Name">`

D) `<div asp-validation="@Model.Email"></div>`

**Cevap:** D) `<div asp-validation="@Model.Email"></div>`

**Açıklama:**
- Doğru validation tag helper kullanımı: `<span asp-validation-for="Email"></span>`
- Tag helper'lar form elementleri ve navigasyon için kullanılır
- Model binding için asp-for attribute'u kullanılır
- Validation mesajları için asp-validation-for kullanılır

## Soru 4: Model ve Entity Kavramları
**Soru:** Aşağıdakilerden hangisi bir Model sınıfının özelliklerinden değildir?

**Şıklar:**

A) Validation kuralları içerebilir

B) Veritabanı ilişkilerini yönetir

C) View'a veri taşır

D) DTO (Data Transfer Object) olarak kullanılır

**Cevap:** B) Veritabanı ilişkilerini yönetir

**Açıklama:**
- Veritabanı ilişkilerini yönetmek Entity sınıflarının görevidir
- Model sınıfları sadece veri taşıma ve validation amaçlıdır
- Model sınıfları view ile controller arasında veri transferi sağlar
- Entity sınıfları veritabanı tablolarını temsil eder

## Soru 5: MVC Mimarisi
**Soru:** MVC mimarisinde Controller'ın temel görevi nedir?

**Şıklar:**

A) Veritabanı işlemlerini yönetmek

B) Kullanıcı arayüzünü oluşturmak

C) Model ve View arasındaki iletişimi yönetmek

D) İş mantığını (business logic) içermek

**Cevap:** C) Model ve View arasındaki iletişimi yönetmek

**Açıklama:**
- Controller, kullanıcı isteklerini karşılar
- Model'den gelen verileri View'a iletir
- Hangi View'ın gösterileceğine karar verir
- Kullanıcı girdilerini işler ve yönlendirir

## Soru 6: DbContext ve Veri Erişimi
**Soru:** Entity Framework Core'da DbContext sınıfı için aşağıdakilerden hangisi doğrudur?

**Şıklar:**

A) Her istek için yeni bir instance oluşturulmalıdır

B) Tüm uygulama için tek bir instance kullanılmalıdır

C) Instance yönetimi önemli değildir

D) Her metot için yeni bir instance oluşturulmalıdır

**Cevap:** A) Her istek için yeni bir instance oluşturulmalıdır

**Açıklama:**
- DbContext Scoped lifetime ile kullanılmalıdır
- Her HTTP isteği için yeni bir instance oluşturulur
- Memory leak'leri önlemek için önemlidir
- Thread safety sağlar

## Soru 7: Generic Repository Pattern
**Soru:** ICommonDal<T> interface'i için aşağıdaki metodlardan hangisi gereksizdir?

**Şıklar:**

A) `T Get(Expression<Func<T, bool>> filter)`

B) `List<T> GetList()`

C) `T Add(T entity)`

D) `void SaveChanges()`

**Cevap:** D) `void SaveChanges()`

**Açıklama:**
- SaveChanges metodu DbContext seviyesinde çağrılmalıdır
- Repository pattern'de unit of work pattern ile yönetilir
- Generic repository temel CRUD operasyonlarını içerir
- Add, Update, Delete, Get, GetList temel metodlardır

## Soru 8: Caching (Önbellekleme)
**Soru:** Aşağıdakilerden hangisi bir web uygulamasında caching kullanmanın avantajlarından değildir?

**Şıklar:**

A) Veritabanı yükünü azaltır

B) Yanıt süresini iyileştirir

C) Veritabanı güvenliğini artırır

D) Sunucu kaynaklarını optimize eder

**Cevap:** C) Veritabanı güvenliğini artırır

**Açıklama:**
- Caching performans iyileştirmesi için kullanılır
- Veritabanı sorgularını azaltır
- Yanıt süresini kısaltır
- Güvenlik ile ilgisi yoktur

## Soru 9: Dependency Injection
**Soru:** Aşağıdaki servis kayıt yöntemlerinden hangisi logging servisi için en uygundur?

**Şıklar:**

A) services.AddScoped<ILogger, Logger>()

B) services.AddTransient<ILogger, Logger>()

C) services.AddSingleton<ILogger, Logger>()

D) new Logger()

**Cevap:** C) services.AddSingleton<ILogger, Logger>()

**Açıklama:**
- Logging servisi uygulama yaşam döngüsü boyunca tek instance olmalıdır
- Singleton pattern bu tür servisler için idealdir
- Memory kullanımını optimize eder
- Thread-safe olmalıdır

## Soru 10: Service Lifetime
**Soru:** DbContext için hangi service lifetime kullanılmalıdır?

**Şıklar:**

A) Singleton

B) Scoped

C) Transient

D) Static

**Cevap:** B) Scoped

**Açıklama:**
- DbContext her request için yeni bir instance gerektirir
- Scoped lifetime her HTTP isteği için yeni instance oluşturur
- Memory leak'leri önler
- Entity Framework best practice'lerine uygundur

## Soru 11: Redis Cache & Serialization
**Soru:** Aşağıdaki Redis cache implementasyonunda hangi hata vardır?

```csharp
public class RedisCacheManager : ICacheManager
{
    private readonly IDatabase _cache;
    
    public T Get<T>(string key)
    {
        var value = _cache.StringGet(key);
        return JsonConvert.DeserializeObject<T>(value);
    }
}
```

**Şıklar:**

A) IDatabase türü yanlış kullanılmış

B) Null kontrolü yapılmamış

C) Generic tip kısıtlaması eksik

D) Redis bağlantısı hatalı

**Cevap:** B) Null kontrolü yapılmamış

**Açıklama:**
- Cache'den gelen değer null olabilir
- Null değer deserialize edilmeye çalışılırsa exception fırlatır
- Güvenli bir implementasyon için null check yapılmalıdır
- Doğru implementasyon şöyle olmalıdır:
```csharp
public T Get<T>(string key)
{
    var value = _cache.StringGet(key);
    return value.HasValue ? JsonConvert.DeserializeObject<T>(value) : default(T);
}
```

## Soru 12: Service Lifetimes
**Soru:** Aşağıdaki servis kayıt senaryolarından hangisi yanlıştır?

**Şıklar:**

A) `services.AddTransient<IEmailService, EmailService>()`

B) `services.AddScoped<DbContext, ApplicationDbContext>()`

C) `services.AddSingleton<DbContext, ApplicationDbContext>()`

D) `services.AddSingleton<IConfiguration, Configuration>()`

**Cevap:** C) `services.AddSingleton<DbContext, ApplicationDbContext>()`

**Açıklama:**
- DbContext singleton olarak kaydedilmemelidir
- DbContext thread-safe değildir
- Her request için yeni bir instance gereklidir
- Memory leak ve concurrency sorunlarına yol açabilir

## Soru 13: ASP.NET Core Tag Helpers
**Soru:** Aşağıdaki form tag helper kullanımlarından hangisi doğrudur?

**Şıklar:**

A) `<form asp-action="Save" asp-antiforgery="false">`

B) `<form asp-controller="Home" asp-action="Index" method="get">`

C) `<form asp-area="Admin" asp-controller="Users" method="delete">`

D) `<form asp-action="Delete" asp-route-id="@Model.Id" method="DELETE">`

**Cevap:** B) `<form asp-controller="Home" asp-action="Index" method="get">`

**Açıklama:**
- GET ve POST geçerli HTTP metodlarıdır
- asp-controller ve asp-action doğru kullanılmış
- DELETE metodu form üzerinden direkt desteklenmez
- Anti-forgery token varsayılan olarak aktif olmalıdır

## Soru 14: Model Binding
**Soru:** Aşağıdaki model binding yaklaşımlarından hangisi yanlıştır?

**Şıklar:**

A) `public IActionResult Edit([FromBody] Product product)`

B) `public IActionResult Create([FromForm] ProductViewModel model)`

C) `public IActionResult Delete([FromRoute] int id)`

D) `public IActionResult Update([FromQuery] Product product)`

**Cevap:** D) `public IActionResult Update([FromQuery] Product product)`

**Açıklama:**
- Kompleks tipler query string'den bind edilmemelidir
- [FromQuery] primitive tipler için uygundur
- Kompleks tipler için [FromBody] veya [FromForm] kullanılmalıdır
- Query string'de büyük veri taşımak uygun değildir

## Soru 15: View Components
**Soru:** View Component'ler ile Partial View'lar arasındaki fark hangisi değildir?

**Şıklar:**

A) View Component'ler bağımsız iş mantığı içerebilir

B) View Component'ler constructor injection destekler

C) View Component'ler async operasyonları destekler

D) View Component'ler layout'ta kullanılamaz

**Cevap:** D) View Component'ler layout'ta kullanılamaz

**Açıklama:**
- View Component'ler layout dahil her yerde kullanılabilir
- Partial View'lardan daha güçlü ve bağımsızdır
- Kendi iş mantıklarını içerebilirler
- Dependency injection desteklerler

## Soru 16: Entity Framework Core
**Soru:** DbContext'te aşağıdaki Fluent API kullanımlarından hangisi yanlıştır?

**Şıklar:**

A) `modelBuilder.Entity<User>().HasIndex(u => u.Email).IsUnique()`

B) `modelBuilder.Entity<Order>().HasMany(o => o.Items).WithOne(i => i.Order)`

C) `modelBuilder.Entity<Product>().Property(p => p.Price).HasColumnType("money")`

D) `modelBuilder.Entity<Customer>().HasData(new { Id = 1, Name = "John" })`

**Cevap:** D) `modelBuilder.Entity<Customer>().HasData(new { Id = 1, Name = "John" })`

**Açıklama:**
- Anonim tip ile seed data tanımlanamaz
- Concrete tip kullanılmalıdır
- Doğru kullanım:
```csharp
modelBuilder.Entity<Customer>().HasData(
    new Customer { Id = 1, Name = "John" }
);
```

## Soru 17: Action Filters
**Soru:** Aşağıdaki action filter kullanımlarından hangisi doğrudur?

**Şıklar:**

A) `[Authorize]`

B) `[ValidateAntiForgeryToken(Order = 2)]`

C) `[ResponseCache(NoStore = true)]`

D) Hepsi doğrudur

**Cevap:** D) Hepsi doğrudur

**Açıklama:**
- [Authorize] authentication kontrolü yapar
- [ValidateAntiForgeryToken] CSRF koruması sağlar
- [ResponseCache] cache davranışını kontrol eder
- Filter'ların sıralaması Order property'si ile yapılabilir

## Soru 18: Routing
**Soru:** Aşağıdaki route tanımlamalarından hangisi hatalıdır?

**Şıklar:**

A) `[Route("api/[controller]")]`

B) `[Route("api/{controller}/{action}/{id?}")]`

C) `[Route("api/[controller]/[action]/{id:int}")]`

D) `[Route("api/[controller]/[action]/{id:string?}")]`

**Cevap:** B) `[Route("api/{controller}/{action}/{id?}")]`

**Açıklama:**
- Controller ve Action token'ları [] içinde olmalıdır
- Doğru yazım: "api/[controller]/[action]/{id?}"
- Route constraint'ler : ile belirtilir
- Optional parametreler ? ile işaretlenir

## Soru 19: Dependency Injection Container
**Soru:** Aşağıdakilerden hangisi built-in DI container'ın bir sınırlaması değildir?

**Şıklar:**

A) Property injection desteklenmez

B) Scoped servisler singleton servislere inject edilemez

C) Named instance'lar desteklenmez

D) Constructor injection desteklenmez

**Cevap:** D) Constructor injection desteklenmez

**Açıklama:**
- Constructor injection tam olarak desteklenir
- Property injection için 3rd party DI container gerekir
- Scoped -> Singleton injection yasaktır
- Named/keyed instance'lar için alternatif DI container kullanılmalıdır

## Soru 20: Error Handling
**Soru:** Global exception handling için aşağıdaki yaklaşımlardan hangisi en uygunudur?

**Şıklar:**

A) Her action'da try-catch blokları kullanmak

B) Base controller'da exception handling yapmak

C) Middleware kullanarak global exception handler yazmak

D) View'larda error handling yapmak

**Cevap:** C) Middleware kullanarak global exception handler yazmak

**Açıklama:**
- Middleware tüm istekleri merkezi olarak yönetir
- Kod tekrarını önler
- Tutarlı error handling sağlar
- Loglama ve hata raporlama için ideal noktadır

## Soru 21: Controller Implementation
**Soru:** Aşağıdaki controller implementasyonunda kaç hata vardır?

```csharp
public class ProductController : Controller
{
    private readonly IProductService productService;

    public ProductController(IProductService _productService) 
    {
        productService = _productService;
    }

    [HttpGet]
    public async Task<IActionResult> List()
    {
        var products = productService.GetAllProducts();
        return View(products);
    }

    [HttpPost]
    public IActionResult Create(ProductViewModel model)
    {
        if(ModelState.IsValid)
            productService.AddProduct(model);
        
        return RedirectToAction("List");
    }
}
```

**Şıklar:**

A) 1

B) 2

C) 3

D) 4

**Cevap:** C) 3

**Açıklama:**
1. GetAllProducts metodu async olarak çağrılmamış (await eksik)
2. Create metodunda model validation sonrası hata durumu kontrol edilmemiş
3. AddProduct işlemi için async/await kullanılmamış
Doğru implementasyon:
```csharp
public class ProductController : Controller
{
    private readonly IProductService _productService; // underscore convention

    public ProductController(IProductService productService) 
    {
        _productService = productService;
    }

    [HttpGet]
    public async Task<IActionResult> List()
    {
        var products = await _productService.GetAllProductsAsync();
        return View(products);
    }

    [HttpPost]
    public async Task<IActionResult> Create(ProductViewModel model)
    {
        if(!ModelState.IsValid)
            return View(model);
            
        await _productService.AddProductAsync(model);
        return RedirectToAction("List");
    }
}
```

## Soru 22: Middleware Implementation
**Soru:** Aşağıdaki custom middleware implementasyonunda hangi hatalar vardır?

```csharp
public class CustomAuthMiddleware
{
    private RequestDelegate next;

    public CustomAuthMiddleware(RequestDelegate _next)
    {
        next = _next;
    }

    public void Invoke(HttpContext context)
    {
        var token = context.Request.Headers["Authorization"];
        
        if (string.IsNullOrEmpty(token))
            context.Response.StatusCode = 401;
        
        next(context);
    }
}
```

**Şıklar:**

A) Constructor parametresi yanlış isimlendirilmiş

B) Invoke metodu async değil

C) 401 durumunda next delegate çağrılmamalı

D) Hepsi

**Cevap:** D) Hepsi

**Açıklama:**
Doğru implementasyon:
```csharp
public class CustomAuthMiddleware
{
    private readonly RequestDelegate _next;

    public CustomAuthMiddleware(RequestDelegate next)
    {
        _next = next;
    }

    public async Task InvokeAsync(HttpContext context)
    {
        var token = context.Request.Headers["Authorization"];
        
        if (string.IsNullOrEmpty(token))
        {
            context.Response.StatusCode = 401;
            return;
        }
        
        await _next(context);
    }
}
```

## Soru 23: View Model Validation
**Soru:** Aşağıdaki view model implementasyonunda hangi hatalar vardır?

```csharp
public class UserViewModel
{
    [Required]
    public string Username { get; set; }

    [Required]
    [MinLength(6)]
    public string Password { get; set; }

    [Compare("Password")]
    public string ConfirmPassword { get; set; }

    [Required]
    public string Email { get; set; }

    public DateTime BirthDate { get; set; }
}
```

**Şıklar:**

A) Email validasyonu eksik

B) Password için maksimum uzunluk belirtilmemiş

C) BirthDate için range kontrolü yok

D) Hepsi

**Cevap:** D) Hepsi

**Açıklama:**
Doğru implementasyon:
```csharp
public class UserViewModel
{
    [Required(ErrorMessage = "Kullanıcı adı zorunludur")]
    [StringLength(50)]
    public string Username { get; set; }

    [Required(ErrorMessage = "Şifre zorunludur")]
    [StringLength(100, MinimumLength = 6)]
    [RegularExpression(@"^(?=.*[a-z])(?=.*[A-Z])(?=.*\d).{6,}$",
        ErrorMessage = "Şifre en az bir büyük harf, bir küçük harf ve bir rakam içermelidir")]
    public string Password { get; set; }

    [Required(ErrorMessage = "Şifre tekrarı zorunludur")]
    [Compare("Password", ErrorMessage = "Şifreler eşleşmiyor")]
    public string ConfirmPassword { get; set; }

    [Required(ErrorMessage = "Email zorunludur")]
    [EmailAddress(ErrorMessage = "Geçerli bir email adresi giriniz")]
    public string Email { get; set; }

    [Required(ErrorMessage = "Doğum tarihi zorunludur")]
    [Range(typeof(DateTime), "1900-01-01", "2010-01-01",
        ErrorMessage = "Geçerli bir doğum tarihi giriniz")]
    public DateTime BirthDate { get; set; }
}
```

## Soru 24: Repository Implementation
**Soru:** Aşağıdaki repository implementasyonunda kaç hata vardır?

```csharp
public class ProductRepository : IProductRepository
{
    private readonly DbContext context;

    public ProductRepository(DbContext _context)
    {
        context = _context;
    }

    public List<Product> GetAll()
    {
        return context.Products.ToList();
    }

    public Product GetById(int id)
    {
        return context.Products.Find(id);
    }

    public void Add(Product product)
    {
        context.Products.Add(product);
    }

    public void Update(Product product)
    {
        context.Entry(product).State = EntityState.Modified;
    }

    public void Delete(int id)
    {
        var product = GetById(id);
        context.Products.Remove(product);
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
1. Field isimlendirmesi yanlış (_context olmalı)
2. Metodlar async/await kullanmıyor
3. SaveChanges() çağrılmıyor
4. Null kontrolleri eksik

Doğru implementasyon:
```csharp
public class ProductRepository : IProductRepository
{
    private readonly DbContext _context;

    public ProductRepository(DbContext context)
    {
        _context = context;
    }

    public async Task<IEnumerable<Product>> GetAllAsync()
    {
        return await _context.Products.ToListAsync();
    }

    public async Task<Product> GetByIdAsync(int id)
    {
        return await _context.Products.FindAsync(id);
    }

    public async Task AddAsync(Product product)
    {
        if (product == null)
            throw new ArgumentNullException(nameof(product));

        await _context.Products.AddAsync(product);
        await _context.SaveChangesAsync();
    }

    public async Task UpdateAsync(Product product)
    {
        if (product == null)
            throw new ArgumentNullException(nameof(product));

        _context.Entry(product).State = EntityState.Modified;
        await _context.SaveChangesAsync();
    }

    public async Task DeleteAsync(int id)
    {
        var product = await GetByIdAsync(id);
        if (product == null)
            throw new NotFoundException($"Product with id {id} not found");

        _context.Products.Remove(product);
        await _context.SaveChangesAsync();
    }
}
```

## Soru 25: Service Configuration
**Soru:** Aşağıdaki servis konfigürasyonunda hangi hatalar vardır?

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddDbContext<ApplicationDbContext>();
    
    services.AddScoped<IProductRepository, ProductRepository>();
    services.AddScoped<IProductService, ProductService>();
    
    services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme);
    
    services.AddControllers();
}
```

**Şıklar:**

A) DbContext konfigürasyonu eksik

B) Authentication konfigürasyonu eksik

C) CORS politikası eksik

D) Hepsi

**Cevap:** D) Hepsi

**Açıklama:**
Doğru implementasyon:
```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddDbContext<ApplicationDbContext>(options =>
        options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    
    services.AddScoped<IProductRepository, ProductRepository>();
    services.AddScoped<IProductService, ProductService>();
    
    services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
        .AddJwtBearer(options =>
        {
            options.TokenValidationParameters = new TokenValidationParameters
            {
                ValidateIssuer = true,
                ValidateAudience = true,
                ValidateLifetime = true,
                ValidateIssuerSigningKey = true,
                ValidIssuer = Configuration["Jwt:Issuer"],
                ValidAudience = Configuration["Jwt:Audience"],
                IssuerSigningKey = new SymmetricSecurityKey(
                    Encoding.UTF8.GetBytes(Configuration["Jwt:Key"]))
            };
        });
    
    services.AddCors(options =>
    {
        options.AddPolicy("AllowAll",
            builder => builder
                .AllowAnyOrigin()
                .AllowAnyMethod()
                .AllowAnyHeader());
    });
    
    services.AddControllers();
}
```

## Soru 26: Action Result Types
**Soru:** Aşağıdaki controller action'larından hangisi hatalıdır?

```csharp
public class ProductController : Controller
{
    [HttpGet]
    public IActionResult GetProduct(int id)
    {
        var product = _productService.GetById(id);
        if (product == null)
            return NotFound();
            
        return Json(new { success = true, data = product });
    }

    [HttpPost]
    public async Task<ActionResult<Product>> CreateProduct(ProductDto dto)
    {
        if (!ModelState.IsValid)
            return BadRequest(ModelState);
            
        var result = await _productService.CreateAsync(dto);
        return Created($"/api/products/{result.Id}", null);
    }

    [HttpGet]
    public FileResult DownloadReport()
    {
        byte[] fileBytes = _reportService.GenerateReport();
        return File(fileBytes, "application/pdf", "report.pdf");
    }

    [HttpGet]
    public ViewResult ShowProduct(int id)
    {
        var product = _productService.GetById(id);
        return View("ProductDetails", product);
    }
}
```

**Şıklar:**

A) GetProduct metodu

B) CreateProduct metodu

C) DownloadReport metodu

D) ShowProduct metodu

**Cevap:** B) CreateProduct metodu

**Açıklama:**
- Created action result'ı için URI ve nesne birlikte verilmelidir
- null yerine oluşturulan nesne dönülmelidir
- Doğru implementasyon:
```csharp
[HttpPost]
public async Task<ActionResult<Product>> CreateProduct(ProductDto dto)
{
    if (!ModelState.IsValid)
        return BadRequest(ModelState);
        
    var result = await _productService.CreateAsync(dto);
    return CreatedAtAction(nameof(GetProduct), new { id = result.Id }, result);
}
```

## Soru 27: LINQ ve Entity Framework
**Soru:** Aşağıdaki LINQ sorgularından hangisi performans açısından en verimsizdir?

```csharp
// Sorgu 1
var result1 = await _context.Orders
    .Where(o => o.Status == OrderStatus.Pending)
    .Select(o => new OrderDto 
    {
        Id = o.Id,
        CustomerName = o.Customer.Name
    })
    .ToListAsync();

// Sorgu 2
var result2 = await _context.Orders
    .Where(o => o.Status == OrderStatus.Pending)
    .Include(o => o.Customer)
    .Include(o => o.OrderItems)
    .ToListAsync();

// Sorgu 3
var result3 = _context.Orders
    .Where(o => o.Status == OrderStatus.Pending)
    .ToList()
    .Select(o => new OrderDto 
    {
        Id = o.Id,
        CustomerName = o.Customer.Name
    });

// Sorgu 4
var result4 = await _context.Orders
    .Include(o => o.Customer)
    .Where(o => o.Status == OrderStatus.Pending)
    .Select(o => new OrderDto 
    {
        Id = o.Id,
        CustomerName = o.Customer.Name
    })
    .ToListAsync();
```

**Şıklar:**

A) Sorgu 1

B) Sorgu 2

C) Sorgu 3

D) Sorgu 4

**Cevap:** C) Sorgu 3

**Açıklama:**
- ToList() çağrısı tüm verileri memory'e çeker
- Select işlemi memory'de yapılır
- Veritabanı tarafında filtreleme yapılmaz
- Doğru yaklaşım Sorgu 1'deki gibi olmalıdır

## Soru 28: View Component Implementation
**Soru:** Aşağıdaki View Component implementasyonunda hangi hatalar vardır?

```csharp
public class CartSummaryViewComponent
{
    private readonly ICartService _cartService;

    public CartSummaryViewComponent(ICartService cartService)
    {
        _cartService = cartService;
    }

    public IViewComponentResult Invoke()
    {
        var cartItems = _cartService.GetCartItems();
        return View(cartItems);
    }
}
```

**Şıklar:**

A) Base class eksik

B) Invoke metodu async değil

C) Model tipi belirtilmemiş

D) A ve B

**Cevap:** D) A ve B

**Açıklama:**
Doğru implementasyon:
```csharp
public class CartSummaryViewComponent : ViewComponent
{
    private readonly ICartService _cartService;

    public CartSummaryViewComponent(ICartService cartService)
    {
        _cartService = cartService;
    }

    public async Task<IViewComponentResult> InvokeAsync()
    {
        var cartItems = await _cartService.GetCartItemsAsync();
        return View<IEnumerable<CartItemViewModel>>(cartItems);
    }
}
```

## Soru 29: Attribute Routing ve Constraints
**Soru:** Aşağıdaki route tanımlamalarından hangisi geçerli değildir?

```csharp
[ApiController]
[Route("api/[controller]")]
public class ProductsController : ControllerBase
{
    // Route 1
    [HttpGet("{id:int}")]
    public IActionResult GetById(int id) { }

    // Route 2
    [HttpGet("category/{categoryName:alpha:minlength(3)}")]
    public IActionResult GetByCategory(string categoryName) { }

    // Route 3
    [HttpGet("search/{query:required}")]
    public IActionResult Search(string query) { }

    // Route 4
    [HttpGet("{*path}")]
    public IActionResult GetByPath(string path) { }
}
```

**Şıklar:**

A) Route 1

B) Route 2

C) Route 3

D) Route 4

**Cevap:** C) Route 3

**Açıklama:**
- required constraint geçerli bir route constraint değildir
- Doğru yaklaşım [HttpGet("search/{query}")] şeklinde olmalıdır
- Parametrenin zorunluluğu [Required] attribute ile sağlanmalıdır
- Route constraint'ler: int, bool, datetime, decimal, double, float, guid, long, minlength, maxlength, length, min, max, range, alpha, regex

## Soru 30: Model Binding ve Validation
**Soru:** Aşağıdaki model binding ve validation yaklaşımlarından hangisi doğrudur?

```csharp
public class OrderController : Controller
{
    // Yaklaşım 1
    [HttpPost]
    public IActionResult Create([FromBody] OrderViewModel model)
    {
        if (!ModelState.IsValid)
            return BadRequest(ModelState);
            
        // ... implementation
    }

    // Yaklaşım 2
    [HttpPost]
    public IActionResult Update([Bind("Id,Name,Price")] Product product)
    {
        if (TryValidateModel(product))
            return View(product);
            
        // ... implementation
    }

    // Yaklaşım 3
    [HttpPost]
    public IActionResult Process([FromForm] OrderDto dto, [FromQuery] string reference)
    {
        if (dto == null)
            return BadRequest();
            
        // ... implementation
    }

    // Yaklaşım 4
    [HttpPost]
    public async Task<IActionResult> Submit([FromBody] Order order)
    {
        var validationResults = await _validator.ValidateAsync(order);
        if (!validationResults.IsValid)
            return BadRequest(validationResults.Errors);
            
        // ... implementation
    }
}
```

**Şıklar:**

A) Yaklaşım 1

B) Yaklaşım 2

C) Yaklaşım 3

D) Yaklaşım 4

**Cevap:** D) Yaklaşım 4

**Açıklama:**
- FluentValidation kullanımı daha esnek ve güçlüdür
- Özel validation kuralları tanımlanabilir
- Validation logic'i model dışında tutulur
- Async validation desteklenir

## Soru 31: Dependency Injection ve Service Registration
**Soru:** Aşağıdaki servis kayıt senaryolarından hangisi yanlıştır?

```csharp
public class Startup
{
    // Senaryo 1
    services.AddScoped<IOrderService>(sp => {
        var dbContext = sp.GetRequiredService<ApplicationDbContext>();
        var logger = sp.GetRequiredService<ILogger<OrderService>>();
        return new OrderService(dbContext, logger);
    });

    // Senaryo 2
    services.AddSingleton<ICacheService, RedisCacheService>(sp => {
        var configuration = sp.GetRequiredService<IConfiguration>();
        var options = new RedisCacheOptions 
        {
            Configuration = configuration["Redis:ConnectionString"]
        };
        return new RedisCacheService(options);
    });

    // Senaryo 3
    services.AddTransient<IEmailService>(sp => {
        var emailService = new SmtpEmailService();
        emailService.Configure(options => {
            options.Host = "smtp.example.com";
            options.Port = 587;
        });
        return emailService;
    });

    // Senaryo 4
    services.AddScoped<IUserService, UserService>()
           .AddScoped<IAuthService>(sp => {
                var userService = sp.GetService<IUserService>();
                return new AuthService(userService);
           });
}
```

**Şıklar:**

A) Senaryo 1

B) Senaryo 2

C) Senaryo 3

D) Senaryo 4

**Cevap:** C) Senaryo 3

**Açıklama:**
- Konfigürasyon options pattern kullanılarak yapılmalıdır
- IOptions<T> kullanılmalıdır
- Doğru implementasyon:
```csharp
services.Configure<SmtpOptions>(configuration.GetSection("Smtp"));
services.AddTransient<IEmailService, SmtpEmailService>();
```

## Soru 32: Exception Handling Middleware
**Soru:** Aşağıdaki exception handling middleware implementasyonlarından hangisi en uygunudur?

```csharp
// Implementasyon 1
app.Use(async (context, next) =>
{
    try
    {
        await next();
    }
    catch (Exception ex)
    {
        context.Response.StatusCode = 500;
        await context.Response.WriteAsync("An error occurred");
    }
});

// Implementasyon 2
app.UseExceptionHandler(errorApp =>
{
    errorApp.Run(async context =>
    {
        context.Response.StatusCode = 500;
        context.Response.ContentType = "application/json";
        
        var error = context.Features.Get<IExceptionHandlerFeature>();
        if (error != null)
        {
            await context.Response.WriteAsync(JsonSerializer.Serialize(new 
            {
                Message = error.Error.Message
            }));
        }
    });
});

// Implementasyon 3
app.UseMiddleware<CustomExceptionMiddleware>();

public class CustomExceptionMiddleware
{
    private readonly RequestDelegate _next;
    
    public CustomExceptionMiddleware(RequestDelegate next)
    {
        _next = next;
    }
    
    public async Task InvokeAsync(HttpContext context)
    {
        try
        {
            await _next(context);
        }
        catch (Exception ex)
        {
            await HandleExceptionAsync(context, ex);
        }
    }
    
    private async Task HandleExceptionAsync(HttpContext context, Exception ex)
    {
        context.Response.ContentType = "application/json";
        
        var response = new ErrorResponse();
        
        switch (ex)
        {
            case NotFoundException notFound:
                context.Response.StatusCode = 404;
                response.Message = notFound.Message;
                break;
            case ValidationException validation:
                context.Response.StatusCode = 400;
                response.Message = validation.Message;
                response.Errors = validation.Errors;
                break;
            default:
                context.Response.StatusCode = 500;
                response.Message = "An unexpected error occurred";
                break;
        }
        
        await context.Response.WriteAsync(JsonSerializer.Serialize(response));
    }
}

// Implementasyon 4
app.UseExceptionHandler("/Home/Error");
```

**Şıklar:**

A) Implementasyon 1

B) Implementasyon 2

C) Implementasyon 3

D) Implementasyon 4

**Cevap:** C) Implementasyon 3

**Açıklama:**
- Özel exception tipleri için farklı handling sağlar
- Yapılandırılabilir ve genişletilebilir
- Detaylı hata bilgisi döner
- Exception'ları merkezi olarak yönetir

## Soru 33: API Versioning
**Soru:** Aşağıdaki API versiyonlama yaklaşımlarından hangisi en uygun değildir?

```csharp
// Yaklaşım 1
[ApiController]
[Route("api/v{version:apiVersion}/[controller]")]
[ApiVersion("1.0")]
public class ProductsController : ControllerBase
{
    [HttpGet]
    public IActionResult Get() { }
}

// Yaklaşım 2
[ApiController]
[Route("api/[controller]")]
public class OrdersController : ControllerBase
{
    [HttpGet, MapToApiVersion("1.0")]
    public IActionResult GetV1() { }
    
    [HttpGet, MapToApiVersion("2.0")]
    public IActionResult GetV2() { }
}

// Yaklaşım 3
[ApiController]
[Route("api/[controller]")]
public class CustomersController : ControllerBase
{
    [HttpGet]
    public IActionResult Get([FromQuery] string version) 
    {
        switch(version)
        {
            case "2.0":
                return Ok("Version 2.0");
            default:
                return Ok("Version 1.0");
        }
    }
}

// Yaklaşım 4
[ApiController]
[Route("api/[controller]")]
public class UsersController : ControllerBase
{
    [HttpGet]
    public IActionResult Get()
    {
        if (Request.Headers.TryGetValue("api-version", out var version))
        {
            switch(version.ToString())
            {
                case "2.0":
                    return Ok("Version 2.0");
                default:
                    return Ok("Version 1.0");
            }
        }
        return Ok("Default Version");
    }
}
```

**Şıklar:**

A) Yaklaşım 1

B) Yaklaşım 2

C) Yaklaşım 3

D) Yaklaşım 4

**Cevap:** C) Yaklaşım 3

**Açıklama:**
- Query string ile versiyonlama önerilmez
- URL veya header based versiyonlama tercih edilmelidir
- Microsoft.AspNetCore.Mvc.Versioning paketi kullanılmalıdır
- Versiyonlama stratejisi tutarlı olmalıdır

## Soru 34: SignalR Implementation
**Soru:** Aşağıdaki SignalR hub implementasyonlarından hangisi en doğrudur?

```csharp
// Hub 1
public class NotificationHub : Hub
{
    public async Task SendNotification(string message)
    {
        await Clients.All.SendAsync("ReceiveNotification", message);
    }
}

// Hub 2
public class ChatHub : Hub<IChatClient>
{
    private readonly IUserTracker _userTracker;
    
    public ChatHub(IUserTracker userTracker)
    {
        _userTracker = userTracker;
    }
    
    public async Task SendMessage(string user, string message)
    {
        await Clients.All.ReceiveMessage(user, message);
        await _userTracker.TrackMessage(user, message);
    }
    
    public override async Task OnConnectedAsync()
    {
        await _userTracker.UserConnected(Context.ConnectionId);
        await base.OnConnectedAsync();
    }
}

// Hub 3
public class GameHub : Hub
{
    private static readonly Dictionary<string, string> _users 
        = new Dictionary<string, string>();
        
    public async Task JoinGame(string userName)
    {
        _users[Context.ConnectionId] = userName;
        await Clients.All.SendAsync("UserJoined", userName);
    }
}

// Hub 4
public class DataHub : Hub
{
    public void BroadcastData(object data)
    {
        Clients.All.SendAsync("ReceiveData", data);
    }
}
```

**Şıklar:**

A) Hub 1

B) Hub 2

C) Hub 3

D) Hub 4

**Cevap:** B) Hub 2

**Açıklama:**
- Strongly-typed hub kullanıyor
- Dependency injection kullanıyor
- Connection lifecycle yönetimi yapıyor
- Async/await pattern doğru kullanılmış

## Soru 35: Caching Implementation
**Soru:** Aşağıdaki caching implementasyonlarından hangisi en uygun değildir?

```csharp
// Implementasyon 1
[ResponseCache(Duration = 3600)]
public IActionResult GetCategories()
{
    return Ok(_categoryService.GetAll());
}

// Implementasyon 2
public async Task<IEnumerable<Product>> GetProducts()
{
    var cacheKey = "products_all";
    var products = await _cache.GetAsync<IEnumerable<Product>>(cacheKey);
    
    if (products == null)
    {
        products = await _productRepository.GetAllAsync();
        await _cache.SetAsync(cacheKey, products, TimeSpan.FromMinutes(30));
    }
    
    return products;
}

// Implementasyon 3
public class CacheService
{
    private static readonly Dictionary<string, object> _cache 
        = new Dictionary<string, object>();
        
    public T Get<T>(string key) where T : class
    {
        if (_cache.ContainsKey(key))
            return _cache[key] as T;
        return null;
    }
    
    public void Set<T>(string key, T value) where T : class
    {
        _cache[key] = value;
    }
}

// Implementasyon 4
public async Task<Product> GetProductById(int id)
{
    return await _cache.GetOrCreateAsync($"product_{id}", async entry =>
    {
        entry.SlidingExpiration = TimeSpan.FromMinutes(10);
        entry.AbsoluteExpirationRelativeToNow = TimeSpan.FromHours(1);
        return await _productRepository.GetByIdAsync(id);
    });
}
```

**Şıklar:**

A) Implementasyon 1

B) Implementasyon 2

C) Implementasyon 3

D) Implementasyon 4

**Cevap:** C) Implementasyon 3

**Açıklama:**
- Static Dictionary thread-safe değil
- Memory management yapılmıyor
- Cache expiration yok
- Distributed caching desteklenmiyor

## Soru 36: Razor View Engine
**Soru:** Aşağıdaki Razor view kodunda hangi hata(lar) vardır?

```csharp
@model List<ProductViewModel>

<div class="container">
    @foreach (var product in Model)
    {
        @if (product.Price > 100)
        {
            <div class="expensive-product">
                <h3>@product.Name</h3>
                @{ var discountedPrice = product.Price * 0.9; }
                <p>Fiyat: @discountedPrice</p>
            </div>
        } else {
            <div class="normal-product">
                <h3>@product.Name</h3>
                <p>Fiyat: @product.Price</p>
            }
        }
    }
</div>
```

**Şıklar:**

A) HTML div kapanış etiketi yanlış yerde

B) discountedPrice değişkeni tanımlaması hatalı

C) else bloğu yanlış konumda

D) Hepsi

**Cevap:** A) HTML div kapanış etiketi yanlış yerde

**Açıklama:**
- HTML etiketlerinin açılış ve kapanışları eşleşmiyor
- else bloğundaki div kapanış etiketi yanlış yerde
- Doğru implementasyon:
```csharp
@model List<ProductViewModel>

<div class="container">
    @foreach (var product in Model)
    {
        @if (product.Price > 100)
        {
            <div class="expensive-product">
                <h3>@product.Name</h3>
                @{ var discountedPrice = product.Price * 0.9; }
                <p>Fiyat: @discountedPrice</p>
            </div>
        }
        else
        {
            <div class="normal-product">
                <h3>@product.Name</h3>
                <p>Fiyat: @product.Price</p>
            }
        }
    }
</div>
```

## Soru 37: Model Validation
**Soru:** Aşağıdaki model sınıfında hangi validation attribute'ları eksiktir?

```csharp
public class OrderViewModel
{
    public int Id { get; set; }

    [Required]
    public string CustomerName { get; set; }

    [Required]
    public string Email { get; set; }

    public decimal TotalAmount { get; set; }

    public DateTime OrderDate { get; set; }

    public string? Notes { get; set; }

    public List<OrderItem> Items { get; set; }
}
```

**Şıklar:**

A) Email için [EmailAddress]

B) TotalAmount için [Range]

C) CustomerName için [StringLength]

D) Hepsi

**Cevap:** D) Hepsi

**Açıklama:**
Doğru implementasyon:
```csharp
public class OrderViewModel
{
    public int Id { get; set; }

    [Required(ErrorMessage = "Müşteri adı zorunludur")]
    [StringLength(100, MinimumLength = 3, ErrorMessage = "Müşteri adı 3-100 karakter arasında olmalıdır")]
    public string CustomerName { get; set; }

    [Required(ErrorMessage = "Email adresi zorunludur")]
    [EmailAddress(ErrorMessage = "Geçerli bir email adresi giriniz")]
    public string Email { get; set; }

    [Required(ErrorMessage = "Toplam tutar zorunludur")]
    [Range(0.01, double.MaxValue, ErrorMessage = "Toplam tutar 0'dan büyük olmalıdır")]
    public decimal TotalAmount { get; set; }

    [Required(ErrorMessage = "Sipariş tarihi zorunludur")]
    [DataType(DataType.DateTime)]
    public DateTime OrderDate { get; set; }

    [StringLength(500, ErrorMessage = "Notlar en fazla 500 karakter olabilir")]
    public string? Notes { get; set; }

    [Required(ErrorMessage = "En az bir ürün eklenmelidir")]
    [MinLength(1, ErrorMessage = "En az bir ürün eklenmelidir")]
    public List<OrderItem> Items { get; set; }
}
```

## Soru 38: Routing ve URL Generation
**Soru:** Aşağıdaki controller ve action metodlarından hangisi yanlış route tanımlaması içermektedir?

```csharp
[Route("api/[controller]")]
public class ProductsController : ControllerBase
{
    // Route 1
    [HttpGet("{id:int}")]
    public IActionResult GetProduct(int id) { }

    // Route 2
    [HttpGet("category/{name}/page/{pageNumber}")]
    public IActionResult GetByCategory(string name, int pageNumber) { }

    // Route 3
    [HttpPost("{categoryId}/{productName}")]
    public IActionResult Create(int categoryId, string productName) { }

    // Route 4
    [HttpGet("search/{query?}")]
    public IActionResult Search([FromRoute]string query, [FromQuery]string sortBy) { }
}
```

**Şıklar:**

A) Route 1

B) Route 2

C) Route 3

D) Route 4

**Cevap:** C) Route 3

**Açıklama:**
- POST işlemleri için route parametreleri kullanılmamalı
- POST verisi request body'de gönderilmeli
- Doğru implementasyon:
```csharp
[HttpPost]
public IActionResult Create([FromBody] CreateProductDto dto) { }
```

## Soru 39: Action Methods
**Soru:** Aşağıdaki action method implementasyonlarından hangisi en doğrudur?

```csharp
// Method 1
public async Task<IActionResult> GetUserProfile(int userId)
{
    var user = await _userService.GetByIdAsync(userId);
    if (user == null)
        return NotFound();
    return View(user);
}

// Method 2
public IActionResult UpdateProfile(UserProfileViewModel model)
{
    if (ModelState.IsValid)
    {
        _userService.UpdateProfile(model);
        return RedirectToAction("Index");
    }
    return View(model);
}

// Method 3
public async Task<ActionResult> DeleteUser(int id)
{
    await _userService.DeleteAsync(id);
    return Json(new { success = true });
}

// Method 4
public async Task<IActionResult> CreateUser([FromBody] CreateUserDto dto)
{
    if (!ModelState.IsValid)
        return BadRequest(ModelState);
        
    var result = await _userService.CreateAsync(dto);
    return CreatedAtAction(nameof(GetUserProfile), new { userId = result.Id }, result);
}
```

**Şıklar:**

A) Method 1

B) Method 2

C) Method 3

D) Method 4

**Cevap:** D) Method 4

**Açıklama:**
Method 4 en doğru implementasyondur çünkü:
- Model validation kontrolü yapılıyor
- Async/await doğru kullanılmış
- CreatedAtAction ile doğru REST response dönülüyor
- Location header için endpoint bilgisi veriliyor
- DTO kullanılarak veri transferi yapılıyor

## Soru 40: Entity Framework Core
**Soru:** Aşağıdaki Entity Framework Core sorgu optimizasyonlarından hangisi yanlıştır?

```csharp
// Query 1
var result1 = await _context.Orders
    .Include(o => o.Customer)
    .Include(o => o.OrderItems)
    .Where(o => o.Status == OrderStatus.Pending)
    .Select(o => new OrderDto
    {
        Id = o.Id,
        CustomerName = o.Customer.Name,
        TotalAmount = o.OrderItems.Sum(i => i.Price)
    })
    .ToListAsync();

// Query 2
var result2 = await _context.Orders
    .Where(o => o.Status == OrderStatus.Pending)
    .Include(o => o.Customer)
    .Include(o => o.OrderItems)
    .ToListAsync();

// Query 3
var result3 = await _context.Orders
    .Include(o => o.Customer)
    .Include(o => o.OrderItems)
    .ToListAsync()
    .Where(o => o.Status == OrderStatus.Pending);

// Query 4
var result4 = await _context.Orders
    .Where(o => o.Status == OrderStatus.Pending)
    .Select(o => new OrderDto
    {
        Id = o.Id,
        CustomerName = o.Customer.Name,
        TotalAmount = o.OrderItems.Sum(i => i.Price)
    })
    .ToListAsync();
```

**Şıklar:**

A) Query 1

B) Query 2

C) Query 3

D) Query 4

**Cevap:** C) Query 3

**Açıklama:**
Query 3 yanlıştır çünkü:
- ToListAsync() çağrısı tüm verileri memory'e çeker
- Filtreleme memory'de yapılır
- Bu durum performans ve memory kullanımı açısından verimsizdir
- Doğru yaklaşım Query 1'deki gibi olmalıdır

## Soru 41: Authentication ve Authorization
**Soru:** Aşağıdaki authentication ve authorization implementasyonlarından hangisi güvenlik açığına neden olabilir?

```csharp
// Implementation 1
[Authorize]
public class AdminController : Controller
{
    [HttpPost]
    public async Task<IActionResult> DeleteUser(int userId)
    {
        await _userService.DeleteAsync(userId);
        return Ok();
    }
}

// Implementation 2
[Authorize(Roles = "Admin")]
public class UsersController : Controller
{
    [AllowAnonymous]
    [HttpGet("api/users/{id}")]
    public async Task<IActionResult> GetUser(int id)
    {
        var user = await _userService.GetByIdAsync(id);
        return Ok(user);
    }
}

// Implementation 3
public class AccountController : Controller
{
    [HttpPost]
    public async Task<IActionResult> Login(LoginViewModel model)
    {
        var user = await _userManager.FindByEmailAsync(model.Email);
        if (user != null && await _userManager.CheckPasswordAsync(user, model.Password))
        {
            await _signInManager.SignInAsync(user, model.RememberMe);
            return RedirectToAction("Index", "Home");
        }
        return View(model);
    }
}

// Implementation 4
[Authorize]
public class ProfileController : Controller
{
    [HttpGet]
    public async Task<IActionResult> Edit(int userId)
    {
        var user = await _userService.GetByIdAsync(userId);
        return View(user);
    }
}
```

**Şıklar:**

A) Implementation 1

B) Implementation 2

C) Implementation 3

D) Implementation 4

**Cevap:** D) Implementation 4

**Açıklama:**
Implementation 4'te güvenlik açığı vardır çünkü:
- userId parametresi üzerinde yetki kontrolü yapılmıyor
- Herhangi bir kullanıcı, başka bir kullanıcının profilini düzenleyebilir
- Doğru implementasyon:
```csharp
[Authorize]
public class ProfileController : Controller
{
    [HttpGet]
    public async Task<IActionResult> Edit()
    {
        var userId = User.FindFirst(ClaimTypes.NameIdentifier)?.Value;
        var user = await _userService.GetByIdAsync(userId);
        return View(user);
    }
}
```

## Soru 42: Middleware Pipeline
**Soru:** Aşağıdaki middleware implementasyonlarından hangisi hatalıdır?

```csharp
// Middleware 1
public class RequestLoggingMiddleware
{
    private readonly RequestDelegate _next;
    private readonly ILogger<RequestLoggingMiddleware> _logger;

    public RequestLoggingMiddleware(RequestDelegate next, ILogger<RequestLoggingMiddleware> logger)
    {
        _next = next;
        _logger = logger;
    }

    public async Task InvokeAsync(HttpContext context)
    {
        _logger.LogInformation($"Request: {context.Request.Path}");
        await _next(context);
        _logger.LogInformation($"Response Status: {context.Response.StatusCode}");
    }
}

// Middleware 2
public class ErrorHandlingMiddleware
{
    private readonly RequestDelegate _next;

    public ErrorHandlingMiddleware(RequestDelegate next)
    {
        _next = next;
    }

    public async Task Invoke(HttpContext context)
    {
        try
        {
            await _next(context);
        }
        catch (Exception ex)
        {
            context.Response.StatusCode = 500;
            await context.Response.WriteAsync("An error occurred");
        }
    }
}

// Middleware 3
public class AuthenticationMiddleware
{
    private readonly RequestDelegate _next;

    public AuthenticationMiddleware(RequestDelegate next)
    {
        _next = next;
    }

    public void Invoke(HttpContext context)
    {
        var token = context.Request.Headers["Authorization"].FirstOrDefault();
        if (string.IsNullOrEmpty(token))
        {
            context.Response.StatusCode = 401;
            return;
        }
        _next(context);
    }
}

// Middleware 4
public class CachingMiddleware
{
    private readonly RequestDelegate _next;
    private readonly IMemoryCache _cache;

    public CachingMiddleware(RequestDelegate next, IMemoryCache cache)
    {
        _next = next;
        _cache = cache;
    }

    public async Task InvokeAsync(HttpContext context)
    {
        var key = context.Request.Path.ToString();
        if (_cache.TryGetValue(key, out var cachedResponse))
        {
            await context.Response.WriteAsync(cachedResponse.ToString());
            return;
        }
        await _next(context);
    }
}
```

**Şıklar:**

A) Middleware 1

B) Middleware 2

C) Middleware 3

D) Middleware 4

**Cevap:** C) Middleware 3

**Açıklama:**
Middleware 3 hatalıdır çünkü:
- Async/await kullanılmamış
- _next delegate async olarak çağrılmamış
- Token kontrolü sonrası response yazılmamış
- Doğru implementasyon:
```csharp
public class AuthenticationMiddleware
{
    private readonly RequestDelegate _next;

    public AuthenticationMiddleware(RequestDelegate next)
    {
        _next = next;
    }

    public async Task InvokeAsync(HttpContext context)
    {
        var token = context.Request.Headers["Authorization"].FirstOrDefault();
        if (string.IsNullOrEmpty(token))
        {
            context.Response.StatusCode = 401;
            await context.Response.WriteAsync("Unauthorized");
            return;
        }
        await _next(context);
    }
}
```

## Soru 43: Configuration Management
**Soru:** Aşağıdaki configuration yönetimi yaklaşımlarından hangisi en güvenlidir?

```csharp
// Approach 1
public class EmailService
{
    private readonly string _smtpServer = "smtp.example.com";
    private readonly string _username = "admin";
    private readonly string _password = "password123";

    public async Task SendEmailAsync(string to, string subject, string body)
    {
        // Implementation
    }
}

// Approach 2
public class PaymentService
{
    private readonly IConfiguration _configuration;

    public PaymentService(IConfiguration configuration)
    {
        _configuration = configuration;
    }

    public async Task ProcessPaymentAsync(decimal amount)
    {
        var apiKey = _configuration["PaymentApi:Key"];
        // Implementation
    }
}

// Approach 3
public class DatabaseService
{
    private readonly string _connectionString;

    public DatabaseService(IOptions<DatabaseOptions> options)
    {
        _connectionString = options.Value.ConnectionString;
    }
}

// Approach 4
public class AuthService
{
    private readonly IConfiguration _configuration;

    public AuthService(IConfiguration configuration)
    {
        _configuration = configuration;
    }

    public string GetJwtKey()
    {
        return Environment.GetEnvironmentVariable("JWT_KEY") 
            ?? _configuration["Jwt:Key"];
    }
}
```

**Şıklar:**

A) Approach 1

B) Approach 2

C) Approach 3

D) Approach 4

**Cevap:** D) Approach 4

**Açıklama:**
Approach 4 en güvenlidir çünkü:
- Environment variable'ları öncelikli olarak kullanır
- Fallback mekanizması içerir
- Hassas bilgileri kod içinde tutmaz
- Configuration değerlerini DI ile alır

## Soru 44: Logging
**Soru:** Aşağıdaki logging implementasyonlarından hangisi en doğrudur?

```csharp
// Implementation 1
public class UserService
{
    private readonly ILogger<UserService> _logger;

    public UserService(ILogger<UserService> logger)
    {
        _logger = logger;
    }

    public async Task<User> CreateUserAsync(CreateUserDto dto)
    {
        try
        {
            _logger.LogInformation($"Creating user: {dto.Email}");
            var user = await _userRepository.CreateAsync(dto);
            _logger.LogInformation($"User created: {user.Id}");
            return user;
        }
        catch (Exception ex)
        {
            _logger.LogError(ex, "Error creating user");
            throw;
        }
    }
}

// Implementation 2
public class OrderService
{
    public async Task<Order> CreateOrderAsync(OrderDto dto)
    {
        Debug.WriteLine($"Creating order for customer: {dto.CustomerId}");
        var order = await _orderRepository.CreateAsync(dto);
        Debug.WriteLine($"Order created: {order.Id}");
        return order;
    }
}

// Implementation 3
public class ProductService
{
    private readonly ILogger _logger;

    public ProductService(ILoggerFactory loggerFactory)
    {
        _logger = loggerFactory.CreateLogger("ProductService");
    }

    public async Task<Product> UpdateProductAsync(UpdateProductDto dto)
    {
        _logger.LogInformation("Updating product: " + dto.Id);
        var product = await _productRepository.UpdateAsync(dto);
        _logger.LogInformation("Product updated: " + product.Id);
        return product;
    }
}

// Implementation 4
public class PaymentService
{
    private static readonly ILogger Logger = LogManager.GetCurrentClassLogger();

    public async Task ProcessPaymentAsync(PaymentDto dto)
    {
        Logger.Info($"Processing payment: {dto.Amount}");
        await _paymentGateway.ProcessAsync(dto);
        Logger.Info($"Payment processed");
    }
}
```

**Şıklar:**

A) Implementation 1

B) Implementation 2

C) Implementation 3

D) Implementation 4

**Cevap:** A) Implementation 1

**Açıklama:**
Implementation 1 en doğrudur çünkü:
- Dependency injection kullanıyor
- Exception handling içeriyor
- Structured logging yapıyor
- Log seviyelerini doğru kullanıyor
- Exception detaylarını loglama sırasında kaydediyor

## Soru 45: Performance Optimization
**Soru:** Aşağıdaki performans optimizasyon yaklaşımlarından hangisi yanlıştır?

```csharp
// Approach 1
public class ProductController : Controller
{
    [ResponseCache(Duration = 3600)]
    public async Task<IActionResult> GetProducts()
    {
        var products = await _productService.GetAllAsync();
        return View(products);
    }
}

// Approach 2
public class CategoryService
{
    private readonly IMemoryCache _cache;
    
    public async Task<List<Category>> GetCategoriesAsync()
    {
        var cacheKey = "categories_all";
        return await _cache.GetOrCreateAsync(cacheKey, async entry =>
        {
            entry.SlidingExpiration = TimeSpan.FromMinutes(30);
            return await _categoryRepository.GetAllAsync();
        });
    }
}

// Approach 3
public class OrderService
{
    public async Task<List<OrderDto>> GetOrdersAsync()
    {
        var orders = await _context.Orders
            .Include(o => o.Customer)
            .Include(o => o.OrderItems)
            .Include(o => o.OrderItems).ThenInclude(i => i.Product)
            .ToListAsync();
            
        return orders.Select(o => new OrderDto
        {
            Id = o.Id,
            CustomerName = o.Customer.Name,
            Items = o.OrderItems.Select(i => i.Product.Name).ToList()
        }).ToList();
    }
}

// Approach 4
public class UserService
{
    private readonly IDistributedCache _cache;
    
    public async Task<UserDto> GetUserAsync(int id)
    {
        var cacheKey = $"user_{id}";
        var user = await _cache.GetAsync<UserDto>(cacheKey);
        if (user == null)
        {
            user = await _userRepository.GetByIdAsync(id);
            await _cache.SetAsync(cacheKey, user, TimeSpan.FromMinutes(10));
        }
        return user;
    }
}
```

**Şıklar:**

A) Approach 1

B) Approach 2

C) Approach 3

D) Approach 4

**Cevap:** C) Approach 3

**Açıklama:**
Approach 3 yanlıştır çünkü:
- Tüm verileri önce memory'e çekiyor
- Dönüşüm işlemini memory'de yapıyor
- Gereksiz Include'lar var
- Doğru implementasyon:
```csharp
public async Task<List<OrderDto>> GetOrdersAsync()
{
    return await _context.Orders
        .Select(o => new OrderDto
        {
            Id = o.Id,
            CustomerName = o.Customer.Name,
            Items = o.OrderItems.Select(i => i.Product.Name).ToList()
        })
        .ToListAsync();
}
```
