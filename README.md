# Dự đoán Khả năng Thành công của Startup

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

## 1. Giới thiệu

Dự án này xây dựng và so sánh các mô hình học máy (Machine Learning) và học sâu (Deep Learning) nhằm dự báo khả năng thành công của một công ty khởi nghiệp. "Thành công" được định nghĩa là việc công ty thực hiện IPO hoặc được một công ty khác mua lại.

Dữ liệu được sử dụng là bộ dữ liệu công khai **Crunchbase 2013 Snapshot**, chứa thông tin về các công ty, các vòng gọi vốn, đội ngũ sáng lập và các cột mốc quan trọng.

## 2. Cấu trúc Thư mục

```
startup-prediction/
├── .gitignore
├── LICENSE
├── README.md
├── requirements.txt
├── data/
│   └── README.md  <-- (Giải thích cách tải dữ liệu)
└── notebooks/
    └── Startup_prediction.ipynb
```

## 3. Dữ liệu

Bộ dữ liệu **Crunchbase 2013 Snapshot** được sử dụng cho dự án này. Do kích thước lớn, dữ liệu không được đưa trực tiếp vào repository này.

Bạn có thể tải bộ dữ liệu từ [Kaggle: Crunchbase 2013](https://www.kaggle.com/datasets/arindam235/crunchbase-2013) và đặt các file `.csv` vào thư mục `data/`.

## 4. Cài đặt

Để chạy được notebook của dự án, bạn cần cài đặt các thư viện cần thiết. Khuyến khích sử dụng môi trường ảo (virtual environment).

**Yêu cầu:**
*   Python 3.8+
*   pip

**Các bước cài đặt:**

1.  **Clone repository này về máy:**
    ```bash
    git clone <URL_CUA_REPOSITORY>
    cd startup-prediction
    ```

2.  **Tạo và kích hoạt môi trường ảo:**
    *   Trên macOS/Linux:
        ```bash
        python3 -m venv env
        source env/bin/activate
        ```
    *   Trên Windows:
        ```bash
        python -m venv env
        .\env\Scripts\activate
        ```

3.  **Cài đặt các thư viện:**
    ```bash
    pip install -r requirements.txt
    ```

## 5. Sử dụng

Sau khi đã cài đặt xong, bạn có thể khởi chạy Jupyter Notebook để xem và chạy lại quy trình phân tích:

```bash
jupyter notebook notebooks/Startup_prediction.ipynb
```

## 6. Quy trình Thực hiện

Dự án được thực hiện theo các bước chuẩn của một quy trình khoa học dữ liệu:

1.  **Thu thập & Tiền xử lý Dữ liệu:** Tổng hợp dữ liệu từ nhiều file, làm sạch và định nghĩa biến mục tiêu.
2.  **Phân tích Khám phá Dữ liệu (EDA):** Sử dụng các biểu đồ trực quan để hiểu sâu về đặc điểm dữ liệu, sự mất cân bằng và mối quan hệ giữa các biến.
3.  **Kiến tạo Đặc trưng (Feature Engineering):** Tạo ra các biến số mới có ý nghĩa (tuổi công ty, tốc độ gọi vốn, v.v.) để tăng hiệu quả cho mô hình.
4.  **Mô hình hóa:** Xây dựng và so sánh hiệu năng của 4 mô hình khác nhau:
    *   MLP (Multi-Layer Perceptron)
    *   XGBoost
    *   1D-CNN (Convolutional Neural Network)
    *   LSTM (Long Short-Term Memory)
5.  **Đánh giá:** Sử dụng phương pháp **Stratified K-Fold Cross-Validation** (K=5) để đánh giá một cách khách quan và đáng tin cậy. Độ đo chính là **ROC AUC**.

## 7. Kết quả

Dựa trên kết quả đánh giá chéo 5-fold, mô hình **XGBoost** cho hiệu năng tốt nhất với điểm **ROC AUC trung bình là 0.845**.

| Mô hình | Mean AUC | Std Dev |
|---------|----------|---------|
| XGBoost | 0.8448   | 0.0034  |
| MLP     | 0.8365   | 0.0044  |
| CNN     | 0.8044   | 0.0050  |
| LSTM    | 0.7809   | 0.0068  |

Phân tích sâu hơn cho thấy mô hình có xu hướng "thà bắt nhầm còn hơn bỏ sót" (Recall cao, Precision thấp cho lớp "Thành công"). Việc **tinh chỉnh ngưỡng quyết định (threshold tuning)** đã được thực hiện để tìm ra điểm cân bằng tốt hơn cho bài toán thực tế.

## 8. Giấy phép

Dự án này được cấp phép theo Giấy phép MIT. Xem chi tiết tại file `LICENSE`.