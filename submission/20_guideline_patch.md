# Guideline patch

- **Rule mới đề xuất:** Phải bao gồm cả gương chiếu hậu (rearview mirror) vào trong bounding box của class `car` và `truck` nếu nó nằm trong trường nhìn rõ ràng.
- **Áp dụng cho:** Class `car`, `truck` (quy tắc vẽ box)
- **Vì sao luật hiện tại (`docs/02-rules-vi.md`) không đủ:** Luật hiện tại (R01/R05) ghi "vẽ sát viền" nhưng không nêu rõ có bao gồm các phần thò ra như gương chiếu hậu hay anten không, dẫn đến mỗi người làm một kiểu (annotator bỏ qua, model thì vẽ vào).
- **`rules_version` mới:** v1.1.0
- **Hiệu lực từ:** Round `rework` trở đi
