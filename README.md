# BookStation – Hệ thống quản lý và bán sách trực tuyến

BookStation là hệ thống web hỗ trợ quản lý và bán sách, bao gồm các tính năng từ phía khách hàng (mua sách, giỏ hàng, đơn hàng, đánh giá, khuyến mãi, tích điểm) đến phía quản trị (quản lý kho, đơn hàng, flash sale, chiến dịch marketing, thống kê nâng cao…).

Dự án gồm:
- **Backend:** Spring Boot (Java 17), SQL Server, Spring Security + JWT
- **Frontend:** Vue 3, Vite, Bootstrap

---

## 1. Tính năng chính

### 1.1. Dành cho khách hàng

- **Tài khoản và xác thực**
  - Đăng ký, đăng nhập với JWT
  - Quản lý thông tin tài khoản cá nhân
  - Lưu trạng thái đăng nhập trên trình duyệt và tự động gửi token khi gọi API

- **Duyệt và tìm kiếm sách**
  - Xem danh sách sách theo danh mục, tác giả, nhà xuất bản
  - Tìm kiếm sách theo từ khóa
  - Xem chi tiết sách: mô tả, giá, tồn kho, nhà cung cấp, đánh giá…

- **Giỏ hàng và mua sách**
  - Thêm sách vào giỏ, cập nhật số lượng, xóa khỏi giỏ
  - Tính tổng tiền tạm tính và các ưu đãi áp dụng
  - Tạo đơn hàng từ giỏ hàng

- **Thanh toán và đơn hàng**
  - Tạo phiên thanh toán (checkout) cho đơn hàng
  - Theo dõi trạng thái đơn (chờ xác nhận, đang xử lý, đang giao, hoàn thành, hủy)
  - Yêu cầu hoàn tiền, gửi kèm minh chứng (hình ảnh, file đính kèm)

- **Địa chỉ và giao hàng**
  - Quản lý danh sách địa chỉ giao hàng
  - Chọn địa chỉ giao hàng khi đặt mua

- **Đánh giá và nhận xét**
  - Viết đánh giá, nhận xét cho sách đã mua
  - Xem đánh giá của người dùng khác cho mỗi sách

- **Tích điểm và xếp hạng**
  - Tích điểm khi mua hàng
  - Xem hạng thành viên và lợi ích tương ứng
  - Đổi điểm, sử dụng điểm để nhận ưu đãi (nếu được cấu hình)

- **Khuyến mãi, Flash Sale, Voucher**
  - Tham gia các chương trình khuyến mãi, chiến dịch marketing
  - Xem và mua hàng trong các đợt flash sale với mức giảm giá đặc biệt
  - Áp dụng mã giảm giá (voucher) vào đơn hàng

- **Minigame và tương tác**
  - Tham gia các minigame (nếu được bật trong hệ thống)
  - Nhận phần thưởng, điểm hoặc mã giảm giá từ minigame

---

### 1.2. Dành cho quản trị viên

- **Quản lý sách và danh mục**
  - Thêm, sửa, xóa sách
  - Cấu hình danh mục, tác giả, nhà xuất bản, nhà cung cấp
  - Quản lý hình ảnh, dữ liệu liên quan đến sách

- **Quản lý kho và bán tại quầy**
  - Quản lý tồn kho, điều chỉnh số lượng
  - Hỗ trợ tạo đơn bán trực tiếp tại quầy
  - Kết hợp dữ liệu bán online và bán trực tiếp

- **Quản lý đơn hàng và hoàn tiền**
  - Xem danh sách đơn hàng theo nhiều tiêu chí
  - Cập nhật trạng thái đơn hàng trong toàn bộ vòng đời
  - Tiếp nhận yêu cầu hoàn tiền, xử lý chứng cứ hoàn tiền và cập nhật kết quả

- **Chương trình khuyến mãi, Flash Sale, Voucher**
  - Tạo và quản lý chiến dịch khuyến mãi
  - Cấu hình flash sale: thời gian, danh sách sách, mức giảm, giới hạn số lượng
  - Tạo và quản lý voucher (mã giảm giá), điều kiện sử dụng

- **Hệ thống điểm thưởng và xếp hạng**
  - Cài đặt và quản lý các hạng thành viên
  - Cấu hình cách tính và sử dụng điểm thưởng
  - Theo dõi lịch sử điểm và phần thưởng của người dùng

- **Thống kê và báo cáo**
  - Dashboard tổng quan: doanh thu, số lượng đơn hàng, số lượng khách hàng, sản phẩm bán chạy
  - Thống kê chi tiết theo thời gian, chiến dịch, kênh bán
  - Xuất báo cáo ra PDF / Excel
  - Phân tích nâng cao cho các chỉ số kinh doanh

- **Quản lý người dùng**
  - Theo dõi danh sách tài khoản
  - Kiểm tra hạng, điểm, đơn hàng liên quan
  - Thực hiện các thao tác quản trị nội bộ (tùy thuộc cấu hình thực tế)

---

## 2. Công nghệ sử dụng

### 2.1. Backend

- **Ngôn ngữ:** Java 17  
- **Framework:**
  - Spring Boot
  - Spring Web (REST API)
  - Spring Security + JWT (xác thực và phân quyền)
  - Spring Data JPA / Hibernate
- **Cơ sở dữ liệu:** SQL Server
- **Build & Dependency:** Maven

### 2.2. Frontend

- **Framework:** Vue 3
- **Bundler:** Vite
- **UI:** Bootstrap
- **HTTP client:** Axios (hoặc fetch, tùy implementation trong repo)

---

## 3. Cách chạy Backend (BookStation-Backend)

### 3.1. Yêu cầu

- Java 17
- Maven 3.x
- SQL Server đã cài đặt và tạo sẵn database

### 3.2. Cấu hình kết nối SQL Server

Trong `src/main/resources/application.properties` (hoặc `.yml`), cấu hình tương tự:

```properties
spring.datasource.url=jdbc:sqlserver://localhost:1433;databaseName=BookStation
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.datasource.driver-class-name=com.microsoft.sqlserver.jdbc.SQLServerDriver

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.SQLServerDialect

# Cấu hình JWT, đặt theo key mà dự án đang sử dụng
jwt.secret=your_jwt_secret
jwt.expiration=3600000
```

### 3.3. Build và chạy

```bash
git clone https://github.com/lilbugsecret/BookStation-Backend.git
cd BookStation-Backend

mvn clean install
mvn spring-boot:run
```

Mặc định (nếu không đổi) server chạy tại:

- `http://localhost:8080`

---

## 4. Cách chạy Frontend (BookStation-Frontend)

### 4.1. Yêu cầu

- Node.js (khuyến nghị >= 18)
- npm hoặc yarn

### 4.2. Cài đặt và cấu hình

```bash
git clone https://github.com/lilbugsecret/BookStation-Frontend.git
cd BookStation-Frontend

npm install
# hoặc
yarn install
```

Cấu hình URL backend (trong `.env` hoặc file config):

```env
VITE_API_BASE_URL=http://localhost:8080/api
```

### 4.3. Chạy ở chế độ phát triển

```bash
npm run dev
# hoặc
yarn dev
```

Truy cập:

- `http://localhost:5173` (mặc định Vite) hoặc theo port log hiển thị.

---

## 5. Build và triển khai

### 5.1. Backend

```bash
mvn clean package
java -jar target/bookstation-*.jar
```

Triển khai trên:
- VPS / máy chủ riêng
- Nền tảng cloud (Azure, AWS, GCP, Render,…)
- Kết hợp reverse proxy (Nginx/Apache) để bật HTTPS

### 5.2. Frontend

```bash
npm run build
# hoặc
yarn build
```

Deploy thư mục `dist/` lên:
- Nginx / Apache
- Vercel / Netlify / bất kỳ static hosting nào

---

## 6. Ghi chú

- Không commit thông tin nhạy cảm (password DB, JWT secret) lên repository.
- Sử dụng biến môi trường cho cấu hình production.
- Cấu hình CORS trên backend để chỉ cho phép domain frontend hợp lệ truy cập API.

---

## 7. Đóng góp

1. Fork repository
2. Tạo branch mới từ `main`
3. Commit thay đổi với message rõ ràng
4. Tạo Pull Request mô tả nội dung chỉnh sửa

Issues:
- Backend: https://github.com/lilbugsecret/BookStation-Backend/issues  
- Frontend: https://github.com/lilbugsecret/BookStation-Frontend/issues
