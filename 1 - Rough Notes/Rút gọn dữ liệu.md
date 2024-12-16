
| Status | Tags                   | Created        |
| ------ | ---------------------- | -------------- |
|        | [[Tiền xử lý dữ liệu]] | 14.12.24 18:45 |

## Rút gọn dữ liệu

- Kho dữ liệu lớn -> mất nhiều thời gian phân tích/khai phá dữ liệu.
- Rút gọn dữ liệu để giảm khối lượng
  dữ liệu mà sinh ra (hầu như) cùng kết quả.
- Chiến lược rút gọn:
	- Tập hợp khối dữ liệu.
	- Giảm chiều - loại bỏ thuộc tính không quan trọng.
	- Nén dữ liệu
	- Giảm tính số hóa - dữ liệu thành mô hình.
	- Rời rạc hóa và sinh cây khái niệm.

### Rút gọn chiều
- Rút gọn đặc trưng: lựa chọn tập nhỏ các đặc trưng sao cho
  phân bố xác suất của các lớp trong dữ liệu tương tự như phân bố ban đầu.
- Rút gọn số lượng mẫu trong tập mẫu.
- Các phương pháp heuristic:
	- Chọn chuyển tiếp: bắt đầu với một tập rỗng, sau đó thêm 
	  từng đặc trưng vào tập đã chọn, miễn là chúng cải thiện hiệu suất.
	- Loại bỏ lạc hậu: bắt đầu bằng toàn bộ đặc trưng và loại bỏ
	  từng đặc trưng ít quan trọng nhất.
	- Kết hợp cả hai: cả chọn chuyển tiếp và loại bỏ lạc hậu.
	- Rút gọn cây quyết định
### Phân cụm
- Phân tập DL thành các cụm và chỉ lưu trữ đại diện của cụm.
- Có thể rất hiệu quả nếu DL không chứa dữ liệu "bẩn".
- Tồn tại nhiều lựa chọn cho xác định phân cụm và thuật toán phân cụm.
### Rút gọn mẫu
- Lựa chọn tập con trình diễn dữ liệu.
- Lấy mẫu ngẫu nhiên có hiệu quả rất tồi nếu có DL lệch.
- Lấy mẫu thích nghi: xấp xỉ phần trăm mỗi lớp trong CSDL tổng thể.
- Một số thuật toán: SRS, SRSWR, SRSWOR