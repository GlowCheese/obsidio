
| Status  | Tags           | Created        |
| ------- | -------------- | -------------- |
| #child  | [[optim-algo]] | 16.12.24 11:43 |

## Heuristic cấu trúc

- $s = (s_1, \dots, s_n)$ đại diện một phương án gồm $n$ thành phần.
- $s_i\in C_i$, trong đó $C_i$ là tập các lựa chọn khả dĩ cho $s_i$>
- lời giải được xây dựng theo cách mở rộng tuần tự, không quay lui.
	- xuất phát từ thành phần khởi tạo $C_1$.
	- lần lượt thêm các thành phần mới theo phương pháp;
		- ngẫu nhiên
		- tất định dựa trên quy tắc heuristic đã chọn
- nhận xét:
	- thông dụng, giải quyết được nhiều bài toán.
	- chạy nhanh nhưng không ước lượng được độ tốt (như $\epsilon$-xấp xỉ tuyệt đối)
	- thường được dùng để xây dựng lời giải cho các phương pháp khác.
