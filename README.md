# Đồ án Khai thác dữ liệu và ứng dụng — Lab 1

## Mô tả dự án

Đồ án này là phần thực hành Lab 1 của môn **Khai thác dữ liệu và ứng dụng**. Mục tiêu chính:
- **Khám phá dữ liệu (EDA)** cho cả dữ liệu ảnh (image), dữ liệu bảng (tabular) và dữ liệu thời gian.
- **Tiền xử lý dữ liệu** (preprocessing) để chuẩn bị cho các phân tích hoặc mô hình tiếp theo.
- **Trực quan hoá** các phát hiện quan trọng từ dữ liệu.

Phân công công việc cụ thể của nhóm trong `docs/Report.pdf`.

---

## 📁 Cấu trúc thư mục

```
.
├── data/
│   ├── raw/                            # Thư mục để các notebooks tải dữ liệu thô
│   └── processed/                      # Thư mục để lưu các dữ liệu đã qua tiền xử lí
├── docs/
│   └── Report.pdf                      # Báo cáo chi tiết của đồ án
├── notebooks/
│   ├── 01_EDA_image.ipynb              # Khám phá dữ liệu ảnh
│   ├── 02_preprocessing_image.ipynb    # Tiền xử lý dữ liệu ảnh
│   ├── 03_EDA_tabular.ipynb            # Khám phá dữ liệu bảng
│   ├── 04_preprocessing_tabular.ipynb  # Tiền xử lý dữ liệu bảng
│   └── 06_temporal_preprocessing.ipynb # Tiền xử lý dữ liệu thời gian
├── README.md                           # Tài liệu này
└── requirements.txt                    # Cụ thể version của các thư viện
```

---

## ⚙️ Yêu cầu hệ thống

### Chạy trên Local
- **Python 3.12**
- **Jupyter Notebook** hoặc **JupyterLab**

### Chạy trên Google Colab
- Tài khoản **Google** (để truy cập Google Drive và Colab)
- Trình duyệt web hỗ trợ Colab (Chrome, Firefox, Safari, Edge, v.v.)
- Không cần cài đặt cục bộ; mọi thứ đã có sẵn trên Colab

---

## 🚀 Hướng dẫn chạy

### **Cách 1: Chạy trên Google Colab (Khuyến nghị)**

**Lý do khuyến nghị:**
- Dataset ảnh có kích thước lớn và yêu cầu tài nguyên cao (RAM, CPU/GPU).
- Colab cung cấp runtime mạnh (GPU/TPU miễn phí) và tích hợp Google Drive để lưu trữ dữ liệu.
- Không cần cài đặt thư viện cục bộ.

**Các bước:**

1. **Truy cập Google Drive:**
   - Mở link: https://drive.google.com/drive/folders/120mvzOAyvNwa2f8BWuBUFNoxExIrRcEU?usp=drive_link
   - Hoặc tải repo này lên Google Drive.

2. **Mở notebook trong Colab:**
   - Nhấp chuột phải vào file `.ipynb` → Mở với → Google Colaboratory
   - Hoặc: File → Open notebook → chọn từ Drive

3. **Chạy notebook:**
   - Chạy từng ô lần lượt (Shift+Enter) hoặc tất cả (Runtime → Run all).

---

### **Cách 2: Chạy trên Local**

**Lưu ý:** Cách này chỉ khuyến nghị nếu:
- Máy tính có đủ RAM (>8GB), ổ cứng (>20GB) và CPU mạnh.
- Hoặc chỉ chạy một phần notebook với dữ liệu mẫu nhỏ.

**Các bước:**

1. **Tạo môi trường ảo (PowerShell - Windows):**
   ```powershell
   python -m venv venv
   .\venv\Scripts\Activate.ps1
   ```

   Hoặc (Command Prompt - Windows):
   ```cmd
   python -m venv venv
   venv\Scripts\activate.bat
   ```

   Hoặc (Linux/macOS):
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

2. **Cài đặt phụ thuộc:**
   ```bash
   pip install --upgrade pip
   pip install requirements.txt
   ```

3. **Chuẩn bị dữ liệu:**
   - Tải dữ liệu từ Google Drive hoặc nguồn khác (xem `docs/Report.pdf` để biết chi tiết).
   - Tạo thư mục `data/` trong thư mục gốc và đặt dữ liệu vào đó.
   - Cập nhật đường dẫn trong notebook (thường ở ô đầu tiên).

4. **Mở Jupyter:**
   ```bash
   jupyter notebook
   ```

5. **Chạy notebook:**
   - Mở notebook từ thư mục `notebooks/`.
   - Chạy từng ô lần lượt (Shift+Enter) hoặc tất cả (Cell → Run All).

---

## 📊 Ghi chú về dữ liệu

- **Kích thước:** Dataset ảnh khá lớn (chi tiết xem trong `notebooks/01_EDA_image.ipynb ` và `notebooks/02_preprocessing_image.ipynb`).
- **Vị trí:** Dữ liệu đã processed được lưu trong `data/processed`.

---

## 📝 Thứ tự chạy các notebook

Khuyến nghị chạy theo thứ tự để tái hiện quy trình hoàn chỉnh:

1. `01_EDA_image.ipynb` — Khám phá ban đầu dữ liệu ảnh
2. `02_preprocessing_image.ipynb` — Tiền xử lý ảnh
3. `03_EDA_tabular.ipynb` — Khám phá dữ liệu bảng
4. `04_preprocessing_tabular.ipynb` — Tiền xử lý bảng
5. `06_temporal_preprocessing.ipynb` — Tiền xử lý dữ liệu thời gian

Tuy nhiên, các notebook có thể chạy độc lập nếu có dữ liệu đầu vào cần thiết.

---

## Kết quả chính

- Các phát hiện chính, biểu đồ và bảng phân tích được tóm tắt trong các markdown của chính notebook phần đó.
- Để xem chi tiết con số, hình ảnh và kết luận, chạy các notebook tương ứng.

---

## 🔗 Liên kết quan trọng

- **Google Drive (dữ liệu & Colab notebooks):** https://drive.google.com/drive/folders/120mvzOAyvNwa2f8BWuBUFNoxExIrRcEU?usp=drive_link
- **Github dành cho Lab 1:** https://github.com/thngoc17/Data-Mining---Lab-1
- **Báo cáo phân công công việc:** `docs/Report.pdf`

