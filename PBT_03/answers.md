Câu A1

1. Inline CSS
`<p style="color: red; font-size: 16px;">Đại học Thủy Lợi.</p>`
- Ưu điểm
    + Dễ dàng áp dụng nhanh để kiểm tra (test) hoặc sửa lỗi giao diện ngay lập tức.
    + Độ ưu tiên (specificity) rất cao, dễ dàng đè lên các style khác.
- Nhược điểm
    + Làm code HTML trở nên rối mắt và khó đọc.
    + Không thể tái sử dụng. Nếu bạn có 10 thẻ <p> cần chung một kiểu, bạn phải copy/paste đoạn style đó 10 lần.
    + Rất khó bảo trì khi dự án lớn lên.
- Khi nào nên dùng
    + Khi cần test nhanh một thuộc tính CSS.
    + Khi viết HTML template cho Email (vì nhiều trình duyệt email không hỗ trợ External hoặc Internal CSS tốt).
    + Khi style được tạo ra động (dynamically) bằng JavaScript.
2. Internal CSS
```html
<head>
    <style>
        p {
            color: blue;
            font-size: 18px;
        }
    </style>
</head>
<body>
    <p>Đại học Thủy Lợi.</p>
</body>
```
- Ưu điểm
    + Gom toàn bộ style của một trang vào một chỗ, dễ quản lý hơn Inline.
    + Không cần gửi thêm một request (yêu cầu) tới server để tải file CSS riêng.\
- Nhược điểm
    + Làm tăng dung lượng của file HTML.
    + Không thể chia sẻ và tái sử dụng style cho các trang HTML khác trong cùng một website. Khách truy cập không thể lưu cache CSS này cho các trang sau.
- Khi nào nên dùng
    + Khi xây dựng một trang web chỉ có duy nhất 1 trang (Landing page đơn giản).
    + Khi trang web có những style đặc thù không xuất hiện ở bất kỳ trang nào khác.
3. External CSS
- Trong file style.css:
    + 
    p {
    color: green;
    font-size: 20px;
    }
    + 
    ```html
    <head>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <p>Đại học Thủy Lợi.</p>
    </body>
    ```
- Ưu điểm
    + Tối ưu nhất cho bảo trì: Giúp tách biệt hoàn toàn nội dung (HTML) và giao diện (CSS). Mã nguồn sẽ rất gọn gàng và dễ nhìn khi bạn làm việc trên các trình soạn thảo code.
    + Tái sử dụng cao: Một file CSS có thể được liên kết và sử dụng cho hàng trăm trang HTML khác nhau.
    + Tăng tốc độ tải trang: Trình duyệt sẽ lưu cache (bộ nhớ tạm) file CSS này ở lần tải đầu tiên, giúp các trang khác trong website tải nhanh hơn.
- Nhược điểm
    + Trình duyệt phải mất thêm một HTTP request để tải file .css về (tuy nhiên với mạng internet hiện nay, nhược điểm này là không đáng kể).
- Khi nào nên dùng 
    + Gần như trong mọi dự án web thực tế, đặc biệt là các trang web có nhiều trang con hoặc khi làm việc nhóm.
- Câu hỏi thêm: Cách nào "thắng"?
Nếu cùng 1 element (phần tử) có cả 3 cách CSS đồng thời áp dụng, thì Inline CSS sẽ "thắng" (được áp dụng cuối cùng).

Câu A2
1. h1
→ Chọn tất cả thẻ `<h1>`
- ShopTLU
2. .price
→ Chọn tất cả phần tử có class price
- 25.990.000đ
- 45.990.000đ
3. #app header
→ Chọn `<header>` nằm trong phần tử có id="app"
- Toàn bộ header chứa:
    + ShopTLU
    + Home
    + Product
    + About
4. .nav a:first-child
→ Không có class nav trong HTML yêu cầu
- Không chọn được gì
5. .product.featured h2
→ Chọn `<h2>` nằm trong phần tử có 2 class: product và featured
Macbook Pro
6. article > p
→ Chọn thẻ `<p>` là con của `<article>`
- 25.990.000đ
- Mô tả sản phẩm...
- 45.990.000đ
- Mô tả sản phẩm...
7. a[href^="/]
→ Chọn `<a>` có href bắt đầu bằng "/"
- Home
- Products
- About
8. .top-bar.dark h1
→ Chọn `<h1>` trong phần tử có 2 class: top-bar và dark
- ShopTLU

Câu A3

```css
/* Trường hợp 1: content-box (mặc định) */
.box-1 {
    width: 400px;
    padding: 20px;
    border: 5px solid black;
    margin: 10px;
}
→ Chiều rộng hiển thị = 450px
→ Không gian chiếm trên trang = 470px

/* Trường hợp 2: border-box */
.box-2 {
    box-sizing: border-box;
    width: 400px;
    padding: 20px;
    border: 5px solid black;
    margin: 10px;
}
→ Chiều rộng hiển thị = 400px
→ Kích thước content thực tế = 350px
→ Không gian chiếm trên trang = 420px

/* Trường hợp 3: Margin collapse */
.box-a { margin-bottom: 25px; }
.box-b { margin-top: 40px; }
→ Khoảng cách giữa box-a và box-b = 40px
→ Giải thích tại sao KHÔNG PHẢI 65px
→ Đây là hiện tượng Margin Collapsing. Trong CSS, khi hai margin dọc (trên và dưới) của các phần tử nằm cạnh nhau (block-level elements) chạm vào nhau, chúng sẽ không cộng dồn. Thay vào đó, trình duyệt sẽ lấy giá trị lớn nhất trong các margin đó làm khoảng cách thực tế.
```

**Nâng cao:** Nếu `.box-a` có `margin-bottom: -10px` và `.box-b` có `margin-top: 40px`, khoảng cách = 30px