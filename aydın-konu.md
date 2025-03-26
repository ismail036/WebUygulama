# ASP.NET Core MVC Tutorial

## 1. MVC (Model-View-Controller) Tasarım Deseni

MVC, yazılım geliştirmede kullanıcı arayüzü ile iş mantığını birbirinden ayıran bir tasarım desenidir. Bu desen üç ana bileşenden oluşur:

1. **Model**
   - Uygulama verilerini ve iş mantığını içerir.
   - Kullanıcı arayüzüyle doğrudan etkileşime girmez.
   - Örneğin, bir öğrenci yönetim sistemi için "Student" sınıfı model olabilir.

2. **View**
   - Model'de bulunan verileri kullanıcıya gösterir.
   - Kullanıcıdan herhangi bir giriş almaz, sadece görüntüleme yapar.
   - HTML ve Razor kullanarak tasarlanır.

3. **Controller**
   - Kullanıcıdan gelen talepleri işler.
   - Model ile View arasındaki etkileşimi yönetir.
   - Örneğin, kullanıcı "öğrenci bilgilerini getir" dediğinde Controller, Model'den veriyi çeker ve View'a yollar.

### Örnek MVC Yapısı:

```csharp
// Model
public class Student {
    public string Name { get; set; }
    public string RollNo { get; set; }
}

// View
public class StudentView {
    public void PrintStudentDetails(string studentName, string studentRollNo) {
        Console.WriteLine($"Name: {studentName}, Roll No: {studentRollNo}");
    }
}

// Controller
public class StudentController {
    private Student model;
    private StudentView view;

    public StudentController(Student model, StudentView view) {
        this.model = model;
        this.view = view;
    }

    public void UpdateView() {
        view.PrintStudentDetails(model.Name, model.RollNo);
    }
}
```

## 2. MVC'nin Kullanım Alanları

MVC deseni ilk olarak 1970'lerde Trygve Reenskaug tarafından geliştirilmiştir. İlk olarak masaüstü uygulamalarında kullanılmış, daha sonra web ve mobil uygulamalarda yaygınlaşmıştır.

### Popüler MVC Kullanılan Teknolojiler:
- .NET Core
- Java Spring
- Django (Python)
- Ruby on Rails
- Angular (Client-Side MVC)
- Laravel (PHP MVC Frameworkü)

## 3. ASP.NET Core MVC

ASP.NET Core MVC, Microsoft tarafından geliştirilen ve hafif, modüler ve yüksek test edilebilir bir framework'tür.

### Öne Çıkan Özellikleri:
- Routing (Yönlendirme)
- Model Binding (Gelen HTTP isteklerini modele dönüştürme)
- Model Validation (Veri doğrulama)
- Dependency Injection (Bağımlılık enjeksiyonu)
- Tag Helpers (HTML etiketlerini kolaylaştırır)
- Razor View Engine (HTML ile kodun birleşmesini sağlar)

### ASP.NET Core MVC'yi Kullanmak İçin Geliştirme Ortamı:
- Visual Studio 2019 veya üstü (Önerilen)
- .NET Core SDK (3.1 veya 5.0)
- Visual Studio Code (Alternatif)
- JetBrains Rider (Öğrenciler için ücretsiz)

## 4. ASP.NET Core MVC Projesi Kurulumu

Yeni bir ASP.NET Core MVC projesi oluşturmak için:

1. Visual Studio'da yeni proje oluşturun.
2. "ASP.NET Core Web App (Model-View-Controller)" seçin.
3. .NET Core 5.0 veya üstü bir sürüm seçin.
4. Proje oluşturulduktan sonra, temel klasörler şu şekildedir:
   - Controllers/
   - Models/
   - Views/
   - wwwroot/

## 5. MVC Klasör Yapısı

ASP.NET Core MVC projelerinde klasör yapısı şu şekildedir:

### Ana Klasörler:
- **Controllers/** → Tüm controller sınıfları burada bulunur.
- **Models/** → Uygulamanın veri yapısını ve iş mantığını tutar.
- **Views/** → HTML sayfalarını içeren Razor view dosyaları burada yer alır.
- **wwwroot/** → Statik dosyalar (CSS, JavaScript, resimler vb.) burada saklanır.

### Önemli Dosyalar:
- **appsettings.json** → Uygulama yapılandırma ayarlarını içerir.
- **Program.cs** → Uygulamanın giriş noktasıdır.
- **Startup.cs** → Servislerin yapılandırıldığı dosyadır.

## 6. Controller Oluşturma

### Controller Nedir?
Controller'lar, HTTP isteklerini karşılayan ve uygun yanıtları döndüren sınıflardır. Tüm controller dosyaları "Controller" kelimesi ile bitmelidir.

### Örnek Controller Kodu:
```csharp
public class HomeController : Controller {
    public IActionResult Index() {
        return View();
    }
}
```

### Controller içinde kullanılan yöntemler:
- `return View();` → Bir sayfa döndürür.
- `return Json(data);` → JSON formatında veri döndürür.
- `return RedirectToAction("ActionName");` → Başka bir metoda yönlendirme yapar.

## 7. View Kullanımı

View, kullanıcıya gösterilecek HTML çıktısını oluşturan bileşendir. Razor View Engine kullanılarak geliştirilir.

### Razor View Örneği (index.cshtml):
```html
@{
    ViewBag.Title = "Ana Sayfa";
}
<h1>Merhaba MVC</h1>
<p>Bu bir Razor View örneğidir.</p>
```

## 8. Model Kullanımı

Model, uygulamanın veri yapısını temsil eder.

### Örnek Model Sınıfı (Student.cs):
```csharp
public class Student {
    public int Id { get; set; }
    public string Name { get; set; }
}
```

### Model'i Controller İçinde Kullanmak:
```csharp
public IActionResult GetStudent() {
    Student student = new Student { Id = 1, Name = "Ahmet" };
    return View(student);
}
```

### View İçinde Model Kullanımı:
```html
@model Student
<h1>@Model.Name</h1>
```

## 9. Veri Transferi Yöntemleri

### Controller'dan View'a Veri Gönderme Yöntemleri:

1. **ViewBag Kullanımı**
```csharp
// Controller
ViewBag.Message = "Merhaba Dünya!";
return View();

// View
<p>@ViewBag.Message</p>
```

2. **Model Kullanımı**
```csharp
// Controller
public IActionResult Index() {
    var student = new Student { Name = "Ali" };
    return View(student);
}

// View
@model Student
<h1>@Model.Name</h1>
```

### View'dan Controller'a Veri Gönderme Yöntemleri:
- Query Strings ( ?x=5&y=10 )
- HTML Form ( <form method="post"> )
- Model Binding ( Student model ) 