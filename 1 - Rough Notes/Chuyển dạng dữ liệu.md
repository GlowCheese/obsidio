
| Status | Tags                   | Created        |
| ------ | ---------------------- | -------------- |
|        | [[Tiền xử lý dữ liệu]] | 14.12.24 18:35 |

## Chuyển dạng dữ liệu

- Làm trơn (smoothing): loại bỏ nhiễu
- Tổng hợp (aggregation): tóm tắt, xây dựng khối dữ liệu
- Tổng quát hóa (generalization): leo kiến trúc khái niệm
- Chuẩn hóa (normalization): thu nhỏ vào miền nhỏ
	- Chuẩn hóa min-max
	- Chuẩn hóa z-score
	- Chuẩn hóa tỷ lệ thập phân
- Xây dựng thuộc tính mới từ thuộc tính sẵn có.

## Chuẩn hóa:
- Chuẩn hóa min-max: $$v'=\frac{v-min_A}{max_A-min_A}(new\_max_A-new\_min_A)+new\_min_A$$
- Chuẩn hóa z-score: $$v'=\frac{v-mean_A}{\sigma_A}$$
- Chuẩn hóa tỷ lệ thập phân: $$\begin{aligned}v'&=v/10^j\\ j &= \log_{10}(max(v))\end{aligned}$$  

## References
