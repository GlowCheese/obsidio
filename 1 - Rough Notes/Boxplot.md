
| Status | Tags             | Created        |
| ------ | ---------------- | -------------- |
|        | [[Hiểu dữ liệu]] | 14.12.24 12:49 |

## Boxplot
- Boxplot (biểu đồ hộp và râu) là một cách biểu diễn dữ liệu dãy số.
- Các thành phần chính:
	- Min, Max: giá trị bé nhất và lớn nhất của dãy.
	- Q1 (phân vị thứ nhất): giá trị sao cho có 25% số phần tử bé hơn giá trị này
		- được định nghĩa là trung vị của nửa dưới
	- Q3 (phân vị thứ ba): giá trị sao cho có 75% số phần tử bé hơn giá trị này
		- được định nghĩa là trung vị của nửa trên
	- IQR = Q3 - Q1
	- Khoảng râu:
		- Giới hạn dưới: max(Min, Q1-1.5\*IQR)
		- Giới hạn trên: min(Max, Q3+1.5\*IQR)
	- Giá trị nằm ngoài khoảng râu được gọi là giá trị ngoại lai.

- Ví dụ: tập dữ liệu {1,2,3,6,8,9,12,14,50}
	- Min=1, Max=50
	- Median=8
	- Q1 (trung vị của {1,2,3,6}) = (2+3)/2 = 2.5
	- Q3 (trung vị của {9,12,14,50}) = (12+14)/2 = 13
	- IQR = Q3-Q1 = 10.5
	- Giới hạn râu:
		- Nửa dưới: max(Min, Q1-1.5\*IQR) = max(1, 2.5-1.5\*10.5) = 1
		- Nửa trên: min(Max, Q3+1.5\*IQR) = min(50, 13+1.5\*10.5) = 28.75
		- Giới hạn cần tìm: [1, 28.75]

	- Tổng hợp boxplot:
		- Min: 1, Q1: 2.5, Median: 8, Q3: 13, Max: 14
		- Giá trị ngoại lai: 50



## References
