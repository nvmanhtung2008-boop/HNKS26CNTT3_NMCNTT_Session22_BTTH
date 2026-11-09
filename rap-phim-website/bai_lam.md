# BÀI LÀM – (ĐỀ LUYỆN TẬP SỐ 02)

- **Mã đề:** 02
- **Họ tên:Nguyễn Văn Mạnh Tùng**
- **Lớp:CNTT3**
- **Link repository:**
- **Hệ điều hành (Windows/macOS):Windows**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
1. pwd
2. ls -Recurse -Force
3. mv ".\bien_ban_ban_giao.txt" ".\docs"
4. mkdir backup
5. copy ".\data\ban_ve_thang_11.xlsx" ".\backup"
6. rm .\cache_991.tmp
7. cd .\logs
 Get-Content .\server.log
 cd..

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
Directory: D:\Project_CNTT\luyen_tap_NMCNTT\Luyen_Tap_11_9\starter-kit\rap-phim-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         11/9/2026   3:35 PM                backup
d-----         11/9/2026   3:32 PM                data
d-----         11/9/2026   3:34 PM                docs
d-----         11/9/2026   3:13 PM                evidence
d-----         11/9/2026   3:32 PM                logs
d-----         11/9/2026   3:08 PM                web
-a----         11/9/2026   3:08 PM             82 .env
-a----         11/9/2026   3:31 PM             37 .env.example
-a----         11/9/2026   3:31 PM              4 .gitignore
-a----         11/9/2026   3:39 PM           3244 bai_lam.md


    Directory: D:\Project_CNTT\luyen_tap_NMCNTT\Luyen_Tap_11_9\starter-kit\rap-phim-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/9/2026   3:08 PM           5693 ban_ve_thang_11.xlsx


    Directory: D:\Project_CNTT\luyen_tap_NMCNTT\Luyen_Tap_11_9\starter-kit\rap-phim-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/9/2026   3:08 PM           5693 ban_ve_thang_11.xlsx


    Directory: D:\Project_CNTT\luyen_tap_NMCNTT\Luyen_Tap_11_9\starter-kit\rap-phim-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/9/2026   3:08 PM            172 bien_ban_ban_giao.txt


    Directory: D:\Project_CNTT\luyen_tap_NMCNTT\Luyen_Tap_11_9\starter-kit\rap-phim-website\evidence


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/9/2026   3:12 PM         115057 console.png
-a----         11/9/2026   3:10 PM         125302 network.png


    Directory: D:\Project_CNTT\luyen_tap_NMCNTT\Luyen_Tap_11_9\starter-kit\rap-phim-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/9/2026   3:08 PM            893 server.log


    Directory: D:\Project_CNTT\luyen_tap_NMCNTT\Luyen_Tap_11_9\starter-kit\rap-phim-website\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----         11/9/2026   3:08 PM                images
-a----         11/9/2026   3:20 PM            620 app.js
-a----         11/9/2026   3:14 PM            553 index.html
-a----         11/9/2026   3:08 PM            460 style.css


    Directory: D:\Project_CNTT\luyen_tap_NMCNTT\Luyen_Tap_11_9\starter-kit\rap-phim-website\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/9/2026   3:08 PM            342 logo-cinebox.png

```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng ERROR

```shell
Get-Content ".\logs\server.log" | Select-String "error" > ".\logs\loi_error.txt"

```

### 2 dòng đầu tiên trong logs/loi_error.txt

```text
2026-11-01 09:25:40 ERROR POST /api/mua-ve
2026-11-01 09:29:11 ERROR POST /api/thanh-toan-qr

```

### b) Lệnh đếm số dòng WARNING và kết quả

```shell
(Get-Content ".\logs\server.log" | Select-String "error").count 

```

```text
6
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

2026-11-01 09:08:10 WARNING GET /phim-sap-chieu-cu
2026-11-01 09:15:30 WARNING GET /uu-dai-thang-9
2026-11-01 09:36:50 WARNING GET /images/phong-imax.jpg
2026-11-01 10:01:20 WARNING GET /voucher-het-han
2026-11-01 10:12:55 WARNING GET /combo-bap-nuoc




Count    : 6
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property : 


```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] README.md: Heading 1, mô tả có **in đậm** và _in nghiêng_, bảng, code block, task list, blockquote
- [x] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [x] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | -------------------------- | --------------------------- | -------------- |
| 1   |              Network              |        Tên ảnh sai                     |          Sửa lại tên ảnh cho đúng      |
| 2   |      console                      |       app.js:18 Uncaught ReferenceError: hienThiBangGia is not defined            |       đổi tên ở dòng 18 thành hienThiBangGiaVe         |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context:Tôi là sinh viên năm nhất chưa học jv và fix lỗi của web bao giờ**
- **Expected: Bây giờ trang web xem phim của tôi muốn có đủ dữ liệu ở bảng**
- **Actual:Thực tế bây giờ dữ liệu của tôi bị trống và khi vào console và thấy thông báo lỗi**
- **Log:ReferenceError: hienThiBangGia is not defined**

### Câu tìm kiếm Google

```text
site:stackoverflow.com "is not defined"

```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/ban_ve_thang_11.xlsx`, không cần ghi vào đây.
