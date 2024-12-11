
| Status | Tags           | Created        |
| ------ | -------------- | -------------- |
| #baby  | [[statistics]] | 11.12.24 13:22 |

### Các loại giả thuyết:
- Giả thuyết không (H0):
	- Là một phát biểu về tham số tổng thể
	- Thường là một tuyên bố bị nghi ngờ
	- Được cho là đúng cho đến khi bị chứng minh là sai
- Giả thuyết thay thế (Ha):
	- Nhà nghiên cứu mong muốn ủng hộ và chứng minh là đúng
	- Là phát biểu ngược với H0
	- Được cho là đúng đến khi H0 bị bác bỏ
- Mục tiêu của kiểm định giả thuyết là bác bỏ hoặc
  không bác bỏ H0. Không nên kết luận là chấp nhận H0

### Các bước kiểm định giả thuyết:
1. Thiết lập hai giả thuyết đối lập.
2. Xác định mức ý nghĩa.
3. Chọn lựa kiểm định phù hợp.
4. Tính chỉ số thống kê tương ứng.
5. Ra quyết định về H0 (bác bỏ hay không bác bỏ).
6. Ra một kết luận tổng thể.

### Các bài toán kiểm định:
- Kiểm định giả thuyết "có thay đổi":
	- Giả thuyết H0: $\mu = \mu_0$ 
	- Giả thuyết Ha: $\mu \ne \mu_0$ 
	- Giá trị kiểm định: $z=\frac{\bar{x}-m_0}{s/\sqrt{n}}$
	- Nếu $z<-z_{\alpha/2}$ hoặc $z>z_{\alpha/2}$ thì bác bỏ giả thuyết H0.
- Kiểm định giả thuyết "thay đổi lớn hơn":
	- Giả thuyết Ha: $\mu > \mu_0$
	- Nếu $z > z_\alpha$ thì bác bỏ giả thuyết H0.
- Kiểm định giả thuyết "thay đổi nhỏ hơn":
	- Giả thuyết Ha: $\mu < \mu_0$
	- Nếu $z < -z_\alpha$ thì bác bỏ giả thuyết H0

### Kiểm định giả thuyết về giá trị xác suất:

- Trong bài toán ước lượng:
	- do không biết $p$ nên:
		- $DF = f(1-f)/n$ với điều kiện $nf>10$ và $n(1-f)>10$.
- Trong bài toán kiểm định:
	- H0: $p = p_0$
	- Ta giả sử H0 đúng nên:
		- $DF=p_0(1-p_0)/n$ với điều kiện $np_0>5$ và $n(1-p_0)>5$.
	- Giá trị kiểm định:
		- $z=\frac{f-p_0}{\sqrt{p_0(1-p_0)/n}}$ 