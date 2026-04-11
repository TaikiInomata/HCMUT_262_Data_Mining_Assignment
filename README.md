# Bài Tập Lớn Khai Phá Dữ Liệu

## Tổng quan

Đây là sản phẩm hoàn chỉnh của nhóm cho bài tập lớn môn Khai phá dữ liệu, triển khai bài toán phân tích giỏ hàng (Market Basket Analysis - MBA) trên dữ liệu giao dịch mua sắm. Quy trình được xây dựng theo hướng có thể tái lập, bao gồm tiền xử lý dữ liệu, xây dựng ma trận giao dịch, khai phá luật kết hợp và trực quan hóa kết quả.

## Phạm vi thực hiện

- Làm sạch và chuẩn hóa dữ liệu giao dịch đầu vào.
- Chuyển dữ liệu sang dạng giao dịch và ma trận nhị phân phục vụ MBA.
- Khai phá tập phổ biến và luật kết hợp bằng Apriori và FP-Growth.
- Đánh giá kết quả theo các độ đo support, confidence và lift.
- Tổng hợp biểu đồ và kết quả để phục vụ báo cáo, thuyết trình và nộp bài.

## Kết quả đạt được

- Dữ liệu sau tiền xử lý gồm 38,006 dòng giao dịch sạch trong `groceries_cleaned.csv`.
- Ma trận giỏ hàng `basket_matrix.csv` có kích thước 14,963 x 167.
- Tập luật cuối cùng trong `association_rules_cleaned.csv` gồm 36 luật có ý nghĩa.
- FP-Growth cho thời gian xử lý tốt hơn Apriori trong bộ dữ liệu này: 0.1084 giây so với 0.3884 giây.
- Hệ thống biểu đồ đã thể hiện rõ top mặt hàng mua nhiều, phân bố kích thước giỏ hàng, phân bố luật kết hợp và mạng lưới mua chung.

## Quy trình thực hiện

1. Tiền xử lý và làm sạch dữ liệu trong `src/preprocessing_MBA.ipynb`.
2. Tạo dữ liệu đầu vào cho bài toán MBA, bao gồm danh sách giao dịch và ma trận basket.
3. Chạy khai phá luật kết hợp trong `src/algorithms_MBA.ipynb` với Apriori và FP-Growth.
4. Lọc và lưu các luật quan trọng vào `src/data/processed/association_rules_cleaned.csv`.
5. Trực quan hóa kết quả trong `src/visualization_MBA.ipynb`.

## Cấu trúc thư mục

- `src/preprocessing_MBA.ipynb`: Notebook tiền xử lý dữ liệu giao dịch.
- `src/algorithms_MBA.ipynb`: Notebook khai phá tập phổ biến và luật kết hợp.
- `src/visualization_MBA.ipynb`: Notebook trực quan hóa kết quả phân tích.
- `src/data/processed/`: Chứa dữ liệu đã xử lý, bao gồm `groceries_cleaned.csv`, `basket_matrix.csv`, `association_rules_cleaned.csv`.
- `src/artifacts/`: Chứa các tệp trung gian phục vụ pipeline.
- `src/reports/metrics/`: Chứa số liệu đánh giá thực nghiệm, ví dụ `performance_metrics.json`.
- `src/reports/figures/`: Chứa các biểu đồ đầu ra của project.
- `requirements.txt`: Danh sách thư viện Python cần cài đặt.

## Môi trường cài đặt

### Yêu cầu

- Python 3.10 trở lên, khuyến nghị Python 3.11 hoặc mới hơn.
- File `requirements.txt` ở thư mục gốc dự án.

### Tạo và kích hoạt môi trường ảo

Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

Nếu hệ thống chặn script lần đầu:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

Windows Command Prompt:

```bat
.venv\Scripts\activate.bat
```

macOS/Linux:

```bash
source .venv/bin/activate
```

### Cài đặt thư viện

```powershell
pip install -r requirements.txt
```

### Kiểm tra môi trường

```powershell
python --version
pip --version
```

Nếu hai lệnh trên trả về đường dẫn trong `.venv`, môi trường đã sẵn sàng sử dụng.

## Hướng dẫn chạy lại

1. Mở và chạy toàn bộ `src/preprocessing_MBA.ipynb` để tái tạo dữ liệu đã làm sạch.
2. Mở và chạy `src/algorithms_MBA.ipynb` để khai phá luật kết hợp và xuất kết quả.
3. Mở và chạy `src/visualization_MBA.ipynb` để sinh lại các biểu đồ minh họa.
4. Sử dụng các tệp trong `src/data/processed/` và `src/reports/figures/` cho báo cáo cuối cùng.

## Kết luận

Project đã hoàn tất đầy đủ pipeline Market Basket Analysis cho bài tập lớn, từ làm sạch dữ liệu đến khai phá và trực quan hóa kết quả. Các tệp đầu ra và biểu đồ đã sẵn sàng cho việc nộp bài và thuyết trình nhóm.
