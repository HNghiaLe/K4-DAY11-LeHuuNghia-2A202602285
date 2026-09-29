# Đối chiếu chất lượng cục bộ — rectangle

Teaching reference, không phải gold set đã phê duyệt; không có điểm đạt tự động.
Nguồn: export r1_craft đã khóa SHA256 `d96e623dc74f6a868dcc5def2ea1dc4cf113c87a9a45fe70b351a0f99be8d2e9`; slice `B3-center`.
Ghép hình học greedy một-một theo IoU ≥ 0.50, rồi so class; H ≥ 40 px.
Box trái nằm chủ yếu trong ignore_region reference không tính. Polygon, polyline, track không được chấm.
Đây là phép tính offline của lab, không phải báo cáo hay kết quả tương đương CVAT Premium.

Frame được tính: adasind_152940.jpg, adasind_167700.jpg, adasind_212280.jpg. Frame thiếu trong export: không.
TP=10; FP=6; FN=8; số lần đối chiếu=21; mean IoU của TP=0.868.

| Chỉ số | Micro | Macro | Nhãn thấp nhất |
|---|---:|---:|---:|
| accuracy | 0.476 | 0.889 | 0.714 |
| precision | 0.625 | 0.321 | 0.000 |
| recall | 0.556 | 0.354 | 0.000 |
| jaccard | 0.417 | 0.265 | 0.000 |
| dice | 0.588 | 0.336 | 0.000 |

| Nhãn | TP | FP | FN | Accuracy | Precision | Recall | Jaccard | Dice |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Bike | 5 | 3 | 3 | 0.714 | 0.625 | 0.625 | 0.455 | 0.625 |
| Bus | 0 | 0 | 1 | 0.952 | 0.000 | 0.000 | 0.000 | 0.000 |
| Car | 0 | 1 | 1 | 0.905 | 0.000 | 0.000 | 0.000 | 0.000 |
| Pedestrian | 0 | 0 | 2 | 0.905 | 0.000 | 0.000 | 0.000 | 0.000 |
| ThreeWheeler | 1 | 1 | 1 | 0.905 | 0.500 | 0.500 | 0.333 | 0.500 |
| Truck | 4 | 1 | 0 | 0.952 | 0.800 | 1.000 | 0.800 | 0.889 |

| Frame | TP | FP | FN | Accuracy | Precision | Recall |
|---|---:|---:|---:|---:|---:|---:|
| adasind_152940.jpg | 5 | 0 | 1 | 0.833 | 1.000 | 0.833 |
| adasind_167700.jpg | 3 | 5 | 6 | 0.250 | 0.375 | 0.333 |
| adasind_212280.jpg | 2 | 1 | 1 | 0.667 | 0.667 | 0.667 |

Confusion matrix: hàng = teaching reference; cột = export đã khóa.
`<missing>` là thiếu box; `<extra>` là box thừa. Xem `local_quality_confusion.csv`.

| Reference \ Export | Bike | Bus | Car | Pedestrian | ThreeWheeler | Truck | <missing> |
|---|---:|---:|---:|---:|---:|---:|---:|
| Bike | 5 | 0 | 0 | 0 | 0 | 0 | 3 |
| Bus | 0 | 0 | 1 | 0 | 0 | 0 | 0 |
| Car | 0 | 0 | 0 | 0 | 0 | 1 | 0 |
| Pedestrian | 1 | 0 | 0 | 0 | 0 | 0 | 1 |
| ThreeWheeler | 0 | 0 | 0 | 0 | 1 | 0 | 1 |
| Truck | 0 | 0 | 0 | 0 | 0 | 4 | 0 |
| <extra> | 2 | 0 | 0 | 0 | 1 | 0 | 0 |

Chi tiết xung đột trong `local_quality_conflicts.csv`; dữ liệu máy đọc trong `local_quality.json`.
Mismatching label đóng góp một FP cho class vẽ và một FN cho class reference; attribute khác được báo riêng.
Micro accuracy đếm mỗi cặp ghép sai class là một lần đối chiếu; Jaccard đếm cả FP và FN.
Macro/worst bỏ nhãn không xuất hiện ở cả hai phía; chỉ số không có mẫu là N/A.
