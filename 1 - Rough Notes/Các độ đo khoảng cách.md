 
| Status | Tags         | Created        |
| ------ | ------------ | -------------- |
|        | [[Phân cụm]] | 11.12.24 21:16 |

## Các tính chất tiền đề của độ đo khoảng cách:
- Tính không âm: $d(i,j)>0$ nếu $i\ne j$, và $d(i,i)=0$ 
- Tính đối xứng: $d(i,j)=d(j,i)$ 
- Bất đẳng thức tam giác: $d(i,j)\le d(i,k)+d(k,j)$ 

## Khoảng cách dữ liệu số
- Khoảng cách Minkowski:
	- $d(a,b)=\sqrt[h]{\sum{|a_i-b_i|^h}}$ 
	- Trường hợp đặc biệt:
		- $h=1$ -> khoảng cách Manhattan ($L_1$-norm)
			- $d(a,b)=\sum{|a_i-b_i|}$ 
		- $h=2$ -> khoảng cách Euclid chuẩn ($L_2$-norm)
			- $d(a,b)=\sqrt{\sum{(a_i-b_i)^2}}$ 
		- $h\to\inf$ -> khoảng cách supremum
			- $d(a,b)=\max(a_i-b_i)$ 

- Độ đo Hamming: số chiều mà ở đó giá trị tương ứng của hai vector là khác nhau.
	- $(1,0,1,0,1)$
	- $(1,1,1,1,0)$
	- Khoảng cách là 3 (có 3 vị trí khác nhau).

- Độ đo Jaccard:
	- $x$ và $y$ là hai tập hợp.
	- Chỉ số Jaccard được định nghĩa là: $$J(x,y)=\frac{|x\cap y|}{|x\cup y|}$$
	- Khi đó, độ đo khoảng cách Jaccard được định nghĩa là: $$d(x,y)=1-J(x,y)$$
- Khoảng cách Kullback-Leibler:
	- $x$ và $y$ là hai phân phối xác suất rời rạc.
	- Kullback-Leibler divergence được định nghĩa là: $$D_{KL}(x||y)=\sum_{i=0}^mx_i\log\frac{x_i}{y_i}$$
	- Vì KL divergence không thỏa mãn tính chất đối xứng nên ta sử dụng độ đo khoảng cách dựa trên KL như sau: $$d(x,y)=\frac{D_{KL}(x||y)+D_{KL}(y||x)}2$$

## References
