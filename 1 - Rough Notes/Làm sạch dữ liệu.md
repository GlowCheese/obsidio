
| Status  | Tags                   | Created        |
| ------- | ---------------------- | -------------- |
| #child  | [[Tiền xử lý dữ liệu]] | 14.12.24 18:02 |

## Làm sạch dữ liệu
- Là quá trình:
	- xác định tính không chính xác, không đầy đủ/tính bất hợp lý của dữ liệu
	- chỉnh sửa các sai sót và thiếu sót được phát hiện
	- nâng cao chất lượng dữ liệu
- Các bài toán thuộc làm sạch dữ liệu:
	- Xử lý giá trị thiếu.
	- Định danh ngoại lai (dữ liệu nhiễu) và làm trơn.
	- Chỉnh sửa dữ liệu không nhất quán.
	- Giải quyết tính dư thừa tạo ra sau tích hợp dữ liệu.
### Xử lý thiếu giá trị:
- Bỏ qua nếu bản ghi:
	- Thiếu nhãn phân lớp (trong bài toán phân lớp)
	- Số lượng giá trị thiếu lớn (bán giám sát)
- Điều giá trị thiếu bằng tay: tẻ nhạt, kém khả thi
- Điền giá trị tự động:
	- Hằng toàn cục: ví dụ đ/n một lớp mới "unknown".
	- Trung bình giá trị thuộc tính các bản ghi hiện có hoặc cùng lớp.
	- Giá trị có khả năng nhất dựa trên suy luận: Bayes hoặc cây quyết định.
### Xử lý dữ liệu nhiễu:
- Nhiễu là lỗi ngẫu nhiên hoặc biến dạng của một biến đo được.
- Phương pháp đóng thùng (binning):
	- Sắp dữ liệu tăng và chia đều vào các thùng.
- Phân cụm: phát hiện và loại bỏ ngoại lai.
- Kết hợp kiểm tra máy tính và con người:
	- Phát hiện giá trị nghi ngờ để con ngừoi kiểm tra.
- Hồi quy: làm trơn bằng cách ghép dữ liệu theo các hàm hồi quy.
#### Phương pháp đóng thùng:
- Phân hoạch theo chiều rộng:
	- chia làm $N$ đoạn dài như nhau
	- không xử lý tốt khi dữ liệu không cân bằng
- Phân hoạch theo chiều sâu:
	- chia làm $N$ đoạn đều nhau về số lượng.
	- việc quản lý thuộc tính lớp: có thể "khôn khéo".
- Làm trơn: theo trung bình, trung tuyến, biên, ...
- Ví dụ:
	![[Pasted image 20241214180636.png]]
#### Phân tích cụm:
![[Pasted image 20241214180929.png]]


#### Hồi quy:
![[Pasted image 20241214181113.png]]