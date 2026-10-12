# Spring Boot CI with GitHub Actions

## 1. Giới thiệu

Dự án xây dựng quy trình Continuous Integration (CI) tự động cho ứng dụng Java Spring Boot sử dụng Gradle và GitHub Actions.

Workflow tự động thực thi các bài kiểm thử JUnit khi có sự kiện `push` lên nhánh `main`, giúp kiểm tra tính ổn định của mã nguồn.

## 2. Công nghệ sử dụng

- Java JDK 17 (Eclipse Temurin)
- Spring Boot 3
- Gradle 8
- JUnit 5
- GitHub Actions
- Ubuntu Runner

## 3. Cấu trúc dự án

```text
spring-boot-gradle-ci/
├── .github/
│   └── workflows/
│       └── ci.yml
        └── ảnh 1 tab action.png
         └──ảnh 2 bên trong Job Run Unit Tests.png
├── gradle/
│   └── wrapper/
│       └── gradle-wrapper.properties
├── src/
│   ├── main/
│   │   └── java/com/example/demo/
│   │       ├── DemoApplication.java
│   │       └── HelloController.java
│   └── test/
│       └── java/com/example/demo/
│           ├── DemoApplicationTests.java
│           └── HelloControllerTest.java
├── build.gradle
├── settings.gradle
├── gradlew
├── gradlew.bat
└── README.md
```

## 4. Chức năng

Ứng dụng cung cấp REST API đơn giản:

**Endpoint:** `GET /hello`

**Response:**

```text
Hello CI!
```

Các bài kiểm thử bao gồm:

- Kiểm tra khởi tạo Spring Application Context.
- Kiểm tra kết quả trả về của HelloController.

## 5. GitHub Actions Workflow

Workflow được định nghĩa tại `.github/workflows/ci.yml`.

Quy trình CI gồm các bước:

1. Checkout mã nguồn từ GitHub Repository.
2. Thiết lập môi trường Java JDK 17 với Eclipse Temurin.
3. Cấp quyền thực thi cho Gradle.
4. Thực thi JUnit Test bằng lệnh `./gradlew test`.
5. Hiển thị kết quả kiểm thử trên GitHub Actions.

## 6. Kết quả mong đợi

Khi có mã nguồn được push lên nhánh `main`, GitHub Actions tự động kích hoạt workflow `Java Spring Boot CI (Gradle)`.

Job `Run Unit Tests` hoàn thành với trạng thái **Success** khi toàn bộ bài kiểm thử thực thi thành công.

## 7. Minh chứng

Kết quả thực thi workflow được ghi nhận thông qua GitHub Actions, bao gồm trạng thái Job và chi tiết các bước kiểm thử.

---

**Bài thực hành 1:** Khởi tạo Workflow chạy Unit Test tự động cho Java Spring Boot với Gradle.
