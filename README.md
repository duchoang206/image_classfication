
# 🐶 Dog Breed Classification (Phân loại giống chó bằng Học Chuyển Giao)

![Python](https://img.shields.io/badge/python-3.8%2B-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)
![Keras](https://img.shields.io/badge/Keras-API-red.svg)
![VNU-HUS](https://img.shields.io/badge/University-VNU--HUS-green.svg)

Dự án này ứng dụng kỹ thuật **Học chuyển giao (Transfer Learning)** với kiến trúc mạng **InceptionV3** để giải quyết bài toán phân loại hình ảnh các giống chó. Đây là một phần trong lộ trình nghiên cứu về Deep Learning và Computer Vision của tôi.

---

## 📖 1. Giới thiệu tổng quan
Dự án tập trung vào việc xây dựng một hệ thống có khả năng nhận diện chính xác hàng chục giống chó khác nhau từ hình ảnh đầu vào. Bằng cách sử dụng mô hình **InceptionV3** đã được huấn luyện trước trên tập dữ liệu ImageNet, chúng tôi có thể trích xuất các đặc trưng hình ảnh phức tạp mà không cần tốn quá nhiều tài nguyên tính toán để huấn luyện lại từ đầu.

## 🛠️ 2. Công nghệ và Thuật toán áp dụng
- **Kiến trúc:** InceptionV3 (Feature Extractor) + Global Average Pooling + Dense Layers (Classifier).
- **Tối ưu hóa (Optimizer):** Thuật toán **Adam** với cơ chế điều chỉnh Learning Rate tự động (`ReduceLROnPlateau`).
- **Xử lý dữ liệu:** - Chuẩn hóa điểm ảnh (Pixel Normalization).
  - Tăng cường dữ liệu (**Data Augmentation**): CoarseDropout, RandomGamma để chống hiện tượng quá khớp (Overfitting).
- **Hàm mất mát:** `Categorical Cross-Entropy`.

## 🗂️ 3. Cấu trúc thư mục chuyên nghiệp
Dự án được tổ chức lại để dễ dàng quản lý và triển khai:

```text
📦 image_classfication
├── 📂 data/                        # Chứa dữ liệu đầu vào
│   ├── labels.csv                  # Nhãn của tập dữ liệu huấn luyện
│   └── sample_submission.csv       # File mẫu định dạng kết quả dự đoán
├── 📂 notebooks/                   # Chứa mã nguồn thực thi
│   └── main.ipynb                  # Toàn bộ quá trình EDA, Training và Evaluation
├── 📂 docs/                        # Tài liệu dự án
│   └── Bao_cao_Phan_loai_anh.pdf   # Báo cáo chi tiết về kiến trúc và toán học
└── 📜 README.md                    # Hướng dẫn tổng quan (File này)