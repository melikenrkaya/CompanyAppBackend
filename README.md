# CompanyAppBackend

Bu proje, şirket çalışanları, yöneticileri ve görev atama sistemi için geliştirilmiş, JWT tabanlı, Katmanlı mimariye sahip bir .NET Core backend uygulamasıdır.

---

## 🚀 Kullanılan Teknolojiler

* **ASP.NET Core 8.0**
* **Entity Framework Core** (Code First + SQL Server)
* **JWT (JSON Web Token)** ile Kimlik Doğrulama
* **RabbitMQ** (Arka plan işlemleri için kuyruk sistemi)
* **Swagger UI** (API test ve dökümantasyon)
* **Katmanlı Mimari** (Entity, DTO, Service, Controller)

---

## 🔧 Özellikler

* Kullanıcı girişi ve JWT token oluşturma
* Şirket çalışanları (Employee) ve yöneticileri (Admin) için CRUD işlemleri
* Görev atama ve görev yönetimi
* RabbitMQ ile arka plan iş takibi
* Email gönderme servisi
* Entity/DTO dönüşümlerinde Extension yapıları

---

## 📁 Proje Yapısı

```
CompanyAppBackend/
├── Controller/           # API uç nokta kontrolcüleri
├── Data/                 # Veritabanı context ve Entity/DTO yapıları
├── Services/             # Uygulama servisleri (Admin, Task, Email, Token)
├── Common/Extensions/    # DTO <-> Entity dönüşümlerini sağlar
├── Migrations/           # EF Core Migration dosyaları
├── Pages/                # Razor Pages
├── Program.cs            # Giriş noktaları
├── appsettings.json      # Yapılandırma
└── wwwroot/              # Statik frontend dosyaları
```

---

## 📆 Kurulum Adımları

1. Öncelikle veritabanı ayarlarını `appsettings.json` içinden yap.
2. Paketleri yükle:

```bash
dotnet restore
```

3. Migration uygula:

```bash
dotnet ef database update
```

4. Uygulamayı başlat:

```bash
dotnet run
```

5. Swagger UI test adresi:

```
https://localhost:{PORT}/swagger
```

---

## 🔐 Kimlik Doğrulama (JWT)

### Giriş örneği:

```http
POST /Account/Login
{
  "email": "admin@example.com",
  "password": "123456"
}
```

Swagger'da **Authorize** butonuna tıkla ve gelen token'la şu formatta kullan:

```
Bearer {token}
```

---

## 🗞️ API Uç Noktaları (Seçme)

* `POST /Account/Login`
* `POST /Account/register`
  
* `GET /Admin/GetAll`
* `GET /Admin/GetById`
* `POST /Admin/Createid‎`
* `PUT /Admin/Update‎`
* `DELETE /Admin/Delete‎‎`
  
* `GET /Employee/GetAll`
* `GET /Employee/GetById`
* `POST /Employee/Createid‎`
* `PUT /Employee/Update‎`
* `DELETE /Employee/Delete‎‎`

* `GET /Task/GetAll`
* `GET /Task/GetById`
* `POST /Task/Createid‎`
* `PUT /Task/Update‎`
* `DELETE /Task/Delete‎‎`

---

## 😍 Geliştirici Notları

* SOLID prensiplerine uygun, sade ve okunabilir bir kod yapısı kullanılmıştır.
* Kodlar servis bazlı organize edilmiştir, Unit Test yazımına uygundur.
* DTO ve Entity'ler arı temizlenmiş ve uzantı (extension) ile dönüştürülmüştür.

---

## 📅 Katkıda Bulunmak

Pull request'lere ve önerilere her zaman açığım.

---

## 👤 Geliştirici

Bu proje, backend değerlendirme ve staj süreci amacıyla **Melikenur Kaya** tarafından geliştirilmiştir.
