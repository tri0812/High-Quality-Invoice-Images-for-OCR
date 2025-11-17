# High-Quality-Invoice-Images-for-OCR

**"High-Quality Invoice Images for OCR"** mô phỏng quy trình tự động hóa xử lý dữ liệu hóa đơn (Invoice / Order) trong doanh nghiệp. Mục tiêu chính là **thu thập, tiền xử lý, lưu trữ, và trực quan hóa dữ liệu hóa đơn** để hỗ trợ các hệ thống OCR, AI hoặc phân tích tài chính.

## 📊 Nguồn dữ liệu

- Tải từ "Foodpanda Order & Delivery Trends" trên Kaggle.
- Cách sử dụng: Download file CSV → đặt vào thư mục `data/foodpanda_orders.csv` → sử dụng script `import_to_sql.py` để import.

## 👥 Phân Công Nhiệm Vụ

| Thành viên                                | Nhiệm vụ chính                                                                                                 | Công cụ chính                      |
| ----------------------------------------- | -------------------------------------------------------------------------------------------------------------- | ---------------------------------- |
| **👨‍💼 Người 1 – Trưởng nhóm - Nguyễn Thái Bảo -  (Data Engineer)** | - Thu thập & import dữ liệu Kaggle vào SQL<br>- Thiết kế Database Schema<br>- Viết script SQL xử lý dữ liệu<br>- Quản lý infrastructure | MySQL, Python (SQLAlchemy, Pandas) |
| **🧹 Người 2 – Nguyễn Hữu Dương - Data Cleaning Specialist**  | - Tiền xử lý và làm sạch dữ liệu<br>- Xử lý missing values, duplicates, outliers<br>- Chuẩn hóa format dữ liệu | Jupyter Notebook, Pandas, NumPy    |
| **📊 Người 3 – Nguyễn Đình Trí - Data Analyst**             | - Phân tích thống kê mô tả<br>- Tìm patterns và trends<br>- Phát hiện insights quan trọng<br>- Viết notebook phân tích | Jupyter Notebook, Pandas, SciPy     |
| **📈 Người 4 – Data Visualization**       | - Trực quan hóa dữ liệu (Seaborn, Plotly)<br>- Tạo biểu đồ tương tác<br>- Thiết kế dashboard | Matplotlib, Seaborn, Plotly         |
| **📝 Người 5 – Report & Documentation**   | - Viết báo cáo tổng hợp<br>- Chuẩn bị slides trình bày<br>- Cập nhật README và tài liệu | Markdown, PowerPoint, LaTeX        |

## 📁 Cấu Trúc Dự Án

```
foodpanda-analytics/
│
├── data/
│   └── foodpanda_orders.csv
│
├── src/
│   ├── import_to_sql.py          # 👨‍💼 Người 1
│   ├── config.py                 # 👨‍💼 Người 1
│   ├── setup_database.py         # 👨‍💼 Người 1
│   ├── check_database.py         # 👨‍💼 Người 1
│   ├── README.md                 # 👨‍💼 Người 1
│   ├── data_cleaning.ipynb       # 🧹 Người 2
│   ├── analysis.ipynb            # 📊 Người 3
│   └── visualization.ipynb       # 📈 Người 4
│
├── sql/
│   ├── schema.sql                # 👨‍💼 Người 1
│   ├── queries.sql               # 👨‍💼 Người 1
│   └── README.md                 # 👨‍💼 Người 1
│
├── reports/
│   └── analysis_report.md        # 📝 Người 5
│
├── README.md                      # 📝 Người 5
└── requirements.txt               # 👨‍💼 Người 1
```

## 🎯 Nhiệm Vụ Chi Tiết

### 👨‍💼 Người 1 – Data Engineer (Trưởng nhóm)
- Thu thập dataset từ Kaggle và kiểm tra chất lượng dữ liệu ban đầu
- Thiết kế và tạo database schema (`sql/schema.sql`)
- Viết script import dữ liệu vào MySQL (`src/import_to_sql.py`, `src/config.py`)
- Tạo script setup database tự động (`src/setup_database.py`)
- Tạo script kiểm tra database (`src/check_database.py`)
- Tạo các SQL queries để extract dữ liệu (`sql/queries.sql`)
- Quản lý `requirements.txt` và dependencies
- Setup và quản lý database infrastructure
- Viết hướng dẫn database (`sql/README.md`, `src/README.md`)

### 🧹 Người 2 – Data Cleaning Specialist
- Tiền xử lý và làm sạch dữ liệu (`src/data_cleaning.ipynb`)
- Xử lý missing values (imputation, removal)
- Xử lý duplicates và outliers
- Chuẩn hóa format dữ liệu (date, numeric, categorical)
- Xử lý các giá trị bất thường và inconsistent data
- Tạo báo cáo về chất lượng dữ liệu sau khi làm sạch

### 📊 Người 3 – Data Analyst
- Phân tích thống kê mô tả (mean, median, mode, std dev)
- Phân tích phân phối dữ liệu
- Tìm các patterns và trends trong dữ liệu
- Phân tích tương quan giữa các biến
- Phát hiện các insights quan trọng từ dữ liệu
- Viết notebook phân tích chi tiết (`src/analysis.ipynb`)
- Đưa ra các nhận định và đề xuất dựa trên phân tích

### 📈 Người 4 – Data Visualization
- Tạo các biểu đồ trực quan hóa dữ liệu (`src/visualization.ipynb`)
- Sử dụng Seaborn và Matplotlib cho static charts
- Sử dụng Plotly cho interactive visualizations
- Tạo các biểu đồ: histogram, boxplot, scatter, heatmap, time series
- Thiết kế dashboard tổng hợp
- Đảm bảo các biểu đồ có ý nghĩa và dễ hiểu

### 📝 Người 5 – Report & Documentation
- Tổng hợp các kết quả từ các thành viên khác
- Viết báo cáo phân tích tổng hợp (`reports/analysis_report.md`)
- Chuẩn bị slides trình bày (nếu cần)
- Cập nhật và hoàn thiện README.md
- Viết tài liệu hướng dẫn sử dụng
- Tổng hợp và trình bày insights một cách logic và dễ hiểu
