# Gán nhãn từ loại Tiếng Việt

### Bài toán:

1. Tách từ Tiếng Việt với thuật toán Longest Matching
2. Gán nhãn từ loại sử dụng mô hình Hidden Markorv kết hợp thuật toán Viterbi
3. So sánh kết quả với thư viện [VnCoreNLP](https://github.com/vncorenlp/VnCoreNLP)

### Cài đặt và cấu hình:

1. Download thư viện [VnCoreNLP](https://drive.google.com/file/d/1CQAwUkjzVkIVqjoNCX0-EpFL9hfuCI2H/view?usp=sharing), giải nén vào thư mục, ví dụ: *D:\VnCoreNLP*
2. Chạy **VnCoreNLPServer**:

    - Mở cmd
    - Chuyển đến thư mục *D:\VnCoreNLP*
    - Chạy chương trình: `java -Xmx2g -jar VnCoreNLPServer.jar VnCoreNLP-1.1.jar -p 9001 -a "wseg,pos,parse"`

3. Cài đặt thư viện VnCoreNLP trên Python: `pip install vncorenlp`
4. Khai báo sử dụng lớp VnCoreNLP trong Python:
   from vncorenlp import VnCoreNLP
5. Tạo đối tượng kết nối với **VnCoreNLPServer**:
    ```python
    client = VnCoreNLP(address="http://127.0.0.1", port=9001)
    ```
6. Tách từ cho một văn bản text, kết quả là danh sách các từ:
    ```python
    wordlist = client.tokenize(text)
    ```
7. Gán nhãn từ loại cho văn bản text, kết quả là danh sách các bộ (word, pos) trong đó word là từ đã được tách và pos là nhãn từ loại tương ứng với nó
    ```python
    tagresult = client.pos_tag(text)
    ```
8. Mã nguồn thư viện: https://github.com/vncorenlp/VnCoreNLP

### Tham khảo:

-   [[VNLP Core] [1] Bài toán tách từ tiếng Việt - Tokenization, Word Segmentation](https://forum.machinelearningcoban.com/t/vnlp-core-1-bai-toan-tach-tu-tieng-viet-tokenization-word-segmentation/2002)
-   [Khóa học Coursera: Natural Language Processing with Probabilistic Models](https://www.coursera.org/learn/probabilistic-models-in-nlp)
