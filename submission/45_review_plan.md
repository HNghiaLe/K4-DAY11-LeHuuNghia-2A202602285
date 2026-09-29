# Kế hoạch review từ lỗi quan sát được

Từ `findings.csv` và `zone_table.md`, chọn **hai lát cắt của bài ADASIND một camera** cần review trước. Bảng này
giải thích dữ liệu thật bạn vừa làm; nó không thay cho kế hoạch bốn camera giả lập ở `45_sampling_plan.csv`.

| Lát cắt / frame | Số ca và loại lỗi | Vì sao review trước | Bằng chứng cần giữ |
|---|---|---|---|
| M_only / L_only | Tập trung vào lỗi MISSING (Model miss nhiều ở zone M) | Model miss hệ thống ở rìa xa. Cần kiểm tra để đưa ra hướng dẫn khắc phục hoặc bổ sung dữ liệu cho model | Lưu các finding `MISSING` và ảnh chụp minh họa. |
| Các ca BOX_GEOMETRY | Có 3 lỗi lẹm viền xe | Đây là lỗi do không hiểu rõ quy tắc lẹm/chạm viền của người gán nhãn, dễ gây sai hàng loạt | Giữ bảng conflict và QA overlay |

Giới hạn của kết luận từ ba frame ADASIND: Số lượng frame quá ít để thống kê và khái quát tỷ lệ lỗi chung cho toàn bộ tập dữ liệu, có thể bị nhiễu do trùng lặp bối cảnh.

## Chuyển sang kế hoạch bốn camera giả lập

Cách soát độ phủ của 200 frame ở `45_sampling_plan.csv` (kể cả tránh đếm nhiều frame liền nhau trong cùng cảnh
như nhiều ca độc lập), và vì sao kế hoạch đó chỉ giúp tìm ca cần soi, chưa đo được tỷ lệ lỗi: Kế hoạch này giúp khám phá (explore) các ca khó từ nhiều điều kiện thời tiết, bối cảnh, camera khác nhau. Tuy nhiên, nó dùng kiểu lấy mẫu có chủ đích (purposive sampling) chứ không ngẫu nhiên (random sampling), do đó chỉ tìm ra loại lỗi chứ không ước lượng chuẩn xác được tỷ lệ phần trăm lỗi trên toàn dataset 50,000 frame.
