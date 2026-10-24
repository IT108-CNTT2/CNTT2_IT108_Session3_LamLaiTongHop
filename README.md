# Phần 1 — Kiến trúc Hệ điều hành

## 1. Chạy nhiều phần mềm cùng lúc

Đây là chức năng **quản lý tiến trình và tài nguyên** của hệ điều hành.

Word, Chrome, VS Code và Portal chạy cùng lúc được vì hệ điều hành chia **CPU, RAM và các tài nguyên** cho từng chương trình. Mỗi chương trình chạy trong tiến trình riêng nên hạn chế xung đột với nhau.

## 2. Shell và Kernel

Khi double-click vào file, thao tác sẽ được xử lý qua **Shell trước**.

Shell là lớp giao tiếp giữa người dùng và hệ điều hành, nhận thao tác như click, mở file, chạy chương trình. Sau đó Shell gửi yêu cầu xuống **Kernel** để Kernel xử lý tài nguyên phần cứng, bộ nhớ, ổ đĩa,...

Người dùng thường không làm việc trực tiếp với Kernel vì Kernel hoạt động ở mức thấp và liên quan trực tiếp đến phần cứng, nếu thao tác sai có thể ảnh hưởng hệ thống.

---

# Phần 2 — Cây thư mục & Ổ đĩa

## 1. Xác định trong cây thư mục

- **Root Directory:** `D:\`
- **Parent Directory của `anh 1.jpg`:** `Hinh anh`
- `anh 1.jpg` là **lá**, vì nó là file và không chứa thành phần con.

## 2. Không nên lưu dự án ở Desktop hoặc Downloads

Hai lý do:

1. Desktop và Downloads nằm trong User Profile trên ổ `C:\`, nếu Windows lỗi hoặc phải cài lại hệ điều hành thì dữ liệu có nguy cơ bị mất.
2. Downloads thường chứa nhiều file tải từ Internet nên dễ lẫn file rác hoặc file có mã độc, khó quản lý dự án.

Nên lưu dự án trên ổ `D:\`, ví dụ:

`D:\02_Projects\BaiTapLonIT101\`

---

# Phần 3 — Đường dẫn Path

## 1. Absolute Path

```text
D:\Nam1\HocKy1\MonHoc\CongNgheThongTin\BaiTapLon\Session02\BaoCaoCuoiKy\Chuong1\Hinh anh\anh 1.jpg
```

## 2. Relative Path

Từ `report.html` đến `logo.png`:

```text
./assets/logo.png
```

Ví dụ trong HTML:

```html
<img src="./assets/logo.png">
```

Dùng Relative Path giúp khi copy hoặc nén cả thư mục sang máy khác thì đường dẫn vẫn hoạt động, miễn là cấu trúc các thư mục bên trong không thay đổi.

---

# Phần 4 — Quy tắc Đặt tên chuẩn

Tên cũ:

```text
Báo cáo bài tập lớn IT101 (bản cuối) v2.docx
```

Đổi sang `kebab-case`:

```text
bao-cao-bai-tap-lon-it101-ban-cuoi-v2.docx
```

Tên mới viết thường, không dấu, không khoảng trắng và dùng dấu `-` để ngăn cách các từ.

---

# Phần 5 — Tổ chức & Dọn dẹp Ổ đĩa

## 1. Số cấp thư mục

Đường dẫn cũ có **9 cấp thư mục**:

```text
Nam1
→ HocKy1
→ MonHoc
→ CongNgheThongTin
→ BaiTapLon
→ Session02
→ BaoCaoCuoiKy
→ Chuong1
→ Hinh anh
```

Nó vi phạm **Quy tắc 3 Cấp Thư Mục** vì bị lồng quá sâu.

Có thể tổ chức lại thành:

```text
D:\01_HocTap\IT101\hinh-anh\anh-1.jpg
```

Trong đó:

- Cấp 1: `01_HocTap`
- Cấp 2: `IT101`
- Cấp 3: `hinh-anh`

Cách này ngắn hơn và dễ tìm file hơn.

---

# Phần 6 — Đuôi file & File ẩn

File hiển thị:

```text
de-thi-dap-an.pdf
```

có thể là một **file giả mạo**. Vì Windows đang ẩn đuôi file nên tên thật có thể là:

```text
de-thi-dap-an.pdf.exe
```

Trong trường hợp này `.pdf` chỉ là một phần của tên file, còn đuôi thật là `.exe`. Nếu mở thì có thể chạy mã độc.

Trước khi mở file, vào **File Explorer → View → Show → File name extensions**.

Sau khi bật lên, Windows sẽ hiện đầy đủ đuôi file. Nếu thấy `.exe`, `.bat`, `.cmd` hoặc đuôi lạ thì không nên mở file đó.
