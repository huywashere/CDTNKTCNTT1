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
git clone [https://github.com/huywashere/CDTNKTCNTT1.git](https://github.com/huywashere/CDTNKTCNTT1.git)
cd CDTNKTCNTT1
