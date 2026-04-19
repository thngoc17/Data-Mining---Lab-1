# Đồ án Khai thác dữ liệu và ứng dụng — Lab 1

## 📋 Mô tả dự án

Đồ án này là phần thực hành Lab 1 của môn **Khai thác dữ liệu**. Mục tiêu chính:
- **Khám phá dữ liệu (EDA)** cho cả dữ liệu ảnh (image) và dữ liệu bảng (tabular).
- **Tiền xử lý dữ liệu** (preprocessing) để chuẩn bị cho các phân tích hoặc mô hình tiếp theo.
- **Trực quan hoá** các phát hiện quan trọng từ dữ liệu.

Báo cáo chi tiết về mục tiêu, phương pháp, kết quả và kết luận nằm trong `docs/Report.pdf`.

---

## 📁 Cấu trúc thư mục

```
.
├── docs/
│   └── Report.pdf                      # Báo cáo chi tiết của đồ án
├── notebooks/
│   ├── 01_EDA_image.ipynb              # Khám phá dữ liệu ảnh
│   ├── 02_preprocessing_image.ipynb    # Tiền xử lý dữ liệu ảnh
│   ├── 03_EDA_tabular.ipynb            # Khám phá dữ liệu bảng
│   ├── 04_preprocessing_tabular.ipynb  # Tiền xử lý dữ liệu bảng
│   └── 06_temporal_preprocessing.ipynb # Tiền xử lý dữ liệu thời gian
└── README.md                            # Tài liệu này
```

---

## ⚙️ Yêu cầu hệ thống

### Chạy trên Local
- **Python 3.12+** (phiên bản cao hơn cũng được hỗ trợ)
- **Jupyter Notebook** hoặc **JupyterLab**
- Các thư viện Python: `numpy`, `pandas`, `matplotlib`, `seaborn`, `scikit-learn`

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
- Không cần cài đặt phần mềm cục bộ.

**Các bước:**

1. **Truy cập Google Drive:**
   - Mở link: https://drive.google.com/drive/folders/120mvzOAyvNwa2f8BWuBUFNoxExIrRcEU?usp=drive_link
   - Hoặc tải repo này lên Google Drive của bạn.

2. **Mở notebook trong Colab:**
   - Nhấp chuột phải vào file `.ipynb` → Mở với → Google Colaboratory
   - Hoặc: File → Open notebook → chọn từ Drive

3. **Mount Google Drive** (nếu dữ liệu nằm trên Drive):
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```
   - Chạy ô này ở đầu notebook để mount Drive.

4. **Cài đặt phụ thuộc** (nếu cần):
   ```python
   !pip install numpy pandas matplotlib seaborn scikit-learn
   ```
   - Hoặc các thư viện khác được sử dụng trong notebook.

5. **Cập nhật đường dẫn dữ liệu:**
   - Sửa đường dẫn trong notebook để trỏ đến vị trí dữ liệu trên Drive (thường là `/content/drive/My Drive/...`).

6. **Chọn runtime (tùy chọn):**
   - Runtime → Change runtime type → T4 GPU (nếu notebook cần xử lý ảnh nặng hoặc đào tạo mô hình).

7. **Chạy notebook:**
   - Chạy từng ô lần lượt (Shift+Enter) hoặc tất cả (Runtime → Run all).

---

### **Cách 2: Chạy trên Local**

**Lưu ý:** Cách này chỉ khuyến nghị nếu:
- Máy tính có đủ RAM (>8GB), ổ cứng (>20GB) và CPU mạnh.
- Hoặc bạn chỉ chạy một phần notebook với dữ liệu mẫu nhỏ.

**Các bước:**

1. **Clone hoặc tải repo:**
   ```bash
   git clone https://github.com/thngoc17/Data-Mining---Lab-1.git
   cd "Data Mining - Lab 1"
   ```

2. **Tạo môi trường ảo (PowerShell - Windows):**
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

3. **Cài đặt phụ thuộc:**
   ```bash
   pip install --upgrade pip
   pip install requirements.txt
   ```

4. **Chuẩn bị dữ liệu:**
   - Tải dữ liệu từ Google Drive hoặc nguồn khác (xem `docs/Report.pdf` để biết chi tiết).
   - Tạo thư mục `data/` trong thư mục gốc và đặt dữ liệu vào đó.
   - Cập nhật đường dẫn trong notebook (thường ở ô đầu tiên).

5. **Mở Jupyter:**
   ```bash
   jupyter notebook
   ```

6. **Chạy notebook:**
   - Mở notebook từ thư mục `notebooks/`.
   - Chạy từng ô lần lượt (Shift+Enter) hoặc tất cả (Cell → Run All).

---

## 📊 Ghi chú về dữ liệu

- **Kích thước:** Dataset ảnh khá lớn (chi tiết xem trong `docs/Report.pdf`).
- **Vị trí:** Dữ liệu được lưu trên **Google Drive** hoặc cung cấp qua link riêng (xem báo cáo).
- **Không có thư mục `data/` cục bộ:** Vì kích thước dữ liệu lớn, nên ưu tiên xử lý trực tiếp trên Colab/Drive thay vì lưu cục bộ.

Chi tiết cách truy cập dữ liệu và hướng dẫn mount Drive được nêu trong `docs/Report.pdf`.

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

## 📖 Kết quả chính

- Các phát hiện chính, biểu đồ và bảng phân tích được tóm tắt trong **`docs/Report.pdf`**.
- Để xem chi tiết con số, hình ảnh và kết luận, mở báo cáo hoặc chạy các notebook tương ứng.

---

## 🔗 Liên kết quan trọng

- **Google Drive (dữ liệu & Colab notebooks):** https://drive.google.com/drive/folders/120mvzOAyvNwa2f8BWuBUFNoxExIrRcEU?usp=drive_link
- **Báo cáo chi tiết:** `docs/Report.pdf`

