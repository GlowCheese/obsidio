
| Status | Tags | Created           |
| ------ | ---- | ----------------- |
|        |      | 16.12.24 11:58 |

### Ý tưởng:
- Bắt đầu từ một phương án chấp nhận được.
- Lặp đi lặp lại bước cải tiến
- Cấu trúc lân cận: tìm những phương án chấp nhận được gần
  với phương án đang xét nhất nhờ thay đổi một số thành phần
- Lân cận $k$-thay đổi: các phương án khác với phương án đang
  xét nhờ thay đổi nhiều nhất $k$ thành phần.
- Dựa trên hai chiến lược: chiến lược tốt nhất và chiến lược tốt hơn.

### Nhận xét
- Không ước lượng được độ tốt của lời giải.
- Lân cận $k$-thay đổi, nếu $k$ lớn thì:
	- nhiều lân cận, dễ tìm nghiệm tốt
	- nhưng độ phức tạp lớn
- Chiến lược tốt nhất:
	- chọn lời giải tốt nhất trong lân cận làm cải tiến
	- bài toán lớn -> hạn chế về thời gian -> có thể không tìm được
- Chiến lược tốt hơn:
	- chọn phương án đầu tiên trong lân cận 
	- cải thiện được hàm mục tiêu.

## References
