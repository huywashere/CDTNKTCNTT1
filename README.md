# 🎣 Phishing Website Detection (Phát hiện Website Lừa đảo)

Dự án này thuộc đồ án **Chuyên đề tốt nghiệp KTCNTT 1 - Nhóm 22**.
Mục tiêu của dự án là xây dựng một mô hình Học máy (Machine Learning) có khả năng phân loại các URL là hợp pháp (Legitimate) hay lừa đảo (Phishing) dựa trên các đặc trưng được trích xuất từ URL đó.  

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Sklearn](https://img.shields.io/badge/Library-ScikitLearn-yellow)
![XGBoost](https://img.shields.io/badge/Model-XGBoost-green)

## 📂 Cấu trúc Dự án

Dưới đây là mô tả các file quan trọng trong repository:

* **`DataFiles/`**: Thư mục chứa các file dữ liệu (dataset) dùng để train và test (ví dụ: `5.urldata.csv`).
* **`URLFeatureExtraction.py`**: File mã nguồn Python chứa các hàm để trích xuất đặc trưng (feature) từ một đường link URL thô (ví dụ: kiểm tra độ dài, kiểm tra IP, check DNS...).
* **`URL Feature Extraction.ipynb`**: Notebook minh họa chi tiết quy trình xử lý và trích xuất đặc trưng.
* **`Phishing Website Detection_Nhom22.ipynb`**: **File chính**. Chứa toàn bộ quy trình từ tiền xử lý dữ liệu, trực quan hóa (EDA), huấn luyện nhiều mô hình (Decision Tree, Random Forest, XGBoost, SVM...) và đánh giá kết quả.
* **`XGBoostClassifier.pickle.dat`**: File mô hình đã được huấn luyện xong và lưu lại (Pre-trained model). Có thể dùng để dự đoán ngay mà không cần train lại.

---

## 🛠 Hướng dẫn Cài đặt (Installation)

Để chạy được dự án này trên máy cục bộ (Local), bạn cần cài đặt Python và các thư viện cần thiết.

### 1. Clone dự án

```bash
git clone https://github.com/huywashere/CDTNKTCNTT1.git
cd CDTNKTCNTT1
```

### 2. Cài đặt thư viện (Dependencies)

Để đảm bảo code chạy mượt mà, bạn cần cài đặt các thư viện Python sau. Mở terminal (hoặc Command Prompt) tại thư mục dự án và chạy lệnh:

```bash
pip install pandas numpy seaborn matplotlib scikit-learn xgboost python-whois beautifulsoup4 requests
```

Giải thích các thư viện chính:

* **pandas, numpy**: Xử lý dữ liệu dạng bảng và ma trận.
* **seaborn, matplotlib**: Vẽ biểu đồ trực quan hóa dữ liệu.
* **scikit-learn**: Cung cấp các thuật toán Machine Learning cơ bản (Decision Tree, SVM, RandomForest...).
* **xgboost**: Thư viện thuật toán XGBoost (Gradient Boosting) hiệu năng cao.
* **python-whois, beautifulsoup4**: Dùng để trích xuất thông tin từ URL (domain age, HTML content...).

---

## 🚀 Hướng dẫn Huấn luyện AI (Training Guide)

Bạn có thể huấn luyện mô hình theo 2 cách: sử dụng Google Colab (khuyên dùng nếu máy yếu) hoặc chạy Local (trên máy tính cá nhân).

### Cách 1: Chạy trên Google Colab (Khuyên dùng)

1. Truy cập [Google Colab](https://colab.research.google.com/).

2. Chọn **File > Upload notebook** và tải lên file `Phishing Website Detection_Nhom22.ipynb`.

3. **Quan trọng - Tải dữ liệu**:
   - Nhìn sang thanh menu bên trái, bấm vào biểu tượng thư mục 📁 (Files).
   - Bấm chuột phải chọn **New Folder**, đặt tên là `DataFiles`.
   - Vào thư mục `DataFiles` vừa tạo, tải file `5.urldata.csv` từ máy tính lên.

4. **Kiểm tra đường dẫn**:
   - Tìm đến dòng code đọc dữ liệu trong notebook:

```python
# Đảm bảo đường dẫn trỏ đúng vào nơi bạn vừa upload file
data0 = pd.read_csv('DataFiles/5.urldata.csv')
```

5. Trên thanh menu, chọn **Runtime > Run all** (hoặc Chạy tất cả) để bắt đầu quá trình huấn luyện từ đầu đến cuối.

### Cách 2: Chạy trên máy cá nhân (Local)

1. Mở terminal tại thư mục dự án (`CDTNKTCNTT1`).

2. Khởi động Jupyter Notebook:

```bash
jupyter notebook
```

3. Trình duyệt sẽ tự mở lên, bạn click chọn file `Phishing Website Detection_Nhom22.ipynb`.

4. Trên thanh công cụ, chọn **Cell > Run All** để chạy toàn bộ dự án.

---

## 🧠 Quy trình Huấn luyện (Training Process)

Khi bạn chạy file Notebook, hệ thống sẽ thực hiện các bước sau:

1. **Load Data**: Đọc dữ liệu từ file `5.urldata.csv`.

2. **EDA (Exploratory Data Analysis)**: Vẽ biểu đồ nhiệt (Heatmap), biểu đồ phân phối để hiểu dữ liệu.

3. **Preprocessing**: Làm sạch dữ liệu, loại bỏ cột không cần thiết (Domain), chia tập dữ liệu thành Train (80%) và Test (20%).

4. **Model Training & Evaluation**: Huấn luyện và đánh giá độ chính xác của các thuật toán:
   - Decision Tree
   - Random Forest
   - XGBoost (Best Model)

5. **Save Model**: Mô hình tốt nhất (XGBoost) sẽ được lưu vào file `XGBoostClassifier.pickle.dat`.

---

## 📊 Kết quả

Mô hình XGBoost đạt được độ chính xác cao nhất trong việc phát hiện website lừa đảo lên tới 86,4%. File model đã được lưu sẵn để sử dụng trực tiếp mà không cần huấn luyện lại.

---

## 📝 License

Dự án này được thực hiện cho mục đích học tập và nghiên cứu.

---

## 👥 Tác giả

- **Nguyễn Phú Huy**
- **Võ Nhật Anh**

**Nhóm 22 - Chuyên đề tốt nghiệp KTCNTT 1**
