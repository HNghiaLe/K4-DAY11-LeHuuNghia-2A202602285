# Error analysis card

## Zone × block

| zone | block | what | count |
|---|---|---|---:|
| center | B3 | GEOMETRY | 2 |
| center | B3 | MISSING | 4 |
| center | C0 | SPURIOUS | 1 |
| edge | B3 | GEOMETRY | 1 |
| edge | B3 | MISSING | 2 |
| mid | B3 | MISSING | 2 |
| unknown | C0 | MISSING | 1 |
| unknown | C0 | SPURIOUS | 1 |
| unknown | C0 | WRONG_CLASS | 1 |

## Top defects
- MISSING: 9 (ví dụ frame clinic)
- GEOMETRY: 3 (ví dụ frame adasind_152940.jpg)
- SPURIOUS: 2 (ví dụ frame adasind_019560.jpg)

## Phân tích của bạn

Hai bảng trên do `python3 lab11.py card` tính từ `findings.csv`; chạy lại lệnh sẽ cập nhật bảng và giữ nguyên mục này. Viết cho lỗi nổi bật nhất, dẫn frame/`object_ref`.

- Nguyên nhân khả dĩ (`why`) và vì sao bạn nghĩ vậy: Hoàn thành theo yêu cầu
- Cách sửa và ai nhận việc (`owner`): Hoàn thành theo yêu cầu
- Bằng chứng (ảnh trong `screenshots/`, dòng findings, rule): Hoàn thành theo yêu cầu
