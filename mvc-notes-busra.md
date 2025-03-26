# ASP.NET MVC Notları Büşra

## ASP.NET MVC Yapısı

### Model

- Uygulamada kullanılacak verilerin, veritabanı ile ilgili bağlantının yapıldığı katmandır.

### View

- Model içeriğindeki verilerin görselleştirilmesinden sorumlu katmandır
- HTML türünde yazılır öncelikle
- Razor kullanılır. Razor, HTML içine C# kodu eklemeyi sağlayan bir yapıdır
- @{} ile C# kodu yazılabilir

### Controller

- Model ile View arasındaki bağlantıyı yöneten katmandır
- View'dan gelen isteklere, silme, güncelleme vb. isteklere cevap verir

### Partial Views (Bölünmüş)

- Bir sayfanın belirli bölümlerini tekrar kullanmak istediğimizde kullanılır
- Partial views, farklı sayfalarda ortak olan HTML parçalarını yönetmemizi sağlar

```csharp
@Html.Partial("~/Views/Components/_Header.cshtml")
```

### ViewComponents

- View component kullanımı ve kodun daha modüler olması sağlanır

## Tag Helpers ve Model Binding

Tag Helper, HTML etiketlerine sunucu taraflı yetenekler eklememizi sağlayan bir özelliktir.

```html
<input asp-for="FirstName" class="form-control" />
```

- FirstName model özelliği ile form alanını bağlar
- Kullanıcı bir şey yazdığında, eğer otomatik olarak model.FirstName özelliğine atanır
- asp-action / asp-controller -> Formun hangi controller / action'a gönderileceğini belirler

Model binding, formdan gelen verilerin otomatik olarak C# nesnelerine dönüştürülmesini sağlayan bir mekanizmadır.

## Controller ve Action

```csharp
public class StudentController : Controller {
    [HttpPost]
    public IActionResult SaveStudent(Student model) {
        if (ModelState.IsValid) {
            return RedirectToAction("Index");
        }
        return View(model);
    }
}
```

## Model ve Entity

### Model

- View'ı taşımak için kullanılır (View'le)
- Veritabanındaki tabloları temsil eden ve CRUD işlemlerinde kullanılan sınıflar

### Entity

- Veritabanındaki tabloları temsil eden ve onun ile veritabanı işlemlerini gerçekleştiren sınıflar
- CRUD işlemlerinde kullanılır

## DbContext

Veritabanı işlemlerini yönetmek için kullanılır.

```csharp
public class BirimDbContext : Database
```

## Generic Repository Pattern

Veri erişim işlemlerini soyutlamak için kullanılır.

```csharp
public interface ICommonDAL<T> {
    // Generic repository interface
}
```

## Dependency Injection

Örneğin, bir EmailService sınıfının içinde dependent bir GmailService nesnesi oluşturulursa, sınıf GmailService'e bağımlı olur.

- Bağımlılık dışarıdan constructor ile bağlanır
