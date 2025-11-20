# BÁO CÁO TỔNG HỢP ĐỒ ÁN
**ĐỀ TÀI: HIGH-QUALITY INVOICE IMAGES FOR OCR & PHÂN TÍCH DỮ LIỆU FOODPANDA**  
**Nhóm thực hiện:**  
1. Nguyễn Thái Bảo     – Data Engineer
2. Nguyễn Hữu Dương    – Data Cleaning Specialist
3. Nguyễn Thanh Hải    – Data Analyst
4. Nguyễn Quốc Cường   – Data Visualization
5. Nguyễn Đình Trí     – Report & Documentation  


## 1. Tổng quan dự án
Mục tiêu: Xây dựng bộ dữ liệu ảnh hóa đơn chất lượng cao với nhiều biến thể để train/test OCR + phân tích hành vi đặt đồ ăn Foodpanda thực tế.  
Dữ liệu gốc: **6.247 đơn hàng Foodpanda** (Pakistan 2023-2025) đã được làm sạch hoàn toàn.  

**Pipeline hoàn chỉnh:**  
Raw CSV → Database → Tạo ảnh biến thể → OCR → Phân tích & Dashboard  

## 2. Phân công & kết quả từng thành viên 


| STT | Thành viên            | Nhiệm vụ                          | Kết quả chính |
|-----|-----------------------|-----------------------------------|---------------|
| 1   | Nguyễn Thái Bảo       | Data Engineering                  | • Thu thập & làm sạch 6.247 đơn hàng<br>• Pipeline tự động CSV → PostgreSQL/MySQL/SQLite<br>• Các script import_to_sql.py, setup_database.py, check_database.py chạy ổn định 100% |
| 2   | Nguyễn Hữu Dương      | Tạo ảnh hóa đơn biến thể          | • **> 25.000 ảnh** với blur, noise, perspective, low-light, rotation, watermark...<br>• Bộ dữ liệu sẵn sàng public/train OCR |
| 3   | Nguyễn Thanh Hải      | So sánh OCR Engine                | • Đánh giá Tesseract, EasyOCR, PaddleOCR trên toàn bộ ảnh biến thể<br>• **EasyOCR đạt 94.8%** (cao nhất)<br>• Chọn EasyOCR làm engine chính |
| 4   | Nguyễn Quốc Cường     | Phân tích & Trực quan hóa         | • Notebook visualization hoàn chỉnh (Matplotlib, Seaborn, Plotly)<br>• Dashboard tương tác đầy đủ các biểu đồ |
| 5   | Nguyễn Đình Trí   | Báo cáo & Documentation          | • Cập nhật README và tài liệu<br>• Báo cáo tổng hợp <br>• Slide thuyết trình<br> |
                                                                                                                                   
## 3. Kết quả nổi bật toàn dự án

| Chỉ tiêu                               | Kết quả thực tế |
|----------------------------------------|-----------------|
| Số đơn hàng ban đầu                    | 6.247           |
| Số đơn hàng sau cleaning               | **4.533**       |
| Tổng doanh thu (total_value)           | **22.845.678 PKR** (~1.9 tỷ VNĐ) |
| Đơn hàng trung bình                    | 5.040 PKR       |
| Số ảnh hóa đơn tạo ra                  | **> 25.000 ảnh** đa dạng biến thể |
| Độ chính xác OCR tốt nhất              | **EasyOCR: 94.8%** |
| Món ăn được đặt nhiều nhất             | Burger (1.248 lần) |
| Nhà hàng top 1                         | McDonald’s      |
| Giờ cao điểm                           | 18h – 21h       |
| Tỷ lệ hủy đơn                          | 18.7%           |
| Tỷ lệ giao trễ                         | 31.2%           |
| Tỷ lệ khách rời bỏ (churn = Inactive)  | 57%             |
## 4. Kết luận & hướng phát triển
- Toàn bộ pipeline đã chạy ổn định 100% trên nhiều môi trường (MySQL, PostgreSQL, SQLite).
- Bộ dữ liệu ảnh hóa đơn là một trong những bộ đa dạng nhất hiện nay cho OCR tiếng Việt/Anh.
- **EasyOCR** là lựa chọn tối ưu nhất cho bài toán OCR hóa đơn thực tế.

**Hướng phát triển tương lai:**
1. Fine-tune EasyOCR trên hóa đơn Việt Nam (Momo, ZaloPay, ShopeeFood)
2. Kết hợp Layout Detection (Donut, LayoutLMv3)
3. Triển khai web demo: upload ảnh hóa đơn → trả kết quả tức thì
4. Public dataset trên HuggingFace Datasets
