
| Status | Tags            | Created        |
| ------ | --------------- | -------------- |
|        | [[data-mining]] | 15.12.24 14:16 |

## Phân lớp và hồi quy
- Phân lớp:
	- Mô hình phân tách dữ liệu thành các lớp rời rạc.
	- Mục tiêu: tìm biên phân lớp tốt nhất
	- Đánh giá bằng độ chính xác, độ hồi tưởng, F1
	- Phương pháp: cây quyết định, rừng ngẫu nhiên, mạng nơ-ron nhân tạo
- Hồi quy:
	- Mô hình thể hiện mối tương quan giữa các biến 
	  độc lập và phụ thuộc, từ đó dự đoán các biến liên tục.
	- Mục tiêu: xác định đường hồi quy tốt nhất.
	- Đánh giá bằng sai số bình phương trung bình.
	- Phương pháp: hồi quy tuyến tính, logistic, đa thức, Lasso

## Bài toán phân lớp
- Đầu vào:
	- Tập dữ liệu $D$ và tập các lớp $C_1,C_2,\dots,C_k$.
	- Mỗi dữ liệu thuộc một lớp $C_i$.
	- Từ $D$ chọn ra một tập ví dụ $D_{exam}$
- Đầu ra:
	- Một mô hình phân lớp ánh xạ $D$ sang $C$.

- Quá trình hai pha:
	- Pha 1: Dạy bộ phân lớp:
		- $D_{exam} = D_{train}(2/3) + D_{test}(1/3)$ 
		- $D_{train}$: xây dựng mô hình phân lớp (tính toán tham số)
		- $D_{test}$: đánh giá mô hình phân lớp (các độ đo hiệu quả)
		- Chọn mô hình có chất lượng nhất.
	- Pha 2: Sử dụng mô hình:
		- xác định lớp cho tập $D \backslash D_{exam}$.

- Các loại phân lớp:
	- Phân lớp nhị phân/đa lớp
	- Phân lớp đơn nhãn/đa nhãn/phân cấp:
		- đơn nhãn: 1 đối tượng chỉ thuộc 1 lớp
		- đa nhãn: 1 đối tượng thuộc 1 hoặc nhiều lớp
		- phân cấp: lớp này là con của lớp kia

## Đánh giá mô hình phân lớp
- Trong phân lớp nhị phân:
	- Độ chính xác: $Accuracy=(f_{11}+f_{00})/(f_{11}+f_{10}+f_{01}+f_{00})$ 
	- Hệ số lỗi: $Error \ rate=(f_{10}+f_{01})/(f_{11}+f_{10}+f_{01}+f_{00})$ 

	- Recall: $Recall=f_{11}/(f_{11}+f_{10})$ 
	- Precision: $Precision=f_{11}/(f_{11}+f_{01})$ 
	
	- Độ đo F1: $F1=2(Precision\cdot Recall)/(Precision+Recall)$ 
	- F1 thể hiện việc đánh giá nhạy cảm với giá trị dữ liệu.
- Trong phân lớp đa lớp:
	- Đánh giá nhị phân cho từng lớp
	- Thuộc lớp $C_i$ hoặc không thuộc lớp $C_i$ 
		- $Re_i = f^i_{11}/(f^i_{11}+f^i_{10})$ 
		- $Pr_i = f^i_{11}/(f^i_{11}+f^u_{01})$ 
		- $F1_i=2(Re_i\cdot Pr_i)/(Re_i+Pr_i)$ 
	- Micro ($\mu$, mịn, vi mô) và Macro ($M$, thô, vĩ mô):

### Phân lớp cây quyết định:
- Mỗi nút là tên thuộc tính, cạnh là điều kiện giá trị thuộc tính.
- phương châm: chia để trị
- các thuật toán phổ biến: Hunt, ID3, C4.5, C5.x

#### Thuật toán Hunt:
![[Pasted image 20241215173123.png]]

#### Thuật toán ID3: chả hiểu gì :(
![[Pasted image 20241215185810.png]]

### Rút gọn cây:
- Chiến lược:
	- phân chia tập dữ liệu
	- coi "chọn thuộc tính" là chiến lược tối ưu hóa
- Dừng phân chia khi:
	- tất cả các dữ liệu thuộc về cùng một lớp
	- tất cả các dữ liệu có giá trị tương tự nhau.
	- việc phân chia không cải thiện chất lượng
#### Độ đo Gini:
- Công thức Gini: $Gini(t)=1-\sum_j [p(j|t)]^2$
	- $p(j|t)$ là tần suất các dữ liệu thuộc lớp $j$ tại nút $t$.
- $0 \le Gini(t) \le 1-1/n_c$, tăng dần theo mức hỗn tạp.
- Nếu một nút $t$ được phân hoạch thành $k$ nút con
  thì chất lượng của việc chia được tính bằng:
	- $Gini_{split}=sum_{i=1}^k\frac{n_i}nGini(i)$ 
#### Độ đo Information Gain:
- Công thức Entropy: $Entropy(t)=-\sum_jp(j|t)\log p(j|t)$ 
- $0\le Entropy(t)\le\log(n_c)$
- Loga cơ số $2$.
- Độ đo Information Gain:
	- $Gain_{split} = entropy(t)-\sum_{i=1}^k\frac{n_i}nentropy(i)$
	- Cải tiến khắc phục xu hướng phân hoạch nhiều tập con:
		- $GainRATIO=\frac{Gain_{split}}{SplitINFO}$
		- $SplitINFO=-\sum\frac{n_i}n\log\frac{n_i}n$

### Phân lớp dựa trên luật
- Luật: <điều kiện> -> y
	- <điều kiện> là sự kết nối các thuộc tính (tiên đề)
	- y là nhãn lớp (kết quả)
- Xây dựng luật phân lớp:
	- Trực tiếp: trích xuất từ dữ liệu
	- Gián tiếp: trích xuất từ mô hình phân lớp khác:
		- cây quyết định, mạng nơ ron 

### Phân lớp Bayes:
- Phân lớp bằng xác suất.
- Mô hình = tập công thức tính xác suất
- Ưu điểm: đơn giản, huấn luyện dễ và nhanh
- Nhược điểm: giả định độc lập, zero-probability,
  không tính đến sự tương tác giữa các xác suất ước lượng.

### Phân lớp k-NN
- Phân lớp cho dữ liệu mới thông qua $k$ láng giềng gần nhất
	- Lớp của dữ liệu mới là lớp xuất hiện nhiều nhất trong $k$ láng giềng đó
	- Số lớp bằng nhau -> chọn lớp có tổng khoảng cách đến các láng giềng nhỏ nhất.
