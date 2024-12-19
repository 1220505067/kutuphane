### Kütüphane Yönetim Sistemi Projesi İçin README

---

#### Proje Genel Bakış

Bu proje, Java kullanılarak Swing ile geliştirilmiş bir **Kütüphane Yönetim Sistemi** uygulamasıdır. Uygulama, kitap yönetimi, kullanıcı yönetimi (öğrenci ve personel), ödünç alma ve iade işlemleri, kullanıcı giriş doğrulama gibi özellikleri destekler. Projede **Factory**, **Strategy**, **Decorator** ve **State** tasarım desenleri, modülerlik ve ölçeklenebilirlik sağlamak amacıyla kullanılmıştır.

---

#### Temel Özellikler

1. **Kullanıcı Yönetimi**:
   - Öğrenci ve personel rolleri desteklenir.
   - Kullanıcı kaydı, giriş yapma ve profil yönetimi sağlanır.
   - Kullanıcılar, kişisel bilgilerini güncelleyebilir ve şifrelerini değiştirebilir.

2. **Kitap Yönetimi**:
   - Kitap ekleme, güncelleme ve silme işlemleri yapılabilir.
   - Mevcut, ödünç alınmış ve kayıp kitaplar görüntülenebilir.
   - Kitap ödünç alma ve iade etme işlemleri, durum yönetimi ile sağlanır.

3. **Arama Fonksiyonu**:
   - Kitapları başlık, yazar veya konuya göre arama desteği sağlanır (**Strategy Deseni** kullanılmıştır).

4. **Uygulanan Tasarım Desenleri**:
   - **Factory Deseni**: Kullanıcı oluşturma işlemleri için.
   - **Strategy Deseni**: Farklı arama stratejilerini uygulamak için.
   - **State Deseni**: Kitap durumlarının (Mevcut, Ödünç Alınmış, Kayıp) yönetimi için.
   - **Decorator Deseni**: Kitaplara ekstra özellikler (örneğin, puanlama) eklemek için.

---

#### Proje Yapısı

Proje, aşağıdaki modüler yapıya sahiptir:

- **`dao`**: Veritabanı işlemleri için Veri Erişim Nesneleri.
  - `BookDAO`: Kitaplarla ilgili CRUD işlemlerini yönetir.
  - `UserDAO`: Kullanıcı verilerini yönetir.
  - `BorrowLogDAO`: Ödünç alma ve iade işlemlerini takip eder.

- **`model`**: Kütüphane sisteminin temel varlıklarını temsil eder.
  - `AbstractUser`: `Student` ve `Staff` için üst sınıf.
  - `Book`: Kütüphanedeki kitapları temsil eder.
  - `Loan`: Ödünç alma işlemlerini temsil eder.

- **`pattern`**: Tasarım desenlerinin implementasyonları.
  - `factory`: Kullanıcı oluşturmak için **Factory Deseni**.
  - `state`: Kitap durum yönetimi (Mevcut, Ödünç Alınmış, Kayıp).
  - `strategy`: Arama stratejileri (Başlığa göre, Yazara göre).
  - `decorator`: Kitaplara ek işlevler eklemek için (örneğin, puanlama).

- **`service`**: İş mantığı katmanı.
  - `UserService`: Kullanıcıyla ilgili işlemleri yönetir.
  - `BookService`: Kitap işlemlerini ve durum geçişlerini yönetir.

- **`ui`**: Swing ile geliştirilmiş kullanıcı arayüzü bileşenleri.
  - `LoginView`: Kullanıcı giriş ekranı.
  - `ManageUsersView`: Kullanıcı yönetim ekranı.
  - `ManageBooksView`: Kitap yönetim ekranı.
  - `StudentView`: Öğrenciler için kullanıcı arayüzü.
  - `StaffView`: Personel için kullanıcı arayüzü.

- **`util`**: Yardımcı sınıflar.
  - `DatabaseConnection`: Veritabanı bağlantısını yönetir.

---

#### Kullanılan Teknolojiler

- **Java**: Programlama dili.
- **Swing**: Kullanıcı arayüzü bileşenleri.
- **MySQL**: Veritabanı yönetim sistemi.
- **Maven**: Derleme otomasyon aracı.

---

#### Kurulum Talimatları

1. **Gereksinimler**:
   - [Java 17+](https://www.oracle.com/java/technologies/javase-downloads.html)'yı yükleyin.
   - [MySQL](https://dev.mysql.com/downloads/)'i yükleyin.
   - Bir IDE kurun (örn. IntelliJ IDEA, Eclipse).

2. **Veritabanı Kurulumu**:
   - `library_db.sql` dosyasını MySQL'e aktarın.
   - `DatabaseConnection.java` dosyasındaki veritabanı bağlantı bilgilerini düzenleyin:
     ```java
     private final String url = "jdbc:mysql://localhost:3306/library_db";
     private final String username = "kendi_kullanıcı_adınız";
     private final String password = "kendi_şifreniz";
     ```

3. **Projeyi Derleme**:
   - Projeyi IDE'nizde açın.
   - Maven kullanarak projeyi derleyin.

4. **Uygulamayı Çalıştırma**:
   - `org.example` paketindeki `Main.java` dosyasını çalıştırın.

---


Daha fazla bilgi eklemek veya düzenlemek isterseniz bana bildirin!
