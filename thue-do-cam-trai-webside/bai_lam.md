# BÀI LÀM – HACKATHON 02

- **Mã đề:** 05
- **Họ tên:Lê Đức Anh**
- **Lớp:CNTT3**
- ** Link repository:https://github.com/danhle220508/HN-KS26-CNTT3_Nhap-mon-CNTT-thong-tin_Hackathon02 **
- **Hệ điều hành (Windows/macOS):Windows**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
# Ghi lần lượt các lệnh đã chạy, mỗi lệnh một dòng
pwd
ls -Force
mv .\quy_dinh_thue.txt .\docs\
mkdir backup
cp .\data\don_thue_thang_5.xlsx .\backup\
rm .\temp_505.tmp
cd .\logs\
ls
cd..
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
 Directory: C:\Users\AD\OneDrive\Documents\Downloads\thi cuoi mon\starter-kit\thue-do-cam-trai-webside


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026  10:53 AM                backup
d-----        11/11/2026  10:52 AM                data
d-----        11/11/2026  10:52 AM                docs
d-----        11/11/2026  10:51 AM                evidence
d-----        11/11/2026  10:52 AM                logs
d-----         11/3/2026   7:07 AM                web
-a----         11/3/2026   7:07 AM             72 .env
-a----         11/3/2026   7:07 AM           2409 bai_lam.md


    Directory: C:\Users\AD\OneDrive\Documents\Downloads\thi cuoi mon\starter-kit\thue-do-cam-trai-webside\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM           6132 don_thue_thang_5.xlsx


    Directory: C:\Users\AD\OneDrive\Documents\Downloads\thi cuoi mon\starter-kit\thue-do-cam-trai-webside\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM           6132 don_thue_thang_5.xlsx


    Directory: C:\Users\AD\OneDrive\Documents\Downloads\thi cuoi mon\starter-kit\thue-do-cam-trai-webside\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            159 quy_dinh_thue.txt


    Directory: C:\Users\AD\OneDrive\Documents\Downloads\thi cuoi mon\starter-kit\thue-do-cam-trai-webside\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            934 rental.log


    Directory: C:\Users\AD\OneDrive\Documents\Downloads\thi cuoi mon\starter-kit\thue-do-cam-trai-webside\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         11/3/2026   7:07 AM                images
-a----         11/3/2026   7:07 AM            582 app.js
-a----         11/3/2026   7:07 AM            534 index.html
-a----         11/3/2026   7:07 AM            460 style.css


    Directory: C:\Users\AD\OneDrive\Documents\Downloads\thi cuoi mon\starter-kit\thue-do-cam-trai-webside\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM           3090 logo-campgo.png

```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
Get-Content .\logs\rental.log | Select-String "status=500" > .\logs\loi_500.txt

```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
2026-05-28 08:17:12 POST /api/kho-do status=500
2026-05-28 08:20:23 POST /api/thue-do status=500


```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
(Get-Content .\logs\rental.log | Select-String "status=404").count

```

```text
4

```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
.\tong_hop.ps1

```

### Nội dung file logs/tong_hop.txt

```text
=== BAO CAO SU CO WEBSITE ===

2026-05-28 08:13:01 GET /combo-cu status=404
2026-05-28 08:30:56 GET /images/leu-6.jpg status=404
2026-05-28 08:33:07 GET /images/leu-6.jpg status=404
2026-05-28 08:49:24 GET /combo-cu status=404




Count    : 6
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property : 


```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [ ] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [ ] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [ ] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 | network | lỗi không hiện logo | sửa lại tên trong html |
| 2 | console | lỗi không hiện bảng giá trị | sửa lại tên trong js |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:Tôi là sinh viên năm nhất chưa fix lỗi hiển thị dữ liệu của web bao giờ** 
- **Expected:Bây giờ trang web cho thuê đồ cắm trại của tôi muốn có đủ dữ liệu ở bảng hiển thị giao diện** 
- **Actual:Dữ liệu trên trang web không có gì và tôi vào tab console thấy thông báo lỗi app.js:18 Uncaught ReferenceError: hienThiBangThue is not defined** 
- **Log:app.js:18 Uncaught ReferenceError: hienThiBangThue is not defined** 

### Câu tìm kiếm Google

```text
site:stackoverflow.com "Uncaught ReferenceError"

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/don_thue_thang_5.xlsx`, không cần ghi vào đây.
