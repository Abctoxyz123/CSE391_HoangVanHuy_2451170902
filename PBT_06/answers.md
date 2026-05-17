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

Câu C1

1. Bạn muốn đổi màu $primary từ xanh mặc định sang #E63946. Giải thích quy trình (cần công cụ gì, modify file nào).

    Bước 1: Tạo file SCSS riêng

    Bước 2: Override variable trước khi import Bootstrap
    ```scss
    $primary: #E63946;
    @import "node_modules/bootstrap/scss/bootstrap";
    ```
    Bước 3: Compile SCSS --> CSS: cần các công cụ có thể chuyển đổi từ file .scss --> .css

    Bước 4: Link file CSS custom

2. Vì sao KHÔNG nên override trực tiếp?

- Vấn đề 1: Chỉ sửa được 1 component
- Vấn đề 2: Specificity war
- Vấn đề 3: Khó duy trì, bời sau vài tháng, không ai nhớ class nào bị override
- Vấn đề 4: Mất tính hệ thống: SCSS variables giúp chúng ta có 1 nguồn dữ liệu trung tâm => đổi 1 nơi, toàn hệ thống đổi theo.

Câu C2

1. Số dòng CSS cần viết

CSS thuần
- Có thể lên đến 50-60 dòng CSS

Bootstrap
- chủ yếu dùng utility classes, CSS tự viết rất ít.

2. Thời gian phát triển

CSS thuần

Chậm hơn vì:

+ phải design layout
+ debug responsie
+ fix spacing
+ test breakpoint

Bootstrap

Nhanh hơn cực nhiều

3. Khả năng tùy biến

CSS thuần

Mạnh nhất

Bạn kiểm soát:

+ từng pixel
+ animation
+ architecture
+ design system

Bootstrap

Bị giới hạn theo framework.

4. Khi nào nên dùng Bootstrap

Dùng khi:

- admin dashboard
- CRUD app
- MVP
- prototype
- deadline ngắn
- team nhỏ
- project nội bộ

Không nên khi:

- website cần design độc quyền
- animation phức tạp
- performance cực tối ưu
- UI/UX custom cao
- sản phẩm lớn có design system riêng