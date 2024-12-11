
| Status | Tags           | Created        |
| ------ | -------------- | -------------- |
| #adult | [[statistics]] | 11.12.24 13:07 |

### Ước lượng điểm:
- Ước lượng kì vọng tổng thể: $\mu \cong \bar{x}$ 
- Ước lượng phương sai tổng thể: $\sigma^2 \cong s^2$ 

### Ước lượng khoảng:
- Ước lượng khoảng tin cậy $\beta \%$ cho kỳ vọng $\mu$ là:
	- Một đoạn $[a, b] = [\bar{x}-u_\beta\sigma_\bar{x}, \bar{x}+u_\beta\sigma_\bar{x}]$ 
		- $u_\beta$ là số lần độ lệch chuẩn.
		- $u_\beta = z_{(1-\beta)/2}$ nếu $n\ge30$ 
		- $u_\beta = t_{(1-\beta)/2}$ nếu $n\le30$ 
		- $P(Z>z_\alpha)\approx\alpha$ với $Z\sim N(0,1)$ (phân phối chuẩn tắc).
		- $P(T > t_\alpha) \approx \alpha$ với $T$ là tuân theo phân phối Student.
	- $P(a\le\mu\le b) = \beta \%$ 

- Ví dụ ($u_\beta = z_{(1-\beta)/2}$):
	- $\beta=90\% \longrightarrow u_\beta=z_{0.05}=1.64$ 
	- $\beta=95\% \longrightarrow u_\beta=z_{0.025}=1.96$ 
	- $\beta=98\% \longrightarrow u_\beta=z_{0.01}=2.33$ 
	- $\beta=99\% \longrightarrow u_\beta=z_{0.005}=2.58$ 

- Khoảng tin cậy cho kỳ vọng:
	- Với độ tin cậy $1 - \alpha$
	- Phương sai chưa biết và $n \ge 30$:
		- $[a,b]=[\bar{x}\pm z_{\alpha/2}\sigma_\bar{x}]$ (normal distribution)
	- Phương sai chưa biết và $n \le 30$:
		- $[a,b]=[\bar{x}\pm t_{\alpha/2}\sigma_\bar{x}]$ (t-distribution)

- Khoảng tin cậy cho tỉ lệ:
	- $p$ là tỉ lệ cá thể có thuộc tính $A$ trong quần thể.
	- $f=k/n$ là tỉ lệ cá thể có thuộc tính $A$ trong mẫu nghiên cứu.
		- Kì vọng $EF = p$
		- Phương sai $DF=p(1-p)/n$  (điều kiện $np>5$ và $n(1-p)>5$).
	- Do không biết $p$ nên:
		- Ước lượng kì vọng $EF = f$
		- Ước lượng phương sai $DF = f(1-f)/n$  (điều kiện $nf > 10$ và $n(1-f) > 10$).
	- Khoảng tin cậy $\beta \%$ cho tỉ lệ $p$ có dạng:
		- $[a,b]=[f-u_\beta \sigma_F,f+u_\beta \sigma_F]$
		- $\sigma_F = \sqrt{DF} = \sqrt{f(1-f)/n}$ 
