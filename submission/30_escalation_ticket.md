# Escalation ticket

## Ticket 1

- **Frame:** adasind_152940.jpg
- **Ảnh chụp:** submission/screenshots/adasind_152940_escalation.png
- **Expected impact:** Model liên tục miss các xe ở quá xa rìa camera (zone `M_only`), có thể dẫn đến việc model dự đoán sai hoặc bỏ lỡ đối tượng khi chạy thực tế.
- **Owner:** `ai_team`
- **Recommendation:** Bổ sung thêm dữ liệu training ở các góc fisheye xa, hoặc điều chỉnh thuật toán cho phép nhận diện tốt hơn ở vùng rìa bị méo nhiều.
