# Phân tích và trực quan hóa sự khác biệt từ vựng giữa ba vùng miền tiếng Việt

## Mục tiêu dự án
Dự án này nhằm phân tích và trực quan hóa sự khác biệt từ vựng giữa ba vùng miền Bắc, Trung, Nam của Việt Nam thông qua bộ dữ liệu ViMD (Vietnamese Multi-Dialect Dataset).

### Đầu vào
- Bộ dữ liệu ViMD từ Hugging Face: [nguyendv02/ViMD_Dataset](https://huggingface.co/datasets/nguyendv02/ViMD_Dataset)
- Dữ liệu bao gồm:
  - 102.56 giờ audio
  - Khoảng 19,000 câu nói
  - Hơn 1.2 triệu từ
  - Phân bố trên 63 tỉnh/thành phố
  - Thông tin về giới tính người nói
  - Văn bản chuyển đổi từ audio

### Đầu ra
Các phân tích và biểu đồ trực quan hóa:
1. Phân tích cơ bản:
   - Phân bố dữ liệu theo vùng miền (Bắc, Trung, Nam)
   - Phân bố dữ liệu theo giới tính
   - Phân bố độ dài audio theo vùng miền
   - Phân bố số lượng từ theo vùng miền

2. Phân tích từ vựng:
   - Word Cloud cho từng vùng miền
   - Phân tích từ vựng đặc trưng theo vùng miền
   - So sánh từ vựng giữa các vùng miền
   - Phân tích độ dài từ và cấu trúc câu

3. Biểu đồ thống kê tổng hợp:
   - Biểu đồ radar so sánh các chỉ số giữa 3 vùng miền
   - Bảng thống kê chi tiết
   - Nhận xét và kết luận

## Yêu cầu hệ thống
- Python 3.11.x (không khuyến nghị dùng Python 3.12 trở lên)
- Windows 10/11
- RAM tối thiểu: 8GB
- Dung lượng ổ cứng trống: ít nhất 5GB

## Cấu trúc dự án
```
.
├── notebooks/            # Jupyter notebooks cho phân tích
│   └── dialect_analysis.ipynb  # Notebook chính cho phân tích dữ liệu
├── requirements.txt      # Danh sách các thư viện cần thiết
└── README.md            # Tài liệu hướng dẫn
```

## Cài đặt

### 1. Tạo môi trường ảo
```bash
# Tạo môi trường ảo
python -m venv venv

# Kích hoạt môi trường
.\venv\Scripts\activate
```

### 2. Cập nhật pip
```bash
python -m pip install --upgrade pip
```

### 3. Cài đặt các thư viện theo thứ tự
```bash
# Cài đặt các thư viện cơ bản
pip install numpy
pip install pandas
pip install matplotlib
pip install seaborn

# Cài đặt các thư viện cho xử lý dữ liệu và trực quan hóa
pip install datasets
pip install plotly
pip install wordcloud

# Cài đặt Jupyter và các extension
pip install jupyter
pip install notebook
pip install ipykernel
```

### 4. Cấu hình Jupyter
```bash
# Thêm kernel mới cho môi trường ảo
python -m ipykernel install --user --name=venv
```

## Sử dụng

### 1. Khởi động Jupyter Notebook
```bash
# Kích hoạt môi trường ảo (nếu chưa kích hoạt)
.\venv\Scripts\activate

# Khởi động Jupyter Notebook
jupyter notebook
```

### 2. Mở và chạy notebook
- Mở file `notebooks/dialect_analysis.ipynb` trong trình duyệt
- Chọn kernel "venv" từ menu Kernel -> Change kernel
- Chạy các cell theo thứ tự để xem kết quả phân tích

### 3. Cấu trúc notebook
1. Giới thiệu và cài đặt
   - Import thư viện
   - Cấu hình hiển thị
2. Tải và xem tổng quan dữ liệu
3. Phân tích cơ bản
4. Phân tích từ vựng
5. Biểu đồ thống kê tổng hợp
6. Kết luận

## Xử lý lỗi thường gặp

### 1. Lỗi khi cài đặt thư viện
```bash
# Thử cài đặt lại với phiên bản cụ thể
pip install wordcloud==1.8.1
pip install seaborn==0.12.2
```

### 2. Lỗi font chữ tiếng Việt
- Đảm bảo đã cài đặt font Arial Unicode MS
- Hoặc thay đổi font trong code:
```python
plt.rcParams['font.family'] = 'DejaVu Sans'
```

### 3. Lỗi khi tải dataset
- Kiểm tra kết nối internet
- Đảm bảo đã cài đặt đúng phiên bản của thư viện datasets
- Thử tải lại dataset

### 4. Lỗi khi tạo biểu đồ
- Kiểm tra quyền ghi vào thư mục results
- Đảm bảo đã cài đặt đầy đủ các thư viện cần thiết
- Kiểm tra dữ liệu đầu vào có đúng định dạng không 