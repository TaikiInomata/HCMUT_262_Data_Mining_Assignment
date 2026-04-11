# Bài Tập Lớn Khai Phá Dữ Liệu

## Tổng quan

Repository này là sản phẩm hoàn chỉnh của nhóm cho bài tập lớn môn Khai phá dữ liệu, tập trung vào bài toán phân tích giỏ hàng (Market Basket Analysis - MBA) trên dữ liệu giao dịch mua sắm. Toàn bộ quy trình đã được triển khai theo hướng có thể tái lập, từ làm sạch dữ liệu, xây dựng ma trận giao dịch, khai phá luật kết hợp cho đến trực quan hóa và tổng hợp kết quả.

## Mục tiêu thực hiện

- Chuẩn hóa và làm sạch dữ liệu giao dịch để phục vụ khai phá dữ liệu.
- Chuyển dữ liệu sang dạng giao dịch và ma trận nhị phân cho bài toán MBA.
- Khai phá tập phổ biến và luật kết hợp bằng các thuật toán tiêu biểu.
- Đánh giá kết quả bằng các độ đo support, confidence và lift.
- Trực quan hóa xu hướng mua chung để phục vụ báo cáo và thuyết trình.

## Kết quả chính

- Dữ liệu sau tiền xử lý gồm 38,006 dòng giao dịch sạch trong `groceries_cleaned.csv`.
- Ma trận giỏ hàng `basket_matrix.csv` có kích thước 14,963 x 167, phù hợp cho khai phá luật kết hợp.
- Tập luật cuối cùng trong `association_rules_cleaned.csv` gồm 36 luật có ý nghĩa theo các ngưỡng đã chọn.
- So sánh tốc độ cho thấy FP-Growth chạy nhanh hơn Apriori trong bộ dữ liệu này: 0.1084 giây so với 0.3884 giây.
- Các biểu đồ đầu ra đã thể hiện được top mặt hàng mua nhiều, phân bố kích thước giỏ hàng, phân bố luật kết hợp và mạng lưới mua chung.

## Quy trình thực hiện

1. Tiền xử lý dữ liệu trong `src/preprocessing_MBA.ipynb`.
2. Tạo dữ liệu đầu vào cho MBA, gồm danh sách giao dịch và ma trận basket.
3. Chạy khai phá luật kết hợp trong `src/algorithms_MBA.ipynb` với Apriori và FP-Growth.
4. Lọc, đánh giá và lưu các luật quan trọng vào `src/data/processed/association_rules_cleaned.csv`.
5. Trực quan hóa kết quả trong `src/visualization_MBA.ipynb`.

## Cấu trúc thư mục

- `src/preprocessing_MBA.ipynb`: Notebook tiền xử lý dữ liệu giao dịch.
- `src/algorithms_MBA.ipynb`: Notebook khai phá tập phổ biến và luật kết hợp.
- `src/visualization_MBA.ipynb`: Notebook trực quan hóa kết quả phân tích.
- `src/data/processed/`: Chứa dữ liệu đã xử lý, gồm `groceries_cleaned.csv`, `basket_matrix.csv`, `association_rules_cleaned.csv`.
- `src/artifacts/`: Chứa các artifact trung gian phục vụ pipeline.
- `src/reports/metrics/`: Chứa số liệu đánh giá thực nghiệm, ví dụ `performance_metrics.json`.
- `src/reports/figures/`: Chứa biểu đồ đầu ra của project.
- `requirements.txt`: Danh sách thư viện Python cần cài.

## Môi trường cài đặt

### Yêu cầu

- Python 3.10 trở lên, khuyến nghị Python 3.11 hoặc mới hơn.
- Có file `requirements.txt` ở thư mục gốc.

### Tạo và kích hoạt môi trường ảo

Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

Nếu máy chặn script lần đầu:

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

### Cài thư viện

Sau khi kích hoạt môi trường ảo:

```powershell
pip install -r requirements.txt
```

### Kiểm tra môi trường

```powershell
python --version
pip --version
```

Nếu hai lệnh trên trả về đường dẫn trong `.venv` thì môi trường đã sẵn sàng.

## Cách chạy lại project

1. Mở `src/preprocessing_MBA.ipynb` và chạy toàn bộ notebook để tái tạo dữ liệu đã làm sạch.
2. Mở `src/algorithms_MBA.ipynb` để chạy khai phá luật kết hợp và tạo file kết quả.
3. Mở `src/visualization_MBA.ipynb` để sinh lại các biểu đồ và hình minh họa.
4. Dùng các file trong `src/data/processed/` và `src/reports/figures/` cho báo cáo cuối cùng.

## Kết luận

Project đã hoàn thành đầy đủ pipeline Market Basket Analysis cho bài tập lớn: từ làm sạch dữ liệu, tạo basket matrix, khai phá luật kết hợp đến trực quan hóa và so sánh thuật toán. Bộ dữ liệu đầu ra và biểu đồ đã sẵn sàng để nộp thầy và dùng cho phần thuyết trình nhóm.
