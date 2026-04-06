# Bài Tập Lớn Khai Phá Dữ Liệu (Data Mining Assignment)

## 1. Giới thiệu

Repository này phục vụ bài tập lớn môn Khai phá dữ liệu, tập trung vào bài toán phân tích giỏ hàng (Market Basket Analysis - MBA) từ dữ liệu giao dịch mua sắm.

## 2. Mục tiêu Assignment

- Thực hiện tiền xử lý dữ liệu giao dịch.
- Áp dụng thuật toán khai phá luật kết hợp để tìm tập phổ biến và luật kết hợp.
- Đánh giá và diễn giải kết quả theo các độ đo như support, confidence, lift.
- Tổng hợp kết quả thành notebook và báo cáo phục vụ thuyết trình nhóm.

## 3. Cấu trúc thư mục

- `src/preprocessing_MBA.ipynb`: Notebook tiền xử lý dữ liệu.
- `src/algorithms_MBA.ipynb`: Notebook áp dụng thuật toán khai phá luật kết hợp.
- `src/visualization_MBA.ipynb`: Notebook trực quan hóa kết quả.
- `src/data/processed/`: Chứa dữ liệu đã xử lý (`groceries_cleaned.csv`, `basket_matrix.csv`, `association_rules_cleaned.csv`, ...).
- `src/artifacts/`: Chứa artifact trung gian (ví dụ `transactions_list.pkl`).
- `src/reports/metrics/`: Chứa chỉ số thực nghiệm (`performance_metrics.json`).
- `src/reports/figures/`: Chứa biểu đồ đầu ra (`*.png`).
- `requirements.txt`: Danh sách thư viện Python.

## 4. Hướng dẫn cài đặt môi trường .venv

### 4.1. Điều kiện cần

- Đã cài Python 3.10+ (khuyến nghị 3.11).
- Có sẵn file `requirements.txt` trong thư mục gốc dự án.

### 4.2. Tạo môi trường ảo

Chạy lệnh tại thư mục gốc dự án:

```powershell
python -m venv .venv
```

### 4.3. Kích hoạt môi trường ảo

Windows (PowerShell):

```powershell
.\.venv\Scripts\Activate.ps1
```

Nếu bị chặn script, chạy một lần:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

Windows (Command Prompt):

```bat
.venv\Scripts\activate.bat
```

macOS/Linux:

```bash
source .venv/bin/activate
```

### 4.4. Cài thư viện

Sau khi kích hoạt `.venv`, chạy:

```powershell
pip install -r requirements.txt
```

### 4.5. Kiểm tra môi trường

```powershell
python --version
pip --version
```

Nếu đường dẫn Python/Pip trỏ về thư mục `.venv` thì môi trường đã hoạt động đúng.

### 4.6. Thoát môi trường ảo

```powershell
deactivate
```

## 5. Quy trình thực hiện gợi ý

1. Chạy notebook `src/preprocessing_MBA.ipynb` để chuẩn hóa và làm sạch dữ liệu.
2. Chạy notebook `src/algorithms_MBA.ipynb` để khai phá tập phổ biến và luật kết hợp.
3. Lọc các luật có ý nghĩa theo ngưỡng support/confidence/lift.
4. Tổng hợp kết quả cho phần báo cáo và trình bày.

## 6. Đầu ra kỳ vọng

- Dataset đã làm sạch và ma trận giao dịch.
- Danh sách luật kết hợp có ý nghĩa thực tiễn.
- Notebook thể hiện đầy đủ quy trình tiền xử lý và khai phá.
