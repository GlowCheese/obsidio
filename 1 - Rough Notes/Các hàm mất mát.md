
| Status | Tags                      | Created        |
| ------ | ------------------------- | -------------- |
| #baby  | [[Các độ đo khoảng cách]] | 12.12.24 23:02 |

## Các hàm mất mát

- Phân kỳ Kullback-Leibler (KL):
	- Dùng để so sánh hai phân bố xác suất.
	- $D_{KL}(p,q)$: phân kỳ của $q$ từ $p$, đo độ mất mát thông tin khi $q$ được dùng để xấp xỉ $p$.
		- Dạng rời rạc: $$D_{KL}(p(x),q(x))=\sum_{x\in X}q(x)ln\frac{q(x)}{p(x)}$$
		- Dạng liên tục: $$D_{KL}(p(x),q(x))=\int_{-\infty}^\infty q(x)ln\frac{q(x)}{p(x)}dx$$
	- Xem xét $p=0$ hoặc $q=0$:
		- $q=0\implies \lim_{q\to0}q\log q=0$
		- $(p=0)\cap(q\ne0)\implies D_{KL}(p, q) = \infty$, tức $p$ và $q$ khác biệt tuyệt đối.  
	- Phân kỳ KL không phải là metric
	
	- Cơ chế smoothing (làm trơn):
		- xem xét khả năng của cái không nhìn thấy là một xác suất rất nhỏ $\epsilon$.
		- Ví dụ: $P: (a: 3/5, b: 1/5, c: 1/5)$ và $Q: (a: 7/9, d: 2/9)$.
			- Tập mẫu quan sát được: $SP=\{a,b,c\}$ và $SQ=\{a,d\}$.
			- Làm trơn:
				- $P': (a: 3/5-\epsilon/3, b:1/5-\epsilon/3, c: 1/5-\epsilon/3, d: \epsilon)$ 
				- $Q': (a: 7/9-\epsilon, b:\epsilon, c:\epsilon, d:2/9-\epsilon)$ 
			- $D_{KL}(P',Q')$ có thể tính được.