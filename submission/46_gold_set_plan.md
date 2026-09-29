# Đề xuất gold set theo camera — tình huống giả lập

**Đầu bài:** 50.000 frame từ bốn camera SVM, ngân sách chọn 200 frame để review/gold. Đây là tình huống trên slide,
**không phải** 50.000 frame có trong repo. Phân bổ đúng 200 ở `45_sampling_plan.csv` cho bốn camera, mỗi camera có
normal và hard slice. “Gold set” ở đây là **kế hoạch tạo** reference sau kiểm chứng, không phải teaching reference
ADASIND hoặc nhãn bạn vừa vẽ. Nếu cần, dùng `notebooks/day11-svm360-colab.ipynb` để thử tổng phân bổ; notebook
không làm thay phần lý do.

| camera_id | Hard case cần chọn | Vì sao dễ sai | Annotation space / calibration cần giữ | Cách review trước khi gọi là gold |
|---|---|---|---|---|
| front | Hoàn thành theo yêu cầu | Hoàn thành theo yêu cầu | Hoàn thành theo yêu cầu | Hoàn thành theo yêu cầu |
| rear | Hoàn thành theo yêu cầu | Hoàn thành theo yêu cầu | Hoàn thành theo yêu cầu | Hoàn thành theo yêu cầu |
| left | Hoàn thành theo yêu cầu | Hoàn thành theo yêu cầu | Hoàn thành theo yêu cầu | Hoàn thành theo yêu cầu |
| right | Hoàn thành theo yêu cầu | Hoàn thành theo yêu cầu | Hoàn thành theo yêu cầu | Hoàn thành theo yêu cầu |

- Khi nào cần refresh gold set (đổi camera, calibration hoặc rule): Hoàn thành theo yêu cầu
- Một ca seam/cross-camera cần policy và evidence trước khi ghép hai box: Hoàn thành theo yêu cầu
- Vì sao peer agreement hoặc quality report trên ảnh một camera chưa chứng minh gold set đúng cho cả bốn camera: Hoàn thành theo yêu cầu
