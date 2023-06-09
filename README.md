# Tiny-Board

Bu örnekte amacım Rust, Actix, SeaORM ve Electron kullanılarak basit bir todo uygulaması geliştirmeye çalışmak. Örneği takip ettiğim [Udemy](https://www.udemy.com/course/build-a-todolist-with-actix-web-rust-and-electron-vue) kursundan esinlenerek geliştirmeye çalışıyorum.

## Rust Projesinin Oluşturulması

İlk olarak rust projesini oluşturuyoruz.

```bash
cargo new tiny-board-api
cd tiny-board-api

# Gerekli küfeler(crates) yüklenir
# Servis arayüzü ve CORS izinleri için Actix, 
# Ortam parametrelerini kullanabilmek için dotnev
# loglama için env_logger ve log

cargo add actix-web actix-cors dotenv serde_json env_logger log futures

# ORM aracı olarak da SeaORM
# ki örnekte postgresql kullanılıyor, asenkron çalışma zamanı içinse actix-runtime
cargo add sea-orm -F sqlx-postgres,runtime-actix-native-tls,macros

# ???
cargo add async-std -F attributes,tokio1

# json serileştirme desteği için standart serde
cargo add serde -F derive

# ???
cargo add tracing-subscriber -F env-filter
```