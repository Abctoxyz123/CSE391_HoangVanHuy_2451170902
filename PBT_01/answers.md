Câu A1 — HTTP & Browser

1.  
- Bước 1: Trình duyệt kiểm tra cache DNS → nếu chưa có thì gửi yêu cầu đến DNS server để phân giải tên miền shopee.vn thành địa chỉ IP.
- Bước 2: Trình duyệt thiết lập kết nối TCP với server (3-way handshake).
- Bước 3: Nếu là HTTPS, thực hiện TLS handshake để mã hóa kết nối.
- Bước 4: Trình duyệt gửi HTTP request (GET /) đến server.
- Bước 5: Server xử lý và trả về HTTP response (HTML, CSS, JS, hình ảnh...).
- Bước 6: Trình duyệt nhận HTML → parse thành DOM.
- Bước 7: Trình duyệt tải các tài nguyên liên quan (CSS, JS, ảnh...).
- Bước 8: Xây dựng CSSOM và render tree → tiến hành layout và paint để hiển thị trang web.

2. 
![screenshot netword tab](screenshots/Screenshot_tabNetwork.png)
![Request returns cssfile](screenshots/Screenshot_fileCSS.png)

- Status Code request đầu tiên: 200
- Tổng thời gian load trang: 1.57s


Câu A2 — Semantic HTML
Trước khi sửa:
<!-- <div class="header">
    <div class="logo">ShopTLU</div>
    <div class="menu">
        <div><a href="/">Trang chủ</a></div>
        <div><a href="/products">Sản phẩm</a></div>
    </div>
</div>
<div class="main">
    <div class="product">
        <div class="title">iPhone 16 Pro</div>
        <div class="price">25.990.000đ</div>
        <div class="image"><img src="iphone.jpg"></div>
    </div>
</div>
<div class="footer">© 2026 ShopTLU</div> -->

- Website bị Goodle đánh giá SEO thấp vì:
    + sử dụng quá nhiều thẻ div không mang ý nghĩa
- Lỗi semantic:
    + phần header dùng thẻ <div>
    + phần nav dùng thẻ <div>
    + phần main dùng thẻ <div>
    + phần product dùng thẻ <div>
    + không có thuộc tính alt cho ảnh

Sau khi sửa :
<!-- <header>
    <div class="logo">ShopTLU</div>
    <nav>
        <a href="/">Trang chủ</a>
        <a href="/products">Sản phẩm</a>
    </nav>
</header>

<main>
    <article class="product">
        <h1>iPhone 16 Pro</h1>
        <p class="price">25.990.000đ</p>
        <img src="iphone.jpg" alt="iPhone 16 Pro chính hãng">
    </article>
</main>

<footer>
    <p>© 2026 ShopTLU</p>
</footer> -->

Câu A3 — Block vs Inline
![img htmle code](screenshots/Câu_A3.png)

Câu A4
- giải thích sự khác nhau giữa thead,tbody,tfoot
    + thead dùng cho tiêu đề cột
    + tbody dùng để chứa phần dữ liệu chính, các bản ghi
    + tfoot dùng để hiện thị tổng kết 

Bài B3 — Debug HTML
- Lỗi 1: Dòng 1 - khai báo DOCTYPE không đúng chuẩn - sửa lại thành `<!DOCTYPE html>`
- Lỗi 2: Dòng 4 - `<title>` không đóng thẻ - bổ sung thẻ đóng ```<title>Trang web</title>```
- Lỗi 3: Dòng 5 - utf8 viết sai - sửa lại thành ```<meata charset="UTF-8">```
- Lỗi 4: Dòng 8 - thẻ `<h1>` đóng sai - sửa lại ```<h1>Welcome to ShopTLU</h1>```
- Lỗi 5: Dòng 12 - link không hợp lệ href="home" - sửa lại href="#home"
- Lỗi 6: Dòng 12 - thẻ `<h1>` đóng sai - sửa lại ```<a href="#home">Trang chủ</a>```
- Lỗi 7: Dòng 20 - thẻ `<img>` thuộc tính src thiếu "" và alt - sửa lại ```<img src="iphone.jpg" alt="iphone16pro">```
- Lỗi 8: Dòng 22 - đóng sai thứ tự các thẻ - ```<p>Giá: <b>25.990.000đ</b></p>```
- Lỗi 9: Dòng 27 - table thiếu thẻ `<thead>` và `<tbody>` - thêm vào `<thead>` và `<tbody>`
- Lỗi 10: Dòng 29 - dùng `<td>` cho header - dùng `<th>` cho header của bảng
- Lỗi 11: Dòng 40 - dùng 2 `<main>` - bỏ thẻ `<main>` thay bằng `<aside>` vì `<aside>` thường được dùng làm thanh bên để chứa danh mục bài viết
- Lỗi 12: Dòng 45 - không đóng thẻ `<p>` - sửa thành ```<p>Coryright 2026</p>```
- Lỗi 13: Thiếu `<html lang="vi>`
- Lỗi 14: Thiếu `<meta view="viewport" content="width=device-width, initial-scale=1.0">`
- Lỗi 15: Thiếu thẻ đóng `</html>` - thêm thẻ đóng `</html>`

Bài B4 — Phân tích trang web thật
1. Trang web: thegioididong.com
- Thẻ img ở đầu trang ![screenshot <img>](screenshots/Screenshot_TGDD_img.png)
- Thẻ h1 ở đầu trang ![screenshot <header>-<h1>](<screenshots/Screenshot_TGDD header-h1.png>)
- Thẻ header cũng ở phần đầu trang 
- Thẻ footer ở cuối trang ![screenshot <footer>](screenshots/Screenshot_TGDD_footer.png)
2. 
- Không tìm thấy thẻ table được sử dụng trong trang web
3. 
![screenshot <form>](screenshots/Screenshot_TGDD_form.png)
- action: /timkiem
- method: GET (mặc định)
- input types: text

Câu C1
```html
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chi tiết sản phẩm</title>
</head>
<body>
    <header>
        <h1>Logo</h1>
        <nav>
            <ul>
                <li><a href="#">Trang chủ</a></li>
                <li><a href="#">Sản phẩm</a></li>
                <li><a href="#">Liên hệ</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <nav aria-label="breamcrumb">
            <ol>
                <li><a href="#">Trang chủ</a></li>
                <li><a href="#">Điện thoại</a></li>
                <li>iPhone 16</li>
            </ol>
        </nav>
        <section id="product-overview">
            <img src="" alt="ảnh viền trái">
            <img src="" alt="ảnh viền phải">
            <img src="" alt="ảnh máy trước">
            <img src="" alt="ảnh mặt sau">
            <img src="" alt="ảnh trên tay">
            <h2>iPhone 16 Pro Max</h2>
            <p>Giá: 29.000.000đ</p>
            <p>Đánh giá: 5 sao</p>
            <p>Mô tả: iPhone 16 Pro Max là đỉnh cao công nghệ mới nhất của Apple với màn hình LTPO Super Retina XDR lớn hơn, mang lại trải nghiệm thị giác cực kỳ mãn nhãn.
            Máy được trang bị chip A18 Pro mạnh mẽ vượt trội, tối ưu hóa cho các tác vụ AI thông minh và khả năng chơi game đồ họa đỉnh cao mượt mà.
            Hệ thống camera được nâng cấp mạnh mẽ với nút điều khiển Camera Control mới, giúp người dùng quay phim và chụp ảnh chuyên nghiệp chỉ trong một cú chạm.
            Thiết kế khung viền Titan bền bỉ cùng thời lượng pin tốt nhất từ trước đến nay giúp đây trở thành lựa chọn hàng đầu cho người dùng đam mê công nghệ và sự sang trọng.
            </p>
        </section>
        <section>
            <h3>Thông số kỹ thuật</h3>
            <table border="1">
                <thead>
                    <tr>
                        <th>Đặc tính</th>
                        <th>Thông số</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Kích thước màn hình</td>
                        <td>6.7 inch</td>
                    </tr>
                    <tr>
                        <td>Chipset</td>
                        <td>A18 Pro</td>
                    </tr>
                </tbody>
            </table>
        </section>
        <section>
            <h3>Đánh giá từ người dùng</h3>
            <article>
                <h4>Nguyễn Văn A</h4>
                <p>Sản phẩm tốt, giao hàng nhanh</p>
            </article>
            <article>
                <h4>Nguyễn Thị B</h4>
                <p>Máy đẹp, chất lượng phục vụ tốt</p>
            </article>
        </section>
        <aside>
            <h3>Sản phẩm tương tự</h3>
            <ul>
                <li>iPhone 17 Pro Max</li>
                <li>Samsung S26 Ultra</li>
            </ul>
        </aside>
    </main>
    <footer>
        <p>&copy; 2026 CSE391 - Hoàng Văn Huy</p>
    </footer>
</body>
</html>
```
Câu C2
Quan điểm cho rằng dùng thẻ `<div>` cho mọi thứ là một quan điểm không phù hợp với việc phát triển web ở thời điểm hiện tại, bời vì Việc sử dụng thẻ Semantic HTML sẽ mang lại những giá trị về kỹ thuật mà thẻ `<div>` không làm được. Thứ nhất là về SEO. Các con bot của Google không nhìn thấy giao diện giống như con người, chúng đọc cấu trúc code. Vậy nên khi sử dụng các thẻ như `<header>`,`<main>`,hay `<article>`, chúng ta đang cung cấp cho nó một cấu trúc thiết kế rõ ràng, giúp engine tìm kiếm đó hiểu đâu là nội dung quan trọng. Một website toàn thẻ `<div>` sẽ trở nên mờ nhạt và khó xếp hạng cao về bot không phân biệt được đâu là nội dung chính, đâu là nội dung phụ. Thứ hai là Accessibility. Đối với người khiếm thị sử dụng trình đọc mà hình, Semantic HTML là đóng vai trò là các mốc, cho phép họ truy cập một cách nhanh chóng đến các phần khác nhau của trang web. Nếu chỉ dùng `<div>`, trình đọc màn hình sẻ chỉ thấy một khối văn bản vô nghĩa, gây khó khăn cho người dùng khuyết tật. Một ví dụ cụ thể chứng minh lợi ích của việc sử dụng Semantic HTML là việc sử dụng thẻ `<button>` và thẻ `<div class="btn">`. Thẻ `<button>` mặc định đã hỗ trợ tương tác bằng bàn phím(nhấn enter hoặc space để kích hoạt) và tự động có trạng thái "focus". Nếu dùng `<div>`, bạn sẽ phải viết thêm rât nhiều dòng JavaScript và CSS chỉ để tiastoaj lại những tính năng căn bản mà thẻ `<button>` đã có sẵn. Tuy nhiên thẻ `<div>` vẫn có chỗ đứng riêng. Nó sẽ phù hpowj trong các trường hợp phục vụ mục đích trình bày và bố cục thuần túy mà không mang ý nghĩa về nội dụng. Ví dụ dùng một thẻ `<div class="container">` để căn giữa nội dung hoặc bọc các khối để tạo layout Grid/Flexbox. Trong những trường hợp này `<div>` là lựa chọn đúng đắn vì nó không làm nhiễu cấu trúc ngữ nghĩa của trang web.

