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

Bài B2

- Hộp 1 (content-box): chiều rộng thực tế = 350 px (đo từ DevTools)
- Hộp 2 (border-box): chiều rộng thực tế = 300 px (đo từ DevTools)
- Giải thích sự khác biệt:
    + Hộp 1 (content-box): Chiều rộng thực tế sẽ là:
    300px(width)+20px∗2(padding)+5px∗2(border)=350px.
    Lý do: Với content-box, thuộc tính width chỉ áp dụng cho nội dung bên trong. Padding và Border được cộng thêm vào bên ngoài, làm hộp phình to ra.
    + Hộp 2 (border-box): Chiều rộng thực tế sẽ là: 300px.
    Lý do: Với border-box, width bao gồm luôn cả nội dung, padding và border. Khi bạn tăng padding, trình duyệt sẽ tự động co phần nội dung lại để giữ nguyên tổng kích thước là 300px.

Bài B3
1. p    (0,0,1)
2. .text    (0,1,0)
3. .text.highlight  (0,2,0)
4. p.text   (0,1,1)
5. p.text.highlight (0,2,1)
6. #demo    (1,0,0)
7. #demo.text   (1,1,0)
8. #demo.text.highlight (1,2,0)
9. p#demo.text.highlight    (1,2,1)
10. `<p .... style="black">Hello World</p>` (1,0,0,0)

- Element cuối cùng hiển thị màu đen vì inline style có độ ưu tiên cao nhất (1,0,0,0) so với các Selector (ID,Class,Type), do đó nó sẽ ghi đè lên tất cả các rule được viết trong file CSS bên ngoài hoặc thẻ `<style>`
- Thay đổi thứ tự rules trong CSS file không làm thay đổi kết quả vì cơ chế của CSS dựa trên Specificity chứ không phải thứ tự khai báo(ngoại trừ trường hợp các selector có cùng độ ưu tiên).


Câu C1
1. Tính chiều rộng thực tế của sidebar và content (content-box!)
- Chiều rộng thực tế của sidebar = 300px + 20px + 20px + 1px + 1px = 342px
- Chiều rộng thực tế của content = 660px + 30px + 30px + 1px + 1px = 722px
2. Giải thích tại sao layout bị vỡ
- Layout bị vỡ vì tổng chiều rộng của sidebar và content lớn hơn chiều rộng của container
3. Đưa ra 2 cách sửa khác nhau (1 cách dùng border-box, 1 cách không dùng)
- Cách 1: sử dụng property (box-sizing: bored-box) cho class sidebar và content
- Cách 2: Tính toán lại các giá trị padding và border từ width gốc để tổng không vượt quá 960px.

Câu C2
1. "Sản phẩm A" (h2) có font-size = 20px và color = green
    - Thẻ h2 này được kế thừa từ .container có font-size: 14px nhưng lại chịu tác động từ .card .title nên font-size của nó là 20px
    - Có 2 quy tắc tác động vào thẻ này để set màu:
        1. #featured .title { color: red; }
        2. .highlight { color: green !important; }
    - quy tắc 2 có !important nên màu được hiển thị là green
2. "Mô tả sản phẩm" (p trong card featured) có color = blue
    - có quy tắc .card p { color: inherit; } áp dụng trực tiếp lên thẻ p này. Từ khóa inherit (kế thừa) buộc trình duyệt phớt lờ các giá trị mặc định và đi tìm màu của phần tử cha trực tiếp chứa nó.
    - Cha của nó là thẻ `<div class="card" id="featured">`. Phần tử cha này đang được áp dụng quy tắc .card { color: blue; }. Vì vậy, thẻ p "vay mượn" màu xanh dương này từ cha của mình.
3. "Sản phẩm B" (h2) có font-size = 20px và color = blue
    - Có selector .card .title tác động vào thẻ này nên font-size sẽ là value của selector này.
    - Thẻ h2 kế thừa từ thẻ cha `<div class="card">`. Thẻ cha này đang có color: blue;. Do đó, thẻ h2 tự động kế thừa màu xanh dương.
4. "Mô tả sản phẩm B" (p.highlight) có color = green
    - có 2 quy tắc cùng lúc tác động lên thẻ p này
        1. .card p{color: inherit} (Specificity: 0-1-1)
        2. .highlight{color: green !important;} (Specificity: 0-1-0)
    - có !important nên quy tắc 2 sẽ có ưu tiên cao nhất và màu sẽ được hiển thị theo quy tắc số hai