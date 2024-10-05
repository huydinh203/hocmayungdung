# Machine Learning 

## 1. Công nghệ sử dụng

Trong dự án này, các công nghệ và thư viện chính được dùng để xây dựng và triển khai mô hình phân loại:

- **Python**: Ngôn ngữ lập trình chính cho dự án.
- **NumPy**: Thư viện tính toán số học cho các mảng và ma trận lớn.
- **Pandas**: Thư viện quản lý và phân tích dữ liệu, hỗ trợ thao tác với dữ liệu dạng bảng.
- **Scikit-learn (sklearn)**: Thư viện học máy phổ biến cung cấp các thuật toán huấn luyện mô hình, chuẩn hóa dữ liệu, chia tập dữ liệu và đánh giá hiệu suất.
  - Các module: `train_test_split`, `ConfusionMatrixDisplay`, `accuracy_score`, v.v.
- **Matplotlib** và **Seaborn**: Các thư viện trực quan hóa dữ liệu, sử dụng để hiển thị các biểu đồ và ma trận nhầm lẫn.
  
## 2. Thuật toán

Dự án này sử dụng các thuật toán phân loại phổ biến bao gồm:

### Naive Bayes
- **Giải thích**: 
  - Naive Bayes là một thuật toán phân loại dựa trên Định lý Bayes và giả định rằng các đặc trưng (features) trong tập dữ liệu là độc lập với nhau. Dù giả định này ít khi đúng hoàn toàn trong thực tế, Naive Bayes vẫn tỏ ra hiệu quả trong nhiều trường hợp, đặc biệt là với bài toán phân loại văn bản (như phát hiện spam).
  
- **Cách hoạt động**:
  - Xác suất của từng nhãn (label) được tính dựa trên xác suất điều kiện của các đặc trưng.
  - Công thức: 
    \[
    P(Y | X) = \frac{P(X | Y) P(Y)}{P(X)}
    \]
  - Thuật toán Naive Bayes tính toán xác suất của từng nhãn và chọn nhãn có xác suất cao nhất làm kết quả dự đoán.

### Decision Tree (Cây Quyết Định)
- **Giải thích**:
  - Decision Tree là một mô hình phân loại dạng cây, nơi mỗi nút trong cây đại diện cho một quyết định dựa trên giá trị của một đặc trưng. Mô hình tiếp tục phân chia dữ liệu thành các nhóm nhỏ hơn cho đến khi đạt được kết quả phân loại.
  
- **Cách hoạt động**:
  - Mỗi nút đại diện cho một điều kiện phân chia (split condition), dựa trên một đặc trưng cụ thể.
  - Mỗi nhánh (branch) đại diện cho một kết quả của điều kiện đó.
  - Các nút lá (leaf nodes) là kết quả cuối cùng, tức là nhãn phân loại của mẫu.
  
- **Chỉ số Gini và Entropy**:
  - Decision Tree sử dụng chỉ số Gini hoặc Entropy để chọn cách phân chia dữ liệu tốt nhất tại mỗi bước.
  - **Entropy** đo lường mức độ hỗn loạn hoặc không chắc chắn trong dữ liệu, và thuật toán sử dụng "information gain" để quyết định phân chia.
  - **Gini Index** đo lường sự bất bình đẳng giữa các nhãn. Chỉ số càng thấp, dữ liệu càng được chia tốt.

### K-Nearest Neighbors
**Giải thích**:
  - Là một thuật toán học máy đơn giản và dễ hiểu, được sử dụng chủ yếu cho các bài toán phân loại và hồi quy. KNN dựa trên ý tưởng rằng các điểm dữ liệu gần nhau trong không gian đặc trưng (feature space) có nhiều khả năng thuộc cùng một nhãn (hoặc có giá trị tương tự).

**Cách hoạt động**:
  - Chọn số lượng "k" (số láng giềng gần nhất)
  - Tính khoảng cách từ điểm cần dự đoán đến tất cả các điểm trong tập huấn luyện
  - Xác định k điểm lân cận gần nhất
  - Phân loại hoặc hồi quy dựa trên k láng giềng gần nhất
  - Đưa ra kết quả dự đoán

