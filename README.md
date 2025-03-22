BÁO CÁO HỆ THỐNG GIÁM SÁT PHƯƠNG TIỆN VI PHẠM GIAO THÔNG VÀ THU THẬP BIỂN SỐ XE
![image](https://github.com/user-attachments/assets/d1572174-b9a5-44f7-b7c8-769db9bdac3e)
Giao thông là một trong những vấn đề quan trọng đối với các đô thị lớn. Việc giám sát và phát hiện phương tiện vi phạm giúp tăng cường an toàn giao thông và giảm thiểu tình trạng ùn tắc. Đề tài này tập trung vào việc xây dựng hệ thống giám sát giao thông tự động, có khả năng phát hiện phương tiện và nhận diện biển số xe theo thời gian thực.

📌 Giới thiệu hệ thống  
Hệ thống phát hiện phương tiện vi phạm giao thông và nhận diện biển số xe sử dụng công nghệ xử lý ảnh và trí tuệ nhân tạo (AI). Hệ thống có khả năng:
- 📸 Nhận diện phương tiện vi phạm (vượt đèn đỏ, không đội mũ bảo hiểm, v.v.)
- 🔍 Trích xuất biển số xe từ video/hình ảnh
- 📊 Lưu trữ dữ liệu vi phạm vào cơ sở dữ liệu
- 📤 Xuất báo cáo chi tiết về các phương tiện vi phạm

 🏗️ Cấu trúc hệ thống
Hệ thống bao gồm các thành phần chính:
1. 📹 Camera giám sát: Ghi lại hình ảnh và video phương tiện giao thông.
2. 🖥️ Xử lý ảnh & AI: Phát hiện vi phạm và nhận diện biển số.
3. 💾 Cơ sở dữ liệu: Lưu thông tin vi phạm,và hỗ trợ truy vấn

![image](https://github.com/user-attachments/assets/7e0b9c63-31e6-4ae7-8ac5-6749f4f6bf2a)

   
 🛠️ Công cụ sử dụng
- Python 🐍 (OpenCV, YOLO, Pytesseract, SQLite)
- Thư viện hỗ trợ: Numpy, Pandas,ultralytics...
- Cơ sở dữ liệu: SQLite/MySQL
- Mô hình AI: YOLOv8 để nhận diện phương tiện
- Mô hình AI riêng:license_plate_detector.pt dùng để nhận diện biển số xe

 🚀 Hướng dẫn cài đặt và chạy
 
 1 Cài đặt thư viện
 
 python 3.7+
 
 Sau đó cài đặt các thư viện trong file requirements.txt với câu lệnh sau
```bash
pip install -r requirements.txt
```
2 Tạo môi truờng ảo(tùy chọn)
``` bash
python -m venv venv
source venv/bin/activate  # Trên macOS/Linux
.\venv\Scripts\activate  # Trên Windows
```
3 Tạo cơ sở dữ liệu
``` bash
conn = sqlite3.connect("violations.db")
c = conn.cursor()
c.execute('''CREATE TABLE IF NOT EXISTS violations (
                id INTEGER PRIMARY KEY AUTOINCREMENT,
                vehicle_type TEXT,
                timestamp TEXT)''')
conn.commit()
```
 4 Chạy hệ thống
```bash
python traffic_violation_detection.py
```

📖 Hướng dẫn sử dụng
1. Mở giao diện và chọn file video/hình ảnh cần kiểm tra.
2. Nhấn nút 'Phát hiện vi phạm' để hệ thống xử lý.
3. Kiểm tra kết quả trên màn hình hoặc xuất báo cáo dưới dạng file CSV/Excel.

⚙️ Cấu hình & Ghi chú
- Cấu hình đường dẫn video trong traffic_violation_detection.py.
- Tùy chỉnh thông số nhận diện biển số trong license_plate_recognition.py.
- Kiểm tra dữ liệu vi phạm trong kiemtradulieudatabase.py.
  
📰 Báo cáo dữ liệu vi phạm
- Hệ thống lưu thông tin vi phạm vào cơ sở dữ liệu violations.db. Để kiểm tra dữ liệu đã lưu, chạy lệnh sau:
```bash
python kiemtradulieudatabase.py
```
📰 Poster

![image](https://github.com/user-attachments/assets/0d28a8a1-e0bd-4420-ae06-1bf4828374c1)



🤝 Đóng góp

Dự án được phát triển bởi 4 thành viên:

![image](https://github.com/user-attachments/assets/428bb98a-60ca-4143-a5af-f77995e84949)



© 2025 NHÓM 7, CNTT16-04, TRƯỜNG ĐẠI HỌC ĐẠI NAM
