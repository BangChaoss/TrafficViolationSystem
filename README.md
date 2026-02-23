![A logo of a university
AI-generated content may be incorrect.](media/image1.png){width="6.275in" height="3.0in"}

**BÁO CÁO BÀI TẬP LỚN**  
**Môn học: PRJ301 Java Web Application Development**

**Đề tài: Xây dựng Website Báo cáo vi phạm giao thông**

**Sinh viên thực hiện:** Phạm Tuấn Kiệt  
**Mã dự án:** KetDZ123  
**Giảng viên hướng dẫn:** CauPD

**Lớp:** SE1950

**Ngày hoàn thành: 20 tháng 7 năm 2025**

**MỤC LỤC**

# Contents {#contents .TOC-Heading}

[1. CASE STUDY (NGHIÊN CỨU TÌNH HUỐNG) [3](#case-study-nghiên-cứu-tình-huống)](#case-study-nghiên-cứu-tình-huống)

[1. Bối cảnh và Vấn đề chính [3](#bối-cảnh-và-vấn-đề-chính)](#bối-cảnh-và-vấn-đề-chính)

[2. DATABASE DESIGN (THIẾT KẾ CƠ SỞ DỮ LIỆU) [4](#database-design-thiết-kế-cơ-sở-dữ-liệu)](#database-design-thiết-kế-cơ-sở-dữ-liệu)

[2.1. Thiết kế Logic (Logical Design) [4](#thiết-kế-logic-logical-design)](#thiết-kế-logic-logical-design)

[2.2. Thiết kế Vật lý (Physical Design) [4](#thiết-kế-vật-lý-physical-design)](#thiết-kế-vật-lý-physical-design)

[3. SYSTEM DESIGN (THIẾT KẾ HỆ THỐNG) [6](#system-design-thiết-kế-hệ-thống)](#system-design-thiết-kế-hệ-thống)

[3.1. Kiến trúc MVC (MVC Architecture) [6](#kiến-trúc-mvc-mvc-architecture)](#kiến-trúc-mvc-mvc-architecture)

[3.2. Sơ đồ UML (UML Diagrams) [6](#sơ-đồ-uml-uml-diagrams)](#sơ-đồ-uml-uml-diagrams)

[3.4. Quy ước Code (Coding Conventions) [8](#quy-ước-code-coding-conventions)](#quy-ước-code-coding-conventions)

[4. SCREENSHOT (ẢNH CHỤP MÀN HÌNH) [9](#screenshot-ảnh-chụp-màn-hình)](#screenshot-ảnh-chụp-màn-hình)

[4.1. Sơ đồ trang (Site Map) [9](#sơ-đồ-trang-site-map)](#sơ-đồ-trang-site-map)

[4.2. Giao diện các Chức năng Chính [9](#giao-diện-các-chức-năng-chính)](#giao-diện-các-chức-năng-chính)

[5. CONCLUSION AND DISCUSSION (KẾT LUẬN VÀ BÀN LUẬN) [13](#conclusion-and-discussion-kết-luận-và-bàn-luận)](#conclusion-and-discussion-kết-luận-và-bàn-luận)

[5.1. Ưu điểm và Nhược điểm (Pros and Cons) [13](#ưu-điểm-và-nhược-điểm-pros-and-cons)](#ưu-điểm-và-nhược-điểm-pros-and-cons)

[5.2. Kiến thức đã học được (Knowledge Learned) [13](#kiến-thức-đã-học-được-knowledge-learned)](#kiến-thức-đã-học-được-knowledge-learned)

[5.3. Hướng phát triển trong tương lai [14](#hướng-phát-triển-trong-tương-lai)](#hướng-phát-triển-trong-tương-lai)

[Ưu tiên hàng đầu - Khắc phục các vấn đề hiện tại: [14](#ưu-tiên-hàng-đầu---khắc-phục-các-vấn-đề-hiện-tại)](#ưu-tiên-hàng-đầu---khắc-phục-các-vấn-đề-hiện-tại)

[Nâng cấp chức năng: [14](#nâng-cấp-chức-năng)](#nâng-cấp-chức-năng)

#  {#section .TOC-Heading}

# 1. CASE STUDY (NGHIÊN CỨU TÌNH HUỐNG) {#case-study-nghiên-cứu-tình-huống}

## 1. Bối cảnh và Vấn đề chính {#bối-cảnh-và-vấn-đề-chính}

Trong bối cảnh đô thị hóa nhanh chóng, tình trạng vi phạm luật lệ giao thông như vượt đèn đỏ, chạy quá tốc độ, đi sai làn đường diễn ra ngày càng phổ biến và phức tạp. Vấn đề chính cần giải quyết là sự thiếu hụt một kênh tương tác chính thức, hiệu quả và nhanh chóng để người dân có thể báo cáo các hành vi vi phạm này cho cơ quan chức năng. Việc xử lý thủ công các báo cáo (nếu có) thường chậm trễ và thiếu minh bạch, làm giảm hiệu quả răn đe và không khuyến khích sự tham gia của cộng đồng.

Dự án \"Hệ thống Báo cáo vi phạm giao thông\" được xây dựng để giải quyết vấn đề này, tạo ra một nền tảng số hóa cho phép người dân trở thành một phần của giải pháp, góp phần xây dựng văn hóa giao thông an toàn.

# 2. DATABASE DESIGN (THIẾT KẾ CƠ SỞ DỮ LIỆU) {#database-design-thiết-kế-cơ-sở-dữ-liệu}

## 2.1. Thiết kế Logic (Logical Design) {#thiết-kế-logic-logical-design}

Thiết kế logic mô tả các thực thể chính và mối quan hệ giữa chúng:

- Một **User** có thể gửi nhiều **Reports**. Một **Report** chỉ do một **User** gửi. (Mối quan hệ 1-Nhiều)

- Một **User** có thể nhận nhiều **Notifications**. Một **Notification** chỉ gửi cho một **User**. (Mối quan hệ 1-Nhiều)

- Một **Report** được duyệt có thể tạo ra một **Violation**. Một **Violation** được tạo ra từ một **Report**. (Mối quan hệ 1-1)

- Một **Report** được xử lý bởi một **User** (Traffic Police). Một **User** có thể xử lý nhiều **Reports**. (Mối quan hệ 1-Nhiều)

## 2.2. Thiết kế Vật lý (Physical Design) {#thiết-kế-vật-lý-physical-design}

Dựa trên thiết kế logic, mô hình dữ liệu vật lý được triển khai trên Microsoft SQL Server với các bảng chính sau:

- **Bảng Users**

  - UserID INT PRIMARY KEY IDENTITY(1,1)

  - FullName NVARCHAR(100)

  - Email VARCHAR(100) UNIQUE NOT NULL

  - Password NVARCHAR(256) NOT NULL

  - Role VARCHAR(20) NOT NULL

  - Phone VARCHAR(15)

  - Address NVARCHAR(255)

- **Bảng Reports**

  - ReportID INT PRIMARY KEY IDENTITY(1,1)

  - ReporterID INT FOREIGN KEY REFERENCES Users(UserID)

  - ViolationType NVARCHAR(100)

  - Description NVARCHAR(MAX)

  - PlateNumber VARCHAR(20)

  - ImageURL VARCHAR(255)

  - VideoURL VARCHAR(255)

  - Location NVARCHAR(255)

  - ReportDate DATETIME DEFAULT GETDATE()

  - Status VARCHAR(20)

  - ProcessedBy INT FOREIGN KEY REFERENCES Users(UserID)

- **Bảng Violations**

  - ViolationID INT PRIMARY KEY IDENTITY(1,1)

  - ReportID INT FOREIGN KEY REFERENCES Reports(ReportID)

  - ViolatorID INT FOREIGN KEY REFERENCES Users(UserID)

  - FineAmount DECIMAL(18, 2)

  - PaidStatus VARCHAR(20)

- **Bảng Notifications**

  - NotificationID INT PRIMARY KEY IDENTITY(1,1)

  - UserID INT FOREIGN KEY REFERENCES Users(UserID)

  - Message NVARCHAR(MAX)

  - PlateNumber VARCHAR(20)

  - SentDate DATETIME DEFAULT GETDATE()

  - IsRead BIT DEFAULT 0

# 3. SYSTEM DESIGN (THIẾT KẾ HỆ THỐNG) {#system-design-thiết-kế-hệ-thống}

## 3.1. Kiến trúc MVC (MVC Architecture) {#kiến-trúc-mvc-mvc-architecture}

Hệ thống được thiết kế dựa trên kiến trúc Model-View-Controller để tách biệt các thành phần logic, dữ liệu và giao diện.

- **Model:** Là các lớp Java (User.java, Report.java, etc.) đóng gói dữ liệu và logic nghiệp vụ cơ bản. Các lớp DAO (UserDAO.java, ReportDAO.java) cũng thuộc tầng này, chịu trách nhiệm truy xuất dữ liệu từ CSDL.

- **View:** Là các file JSP (index.jsp, report.jsp) chịu trách nhiệm hiển thị giao diện. Chúng nhận dữ liệu đã được chuẩn bị sẵn từ Controller để hiển thị.

- **Controller:** Là các lớp Servlet (LoginServlet.java, RPServlet.java) đóng vai trò điều phối. Chúng nhận request từ người dùng, gọi các lớp ở tầng Model để xử lý, sau đó chọn View thích hợp để phản hồi.

**Ví dụ luồng xử lý đăng nhập:**  
index.jsp → LoginServlet → UserDAO.getUserByEmailAndPassword() → LoginServlet → (redirect) → homeci.jsp.

## 3.2. Sơ đồ UML (UML Diagrams) {#sơ-đồ-uml-uml-diagrams}

Sơ đồ lớp mô tả các lớp chính và mối quan hệ giữa chúng. Các lớp quan trọng bao gồm:

- **Các lớp Model:** User, Report, Violation, Notification.

- **Các lớp DAO:** UserDAO, ReportDAO, ViolationDAO (có mối quan hệ phụ thuộc vào các lớp Model và DBConnection).

- **Các lớp Controller:** LoginServlet, RPServlet, PoliceSL (có mối quan hệ phụ thuộc vào các lớp DAO).  
  Mối quan hệ chính là Association (liên kết) và Dependency (phụ thuộc).![A diagram of a computer
  AI-generated content may be incorrect.](media/image2.png){width="6.5in" height="3.227777777777778in"}

Sơ đồ tuần tự mô tả luồng tương tác giữa các đối tượng theo thời gian cho chức năng gửi báo cáo.

1.  **Actor Citizen** gửi yêu cầu POST từ report.jsp.

2.  **RPServlet** nhận request, gọi phương thức getParameter() và getPart() để lấy dữ liệu.

3.  **RPServlet** gọi phương thức saveFile() của chính nó.

4.  **RPServlet** tạo đối tượng Report.

5.  **RPServlet** gọi ReportDAO.insertReport(report).

6.  **ReportDAO** gọi DBConnection.getConnection().

7.  **ReportDAO** thực thi PreparedStatement lên CSDL.

8.  Kết quả được trả ngược về RPServlet.

9.  **RPServlet** gửi response.sendRedirect() về cho Citizen.

![A diagram of a computer
AI-generated content may be incorrect.](media/image3.png){width="6.5in" height="2.925in"}3.3. Công nghệ mới sử dụng

Dự án chủ yếu sử dụng ngăn xếp công nghệ kinh điển của Jakarta EE. Tuy nhiên, một công nghệ/thư viện phía client hiện đại đã được áp dụng để cải thiện trải nghiệm người dùng:

- **Bootstrap 5:** Là một framework CSS/JavaScript mã nguồn mở, được sử dụng để xây dựng giao diện người dùng có tính thẩm mỹ cao, đồng bộ và đặc biệt là có khả năng đáp ứng (responsive), giúp website hiển thị tốt trên nhiều kích thước màn hình khác nhau (desktop, tablet, mobile).

## 3.4. Quy ước Code (Coding Conventions) {#quy-ước-code-coding-conventions}

Dự án tuân thủ các quy ước code cơ bản để đảm bảo tính nhất quán và dễ đọc:

- **Java:**

  - Tên lớp theo quy tắc PascalCase (ví dụ: ReportDAO).

  - Tên phương thức và biến theo quy tắc camelCase (ví dụ: getReportsByUser).

  - Hằng số được viết hoa và phân cách bằng dấu gạch dưới (ví dụ: UPLOAD_DIR).

- **Kiến trúc:**

  - Tuân thủ chặt chẽ mô hình MVC, tách biệt logic trong Servlet và hiển thị trong JSP.

  - Sử dụng Data Access Object (DAO) pattern để cô lập tầng truy cập dữ liệu.

- **Comments:** Mã nguồn được yêu cầu phải có bình luận (comments) để giải thích các đoạn logic phức tạp hoặc mục đích của các phương thức.

# 4. SCREENSHOT (ẢNH CHỤP MÀN HÌNH) {#screenshot-ảnh-chụp-màn-hình}

## 4.1. Sơ đồ trang (Site Map) {#sơ-đồ-trang-site-map}

Sơ đồ trang mô tả cấu trúc các trang chính của website.

- **Public Area (Khu vực công khai)**

  - /index.jsp (Trang chủ & Đăng nhập)

  - /register.jsp (Trang Đăng ký)

  - /contact.jsp (Trang Liên hệ)

- **Citizen Area (Khu vực của Người dân)**

  - /homeci.jsp (Trang chủ của Citizen)

  - /report.jsp (Form Gửi Báo cáo)

  - /reporthome.jsp (Xem Lịch sử Báo cáo)

  - /notification.jsp (Xem Thông báo)

- **Traffic Police Area (Khu vực của Cảnh sát)**

  - /home.jsp (Trang chủ của Cảnh sát)

  - /PoliceDashboard.jsp (Bảng điều khiển Xử lý Báo cáo)

  - /statistics.jsp (Xem Thống kê)

- **Admin Area (Khu vực của Quản trị viên)**

  - /admin.jsp (Bảng điều khiển Quản lý Người dùng)

  - /add_user.jsp (Form Thêm Người dùng)

  - /edit_user.jsp (Form Sửa Người dùng)

## 4.2. Giao diện các Chức năng Chính {#giao-diện-các-chức-năng-chính}

Trang đăng nhập là cổng vào hệ thống. Giao diện đơn giản, yêu cầu email và mật khẩu. Trang đăng ký thu thập các thông tin cần thiết để tạo tài khoản mới.

![](media/image4.png){width="6.5in" height="3.3180555555555555in"} ![A screenshot of a computer
AI-generated content may be incorrect.](media/image5.png){width="6.5in" height="3.323611111111111in"}

Đây là chức năng cốt lõi cho người dân, form cho phép nhập đầy đủ thông tin vi phạm và đính kèm bằng chứng.

![A screenshot of a computer
AI-generated content may be incorrect.](media/image6.png){width="6.5in" height="3.2819444444444446in"}Giao diện hiển thị danh sách các báo cáo đang chờ xử lý dưới dạng bảng. Mỗi hàng có form nhỏ để cảnh sát điền mức phạt và đưa ra quyết định \"Duyệt\" hoặc \"Từ chối\".

![A screenshot of a computer
AI-generated content may be incorrect.](media/image7.png){width="6.5in" height="3.316666666666667in"}

Giao diện hiển thị danh sách tất cả người dùng trong hệ thống. Admin có thể thực hiện các thao tác Sửa/Xóa trực tiếp trên bảng này hoặc nhấn nút để thêm người dùng mới.

![A screenshot of a computer
AI-generated content may be incorrect.](media/image8.png){width="6.5in" height="2.259027777777778in"}

# 5. CONCLUSION AND DISCUSSION (KẾT LUẬN VÀ BÀN LUẬN) {#conclusion-and-discussion-kết-luận-và-bàn-luận}

## 5.1. Ưu điểm và Nhược điểm (Pros and Cons) {#ưu-điểm-và-nhược-điểm-pros-and-cons}

- **Ưu điểm (Pros):**

  - **Kiến trúc rõ ràng:** Việc áp dụng mô hình MVC giúp hệ thống có cấu trúc tốt, dễ dàng phân chia công việc, bảo trì và mở rộng.

  - **An toàn trước SQL Injection:** Việc sử dụng PreparedStatement một cách nhất quán trong toàn bộ các lớp DAO đã ngăn chặn được một trong những lỗ hổng web phổ biến và nguy hiểm nhất.

  - **Đáp ứng yêu cầu nghiệp vụ:** Hệ thống đã hoàn thành và đáp ứng được đầy đủ các luồng chức năng chính đã đề ra trong các use case.

- **Nhược điểm (Cons) và các Vấn đề còn tồn tại:**

  - **Lỗ hổng bảo mật nghiêm trọng về mật khẩu:** Hệ thống đang lưu trữ và so sánh mật khẩu người dùng ở dạng văn bản thô, vi phạm nguyên tắc an toàn thông tin cơ bản nhất.

  - **Lỗ hổng phân quyền:** Chức năng quản trị (đặc biệt là xóa người dùng) không có cơ chế kiểm tra quyền hạn, cho phép bất kỳ ai cũng có thể thực hiện nếu biết URL.

  - **Vi phạm nguyên tắc MVC trong tầng View:** Rất nhiều trang JSP chứa mã Java (scriptlet) để truy vấn trực tiếp CSDL, làm cho code ở tầng View trở nên phức tạp, khó gỡ lỗi và vi phạm nguyên tắc tách biệt logic.

## 5.2. Kiến thức đã học được (Knowledge Learned) {#kiến-thức-đã-học-được-knowledge-learned}

Qua quá trình thực hiện dự án, bản thân đã học hỏi và củng cố được nhiều kiến thức, kỹ năng quan trọng:

- Nắm vững cách triển khai và vận dụng mô hình kiến trúc MVC trong một ứng dụng Java Web thực tế.

- Có kinh nghiệm thực tiễn trong việc làm việc với JDBC, Servlet, JSP và luồng xử lý request/response.

- Hiểu rõ tầm quan trọng của việc phòng chống các lỗ hổng bảo mật cơ bản như SQL Injection, và nhận thức được các rủi ro từ việc xử lý mật khẩu và phân quyền không đúng cách.

- Học được cách tích hợp một framework frontend (Bootstrap) vào dự án để cải thiện chất lượng giao diện.

## 5.3. Hướng phát triển trong tương lai {#hướng-phát-triển-trong-tương-lai}

Nếu có thêm thời gian, dự án sẽ được cải thiện và mở rộng theo các hướng sau:

### Ưu tiên hàng đầu - Khắc phục các vấn đề hiện tại:

- **Refactor toàn bộ code:** Loại bỏ hoàn toàn scriptlet khỏi các file JSP, chuyển logic xử lý sang các Servlet.

- **Vá lỗ hổng bảo mật:** Tích hợp PasswordUtil để hash mật khẩu bằng bcrypt; thêm bộ lọc (Filter) để kiểm tra quyền truy cập cho các URL của admin và cảnh sát.

### Nâng cấp chức năng:

- Thêm chức năng **quên mật khẩu** và đặt lại mật khẩu qua email.

- Phát triển giao diện **thống kê trực quan** hơn bằng cách sử dụng các thư viện biểu đồ JavaScript (vd: Chart.js).

- Xây dựng các **API (RESTful web services)** để cho phép các ứng dụng di động trong tương lai có thể kết nối và sử dụng dịch vụ.
