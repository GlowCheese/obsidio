
| Status | Tags            | Created        |
| ------ | --------------- | -------------- |
|        | [[data-mining]] | 14.12.24 20:06 |

## Phân cụm
- là bài toán
	- gom các đối tượng dữ liệu vào thành từng nhóm/cụm
	- các đối tượng trong cùng một cụm có sự tương đồng theo một tiêu chí nào đó.
- Đặc điểm:
	- Số cụm thường không được biết trước một cách chính xác.
	- Có nhiều cách tiếp cận để giải quyết.
	- Các kỹ thuật khác nhau thường mang lại kết quả khác nhau.
- Hai kiểu phân cụm: cứng (hard clustering) và mềm (hard clustering)

## Các cách tiếp cận phân cụm:
- Phân cụm phân cấp (hierarchical, connectivity-based):
	- Phương pháp top-down, bottom-up
	- Phân cụm cứng, sử dụng cây phân cụm
- Phân cụm phân hoạch (partitioning, centroid-based):
	- Khởi tạo với $k$ cụm. Lặp đi lặp lại việc gán đối tượng vào cụm có tâm gần nhất, sau đó điều chỉnh tâm các cụm.
	- Phương pháp: K-means, K-medoids.
	- Phân cụm cứng, cần xác định số cụm, cụm hình khối cầu.
- Phân cụm dựa trên phân bố (distribution-based):
	- Mỗi cụm dữ liệu sinh ra từ một phân bố xác suất.
	- Phương pháp: mô hình trộn Gauss với thuật toán EM
	- Phân cụm mềm, cần xác định số cụm, cần giả định phân bố dữ liệu
- Phân cụm dựa trên mật độ (density-based)
	- Các cụm là các vùng có mật độ cao
	- Phương pháp: DBSCAN, OPTICS
	- Hình dạng cụm bất kỳ, các cụm phân biệt bởi vùng có mật độ thấp, có thể tìm được ngoại lai
- Phân cụm dựa trên lưới (grid-based):
	- Phân chia dữ liệu thành các ô lưới
	- Nhiều kích thước ô lưới, thời gian tính toán nhanh.
- Phân cụm dựa trên đồ thị (graph-based)
	- Các cụm là vùng đồ thị con dày đặc (đầy đủ hoặc gần đầy đủ)
	- Phương pháp HCS
### Phân cụm phân cấp (top-down, agglomerative):
- Ý tưởng: khởi đầu mỗi điểm là một cụm. Thuật toán sáp nhập
  những cụm nhỏ gần nhau nhất thành cụm lớn hơn tại mỗi vòng lặp.
- Cần xác định:
	- Các biểu diễn các cụm
	- Tiêu chí chọn 2 cụm gần nhau nhất.
	- Khi nào thuật toán ngừng sáp nhập.
- Dừng sáp nhập khi:
	- Có hiểu biết hoặc phỏng đoán về số cụm trong bộ dữ liệu.
	- Khi việc sáp nhập 2 cụm nào đó tạo ra một cụm kém chất lượng
	  (ví dụ: khoảng cách trung bình từ các điểm đến tâm cụm quá lớn)
	- Có thể dừng khi tạo ra cụm cuối cùng bao gồm tất cả các đối tượng
	  kết quả là một cây phân cấp cụm
- Các tiêu chí chọn 2 cụm để sáp nhập:
	- Centroid-linkage: khoảng cách giữa 2 tâm của 2 cụm
	- Single-linkage: khoảng cách 2 điểm gần nhau nhất thuộc 2 cụm
	- Average-linkage: trung bình khoảng cách giữa mọi cặp điểm thuộc 2 cụm
	- Complete-linkage: khoảng cách xa nhất giữa 2 điểm của 2 cụm
	- Radius: bán kính là khoảng cách từ điểm xa nhất của cụm tới tâm cụm. sáp nhập 2 cụm nào tạo ra cụm mới có bán kính nhỏ nhất.
	- Diameter: tương tự Radius, nma là khoảng cách giữa 2 điểm xa nhất trong cụm.
- Độ phức tạp: O(n^3) hoặc O(n^2logn) (tối ưu bằng heap)
- Nếu không gian khác Euclid:
	- Áp dụng các độ đo khác (Jaccard, KL)
	- Tâm cụm được chọn là một đối tượng nào đó trong cụm.

### Phân cụm với K-means:
- Ý tưởng:
	- khởi đầu với $k$ tâm điểm của $k$ cụm
	- lặp đi lặp lại việc gán các điểm vào các cụm
	  có tâm cụm gần nhất và tính toán lại tâm cụm
	- cho đến khi không hoặc ít có sự thay đổi cụm
	  của các điểm hay sự dịch chuyển các tâm cụm.
- Cần xác định trước số cụm, tuy nhiên có thể suy diễn bằng
  phương pháp thử sai hoặc bằng các phương pháp điều chỉnh số cụm.
- Mục tiêu: tìm phân hoạch $S^* = \{S_1^*, S_2^*, \dots, S_k^*\}$ để biểu thức sau đạt cực tiểu: $$\sum_{i=1}^k\sum_{x\in S_i}(x-\mu_i)^2$$
	trong đó $\mu_i$ là tâm của cụm $S_i$.
- Giải pháp:
  ![[Pasted image 20241215010016.png]]
  ![[Pasted image 20241215010037.png]]
- Khởi tạo tâm các cụm ban đầu:
	- Lựa chọn các điểm làm tâm các cụm từng đôi một càng xa nhau càng tốt
		- Cụm đầu tiên là một điểm ngẫu nhiên
		- Mỗi cụm còn lại, chọn điểm có khoảng cách nhỏ nhất
		  tới những tâm điểm đã chọn là lớn nhất có thể.
	- Thực hiện phân cụm trên một mẫu nhỏ của tập D, sử dụng một thuật toán phân cụm nào đó (ví dụ: phân cụm phân cấp). Dừng ở mức $k$ cụm, sau đó lấy mỗi điểm gần tâm mỗi cụm làm tâm cụm đầu vào cho K-means.
- Độ phức tạp: O(tknm)
- Kết quả chỉ tốt khi các cụm dữ liệu đứng riêng rẽ và có hình dạng khối cầu.

### DBSCAN:
- Ý tưởng: chọn các đối tượng cốt lõi (core objects) có mật độ cao và kết nối
  các đối tượng đó với láng giềng của chúng để tạo lập các vùng có mật độ cao.
- Một số khái niệm:
	- $\epsilon$-neighborhood(x) là khối cầu có bán kính $\epsilon$ (>0) với tập tại x.
	- $\epsilon$-density(x) là mật độ của x - tổng số đối tượng trong $\epsilon$-neighborhood(x).
	- x được gọi là đối tượng cốt lõi nếu $\epsilon$-density(x) $\ge$ MinPts
- (directly) density-reachable:
	- xét $q$ và $p$ là hai đối tượng thuộc $D$.
	- $q$ là 1 điểm cốt lõi thì $p$ có-thể-với-tới-trực-tiếp-theo-mật-độ từ $q$ nếu $p$ nằm trong $\epsilon$-neighborhood(q).
	- $p$ có-thể-với-tới-theo-mật-độ từ $q$ nếu tồn tại một dãy $p_1, p_2, \dots, p_h$ sao cho $p_1=q$, $p_h=p$ và $p_{i+1}$ có-thể-với-tới-trực-tiếp-theo-mật-độ từ $p_i$ ($0\le i < h$).
- density-connectedness:
	- xét $p_1$, $p_2$, $q$ là các đối tượng thuộc $D$.
	- $p_1$ và $p_2$ được gọi là có-thể-kết-nối-theo-mật-độ nếu:
		- cả $p_1$ và $p_2$ đều có-thể-với-tới-theo-mật-độ từ $q$.
- Một tập con $S\subset D$ là một cụm nếu:
	- Mọi cặp đối tượng trong $S$ là có-thể-kết-nối-theo-mật-độ.
	- Không đối tượng nào trong $S$ có-thể-kết-nối-theo-mật-độ với một đối tượng ngoài $S$.
- giải pháp:
  ![[Pasted image 20241215021315.png]]
- hiệu quả:
  ![[Pasted image 20241215021708.png]]

## Đánh giá và đo đạc trong phân cụm? (đọc trong slide)