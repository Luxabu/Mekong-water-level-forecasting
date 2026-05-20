# Mekong Water Level Forecasting

## 📊 Dự án dự báo mực nước sông Mekong

Dự án này sử dụng **Ensemble Learning** để dự báo mực nước sông Mekong tại các trạm quan trắc khác nhau dọc theo dòng sông.

## 🎯 Mục tiêu

- Dự báo mực nước sông Mekong tại **24 trạm** khác nhau
- So sánh hiệu suất các mô hình machine learning
- Xây dựng ensemble model tối ưu

## 📁 Cấu trúc thư mục

```
├── main.ipynb                          # Notebook chính - huấn luyện & đánh giá
├── README.md                            # File này
├── .gitignore                           # Git ignore rules
├── station_metadata_master.csv          # Metadata các trạm
├── stations_map.html                    # Bản đồ các trạm quan trắc
│
├── data/                                # Dữ liệu training/test
│   ├── Ban_Had_Paeng/
│   │   ├── Ban_Had_Paeng.json
│   │   ├── train.csv
│   │   └── test.csv
│   ├── Ban_Kengdone/
│   ├── Ban_Mai_Singsamphan/
│   ├── Ban_Mixai/
│   ├── Ban_Nape/
│   ├── Ban_Tha_Kok_Daeng/
│   ├── Ban_Veunkhen/
│   ├── Bueng_Kan/
│   ├── Can_Tho/
│   ├── Chaktomuk/
│   ├── Chau_Doc/
│   ├── Kamrieng/
│   ├── Koh_Khel/
│   ├── Kompong_Cham/
│   ├── Kratie/
│   ├── Muang_Kao/
│   ├── Muong_Ngoy/
│   ├── My_Thuan/
│   ├── Neak_Luong/
│   ├── Nong_Khai_2/
│   ├── Pha_Phin/
│   ├── Phnom_Koy/
│   ├── Prek_Kdam/
│   ├── Siempang/
│   ├── Stung_Treng/
│   └── Tan_Chau/
│
├── models/                              # Mô hình đã huấn luyện
│   ├── regression_summary.csv           # Tóm tắt kết quả regression
│   ├── station_performance.csv          # Hiệu suất từng station
│   ├── scalers/                         # Scaler objects
│   ├── regression/                      # Mô hình regression
│   └── forecasts/                       # Dự báo đã lưu
│
└── ensemble_results/                    # Kết quả từ ensemble model
    ├── Ban_Had_Paeng/
    │   ├── Ban_Had_Paeng_results.csv
    │   └── Ban_Had_Paeng_feature_importance.csv
    ├── Ban_Kengdone/
    └── ... (các station khác)
```

## 🛠️ Cài đặt

### 1. Clone repository
```bash
git clone <repository-url>
cd Mekong-water-level-forecasting
```

### 2. Tạo virtual environment
```bash
python -m venv venv
source venv/bin/activate  # Trên Linux/Mac
# hoặc
venv\Scripts\activate  # Trên Windows
```

### 3. Cài đặt dependencies
```bash
pip install -r requirements.txt
```

### 4. Tải dữ liệu (nếu cần)
```bash
# Dữ liệu nằm trong thư mục data/
# Nếu chưa có, liên hệ để lấy dữ liệu gốc
```

## 🚀 Sử dụng

### Chạy notebook chính
```bash
jupyter notebook main.ipynb
```

Notebook bao gồm:
1. **Load & preprocess dữ liệu** - Tải dữ liệu từ CSV
2. **Feature engineering** - Tạo features từ dữ liệu thô
3. **Train models** - Huấn luyện các mô hình:
   - Linear Regression
   - Decision Tree Regression
   - Random Forest
   - Gradient Boosting
   - Support Vector Regression
4. **Ensemble learning** - Kết hợp các mô hình
5. **Evaluation & visualization** - Đánh giá & vẽ biểu đồ

## 📊 Dữ liệu

### Format dữ liệu
- **train.csv**: Dữ liệu huấn luyện với cột `water_level` (target)
- **test.csv**: Dữ liệu kiểm tra
- **.json**: Metadata về station (vị trí địa lý, tên, mô tả)

### Các trạm quan trắc (24 stations)
Các trạm nằm dọc theo sông Mekong:
- Thượng lưu: Ban_Had_Paeng, Pha_Phin, Muong_Ngoy, Kamrieng, ...
- Hạ lưu: Chau_Doc, Can_Tho, My_Thuan, ...

## 📈 Kết quả

### Output Files
- **regression_summary.csv** - Tóm tắt kết quả regression cho tất cả station
- **station_performance.csv** - Metrics (MAE, RMSE, R²) cho từng station
- **ensemble_results/** - Kết quả chi tiết:
  - `*_results.csv` - Dự báo & độ lỗi
  - `*_feature_importance.csv` - Tầm quan trọng các features

### Metrics
- **MAE** (Mean Absolute Error) - Sai số tuyệt đối trung bình
- **RMSE** (Root Mean Squared Error) - Căn bậc hai sai số bình phương
- **R² Score** - Hệ số xác định

## 🔗 Bản đồ Visualization
Mở file `stations_map.html` trong trình duyệt để xem bản đồ vị trí các trạm quan trắc.

## 📝 Lưu ý

- **Dữ liệu lớn**: File CSV có thể rất lớn, được ignore trên GitHub
- **Model files**: Các mô hình đã huấn luyện cũng được ignore, có thể retrain từ dữ liệu
- **Ensemble results**: Kết quả có thể tái tính từ mô hình

## 👨‍💻 Tác giả

Dự án Water Level Forecasting - Data Science

## 📄 License

MIT License - Tự do sử dụng cho mục đích học tập và nghiên cứu
