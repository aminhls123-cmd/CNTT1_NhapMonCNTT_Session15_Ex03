# Bài 3 : Ngăn chặn quá tải lưu trữ khi đồng bộ mã nguồn

## 1. Phân tích Luồng Dữ liệu từ `Ctrl+S` đến Tích xanh
1. **Local Write:** Nhấn `Ctrl+S` -> Ghi dữ liệu từ RAM xuống ổ cứng SSD cục bộ (`Local Storage`).
2. **File Watcher:** Ứng dụng Cloud phát hiện sự thay đổi (`Modified Event`) trong thư mục dự án.
3. **Delta Analysis:** Thuật toán đồng bộ vi sai chỉ trích xuất phần byte thực sự thay đổi thay vì tải cả tệp.
4. **Cloud Upload:** Truyền các khối dữ liệu thay đổi qua giao thức HTTPS lên máy chủ đám mây.
5. **Sync Complete:** Máy chủ xác nhận thành công và trả tín hiệu hiển thị **tích xanh** trên tệp.

---

## 2. Sơ đồ Tổ chức Thư mục Chuẩn cho Lập trình viên
```text
📁 Project_Name/
├── 📁 src/                  # Mã nguồn chính (Source Code)
├── 📁 docs/                 # Tài liệu kỹ thuật, đặc tả, báo cáo dự án
├── 📁 assets/               # Tài nguyên hình ảnh, thiết kế, icon
├── 📄 package.json          # Quản lý thư viện phụ thuộc JavaScript
├── 📄 .gitignore            # Loại trừ node_modules, file cấu hình nhạy cảm (.env)
└── 📄 README.md             # Tệp hướng dẫn sử dụng dự án
