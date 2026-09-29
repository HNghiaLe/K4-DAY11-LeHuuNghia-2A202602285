# Exit ticket

Đọc `docs/10-svm360-reading-vi.md` trước khi trả lời câu 1–2. Các câu về zone, `why`, rework, parking và sampling
đã nằm trong file tương ứng nên không hỏi lại ở đây.

1. Một vật ở vùng seam giữa hai camera thật xuất hiện với hai box khác nhau: đó là lỗi `DUPLICATE` hay cần một quy
   tắc riêng? Vì sao?
   *Trả lời*: Đây không phải lỗi `DUPLICATE` mà là một trường hợp hợp lệ cần quy tắc riêng. Vì vùng chồng (seam) cho phép hai camera cùng nhìn thấy một vật từ hai góc khác nhau, mỗi camera cần gán một box độc lập. Việc hợp nhất (fusion) hay xóa box thuộc về hệ thống xử lý phía sau (dựa trên policy và calibration) chứ không tự quyết định gộp ở bước gán nhãn 2D trên từng ảnh gốc.

2. Một vật đi qua nhiều frame trên cùng camera: khi nào giữ cùng track ID, khi nào thêm keyframe hoặc trạng thái
   Outside? Nêu bằng chứng sẽ cần trước khi nối track qua hai camera.
   *Trả lời*: Giữ cùng track ID khi vật còn đang xuất hiện và di chuyển liên tục. Thêm keyframe khi box có sự thay đổi lớn về hình học. Chuyển sang `Outside` khi vật ra khỏi trường nhìn. Để nối track qua hai camera, cần có timestamp đồng bộ, calibration và chính sách (policy output) rõ ràng về việc định danh liên camera.

3. Nhìn lại cả buổi: một chỗ bạn tin nhãn mình đúng nhưng reference hoặc người soát nghĩ khác (dẫn frame/`object_ref`),
   bạn đã xử lý thế nào, và nếu làm lại slice này bạn sẽ đổi gì trong cách làm?
   *Trả lời*: Đối với một số lỗi `BOX_GEOMETRY`, tôi tin mình đã vẽ đúng viền vật thể nhưng người soát cho rằng hơi lẹm ra ngoài khoảng trống. Tôi đã ghi nhận finding, đối chiếu lại luật tight box (R01, R05) và lập luận giữ nguyên (`keep_with_reason`) khi thực sự mép xe sát viền. Nếu làm lại, tôi sẽ đọc kỹ các `edge_cases` và thống nhất với team về biên độ chấp nhận lẹm trước khi làm task.
