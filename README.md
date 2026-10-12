# Spring Boot Gradle CI - Bài 1

Dự án Java 17 Spring Boot có REST API `/hello`, JUnit test và GitHub Actions chạy khi push lên `main`.

## Đẩy lên GitHub

Tạo repository trống trên GitHub, sau đó tại thư mục này chạy:

```powershell
git init
git branch -M main
git add .
git commit -m "Submit exercise 1 CI"
git remote add origin https://github.com/USERNAME/REPOSITORY.git
git push -u origin main
```

Thay `USERNAME` và `REPOSITORY` bằng thông tin của bạn. Vào tab **Actions** để xem job **Run Unit Tests**.

## Chạy test trên Windows

```powershell
.\gradlew.bat test
```

Dự án không sử dụng MySQL, tránh lỗi kết nối database khi test trên GitHub.

**Lưu ý:** Các script `gradlew` và `gradlew.bat` trong bản đóng gói này là bootstrap tùy chỉnh tải Gradle 8.14.3 từ services.gradle.org, không phải Gradle Wrapper chính thức có `gradle-wrapper.jar`. Chúng vẫn hỗ trợ `./gradlew test` như bài yêu cầu. Khi có Gradle trên máy, có thể tạo wrapper chính thức bằng `gradle wrapper --gradle-version 8.14.3` rồi commit các file được sinh ra.
