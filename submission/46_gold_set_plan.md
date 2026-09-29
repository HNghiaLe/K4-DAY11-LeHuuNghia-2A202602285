# Đề xuất gold set theo camera — tình huống giả lập

**Đầu bài:** 50.000 frame từ bốn camera SVM, ngân sách chọn 200 frame để review/gold. Đây là tình huống trên slide,
**không phải** 50.000 frame có trong repo. Phân bổ đúng 200 ở `45_sampling_plan.csv` cho bốn camera, mỗi camera có
normal và hard slice. “Gold set” ở đây là **kế hoạch tạo** reference sau kiểm chứng, không phải teaching reference
ADASIND hoặc nhãn bạn vừa vẽ. Nếu cần, dùng `notebooks/day11-svm360-colab.ipynb` để thử tổng phân bổ; notebook
không làm thay phần lý do.

| camera_id | Hard case cần chọn | Vì sao dễ sai | Annotation space / calibration cần giữ | Cách review trước khi gọi là gold |
|---|---|---|---|---|
| front | Xe ở xa, người đi bộ nhỏ | Dễ miss do kích thước quá nhỏ trong fisheye | Giữ đúng thông số fisheye, zone `M_only` | Review chéo 2 annotator, so sánh BEV |
| rear | Xe máy bám sát đuôi xe | Dễ lẹm vào ego_body, điểm mù lớn | Chú ý mask ego_body, giữ nguyên méo rìa | Kiểm tra lớp mask ego_body có che khuất không |
| left | Xe máy lách lên từ bên trái | Vùng seam chồng với front, dễ duplicate | Cần timestamp đồng bộ với front | Kiểm tra ID track chéo với cam front |
| right | Chướng ngại vật tĩnh sát lề phải | Mờ, méo, khó phân biệt với vỉa hè | Cần độ phân giải cao tại zone `L_only` | So sánh với dữ liệu lidar nếu có để confirm |

- Khi nào cần refresh gold set (đổi camera, calibration hoặc rule): Khi có bản cập nhật guideline (rule mới), đổi cấu hình góc đặt camera trên xe, hoặc thuật toán de-warp thay đổi.
- Một ca seam/cross-camera cần policy và evidence trước khi ghép hai box: Cần timestamp đồng bộ và thông số calibration chính xác giữa hai camera để xác định vị trí tuyệt đối của xe trước khi gộp chung một ID track.
- Vì sao peer agreement hoặc quality report trên ảnh một camera chưa chứng minh gold set đúng cho cả bốn camera: Vì ảnh đơn không thể hiện được tính nhất quán không gian và thời gian khi xe di chuyển qua lại giữa các camera (đặc biệt vùng seam chồng lấp).
