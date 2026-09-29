# Quan sát vạch ô đỗ

- Hai vạch `parking_line` đã vẽ (mô tả vị trí trong ảnh): Các vạch sơn ngắn chia ô đỗ xe nằm ở phần nửa dưới (tiền cảnh) của bức ảnh.
- Một vạch/dấu sơn hoặc biên **không** vẽ, và vì sao: Không vẽ vạch sơn dài vắt ngang bãi, vì nó là vạch phân làn/dẫn hướng xe chạy chứ không phải vạch ranh giới chia từng ô đỗ riêng lẻ.
- Polygon `free_space` dừng ở đâu; có phần bị che nào không: Khoanh trong khoảng mặt đường nhựa trống, dừng lại ở mép các ô đỗ xe, không lấn vào chiếc xe màu đỏ hay bãi cỏ phía sau.
- Ca chưa chắc cần hỏi người soát (nếu không có, ghi “không có”): Không có.
