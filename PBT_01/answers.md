Câu A1
1.  
B1: Trình duyệt kiểm tra cache DNS → nếu chưa có thì gửi yêu cầu đến DNS server để phân giải tên miền shopee.vn thành địa chỉ IP.
B2: Trình duyệt thiết lập kết nối TCP với server (3-way handshake).
B3: Nếu là HTTPS, thực hiện TLS handshake để mã hóa kết nối.
B4: Trình duyệt gửi HTTP request (GET /) đến server.
B5: Server xử lý và trả về HTTP response (HTML, CSS, JS, hình ảnh...).
B6: Trình duyệt nhận HTML → parse thành DOM.
B7: Trình duyệt tải các tài nguyên liên quan (CSS, JS, ảnh...).
B8: Xây dựng CSSOM và render tree → tiến hành layout và paint để hiển thị trang web.

2. 
![Screenshot network tab](screenshots/Screenshot%20tabNetwork.png)
![Request returns cssfile](screenshots/Screenshot%20fileCSS.png)

- Status Code request đầu tiên: 200
- Tổng thời gian load trang: 1.57s


Câu A2
Trước khi sửa:
<div class="header">
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
<div class="footer">© 2026 ShopTLU</div>

Web này bị Google đánh giá SEO thấp vì dùng thẻ <div> cho tất cả 
Website bị Goodle đánh giá SEO thấp vì:
+ sử dụng quá nhiều thẻ div không mang ý nghĩa
Lỗi semantic:
+ phần header dùng thẻ <div>
+ phần nav dùng thẻ <div>
+ phần main dùng thẻ <div>
+ phần product dùng thẻ <div>
+ không có thuộc tính alt cho ảnh

Sau khi sửa :
<header>
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
</footer>

Câu A3
![image html code](screenshots/Câu%20A3.png)

Câu A4
giải thích sự khác nhau giữa <thead>,<tbody>,<tfoot>
<thead> dùng cho tiêu đề cột
<tbody> dùng để chứa phần dữ liệu chính, các bản ghi
<tfoot> dùng để hiện thị tổng kết 





