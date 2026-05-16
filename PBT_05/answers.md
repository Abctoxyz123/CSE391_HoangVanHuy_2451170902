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

Câu A3

| Chiều rộng màn hình | `.container` width |
|---------------------|--------------------|
| 375px (iPhone SE) | 375px |
| 600px | 540px |
| 800px | 720px |
| 1000px | 960px |
| 1400px | 1140px |

Câu A4

1. Variables ($primary-color)
- ý tưởng: lưu giá trị vào biến để tái sử dụng
- Ví dụ:
```css
$primary-color: #3498db;
$text-color: white;

.button {
    background: $primary-color;
    color: $text-color;
}
```
- Compile ra CSS
```css
.button {
    background: #3498db;
    color: white;
}
```
2. Nesting (CSS lồng nhau)
- Ý tưởng: Viết selector theo cấu trúc HTML thật.

Ví dụ:
```css
.navbar {
    background: black;

    ul {
        list-style: none;
    }

    li {
        display: inline-block;
    }

    a {
        color: white;

        &:hover {
            color: yellow;
        }
    }
}
```
Compile ra CSS
```css
.navbar {
    background: black;
}

.navbar ul {
    list-style: none;
}

.navbar li {
    display: inline-block;
}

.navbar a {
    color: white;
}

.navbar a:hover {
    color: yellow;
}
```
3. Mixins(@mixin, @include)
- Ý tưởng: Tạo "template CSS" tái sử dụng được. Giống function trong lập trình.

Ví dụ
```scss
@mixin flex-center {
    display: flex;
    justify-content: center;
    align-items: center;
}

.box {
    @include flex-center;
    height: 200px;
}
```

Compile ra CSS
```css
.box {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 200px;
}
```
4. @extend/Inheritance
- Ý tưởng: Cho class kế thừa CSS từ class khác

Ví dụ
```scss
.button {
    padding: 10px 20px;
    border-radius: 8px;
    color: white;
}

.success-button {
    @extend .button;
    background: green;
}

.error-button {
    @extend .button;
    background: red;
}
```

Compile ra CSS
```css
.button,
.success-button,
.error-button {
    padding: 10px 20px;
    border-radius: 8px;
    color: white;
}

.success-button {
    background: green;
}

.error-button {
    background: red;
}
```

Giải thích tại sao trình duyệt không đọc được .scss?

Vì: SCSS không phải ngôn ngữ chuẩn mà browser hiểu.

Browser chỉ hiểu:
- HTML
- CSS
- JS

Cần bước gì để chuyển SCSS --> CSS

Cần compile(biên dịch) từ SCSS --> CSS

Các công cụ phổ biến: Live Sass Compiler, Sass CLI, Vite,...

Câu C1

- navigation ở 1440px nằm ngang và hiện đầy đủ category: thời sự, kinh doanh, thể thao, giải trí,...
- không có hamburger

- layout chia thành nhiều vùng: main content + sidebar + widgets
- tin tức hiển thị:
    + nhiều cột
    + nhiều block song song
- Elements bị ẩn trên mobile: sidebar, widget phụ, nhiều category, block nhỏ, quảng cáo lớn,...
- font-size có thay đổi