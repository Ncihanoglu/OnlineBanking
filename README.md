# OnlineBanking

	OnlineBanking 1.0 Uygulama Dökümantasyonu

























Uygulama Hakkında
 	Online Banking hesaplar arasında para transferi yapan kullanıcılar arası para transferi gerçekleştiren bir internet bankacılık uygulamasıdır. Online Banking’de bankadan işlemlerini gerçekleştirmek için randevu alabilir. Mevcut hesap bakiyesini görüntüleyebilir.
Kullanılan Teknolojiler
Eclipe Neon 3
Maven 2.0
Spring Boot Latest
Hibernate 
Thymeleaf(HTML5)


















Uygulama Özellikleri


Kullanıcı Girişi: Uygulamaya kullanıcılar giriş yaparak ve ya mevcut bir hesaba sahip değilse yeni bir hesap oluşturarak uygulamaya erişilir.                                                



Kullanıcılar kullanıcı adı ve şifresini girerek uygulamaya erişirler.
Mevcut bir hesabı olmayan kullanıcılar, gerekli alanları doldurarak yeni bir hesap oluştururlar. 
İşlemler Sayfası: Kullanıcı işlemler sayfasından aşağıda belirtilen işlemleri yapabilir.
•	Kendi hesabından para çekme.
•	Kendi hesabına para yatırma.
•	Diğer hesaplara para transferi.
•	Randevu ayarlama
•	Profil özelliklerini güncelleme.









Para yatırma sayfası: Kullanıcı bu sayfada kendi hesabına para yatırır. 
Ana para veya yatırım fonu hesap seçeneklerinden birini seçerek istediği miktardaki tutarı kendi hesabına yatırır. Yatırılan tutar işlemler sayfasındaki ana para ve yatırım hesabı miktarına yansır.

Para çekme sayfası: Kullanıcı bu sayfada kendi hesabından para çeker. 
Ana para veya yatırım fonu hesap seçeneklerinden birini seçerek istediği miktardaki tutarı hesap bakiyesi maksimum sınır olmak üzere hesabından çeker. Çekilen tutar işlemler sayfasındaki ana para ve yatırım hesabı miktarına yansır.


Para transferi Sayfası: Kullanıcı ana para ve ya yatırım fonu parası arasında transfer yapabilir ve ya diğer bir hesaba para yatırabilir.


Alıcı hesabı oluşturma: Kullanıcı diğer hesap transferlerinde gönderdiği hesapları kaydedebilir.


Randevu sayfası: Kullanıcı banka işlemleri için bankadan randevu alabilir.

MVC mimarisi kullanılarak yapılmıştır. Uygulamaya gelen istekler ilgili controller’a gider. Controller isteğin URL ile eşleşen GET POST metotları bulunmaktadır. Controller metotlar veritabanı işlemlerini gerçekleştiren özelleştirilmiş DAO(Domain Access Object) sınıflarını servisler üzerinden kullanır. Bu işlemler veri ekleme ve çekme gibi işlemlerdir. DAO sınıfları ilgili entity modellerine göre gerekli işlemi gerçekleştirir, gerçekleştirilen işlemler ilgili view ekranına yansır. 
Örnek use-case:
Bu use-case’de profil sayfasına kullanıcı bilgilerinin getirilmesi durumu MVC mantığında gösterilmektedir.
Profil view’ı User, PrimaryAccount ve SavingsAccount entity modellerini kullanır. Kullanıcı profil sayfasına girdiğinde kullanıcı bilgileri getirme işlemi için UserController da bulunan ilgili metoda GET isteği yapar. İlgili metot servis UserServiceImpl sınıfı UserService interface’sini implement eder. Bu sınıf içerisinde kullanıcılar ilgili metotlar bulunur.
