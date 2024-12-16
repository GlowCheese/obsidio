
| Status | Tags                   | Created        |
| ------ | ---------------------- | -------------- |
|        | [[Tiền xử lý dữ liệu]] | 14.12.24 18:11 |

## Tích hợp dữ liệu

- Tích hợp dữ liệu (data integration):
	- kết hợp dữ liệu từ nhiều nguồn thành một nguồn lưu trữ chung.
- Tích hợp sơ đồ (schema integration):
	- tích hợp siêu dữ liệu (metadata) từ các nguồn khác nhau.
	- vấn đề định danh thực thể: làm thể nào để biết hai thực thể
	  từ các nguồn các nhau trỏ đến cùng một thực thể trong thực tế.
- Phát hiện vấn đề thiếu nhất quán dữ liệu:
	- vấn đề khi cùng một thực thể nhưng lại có
	  giá trị thuộc tính khác nhau giữa các nguồn.
	- nguyên nhân do cách trình bày (format)
	  khác nhau, đơn vị đo lường khác nhau, ...

## Nắm bắt dư thừa:
- Thường xảy ra khi tích hợp từ nhiều nguồn khác nhau.
	- cùng một thuộc tính nhưng có hai tên khác nhau.
	- một thuộc tính lại được tính toán từ một thuộc tính khác.
- Có thể phát hiện khi phân tích tương quan.
- Tích hợp cẩn trọng -> giảm/tránh dư thừa, thiếu nhất quán 
