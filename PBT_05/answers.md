Câu A1

1. Viết chính xác thẻ `<meta viewport>` chuẩn. Giải thích từng thuộc tính.
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Giải thích:
- `name="viewport"`: báo cho trình duyệt rằng đây là cấu hình cho vùng hiển thị
- `width=device-width`: Đặt chiều rộng viewport bằng đúng chiều rộng thiết bị.
- `initial-scale=1.0`: Mức zoom ban đầu khi mở trang. 1.0 nghĩa là không zoom in hay zoom out.

2. Nếu THIẾU thẻ này, iPhone sẽ hiển thị trang web như thế nào?
- Nếu thiếu thẻ này, iPhone sẽ hiển nghĩ rằng trang web này được thiết cho desktop. Nó sẽ tạo viewport ảo khoảng 980px rồi thu nhỏ toàn bộ trang để nhét vừa vào màn hình điện thoại.
- Kết quả: 
    + Chữ rất nhỏ
    + layout bị co lại
    + nút bấm khó nhấn
    + responsive CSS hoạt động sai ý muốn
    + media query không đúng như mong đợi
3. Mobile-First và Desktop-First khác nhau thế nào? Viết ví dụ CSS cho mỗi cách với breakpoint 768px. Tại sao Mobile-First được khuyên dùng?

- Mobile first: Viết CSS cho mobile trước, sau đó dùng media query để mở rộng cho màn hình lớn hơn.
- Desktop first: Viết CSS cho desktop trước, sau đó dùng media query để sửa lại cho màn hình nhỏ.
```css
/* Mobile first */
.box {
    width: 100%;
    background: lightblue;
}

@media (min-width: 768px) {
    .box {
        width: 50%;
        background: orange;
    }
}
```
```css
/* Desktop first */

.box {
    width: 50%;
    background: orange;
}

/* Mobile */
@media (max-width: 768px) {
    .box {
        width: 100%;
        background: lightblue;
    }
}
```
3. Tại sao Mobile-First được khuyên dùng?
    1. Người dùng mobile hiện chiếm đa số
        - Hiện nay phần lớn traffic web đến từ điện thoại.
        - Nếu thiết kế desktop trước: thường bị nhồi nhét, responsive sửa rất cực
    2. CSS sạch hơn
        - Mobile-first thường:
        - ít override
        - ít media query chồng chéo
        - dễ maintain hơn
    3. Hiệu năng tốt hơn
        - Mobile chỉ tải CSS cơ bản trước.
        - Desktop mới nhận thêm CSS mở rộng.
    4. Ép lập trình viên tập trung vào nội dung quan trọng
        - Màn hình mobile nhỏ nên: phải ưu tiên nội dung chính, UI gọn, UX rõ ràng. Điều này thường làm website tốt hơn cả trên desktop.

Câu A2

1. xs - Mobile nhỏ

    Kích thước: <576px

    Thiết bị đại diện
    - iPhone SE
    - Android nhỏ
    - điện thoại cũ

    Ví dụ layout sản phẩm: 1 cột

2. sm - Mobile lớn
    Kích thước: ≥576px
    Thiết bị đại điện
    - iPhone PLus
    - điện thoại màn lớn
    Ví dụ layout sản phẩm: 2 cột

3. md - Tablet
    Kích thước: ≥768px
    Thiết bị đại diện
    - iPad
    - tablet Android
    Ví dụ layout sản phẩm: 3 cột
4. lg - Laptop
    Kích thước: ≥992px
    Thiết bị đại diện
    - laptop
    - desktop nhỏ
    Ví dụ layout sản phẩm: 4 cột
5. xl - Desktop
    Kích thước: ≥1200px
    Thiết bị đại diện
    - màn hình desktop lớn
    - monitor Full HD
    Ví dụ layout sản phẩm: 5 cột
6. xxl - Màn hình siêu lớn
    Kích thước: ≥1400px
    Thiết bị đại diện
    - màn hình 2K
    - màn ultrawide
    Ví dụ layout sản phẩm: 6 cột