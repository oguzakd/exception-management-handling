# Spring Boot Student Management Example

Bu proje, **Spring Boot** kullanılarak geliştirilmiş, katmanlı mimariye sahip örnek bir backend uygulamasıdır.  
Proje özellikle **Exception Handling**, **JUnit ile test yazımı** ve **Scheduled task (zamanlanmış görevler)** konularını öğrenmek ve pekiştirmek amacıyla hazırlanmıştır.

---

## 🚀 Kullanılan Teknolojiler

- Java 17+
- Spring Boot
- Spring Data JPA
- Hibernate
- H2 / MySQL (konfigüre edilebilir)
- JUnit 5
- Spring Scheduler
- Maven

---

## 🧱 Mimari Yapı

Proje **katmanlı mimari** prensiplerine uygun olarak geliştirilmiştir:

```
Controller
   ↓
Service (Interface + Implementation)
   ↓
Repository
   ↓
Database
```

### Katmanlar

- **Controller Layer**
  - REST API endpoint’lerini barındırır.
  - Request ve Response işlemlerini yönetir.
- **Service Layer**
  - İş kuralları bu katmanda yer alır.
  - Interface + Impl yapısı kullanılarak loose coupling sağlanmıştır.
- **Repository Layer**
  - Spring Data JPA kullanılarak veritabanı işlemleri gerçekleştirilir.
- **DTO Layer**
  - Entity ile client arasındaki veri transferi DTO’lar üzerinden yapılır.
- **Entity Layer**
  - Veritabanı tablolarını temsil eden JPA entity sınıfları içerir.

---

## 🔄 DTO Yapısı

Projede **Entity – DTO ayrımı** net bir şekilde uygulanmıştır.

- `DtoStudent`
  - Client’a dönen response objesi
- `DtoStudentIU`
  - Insert / Update işlemleri için kullanılan request objesi

Bu yapı sayesinde:
- Gereksiz alanların dışarı açılması engellenir
- API güvenliği ve esnekliği artırılır

---

## ⚠️ Exception Handling

Proje genelinde **global exception handling** uygulanmıştır.

- Özel exception sınıfları oluşturulmuştur
- `@ControllerAdvice` ve `@ExceptionHandler` kullanılarak merkezi hata yönetimi sağlanmıştır
- API üzerinden anlamlı ve okunabilir hata mesajları döndürülmektedir

---

## 🧪 JUnit Testleri

Projede **JUnit 5** kullanılarak testler yazılmıştır.

- Service katmanı test edilmiştir
- İş mantığının doğruluğu testlerle garanti altına alınmıştır
- Test edilebilirlik için interface tabanlı yapı tercih edilmiştir

---

## ⏰ Scheduled Tasks

Projede **Spring Scheduler** kullanılarak zamanlanmış görevler tanımlanmıştır.

- `@Scheduled` anotasyonu kullanılmıştır
- Belirli aralıklarla otomatik çalışan işlemler örneklenmiştir

---

## 📌 Örnek API Endpoint’leri

| HTTP | Endpoint | Açıklama |
|---|---|---|
| POST | `/student/save` | Öğrenci kaydet |
| GET | `/student/getAll` | Tüm öğrencileri listele |
| GET | `/student/get/{id}` | ID’ye göre öğrenci getir |
| PUT | `/student/update/{id}` | Öğrenci güncelle |
| DELETE | `/student/delete/{id}` | Öğrenci sil |

---

## ▶️ Projeyi Çalıştırma

```bash
mvn clean install
mvn spring-boot:run
```

Uygulama varsayılan olarak:
```
http://localhost:8080
```
adresinde çalışır.

---

## 🎯 Projenin Amacı

Bu proje aşağıdaki konuları öğrenmek isteyenler için hazırlanmıştır:

- Spring Boot ile katmanlı mimari
- DTO ve Entity ayrımı
- Exception handling
- JUnit ile test yazımı
- Scheduled task kullanımı
- Spring Data JPA temelleri

---

## 📝 Not

Bu proje **öğrenme ve geliştirme amaçlı** hazırlanmıştır ve gerçek hayattaki kurumsal Spring Boot projeleri için sağlam bir temel sunar.

---

## 👤 Geliştirici

**Oğuzhan Akduman**
