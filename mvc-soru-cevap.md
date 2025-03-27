<# ASP.NET Core MVC Soru ve Cevapları

## 1. Routing (Yönlendirme)

Routing, istemciden gelen HTTP isteklerini uygun denetleyici (controller) ve eylem metoduna (action method) yönlendiren mekanizmadır. ASP.NET Core MVC, varsayılan olarak geleneksel yönlendirme (conventional routing) ve öznitelik yönlendirme (attribute routing) olmak üzere iki farklı yönlendirme türü sunar.

### Soru 1

ASP.NET Core MVC'de öznitelik yönlendirme (attribute routing) nasıl tanımlanır?

A) [Route("Home/Index")]
B) [Map("Home/Index")]
C) [Url("Home/Index")]
D) [Action("Home/Index")]

**Cevap:** A) [Route("Home/Index")]

### Soru 2

Aşağıdakilerden hangisi geleneksel yönlendirme (conventional routing) tanımı için doğrudur?

A) app.UseRouting(routes => { routes.MapControllerRoute("default", "{controller=Home}/{action=Index}/{id?}"); });
B) app.MapRoutes("default", "{controller=Home}/{action=Index}/{id?}");
C) app.UseEndpoints(endpoints => { endpoints.MapRoute("default", "{controller=Home}/{action=Index}/{id?}"); });
D) app.ConfigureRouting(routes => { routes.Map("default", "{controller=Home}/{action=Index}/{id?}"); });

**Cevap:** C) app.UseEndpoints(endpoints => { endpoints.MapRoute("default", "{controller=Home}/{action=Index}/{id?}"); });

## 2. Model Binding (Model Bağlama)

Model binding, HTTP isteklerindeki verileri otomatik olarak C# nesnelerine dönüştüren bir mekanizmadır. Bu özellik, form verileri, JSON nesneleri ve sorgu parametreleri gibi girdileri model sınıflarına bağlamayı sağlar.

### Soru 1

Aşağıdakilerden hangisi model bağlama sürecinde kullanılan veri kaynaklarından biri değildir?

A) Query string
B) Form verileri
C) XML dosyaları
D) JSON gövdesi (request body)

**Cevap:** C) XML dosyaları

### Soru 2

ASP.NET Core MVC'de FromBody özniteliği hangi durumda kullanılır?

A) Model verisini yalnızca URL parametrelerinden almak için
B) Model verisini yalnızca JSON gövdesinden almak için
C) Model verisini yalnızca form verilerinden almak için
D) Model verisini yalnızca çerezlerden almak için

**Cevap:** B) Model verisini yalnızca JSON gövdesinden almak için

## 3. Model Validation (Model Doğrulama)

Model doğrulama, istemciden gelen verilerin belirlenen kurallara uyup uymadığını kontrol eden bir mekanizmadır. ASP.NET Core, DataAnnotations öznitelikleriyle model doğrulama işlemlerini sağlar.

### Soru 1

Aşağıdaki özniteliklerden hangisi bir model özelliğinin boş olamayacağını belirtir?

A) [Required]
B) [MaxLength(50)]
C) [Range(1, 100)]
D) [RegularExpression("[a-zA-Z]+")]

**Cevap:** A) [Required]

### Soru 2

[Range(1, 100)] özniteliği ne işe yarar?

A) Bir özelliğin sadece 1 ile 100 arasında değer almasını sağlar
B) Özelliğin yalnızca sayısal karakterlerden oluşmasını sağlar
C) Özelliğin en fazla 100 karakter uzunluğunda olmasını sağlar
D) Özelliğin yalnızca zorunlu (required) olmasını sağlar

**Cevap:** A) Bir özelliğin sadece 1 ile 100 arasında değer almasını sağlar

## 4. Dependency Injection (Bağımlılık Enjeksiyonu - DI)

Bağımlılık enjeksiyonu (Dependency Injection), nesneler arasındaki bağımlılıkları dışarıdan yönetmek için kullanılan bir tasarım desenidir. ASP.NET Core, varsayılan olarak bir DI konteyneri sunar.

### Soru 1

ASP.NET Core'da bir servisi bağımlılık enjeksiyonu sistemine eklemek için hangi yöntem kullanılır?

A) services.AddService<IMyService, MyService>();
B) services.Register<IMyService, MyService>();
C) services.AddScoped<IMyService, MyService>();
D) services.Include<IMyService, MyService>();

**Cevap:** C) services.AddScoped<IMyService, MyService>();

### Soru 2

Aşağıdaki DI yaşam döngüsü türlerinden hangisi her HTTP isteğinde yeni bir örnek oluşturur?

A) Singleton
B) Transient
C) Scoped
D) Static

**Cevap:** C) Scoped

## 5. Filters (Filtreler)

Filtreler, ASP.NET Core MVC uygulamalarında isteklere müdahale etmek ve özel işlemler gerçekleştirmek için kullanılan bileşenlerdir.

### Soru 1

Aşağıdaki filtre türlerinden hangisi yetkilendirme (authentication) kontrolleri için kullanılır?

A) Action Filter
B) Authorization Filter
C) Resource Filter
D) Exception Filter

**Cevap:** B) Authorization Filter

### Soru 2

Hata yakalamak ve özel hata sayfaları göstermek için hangi filtre kullanılır?

A) Action Filter
B) Exception Filter
C) Result Filter
D) Authorization Filter

**Cevap:** B) Exception Filter

## 6. Areas (Bölgeler)

Areas, büyük ASP.NET Core MVC projelerinde kodu modüler hale getirmek için kullanılan bir yapıdır. Her area, kendi içinde Controllers, Views ve Models klasörlerine sahip olabilir ve büyük ölçekli uygulamalarda daha düzenli bir yapı sağlar.

### Soru 1

ASP.NET Core MVC'de bir area oluşturmak için hangi öznitelik kullanılır?

A) [Module("Admin")]
B) [Area("Admin")]
C) [Section("Admin")]
D) [Region("Admin")]

**Cevap:** B) [Area("Admin")]

### Soru 2

Bir area içindeki bir denetleyiciye (controller) yönlendirme yapmak için hangi URL yapısı kullanılır?

A) /Admin/Home/Index
B) /Areas/Admin/Home/Index
C) /Home/Index/Admin
D) /Index/Home/Admin

**Cevap:** A) /Admin/Home/Index

## 7. Web APIs (Web API'ler)

ASP.NET Core Web API, HTTP istekleriyle çalışan RESTful servisler geliştirmek için kullanılan bir çerçevedir. Web API, JSON formatında veri alıp göndermek için yaygın olarak kullanılır.

### Soru 1

Aşağıdakilerden hangisi bir ASP.NET Core Web API denetleyicisinde (controller) JSON yanıtı döndürmek için kullanılır?

A) return View(data);
B) return Json(data);
C) return Ok(data);
D) return Redirect(data);

**Cevap:** C) return Ok(data);

### Soru 2

Web API'de HttpGet, HttpPost, HttpPut ve HttpDelete neyi temsil eder?

A) MVC yönlendirme kuralları
B) HTTP istek yöntemleri
C) Veri tabanı bağlantı türleri
D) Oturum yönetim yöntemleri

**Cevap:** B) HTTP istek yöntemleri

## 8. Testability (Test Edilebilirlik)

ASP.NET Core MVC, bağımlılık enjeksiyonu (DI) kullanarak test edilebilirliği artırır. Birim testler ve entegrasyon testleri ile kodun doğruluğu test edilebilir.

### Soru 1

ASP.NET Core MVC'de bağımlılık enjeksiyonu (DI) test edilebilirliği nasıl artırır?

A) Kod tekrarını azaltarak
B) Nesneleri dışarıdan sağlayarak
C) Veritabanı erişimini hızlandırarak
D) Uygulamanın performansını artırarak

**Cevap:** B) Nesneleri dışarıdan sağlayarak

### Soru 2

Aşağıdakilerden hangisi birim testlerinde kullanılan mocking araçlarından biridir?

A) Entity Framework
B) Moq
C) Razor
D) Bootstrap

**Cevap:** B) Moq

## 9. Razor View Engine (Razor Görünüm Motoru)

Razor, ASP.NET Core MVC'de HTML ve C# kodlarını birleştirmek için kullanılan bir görünüm motorudur.

### Soru 1

ASP.NET Core MVC'de Razor sözdiziminde C# kodu nasıl başlatılır?

A) {{ code }}
B) <? code ?>
C) <% code %>
D) @code

**Cevap:** D) @code

### Soru 2

Razor görünümlerinde bir değişken tanımlamak için hangi sözdizimi kullanılır?

A) @var message = "Merhaba Dünya";
B) {{ var message = "Merhaba Dünya"; }}
C) <script> var message = "Merhaba Dünya"; </script>
D) <?php var message = "Merhaba Dünya"; ?>

**Cevap:** A) @var message = "Merhaba Dünya";

## 10. Strongly Typed Views (Güçlü Türlü Görünümler)

Güçlü türlü görünümler, model nesneleriyle doğrudan çalışarak daha güvenli ve hata yakalamayı kolaylaştıran bir yapı sunar.

### Soru 1

ASP.NET Core MVC'de güçlü türlü bir görünüm nasıl tanımlanır?

A) @model MyApp.Models.MyModel
B) @using MyApp.Models.MyModel
C) @include MyApp.Models.MyModel
D) @import MyApp.Models.MyModel

**Cevap:** A) @model MyApp.Models.MyModel

### Soru 2

Güçlü türlü bir görünümde Model.PropertyName kullanımı ne sağlar?

A) Model özelliklerine doğrudan erişim
B) Veritabanı bağlantısını yönetme
C) JavaScript ile etkileşim sağlama
D) Otomatik yönlendirme işlemi

**Cevap:** A) Model özelliklerine doğrudan erişim

## 11. Tag Helpers (Etiket Yardımcıları)

Tag Helpers, Razor sayfalarında HTML öğeleri üzerinde dinamik değişiklikler yapmayı sağlar.

### Soru 1

ASP.NET Core'da bir Tag Helper'ı etkinleştirmek için ne yapılmalıdır?

A) @using Microsoft.AspNetCore.Mvc.TagHelpers
B) @import TagHelpers
C) @addTagHelper \*, Microsoft.AspNetCore.Mvc.TagHelpers
D) @include TagHelpers

**Cevap:** C) @addTagHelper \*, Microsoft.AspNetCore.Mvc.TagHelpers

### Soru 2

ASP.NET Core MVC'de <input asp-for="Name" /> ifadesi ne işe yarar?

A) Bir input alanını modeldeki "Name" özelliğine bağlar
B) HTML form elemanını gizler
C) Sayfa yüklenmeden önce verileri doğrular
D) Yeni bir HTML etiketi oluşturur

**Cevap:** A) Bir input alanını modeldeki "Name" özelliğine bağlar

## 12. View Components (Görünüm Bileşenleri)

View Components, ASP.NET Core MVC'de parçalanmış ve yeniden kullanılabilir görünüm bileşenleri oluşturmak için kullanılır.

### Soru 1

Bir View Component nasıl çağrılır?

A) @Component.Invoke("MyComponent")
B) @ViewComponent("MyComponent")
C) @InvokeComponent("MyComponent")
D) @RenderComponent("MyComponent")

**Cevap:** B) @ViewComponent("MyComponent")

### Soru 2

View Component'lerde hangi metodun override edilmesi gerekir?

A) ExecuteViewComponent()
B) InvokeAsync()
C) RenderComponent()
D) LoadViewComponent()

**Cevap:** B) InvokeAsync()
