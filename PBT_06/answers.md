Câu A1

```
Mobile < 768px
┌──────────────┐
│    Box 1     │
└──────────────┘

┌──────────────┐
│    Box 2     │
└──────────────┘

┌──────────────┐
│    Box 3     │
└──────────────┘

┌──────────────┐
│    Box 4     │
└──────────────┘
```
```
Tablet 768px - 991px
┌──────────────┬──────────────┐
│    Box 1     │    Box 2     │
└──────────────┴──────────────┘

┌──────────────┬──────────────┐
│    Box 3     │    Box 4     │
└──────────────┴──────────────┘
```
```
Desktop >= 992px
┌──────┬──────┬──────┬──────┐
│Box 1 │Box 2 │Box 3 │Box 4 │
└──────┴──────┴──────┴──────┘
```
| Kích thước | < 768px | 768px - 991px | ≥ 992px |
|------------|---------|---------------|---------|
| Số cột | 1 cột | 2 cột | 4 cột |
| Box layout | 1 box/hàng | 2 box/hàng | 4 box/hàng |

Câu hỏi thêm: `col-md-6` nghĩa là khi màn hình >=md breakpoint thì phần tử chiếm 6/12 cột

Câu A2

1. Giải thích class d-none d-md-block. Element này hiển thị khi nào, ẩn khi nào?

Class `d-none d-md-block` tức là khi độ rộng của trang nhỏ hơn md thì phần tử này sẽ không hiển thị, còn từ md trở lên thì sẽ hiển thị dưới dạng block.

2. Liệt kê 5 spacing utilities (margin/padding) và giải thích. VD: mt-3, px-4, mb-auto

| Utility | Ý nghĩa | Giải thích |
|------------|---------|--------------|
| mt-3 | margin-top | Tạo khoảng cách phía trên phần tử |
| mb-auto | margin-bottom: auto | Tự động đẩy khoảng cách dưới, hay dùng với flex |
| px-4 | padding-left + padding-right | Tạo padding ngang 2 bên |
| py-2 | padding-top + padding-bottom | Tạo padding trên và dưới |
| mx-auto | margin-left + margin-right: auto | Căn giữa phần tử theo chiều ngang |

3. Sự khác nhau giữa .container, .container-fluid, .container-md?

| Class | Đặc điểm |
|------------|---------|
| `container` | Có max-width theo từng breakpoint |
| `container-fluid` | Luôn full chiều ngang 100% |
| `container-md` | Full width ở mobile, có max width tử md trở lên |

