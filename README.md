# Startup Screening for Venture Capital

This project applies Deep Learning and Machine Learning models to build a robust system for screening and predicting the success potential of startups. The solution is designed to tackle the challenge of massive deal flow faced by Venture Capital (VC) firms, using VinaCapital Ventures (VCV) as a case study.

## 1. The Problem & The Challenge

In a thriving startup ecosystem, VC firms often face the "drinking from a firehose" problem—processing thousands of investment proposals annually. The traditional manual screening process is not only time-consuming and resource-intensive but also prone to risks like:

*   **Opportunity Cost:** Valuable analyst time is spent on eliminating low-potential companies instead of conducting deep due diligence on promising ones.
*   **Cognitive Bias:** Subjective judgments can lead to overlooking unconventional but high-potential "hidden gems."
*   **Scalability Issues:** Manual processes struggle to keep pace with an ever-increasing deal flow.

This project was built to answer the strategic question: *"How can we empower the investment team to work more efficiently, make faster data-driven decisions, and minimize the risk of missing out on the next unicorn?"*

## 2. Project Objectives

*   **Develop & Evaluate:** Build and systematically compare the performance of a **Wide & Deep** model (integrating Entity Embeddings and Focal Loss) against a powerful **XGBoost** baseline.
*   **Implement Practical Tools:** Deploy the optimal model to create decision-support tools, including:
    1.  An **Intelligent Deal Funnel** to automatically classify and prioritize potential startups.
    2.  An **Automated Investment Memo Generator** to produce preliminary analysis, highlight strengths and weaknesses, and suggest due diligence questions.
    3.  A **Strategic Industry Analysis** tool using embeddings to visualize the startup landscape.

## 3. Project Structure

```
.
├── data/
│   ├── objects.csv
│   ├── funding_rounds.csv
│   ├── ipos.csv
│   ├── acquisitions.csv
│   ├── relationships.csv
│   ├── milestones.csv
│   ├── investments.csv
│   ├── funds.csv
│   └── degrees.csv
├── notebooks/
│   └── Startup_prediction.ipynb
├── .gitignore
├── README.md
└── requirements.txt
```

*   `data/`: Contains the raw Crunchbase dataset files.
*   `notebooks/`: Contains the `Startup_prediction.ipynb` Jupyter Notebook with all analysis and modeling code.
*   `.gitignore`: Specifies files and directories to be ignored by Git.
*   `README.md`: This file.
*   `requirements.txt`: A list of Python dependencies required to run the project.

## 4. Methodology / Workflow

The `Startup_prediction.ipynb` notebook is organized into the following key sections:

*   **Part 0: Environment Setup:** Imports necessary libraries and sets up configurations.
*   **Part 1: Data Loading & Feature Engineering:** Loads the dataset and creates meaningful features (e.g., company age, funding velocity, founder experience, investor quality).
*   **Part 2: Exploratory Data Analysis (EDA):** Investigates data distributions and relationships to gain initial insights.
*   **Part 3: Data Preparation for Modeling:** Splits and preprocesses the data for the Wide & Deep architecture.
*   **Part 4: Wide & Deep Model Architecture:** Defines the model, using Entity Embeddings for categorical features and Focal Loss to handle severe class imbalance.
*   **Part 5: Model Training & Evaluation:** Trains the model, evaluates its performance using metrics (Precision, Recall, F1-score, AUC), and compares it against the XGBoost baseline.
*   **Part 6: Applications for VC:** Demonstrates the practical, value-added applications of the final model.

## 5. Installation and Usage

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/[YourUsername]/[YourRepositoryName].git
    cd [YourRepositoryName]
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3.  **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the Notebook:**
    Launch Jupyter Notebook or Jupyter Lab and open the `notebooks/Startup_prediction.ipynb` file.
    ```bash
    jupyter notebook
    ```
    *Note: Ensure the file paths to the `data/` directory are correctly specified within the notebook.*

## 6. Key Results

The final Wide & Deep model provides a significant efficiency gain. By focusing on the **top 20% of startups** as ranked by the model, an investment team can identify nearly **70% of all future successful companies**. This allows for a massive reduction in manual screening workload while maximizing the chances of discovering high-potential investment opportunities.
---
# Sàng lọc Startup cho Quỹ Đầu tư Mạo hiểm

Dự án này ứng dụng các mô hình Học Sâu (Deep Learning) và Học Máy (Machine Learning) để xây dựng một hệ thống sàng lọc và đánh giá tiềm năng thành công của các công ty khởi nghiệp. Giải pháp được thiết kế để giải quyết bài toán xử lý dòng chảy thương vụ (deal flow) khổng lồ cho các quỹ đầu tư mạo hiểm như VinaCapital Ventures (VCV).

## 1. Bối cảnh & Thách thức

Trong bối cảnh hệ sinh thái khởi nghiệp phát triển mạnh mẽ, các quỹ đầu tư mạo hiểm phải đối mặt với thách thức xử lý hàng ngàn hồ sơ đầu tư mỗi năm. Quy trình sàng lọc thủ công không chỉ tốn kém thời gian, nguồn lực mà còn tiềm ẩn rủi ro bỏ lỡ các cơ hội tiềm năng do thiên kiến chủ quan.

Dự án này được xây dựng để trả lời câu hỏi: *"Làm thế nào chúng ta có thể giúp đội ngũ đầu tư làm việc hiệu quả hơn, ra quyết định dựa trên dữ liệu nhanh hơn và giảm thiểu rủi ro bỏ lọt các cơ hội đầu tư triển vọng?"*

## 2. Mục tiêu

*   **Xây dựng & Đánh giá:** Phát triển và so sánh hiệu năng giữa mô hình học sâu **Wide & Deep** (tích hợp Entity Embedding và Focal Loss) và mô hình nền tảng **XGBoost**.
*   **Ứng dụng thực tiễn:** Triển khai mô hình tối ưu để xây dựng các công cụ hỗ trợ ra quyết định, bao gồm:
    1.  **Phễu Sàng lọc Deal Thông minh:** Tự động phân loại và ưu tiên các startup tiềm năng.
    2.  **Báo cáo Tóm tắt Đầu tư Tự động:** Tạo các bản ghi nhớ đầu tư sơ bộ, nêu bật điểm mạnh, rủi ro và gợi ý câu hỏi thẩm định.
    3.  **Phân tích Chiến lược Ngành:** Trực quan hóa không gian các ngành để tìm ra các cụm và xu hướng đầu tư.

## 3. Cấu trúc Dự án

```
.
├── data/
│   ├── objects.csv
│   ├── funding_rounds.csv
│   ├── ipos.csv
│   ├── acquisitions.csv
│   ├── relationships.csv
│   ├── milestones.csv
│   ├── investments.csv
│   ├── funds.csv
│   └── degrees.csv
├── notebooks/
│   └── Startup_prediction.ipynb
├── .gitignore
├── README.md
└── requirements.txt
```

*   `data/`: Thư mục chứa các file dữ liệu thô từ Crunchbase.
*   `notebooks/`: Chứa file Jupyter Notebook/Colab `Startup_prediction.ipynb` với toàn bộ mã nguồn phân tích và xây dựng mô hình.
*   `.gitignore`: Chỉ định các file và thư mục cần bỏ qua khi đưa lên Git.
*   `README.md`: File bạn đang đọc.
*   `requirements.txt`: Danh sách các thư viện Python cần thiết để chạy dự án.

## 4. Quy trình thực hiện

File `Startup_prediction.ipynb` bao gồm các phần chính sau:

*   **Phần 0: Thiết lập Môi trường:** Import thư viện và cấu hình cần thiết.
*   **Phần 1: Tải và Feature Engineering:** Tải dữ liệu và tạo ra các đặc trưng có ý nghĩa (ví dụ: tuổi công ty, tốc độ gọi vốn, kinh nghiệm nhà sáng lập).
*   **Phần 2: Phân tích Khám phá Dữ liệu (EDA):** Khám phá các mối quan hệ trong dữ liệu để có những hiểu biết ban đầu.
*   **Phần 3: Chuẩn bị Dữ liệu cho Mô hình:** Tách và chuẩn hóa dữ liệu cho các luồng Wide & Deep.
*   **Phần 4: Xây dựng Mô hình Wide & Deep:** Định nghĩa kiến trúc mô hình, sử dụng Embedding cho biến phân loại và Focal Loss để xử lý mất cân bằng.
*   **Phần 5: Huấn luyện và Đánh giá:** Huấn luyện mô hình, đánh giá hiệu năng qua các chỉ số (Precision, Recall, F1, AUC) và so sánh với mô hình XGBoost.
*   **Phần 6: Ứng dụng cho VCV:** Trình bày các ứng dụng thực tiễn của mô hình đã xây dựng.

## 5. Hướng dẫn cài đặt và sử dụng

1.  **Clone repository:**
    ```bash
    git clone https://github.com/[YourUsername]/[YourRepositoryName].git
    cd [YourRepositoryName]
    ```

2.  **Tạo môi trường ảo (khuyến nghị):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # Trên Windows: venv\Scripts\activate
    ```

3.  **Cài đặt các thư viện cần thiết:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Chạy Notebook:**
    Mở Jupyter Notebook hoặc Jupyter Lab và chạy file `notebooks/Startup_prediction.ipynb`.
    ```bash
    jupyter notebook
    ```
    *Lưu ý: Đảm bảo rằng đường dẫn đến thư mục `data/` trong notebook là chính xác.*

## 6. Kết quả chính

Mô hình Wide & Deep cho phép **tập trung vào 20% startup tiềm năng nhất** nhưng có thể **xác định được gần 70% tổng số các startup thành công**, giúp giảm đáng kể khối lượng công việc sàng lọc thủ công và tăng hiệu quả cho đội ngũ đầu tư.