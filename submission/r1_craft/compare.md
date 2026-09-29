# So sánh L với R

Chỉ số L/R là thứ tự box cao ≥ H=40 trong từng frame, theo thứ tự XML; bắt đầu từ 1.
Box L trong ignore_region được báo IGNORE_SCOPE, không tính SPURIOUS.

## adasind_152940.jpg
- R6 mid MISSING
## adasind_167700.jpg
- L3+R4 center WRONG_CLASS
- L5 mid SPURIOUS
- L6 mid SPURIOUS
- L7+R5 center BOX_GEOMETRY
- L8+R3 mid WRONG_CLASS
- R1 center MISSING
- R2 mid MISSING
- R9 mid MISSING
## adasind_212280.jpg
- L2 mid IGNORE_SCOPE
- L3+R3 edge WRONG_CLASS

## Theo zone
| zone | n_ref | matched | missing | spurious |
|---|---|---|---|---|
| center | 10 | 7 | 3 | 2 |
| mid | 6 | 2 | 4 | 3 |
| edge | 2 | 1 | 1 | 1 |
