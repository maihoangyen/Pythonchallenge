# <div align="center"><p>Pythonchallenge</p></div>
 ## Họ và tên: Mai Thị Hoàng Yến
 ## Ngày báo cáo: Ngày 4/4/2022
 ### MỤC LỤC
 1. [Ý tưởng giải challenge](#yt)      
 2. [Sử dụng request để giải challenge](#sd)
 3. [Thêm comment vào code](#tc)
 4. [Sử dụng `__name__ = '__main__'`](#sdu)
 5. [Ý nghĩa các hàm cần sử dụng](#yn) 

### Nội dung báo cáo 
#### 1. Ý tưởng giải challenge <a name="yt"></a>

  - Đầu tiên, khi chúng ta nhấn vào liên kết`http://www.pythonchallenge.com/pc/def/equality.html` thì sẽ hiện ra hình ảnh như hình bên dưới. Như chúng ta có thể thấy đây là hình ảnh 1 cây nén nhỏ bên trái và bên phải đều có 3 cây nến lớn. Ở đây, chúng ta tạm ký hiệu cho nó là `XXXaVVV`.
    
    ![image](https://user-images.githubusercontent.com/101852647/161515482-fc906d5e-7b5e-4c63-b8b7-86d8c748a5cd.png)
    
  - Tiếp theo, chúng ta sẽ mở source code của trang web này để xem thử thì thấy ở cuối dòng xuất hiện một khối cái chữ cái khác nhau như hình dưới đây
  
    ![image](https://user-images.githubusercontent.com/101852647/161515500-2c73c905-32ee-4c9b-9d67-f9d919c1ee2b.png)
  
  - Sau đó chúng ta copy đoạn chữ cái ở cuối trang trong source code vào file .txt hoặc là có thể trích xuất văn bản trực tiếp từ html để có thể tải dữ liệu lên.
  - Tiếp theo chúng ta có thể sử dụng được những biểu thức chính quy để để tìm kết quả phù hợp.
  - Sau khi tìm được những chữ cái phù hợp thì chúng ta sẽ ghép chúng lại với nhau. Như vậy là chúng ta đã có được kết quả.
  
#### 2. Sử dụng request để giải challenge <a name="sd"></a>  
   
- Như ở trên em đã trình bày ý tưởng thì sau khi đã tìm được đoạn chữ cái ở cuối trang trong source code thì em sẽ bắt đầu trích xuất văn bản trực tiếp từ HTML và em chạy tất cả chương trình trên google colab.
  
    ![image](https://user-images.githubusercontent.com/101852647/161509487-4cab38e1-eb67-4722-8e59-651486c41c30.png)
    
- Hoặc em có thể copy nó và lưu nó vào file `task4.txt` và tải file đó lên để bắt đầu đọc nó. Ở đây e sử dụng câu lệnh `data = open('/task4.txt').read()` 

    ![image](https://user-images.githubusercontent.com/101852647/161515548-6e5d5eea-7969-449f-a2d7-84702725e622.png)
    
    ![image](https://user-images.githubusercontent.com/101852647/161508312-92399a61-1b5a-4c7f-9da1-c57408a0b898.png)
    
- Tiếp theo, em sẽ sử dụng các biểu thức chính quy để tìm tất cả kết quả phù hợp. Bây giờ, em sẽ phân tích các biểu thức để có được kết quả như mong muốn

     - `[a-z]:` 1 chữ thường
     
     - `[A-Z]:` 1 chữ in hoa
     
     - `[A-Z]{3}:` 3 chữ cái viết hoa liên tiếp
     
     - `[A-Z]{3}[a-z][A-Z]{3}:` 3 chữ hoa + 1 chữ thường + 3 chữ hoa
     
     - `[^A-Z]:` bất kỳ ký tự nhưng một ký tự hoa
     
     - `[^A-Z]+:` ít nhất một ký tự như vậy
     
     - `[^A-Z]+[A-Z]{3}[a-z][A-Z]{3}[^A-Z]+:` một cái gì đó khác trước và sau mẫu ( XXXaVVV) của chúng ta, vì vậy không có nhiều hơn 3 chữ cái viết hoa liên tiếp ở mỗi bên
     
     - `[^A-Z]+[A-Z]{3}([a-z])[A-Z]{3}[^A-Z]+:` chúng ta chỉ quan tâm đến chữ thường
      
   ![image](https://user-images.githubusercontent.com/101852647/161511501-ce2d278b-fade-410e-8c09-86fddf725369.png)
    
- Sau khi đã có được những chữ cái phù hợp rồi chúng ta sẽ ghép chúng lại với nhau để có được kết quả mong đợi. Cuối cùng, chúng ta đã có kết quả sau khi ghép lại là: `linkedlist`

    ![image](https://user-images.githubusercontent.com/101852647/161512139-8d65a864-6f0a-4724-8f07-53d0d67ec3c5.png)
      
- Đây là toàn bộ code để tìm được kết quả:

    ![image](https://user-images.githubusercontent.com/101852647/161513103-a8574562-8bec-4841-840d-adf600ec692d.png)

#### 3. Thêm comment vào code<a name="tc"></a>  

   ![image](https://user-images.githubusercontent.com/101852647/161561356-ed9d675e-264e-45af-85d0-d7154e3b267c.png)

#### 4. Sử dụng `__name__ = '__main__'`<a name="sdu"></a>

 - Trong Python, `"if__name __ ==" __main__ "` cho phép chúng ta chạy các tệp chứa mã nguồn Python dưới dạng các mô-đun có thể tái sử dụng hoặc các chương trình độc lập.
 
   ![image](https://user-images.githubusercontent.com/101852647/161567970-cc0e6f26-f4a2-4760-b1c3-fb6c38707358.png)
   
#### 5. Ý nghĩa các hàm cần sử dụng <a name="yn"></a>

 - `urllib.request`: Thư viện này được sử dụng chủ yếu cho việc mở và lấy URL
 - `re`: Thư viện này sử dụng để làm việc với biểu thức chính quy
 - `urllib.request.urlopen` : Giúp chúng ta mở tệp HTML từ URL
 - `read()`: Sử dụng để đọc một tệp HTML từ URL
 - `decode()`: Nó chấp nhận mã hóa của chuỗi mã hóa để giải mã nó và trả về chuỗi ban đầu
 - `re.findall`: Được sử dụng để nhận tất cả các kết quả phù hợp không chồng chéo của mẫu trong chuỗi dữ liệu dưới dạng trả về, ở dạng danh sách các chuỗi
 - `re.DOTALL`: Làm cho ký tự đặc biệt ‘.’ Khớp với tất cả các ký tự, bao gồm cả các ký tự dòng mới
 - `join`: trả về một chuỗi bằng cách nối tất cả các phần tử của một chuỗi có thể lặp lại, được phân tách bằng dấu phân cách chuỗi.
 - `__name__ == '__main__'`: cho phép chúng ta chạy các tệp chứa mã nguồn Python dưới dạng các mô-đun có thể tái sử dụng hoặc các chương trình độc lập
