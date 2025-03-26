# MVC ve Web Programlama Sınav Soruları ve Çözümleri

## Soru 1
**Soru:** MVC Razor'da kullanılan aşağıdaki kod bloğu ne amaçla kullanılmıştır?
```csharp
@foreach (var student in Model)
{
    <tr>
        <td>@student.Id</td>
        <td>@student.FirstName</td>
        <td>@student.LastName</td>
        <td>@student.Department</td>
    </tr>
}
```

**Şıklar:**

A) Bir veritabanındaki öğrenci bilgilerini alfabetik sırayla listelemek

B) Öğrenci bilgilerini HTML tablosu formatında görüntülemek

C) Öğrenci kayıtlarını silmek için bir form oluşturmak

D) Öğrencilerin bilgilerini düzenlemek için bir güncelleme formu sağlamak

**Cevap:** B) Öğrenci bilgilerini HTML tablosu formatında görüntülemek

**Açıklama:**
- Kod bloğu bir HTML tablosu (`<tr>` ve `<td>` elementleri) oluşturuyor
- Model içindeki her öğrenci için bir tablo satırı oluşturuluyor
- Her öğrencinin bilgileri (Id, FirstName, LastName, Department) ayrı hücrelerde gösteriliyor
- Bu yapı tipik bir veri listeleme/görüntüleme formatıdır

## Soru 2
**Soru:** Aşağıdaki kod bloğu ne amaçla kullanılmıştır?
```csharp
@Html.Partial("/Views/Components/_Header.cshtml")
```

**Şıklar:**
A) Header bölümünü başka bir sayfadan içe aktarmak
B) Header bölümünü CSS ile stilize etmek
C) Header bölümünde JavaScript kodu çalıştırmak
D) Header bölümünü veritabanına kaydetmek

**Cevap:** A) Header bölümünü başka bir sayfadan içe aktarmak

**Açıklama:**
- @Html.Partial metodu, belirtilen view dosyasını mevcut sayfaya dahil eder
- _Header.cshtml bir partial view'dur
- Bu yöntem, tekrar eden UI bileşenlerini modüler hale getirmek için kullanılır
- Header gibi ortak kullanılan bileşenleri tek bir yerden yönetmeyi sağlar

## Soru 3
**Soru:** <input> elementlerinin asp-for özelliği ne işe yarar?

**Şıklar:**
A) Gönderilecek form verilerini doğrulamak için kullanılır
B) Formun hangi controller'a ve hangi action'a gönderileceğini belirtir
C) Form elemanlarını modeldeki ilgili özelliklerle ilişkilendirir
D) HTML elementlerine CSS sınıfları eklemek için kullanılır

**Cevap:** C) Form elemanlarını modeldeki ilgili özelliklerle ilişkilendirir

**Açıklama:**
- asp-for özelliği model property'leri ile form elementlerini bağlar
- Otomatik olarak model binding sağlar
- Form validation için gerekli HTML attributelerini ekler
- Model property'sinin tipine göre uygun input tipini belirler

## Soru 5
**Soru:** Nesneye yönelik programlama dilinde, aşağıdakilerden hangisi model sınıfı ile entity sınıfı arasındaki temel bir farkı doğru bir şekilde açıklar?

**Şıklar:**
A) Model sınıfları veritabanı tablolarıyla doğrudan ilişkilendirilirken entity sınıfları veritabanı ile ilişkilendirilmez
B) Entity sınıfları veritabanı tablolarını temsil eder ve genellikle
C) Model sınıfları yalnızca veri taşımak için kullanılırken entity sınıfları hem veri taşıma hem de iş mantığı işlemleri gerçekleştirir
D) Entity sınıfları yalnızca statik veriler içerirken model sınıfları dinamik verilerle çalışmak için tasarlanmıştır

**Cevap:** C) Model sınıfları yalnızca veri taşımak için kullanılırken entity sınıfları hem veri taşıma hem de iş mantığı işlemleri gerçekleştirir

**Açıklama:**
Model ve Entity sınıfları arasındaki temel farklar:
1. Model sınıfları (DTO - Data Transfer Objects):
   - Sadece veri taşıma amaçlıdır
   - Genellikle view ile controller arasında veri transferi için kullanılır
   - İş mantığı içermez
   - Validation kuralları içerebilir

2. Entity sınıfları:
   - Veritabanı tablolarını temsil eder
   - İş mantığı metodları içerebilir
   - Domain logic barındırabilir
   - Diğer entity'lerle ilişkiler kurabilir
   - CRUD operasyonlarını destekler 

## Soru 6
**Soru:** MVC mimarisindeki model bileşeni aşağıdakilerden hangisi ile en iyi şekilde tanımlanır?

**Şıklar:**
A) Kullanıcıya gösterilen veri ve kullanıcı arayüzü elementlerini yönetir
B) Kullanıcı girişlerine yanıt olarak model ve görünüm arasındaki veri akışını kontrol eder
C) Kullanıcıya gösterilen bilgilerin görsel sunumunu sağlar
D) Uygulamanın veritabanı mantık ve sunucu tarafı işlevlerini içerir

**Cevap:** D) Uygulamanın veritabanı mantık ve sunucu tarafı işlevlerini içerir

**Açıklama:**
MVC'de Model bileşeni:
- İş mantığını (business logic) içerir
- Veri erişim katmanını barındırır
- Veritabanı işlemlerini yönetir
- Veri doğrulama kurallarını içerir
- Uygulama verilerinin durumunu yönetir

## Soru 7
**Soru:** Aşağıdakilerden hangisi MVC mimarisinde controller katmanının sorumlulukları arasında yanlış olarak sıralanmıştır?

**Şıklar:**
A) Kullanıcı isteklerini karşılamak ve bu isteklere yanıt vermek
B) Uygun modeli seçmek ve veri güncellemelerini model üzerinde gerçekleştirmek
C) Veri erişimi ve iş mantığını yönetmek
D) İstemciye sunulacak son veri görünümünü seçmek

**Cevap:** C) Veri erişimi ve iş mantığını yönetmek

**Açıklama:**
Controller'ın sorumlulukları:
- Kullanıcı isteklerini karşılamak
- Model ve View arasında koordinasyonu sağlamak
- Uygun View'ı seçmek
- Kullanıcı girdilerini işlemek

Veri erişimi ve iş mantığı Model katmanının sorumluluğundadır, Controller'ın değil.

## Soru 8-9
**Soru:** Aşağıdakilerden hangisi bir web uygulamasında önbellekleme(caching) stratejilerinden biri olarak kullanılmaz?

**Şıklar:**
A) İstemci tarafı önbellekleme
B) Sunucu tarafı önbellekleme
C) Veritabanı önbellekleme
D) Veritabanı normalizasyonu

**Cevap:** D) Veritabanı normalizasyonu

**Açıklama:**
Önbellekleme (caching) stratejileri:
- İstemci tarafı önbellekleme: Tarayıcıda veri saklanması
- Sunucu tarafı önbellekleme: Sunucuda veri saklanması
- Veritabanı önbellekleme: Sorgu sonuçlarının önbelleğe alınması

Veritabanı normalizasyonu bir veri modelleme tekniğidir ve önbellekleme ile ilgisi yoktur.

## Soru 10
**Soru:** Aşağıdakilerden hangisi MVC mimarisi kullanan bir web uygulamasında Model bileşeninin sorumluluğu olarak en doğru şekilde tanımlanır?

**Şıklar:**
A) Kullanıcı arayüzü bileşenlerini ve kullanıcı etkileşimlerini yönetir
B) Uygulamanın iş mantığını ve veri erişim katmanını içerir
C) İstekleri karşılayan ve uygun yanıtları oluşturan kontrol edicileri içerir
D) [Şık eksik]

**Cevap:** B) Uygulamanın iş mantığını ve veri erişim katmanını içerir

**Açıklama:**
Model bileşeninin sorumlulukları:
- Veri erişim katmanını yönetir
- İş mantığını (business logic) içerir
- Veri doğrulama kurallarını barındırır
- Veritabanı işlemlerini gerçekleştirir
- Uygulama verilerinin durumunu yönetir

## Soru 11
**Soru:** Aşağıda verilen db context sınıf tanımında kaç hata vardır?

```csharp
public class BiruniSchoolDbContext:Database
{
    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
        var connString = "server - .; databas - BiruniSchoolDb;
        Trusted_Connection=True; TrustServerCertificate=True";
        options<Builder.UseSqlServer(connString);
    }
    public List<Faculty>?Faculties | get; set }
    public List<Department>? Departments | get; set }
    public List<Student>? Students | get; set }
}
```

**Şıklar:**
A) 1
B) 2
C) 3
D) 4

**Cevap:** C) 3

**Açıklama:**
Kod içerisindeki hatalar:
1. Sınıf yanlış base class'tan türetilmiş (`Database` yerine `DbContext` olmalı)
2. Connection string formatı hatalı (tire işareti yerine nokta olmalı)
3. Property tanımlamaları hatalı:
   - List<T> yerine DbSet<T> kullanılmalı
   - Syntax hataları (| yerine { kullanılmış)
   - Kapanış süslü parantezleri hatalı

Doğru yazımı şöyle olmalıdır:
```csharp
public class BiruniSchoolDbContext : DbContext
{
    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
        var connString = "server=.; database=BiruniSchoolDb; Trusted_Connection=True; TrustServerCertificate=True";
        optionsBuilder.UseSqlServer(connString);
    }

    public DbSet<Faculty> Faculties { get; set; }
    public DbSet<Department> Departments { get; set; }
    public DbSet<Student> Students { get; set; }
}
```

## Soru 12
**Soru:** Aşağıdakilerden hangisi, ICommonDal<T> arayüzünün sağladığı fonksiyonlardan değildir?

```csharp
public interface ICommonDal<T>
{
    bool Any(Expression<Func<T, bool>> filter);
    T Get(Expression<Func<T, bool>> filter);
    List<T> GetList(Expression<Func<T, bool>>? filter = null);
    T Add(T entity);
    T Update(T entity);
    T Remove(T entity);
}
```

**Şıklar:**
A) Belirli bir koşula göre bir nesne döndüren Get(Expression<Func<T, bool>> filter) metodunu kullanmak
B) Belirli bir koşula göre nesne listesi döndüren GetList(Expression<Func<T, bool>>? filter = null) metodunu kullanmak
C) ICommonDal<T> arayüzündeki tüm metodların asenkron versiyonlarını sağlamak
D) Belirtilen bir Department nesnesini güncelleyen bir Update(Department entity) metodunu çağırmak

**Cevap:** C) ICommonDal<T> arayüzündeki tüm metodların asenkron versiyonlarını sağlamak

**Açıklama:**
- Interface'de tanımlanan metodlar:
  - Any: Belirli bir koşula göre varlık kontrolü
  - Get: Tek bir entity getirme
  - GetList: Filtreye göre liste getirme
  - Add: Entity ekleme
  - Update: Entity güncelleme
  - Remove: Entity silme
- Asenkron versiyonlar (Task dönen metodlar) interface'de tanımlanmamış
- Diğer seçenekler interface'de mevcut olan metodların kullanımını tanımlıyor

## Soru 13
**Soru:** Dependency Injection kullanarak bir uygulamada servisleri yönetmek için aşağıdaki seçeneklerden hangisi en uygun yöntemdir?

**Şıklar:**
A) Tüm servis sınıflarını statik olarak tanımlamak ve doğrudan çağırmak
B) Servisleri gerektiği yerde new anahtar kelimesi ile yeni nesneler olarak oluşturmak
C) Uygulamanın başlangıç sınıfında (Program.cs) bir servis konteyneri kullanarak servisleri kaydetmek ve gerektiğinde bu konteyner aracılığıyla servisleri çözümlemek
D) Veritabanı bağlantılarını her seferinde yeniden oluşturmak ve bağımlılıkları manuel olarak yönetmek

**Cevap:** C) Uygulamanın başlangıç sınıfında (Program.cs) bir servis konteyneri kullanarak servisleri kaydetmek ve gerektiğinde bu konteyner aracılığıyla servisleri çözümlemek

**Açıklama:**
- Bu yöntem en uygun çözümdür çünkü:
  - Merkezi bir yapılandırma sağlar
  - Bağımlılıkların yönetimini kolaylaştırır
  - Test edilebilirliği artırır
  - Loose coupling (gevşek bağlılık) sağlar
  - Servis yaşam döngüsünü kontrol eder
  - Kod tekrarını önler

## Soru 14
**Soru:** Aşağıdaki kod bloğunda kaç adet hatalı kısım vardır?

```csharp
public class RedisCacheProvider implements ICacheProvider
{
    private IDatabase _database= ConnectionMultiplexer.Connect("localhost:6379").GetDatabase(0);

    public bool Any (string key)
    {
        return database.KeyExists(key);
    }

    public T Get<T>(string key)
    {
        var cacheString = _database.StringGet(key);
        var result = JsonConvert.DeserializeObject<T>(cacheString);
        return result;
    }

    public void Set<T>(string key, T value, TimeSpan expiration)
    {
        var result = JsonConvert.SerializeObject(value);
        database.StringSet(key, result, expiration);
    }
    public bool Remove(string key)
    {
        return _database.KeyDelete(key);
    }
}
```

**Şıklar:**
A) 0
B) 1
C) 2
D) 3

**Cevap:** C) 2

**Açıklama:**
Kod içerisinde 2 adet hatalı kısım vardır:

1. Tutarsız değişken kullanımı:
   - Field tanımı `_database` olarak yapılmış
   - Ancak metotlarda bazen `database` olarak kullanılmış (underscore olmadan)
   - Any metodunda `database.KeyExists`
   - Set metodunda `database.StringSet`
   - Get ve Remove metodlarında doğru şekilde `_database` kullanılmış

2. Interface implementasyonu hatası:
   - C# dilinde interface implementasyonu için `implements` anahtar kelimesi kullanılmaz
   - Bu, Java dilinde kullanılan bir yapıdır
   - C# dilinde interface implementasyonu için `:` operatörü kullanılmalıdır
   - Örnek:
     ```csharp
     // YANLIŞ KULLANIM (Java tarzı):
     public class RedisCacheProvider implements ICacheProvider
     
     // DOĞRU KULLANIM (C# tarzı):
     public class RedisCacheProvider : ICacheProvider
     ```

Doğru yazımı şöyle olmalıdır:
```csharp
public class RedisCacheProvider : ICacheProvider
{
    private readonly IDatabase _database = ConnectionMultiplexer.Connect("localhost:6379").GetDatabase(0);

    public bool Any(string key)
    {
        return _database.KeyExists(key);
    }

    public T Get<T>(string key)
    {
        var cacheString = _database.StringGet(key);
        var result = JsonConvert.DeserializeObject<T>(cacheString);
        return result;
    }

    public void Set<T>(string key, T value, TimeSpan expiration)
    {
        var result = JsonConvert.SerializeObject(value);
        _database.StringSet(key, result, expiration);
    }

    public bool Remove(string key)
    {
        return _database.KeyDelete(key);
    }
}
```

## Soru 15
**Soru:** Bir .NET Core MVC uygulamasında her kullanıcı isteği için ayrı bir servis nesnesi oluşturmak istiyorsunuz, hangi dependency injection yaşam döngüsü türünü seçmelisiniz?

**Şıklar:**
A) Scoped
B) Singleton
C) Transient
D) Instance

**Cevap:** A) Scoped

**Açıklama:**
Dependency Injection yaşam döngüleri:

1. Scoped (Request bazlı):
   - Her HTTP isteği için bir instance oluşturulur
   - Aynı HTTP isteği içinde aynı instance kullanılır
   - Kullanıcı isteği (request) bazlı servislerde kullanılır
   - Request tamamlandığında instance dispose edilir
   - Örnek: DbContext, Identity servisleri

2. Transient (Geçici):
   - Her inject edildiğinde yeni bir instance oluşturulur
   - En kısa yaşam süresine sahiptir
   - Hafif, stateless servisler için uygundur
   - Memory kullanımı yüksektir
   - Örnek: Lightweight computing services

3. Singleton (Tek örnek):
   - Uygulama yaşam döngüsü boyunca tek bir instance kullanılır
   - Tüm kullanıcılar ve requestler aynı instance'ı paylaşır
   - Memory kullanımı düşüktür
   - Thread-safe olmalıdır
   - Örnek: Logging servisleri, Cache servisleri

Bu soruda "her kullanıcı isteği için ayrı bir servis nesnesi" istendiğinden Scoped seçilmelidir. Çünkü:
- Her kullanıcı isteği (HTTP request) için yeni bir instance oluşturur
- Aynı istek içinde tutarlılık sağlar
- Request tamamlandığında kaynakları temizler
- Kullanıcı bazlı işlemlerde en uygun seçenektir 