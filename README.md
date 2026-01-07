Thông tin thực tập sinh: Họ tên:Ngô Việt Hoàng – MSSV: 64139028 – Trường: Đại học Nha Trang/Lớp:64.CNTT_CLC
# Cuộc thi Năng lực số Khánh Hòa

Website quản lý và giới thiệu Cuộc thi Năng lực số học sinh tỉnh Khánh Hòa với chủ đề "AI & Robotics vì môi trường xanh – Tương lai bền vững".

 Mô tả chức năng chính

 Trang công khai (Public)
- Trang chủ: Giới thiệu tổng quan cuộc thi với banner, timeline, tin tức nổi bật
- Bảng thi (Categories): 3 bảng thi chính - MATCH (Thi đấu Robot), MAKE (Sáng tạo sản phẩm), MENTOR (Hướng dẫn viên AI)
- Tin tức & Thông báo: Quản lý bài viết với 2 loại NEWS và ANNOUNCEMENT
- Tài liệu: Download tài liệu cuộc thi theo danh mục, tracking số lượt tải
- Lịch trình (Timeline): Các mốc thời gian quan trọng của cuộc thi
- Giải thưởng: Cơ cấu giải thưởng theo từng bảng thi
- Thư viện ảnh/video: Gallery media từ các hoạt động
- Liên hệ: Form gửi tin nhắn với tích hợp email SMTP

 Trang quản trị (Admin)
- Dashboard: Thống kê tổng quan (bài viết, tài liệu, lượt truy cập...)
- Quản lý Tin tức/Thông báo: CRUD bài viết với WYSIWYG editor
- Quản lý Bảng thi: Cấu hình 3 bảng thi và thể lệ
- Quản lý Tài liệu: Upload/download tài liệu theo danh mục
- Quản lý Timeline: Cập nhật lịch trình cuộc thi
- Quản lý Giải thưởng: Cấu hình giải thưởng theo bảng thi
- Quản lý Media: Upload ảnh/video vào thư viện
- Quản lý Liên hệ: Xem và trả lời tin nhắn từ người dùng
- Cài đặt hệ thống: Logo, thông tin liên hệ, SEO...
- Nhật ký hoạt động: Theo dõi mọi thao tác của admin
- Quản lý tài khoản: Phân quyền admin

---

 Công nghệ sử dụng

 Backend
| Công nghệ | Phiên bản | Mô tả |
|-----------|-----------|-------|
| Java | 17 | Ngôn ngữ lập trình chính |
| Spring Boot | 3.2.0 | Framework chính |
| Spring Security | 6.x | Xác thực và phân quyền |
| Spring Data JPA | 3.x | ORM với Hibernate |
| Spring Mail | 3.x | Gửi email SMTP |
| Thymeleaf | 3.x | Template engine |
| Lombok | - | Giảm boilerplate code |
| MySQL | 8.x | Cơ sở dữ liệu |

 Frontend
| Công nghệ | Mô tả |
|-----------|-------|
| Thymeleaf | Server-side rendering |
| TailwindCSS | Utility-first CSS framework |
| Font Awesome | Icon library |
| JavaScript (Vanilla) | Client-side interactivity |

 Công cụ phát triển
| Công cụ | Mô tả |
|---------|-------|
| Maven | Build tool & dependency management |
| XAMPP | Local MySQL server |
| Spring DevTools | Hot reload trong development |

---

 Cấu trúc dự án

competition-website/
├── pom.xml                          # Maven dependencies
├── scripts/                         # SQL scripts
│   ├── 001-create-tables.sql        # Tạo bảng database
│   └── 002-seed-data.sql            # Dữ liệu mẫu
├── src/main/java/com/competition/
│   ├── CompetitionWebsiteApplication.java  # Main class
│   ├── config/                      # Cấu hình Spring
│   │   ├── SecurityConfig.java      # Spring Security
│   │   ├── WebConfig.java           # Web MVC config
│   │   └── GlobalControllerAdvice.java
│   ├── controller/                  # Controllers
│   │   ├── HomeController.java      # Trang chủ
│   │   ├── ContestController.java   # Bảng thi
│   │   ├── PostController.java      # Tin tức
│   │   ├── DocumentController.java  # Tài liệu
│   │   ├── MediaController.java     # Media
│   │   ├── AuthController.java      # Đăng nhập
│   │   └── admin/                   # Admin controllers
│   ├── entity/                      # JPA Entities
│   │   ├── AdminAccount.java
│   │   ├── Post.java
│   │   ├── ContestCategory.java
│   │   ├── Document.java
│   │   ├── Timeline.java
│   │   ├── Award.java
│   │   ├── MediaGallery.java
│   │   ├── ContactMessage.java
│   │   └── ...
│   ├── repository/                  # Spring Data JPA
│   └── service/                     # Business logic
├── src/main/resources/
│   ├── application.properties       # Cấu hình ứng dụng
│   ├── static/                      # CSS, JS, images
│   │   ├── css/
│   │   │   ├── app.css              # Styles chính
│   │   │   ├── admin.css            # Admin styles
│   │   │   └── animations.css       # Animations
│   │   └── js/
│   │       └── main.js              # JavaScript chính
│   └── templates/                   # Thymeleaf templates
│       ├── public/                  # Trang công khai
│       ├── admin/                   # Trang quản trị
│       ├── auth/                    # Đăng nhập
│       ├── error/                   # Trang lỗi
│       └── fragments/               # Header, Footer
└── uploads/                         # Thư mục upload files

---

Hướng dẫn cài đặt và chạy

 Yêu cầu hệ thống
- JDK 17 trở lên
- Maven 3.8+
- MySQL 8.x (khuyến nghị dùng XAMPP)
- IDE: Eclipse ide for enterprise java and web developers

 Bước 1: Cài đặt Database

1. Khởi động MySQL (XAMPP hoặc MySQL Server)
2. Chạy script tạo database:

mysql -u root -p < scripts/001-create-tables.sql
mysql -u root -p < scripts/002-seed-data.sql


Hoặc import qua phpMyAdmin:
- Truy cập `http://localhost/phpmyadmin`
- Import file `scripts/001-create-tables.sql`
- Import file `scripts/002-seed-data.sql`

 Bước 2: Cấu hình ứng dụng

Mở file `src/main/resources/application.properties` và cập nhật:

```properties
# Database (mặc định cho XAMPP)
spring.datasource.url=jdbc:mysql://localhost:3306/competition_db
spring.datasource.username=root
spring.datasource.password=

# Email SMTP (Gmail)
spring.mail.username=your-email@gmail.com
spring.mail.password=your-app-password
