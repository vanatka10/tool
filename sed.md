# sed (Stream Editor)
sed là một công cụ xử lý văn bản dòng (stream editor) dùng để thay thế, xóa, chèn, hoặc chỉnh sửa văn bản trong một tệp hoặc đầu vào từ dòng lệnh. Nó hoạt động trên từng dòng của tệp và có thể thực hiện nhiều thao tác khác nhau.

# Cách sử dụng cơ bản:
bash
Sao chép mã
sed [OPTION]... '{command}' [file...]
## Các lệnh chính trong sed:
### Thay thế (s/old/new/): Thay thế tất cả các từ hoặc mẫu trong mỗi dòng khớp với old thành new.

Ví dụ:

bash
Sao chép mã
echo "Hello World" | sed 's/World/Universe/'
Kết quả:
Hello Universe

### Thay thế có chỉ định số lần thay thế (g cho tất cả) Sử dụng g để thay thế tất cả các lần xuất hiện của một mẫu trong dòng.

Ví dụ:
```
echo "apple apple apple" | sed 's/apple/fruit/g'
Kết quả:
fruit fruit fruit
```
### Xóa dòng (d): Xóa các dòng khớp với mẫu.

Ví dụ:
```
echo -e "Line 1\nLine 2\nLine 3" | sed '/Line 2/d'
Kết quả:

mathematica
```

Line 1
Line 3
Chèn dòng (i hoặc a): Chèn dòng mới trước hoặc sau dòng khớp với mẫu.

Ví dụ (chèn trước):

echo -e "Line 1\nLine 2\nLine 3" | sed '/Line 2/i This is inserted before Line 2'

### Thay thế với ký tự đặc biệt: sed hỗ trợ các ký tự đặc biệt như \n (xuống dòng), \t (tab), & (lặp lại mẫu đã thay thế).

Ví dụ:
```
echo "apple banana cherry" | sed 's/apple/& pie/'
Kết quả:
apple pie banana cherry
```
### Sử dụng -e để thực hiện nhiều lệnh: Bạn có thể chỉ định nhiều lệnh sed để thực hiện trong một lần.
Ví dụ:
```
echo "apple banana cherry" | sed -e 's/apple/fruit/' -e 's/banana/berry/'
Kết quả:
fruit berry cherry
```
