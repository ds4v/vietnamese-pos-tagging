# Gán nhãn từ loại Tiếng Việt

### Bài toán:

1. Tách từ Tiếng Việt với thuật toán **Longest Matching**
2. Gán nhãn từ loại sử dụng mô hình **Hidden Markorv** kết hợp thuật toán **Viterbi**
3. So sánh kết quả với thư viện **VnCoreNLP**

### Cài đặt [VnCoreNLP](https://github.com/vncorenlp/VnCoreNLP):

1. Download tập tin [CoreNLP.zip](https://drive.google.com/file/d/1CQAwUkjzVkIVqjoNCX0-EpFL9hfuCI2H/view?usp=sharing), giải nén vào thư mục, ví dụ: *D:\VnCoreNLP*
2. Chạy **VnCoreNLPServer**:

    - Mở cmd
    - Chuyển đến thư mục *D:\VnCoreNLP*
    - Chạy chương trình: `java -Xmx2g -jar VnCoreNLPServer.jar VnCoreNLP-1.1.jar -p 9001 -a "wseg,pos,parse"`

3. Cài đặt thư viện VnCoreNLP trên Python: `pip install vncorenlp`
4. Tạo đối tượng kết nối với **VnCoreNLPServer**:
    ```python
    from vncorenlp import VnCoreNLP
    client = VnCoreNLP(address="http://127.0.0.1", port=9001)
    ```
5. Tách từ cho một văn bản text, kết quả là danh sách các từ:
    ```python
    wordlist = client.tokenize(text)
    ```
6. Gán nhãn từ loại cho văn bản text, kết quả là danh sách các bộ (word, pos) trong đó word là từ đã được tách và pos là nhãn từ loại tương ứng với nó:
    ```python
    tagresult = client.pos_tag(text)
    ```

### Tham khảo:

-   [[VNLP Core] [1] Bài toán tách từ tiếng Việt - Tokenization, Word Segmentation](https://forum.machinelearningcoban.com/t/vnlp-core-1-bai-toan-tach-tu-tieng-viet-tokenization-word-segmentation/2002)
-   [Khóa học Coursera: Natural Language Processing with Probabilistic Models](https://www.coursera.org/learn/probabilistic-models-in-nlp)
- [VnCoreNLP: A Vietnamese natural language processing toolkit](https://github.com/vncorenlp/VnCoreNLP)
