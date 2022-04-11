# Thêm các thư viện
import urllib.request # Thư viện này được sử dụng chủ yếu cho việc mở và lấy URL
import re # Thư viện này sử dụng để làm việc với biểu thức chính quy
def main():
  # Đọc dữ liệu trong url và lưu thành chuỗi sau đó giải mã
  html = urllib.request.urlopen("http://www.pythonchallenge.com/pc/def/equality.html").read().decode()
  # Trả về tất cả các kêt quả dưới dạng danh sách
  data = re.findall("<!--(.*)-->", html, re.DOTALL)[-1]
  # Ghép kết quả lại và in nó ra màn hình 
  print("".join(re.findall("[^A-Z]+[A-Z]{3}([a-z])[A-Z]{3}[^A-Z]+", data)))
if __name__ == '__main__':
    main()