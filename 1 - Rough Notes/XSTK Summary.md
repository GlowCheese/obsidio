
| Status | Tags                           | Created        |
| ------ | ------------------------------ | -------------- |
|        | [[probability and statistics]] | 18.12.24 11:31 |


## 1. Xác suất có điều kiện

$$
P(A|B) = \frac{P(A \cap B)}{P(B)} \quad \text{với} \, P(B) > 0
$$
$$
P(A_1 \cup A_2 \cup \dots \cup A_n | B) = \sum_{i=1}^{n} P(A_i | B) = \sum_{i=1}^{n} \frac{P(A_i \cap B)}{P(B)}
$$

## 2. Hệ đầy đủ

Một hệ các sự kiện $\{A_1, A_2, ..., A_n\}$ được gọi là hệ đầy đủ nếu:

$$
P(A_1 \cup A_2 \cup \dots \cup A_n) = 1
$$

và các sự kiện $A_1, A_2, ..., A_n$ không giao nhau, tức là:

$$
P(A_i \cap A_j) = 0 \quad \text{với} \, i \neq j
$$

## 3. Công thức Bayes

Công thức Bayes cho phép tính xác suất có điều kiện ngược lại:

$$
P(A|B) = \frac{P(B|A) P(A)}{P(B)}
$$

Trong đó:
- $P(B|A)$ là xác suất của sự kiện $B$ khi đã biết $A$.
- $P(A)$ là xác suất của sự kiện $A$.
- $P(B)$ là xác suất của sự kiện $B$.

## 4. Kỳ vọng biến ngẫu nhiên và các tính chất của kỳ vọng

Kỳ vọng của biến ngẫu nhiên $X$ được định nghĩa là:

- Đối với biến ngẫu nhiên rời rạc:

$$
E[X] = \sum_{x} x P(X = x)
$$

- Đối với biến ngẫu nhiên liên tục:

$$
E[X] = \int_{-\infty}^{\infty} x f_X(x) dx
$$

Một số tính chất của kỳ vọng:
- $E[aX + b] = aE[X] + b$
- $E[X + Y] = E[X] + E[Y]$
- $E[X Y] = E[X]E[Y]$ (nếu $X$ và $Y$ độc lập)

## 5. Phương sai biến ngẫu nhiên và các tính chất của phương sai

Phương sai của biến ngẫu nhiên $X$ là:

$$
Var(X) = E[X^2] - (E[X])^2
$$

Một số tính chất của phương sai:
- $Var(aX + b) = a^2 Var(X)$
- $Var(X + Y) = Var(X) + Var(Y)$ (nếu $X$ và $Y$ độc lập)

## 6. Hàm mật độ biến ngẫu nhiên liên tục và các tính chất

Hàm mật độ xác suất (PDF) của biến ngẫu nhiên liên tục $X$ có tính chất:

$$
P(a \leq X \leq b) = \int_{a}^{b} f_X(x) dx
$$

Các tính chất:
- $f_X(x) \geq 0$ với mọi $x$
- $\int_{-\infty}^{\infty} f_X(x) dx = 1$

## 7. Các phân phối phổ biến

### 7.1. Phân phối Bernoulli

$$
P(X = 1) = p, \quad P(X = 0) = 1 - p
$$
$$
E[X] = p, \quad Var(X) = p(1 - p)
$$

### 7.2. Phân phối Poisson
$$
P(X = k) = \frac{\lambda^k e^{-\lambda}}{k!}, \quad k = 0, 1, 2, \dots
$$
$$
E[X] = \lambda, \quad Var(X) = \lambda
$$
### 7.3. Phân phối đều
$$
f_X(x) = \frac{1}{b - a}, \quad a \leq x \leq b
$$
$$ F_X(x) = \frac{x - a}{b - a}, \quad a \leq x \leq b $$
$$
E[X] = \frac{a + b}{2}, \quad Var(X) = \frac{(b - a)^2}{12}
$$

### 7.4. Phân phối mũ
$$
f_X(x) = \lambda e^{-\lambda x}, \quad x \geq 0
$$
$$ F_X(x) = P(X \leq x) = 1 - e^{-\lambda x}, \quad x \geq 0 $$
$$
E[X] = \frac{1}{\lambda}, \quad Var(X) = \frac{1}{\lambda^2}
$$
### 7.5. Phân phối nhị thức
$$
P(X = k) = \binom{n}{k} p^k (1 - p)^{n-k}, \quad k = 0, 1, 2, \dots, n
$$
$$
E[X] = np, \quad Var(X) = np(1 - p)
$$
## 8. Xấp xỉ phân phối nhị thức bằng phân phối chuẩn (n >= 30)
$$
X \sim N(np, np(1 - p))
$$
### 8.1. Áp dụng chuẩn hóa
Để sử dụng phân phối chuẩn, ta chuẩn hóa biến ngẫu nhiên $X$ như sau:

$$
Z = \frac{X - np}{\sqrt{np(1 - p)}}
$$
Khi đó, $Z \sim N(0, 1)$.





## References
