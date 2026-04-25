Câu A1

1. type="text" --> ô nhập text bình thường --> Dùng để nhập tên sản phẩm
2. type="email" --> ô nhập text, tự kiêm tra có @ --> Dùng cho form đăng ký
3. type="password" --> ô nhập text nhưng ký tự bị ẩn --> Dùng để nhập mật khẩu 
4. type="tel" --> Ô nhập số điện thoại --> Dùng để nhập số điện thoại giao hàng
5. type="number" --> Ô nhập số, có nút tăng/giảm --> Dùng để chọn số lượng sản phẩm
6. type="radio" --> Nút tròn, chỉ được chọn 1 trong nhiều lựa chọn --> Dùng để chọn phương thức thanh toán
7. type="checkbox" --> Ô vuông, có thể chọn nhiều lựa chọn --> Dùng để chọn nhiều sản phẩm hoặc đồng ý điều khoản
8. type="search" --> Ô nhpaja gióng text nhưng tối ưu cho tìm kiếm --> Dùng để tìm sản phẩm
9. type="range" --> Thanh trượt (slider) --> Dùng để lọc giá sản phẩm
10. type="date" --> Bộ chọn ngày (calender) --> Dùng để chọn ngày giao hàng

Câu A2

- Trường hợp 1 không submit được vì: Có required (bắt buộc nhập) mà user lại để trống
- Trường hợp 2 không submit được vì: type="email" mà người dùng nhập "abc" thì khi browser kiểm tra định dạng không có "@" thì sẽ báo lỗi
- Trường hợp 3 không submit được vì: thuộc tính max="10 mà user lại nhập 15, vượt quá max
- Trường hợp 4 không submit được vì: mẫu yêu cầu có 10 chữ số mà user nhập không đủ 10 chữ số
- Trường hợp 5 không submit được vì: minlength=8 mà người dùng nhập 3 ký tự, không đủ số ký tự tối thiểu

Câu A3
1. Vì khi người dùng sử dụng Screen Reader di chuyển vào ô nhập liệu, thiết bị sẽ đọc to nội dung của nhãn của ô đó lên để người dùng biết phải điền thông tin gì vào ô đó.
2. Dùng khi chúng ta muốn nhóm các câu hỏi hoặc các ô nhập liệu có liện quan mật thiết với nhau để tạo ngữ cảnh rõ ràng.
3. Nó được dùng khi một phần tử tương tác (như button, link) không có văn bản hiển thị trên màn hình nhưng vẫn cần mô tả chức năng cho người dùng Screen Reader. Tuy nhiên khi đã có `<label>` chúng ta không nên dùng thêm aria-label vì sẽ gây xung đột, screen reader sẽ ưu tiên đọc nhãn thẻ `<label>`. Thêm aria-label có nội dung tương tự sẽ khiến máy đọc lặp đi lặp lại hoặc ghi đè lên nội dung của `<label>`

Câu A4
1. Thuộc tính loading="lazy" trên thẻ `<img>`
- loading="lazy" là kĩ thuật thay vì tải tất cả hình ảnh ngay khi vừa mở trang web, trình duyệt sẽ trì hoãn việc tải những ảnh ở xa (nằm dưới cùng trang) cho đến khi người dùng cuộn chuột đến gần vị trí của chúng. 
- Nó cải thiện điều gì:
    + Tốc độ tải trang: Giúp nội dung chính hiện ra nhanh hơn vì trình duyệt không phải "gồng mình" tải hàng chục cái ảnh cùng lúc.
    + Tiết kiệm dữ liệu: Cực kỳ hữu ích cho người dùng 4G/5G vì họ không phải tốn dung lượng cho những tấm ảnh mà họ chưa kịp xem tới.
    + Giảm tải máy chủ: Server chỉ phải gửi dữ liệu khi thực sự cần thiết.
- Khi nào không nên dùng:
    + Không dùng cho những ảnh phần đầu trang web hiện ra ngay khi vừa load. Ví dụ nếu bạn lazy load ảnh banner chính (hero image), nó sẽ gây ra hiện tượng giật hoặc trắng màn hình trong tích tắc, làm giảm trải nghiệm người dùng.
2. Tại sao nên cung cấp nhiều `<source>` trong thẻ `<video>`?
-  Lý do: Để đảm bảo khả năng tương thích trên mọi trình duyệt. Mỗi trình duyệt (Chrome, Safari, Firefox) lại hỗ trợ các định dạng video (codec) khác nhau. Khi bạn cung cấp nhiều `<source>`, trình duyệt sẽ kiểm tra từ trên xuống dưới và phát định dạng đầu tiên mà nó hỗ trợ.
- 3 format video web phổ biến:
    + MP4 (.mp4): Phổ biến nhất, hầu như trình duyệt và thiết bị nào cũng hỗ trợ.
    + WebM (.webm): Do Google phát triển, cho chất lượng tốt nhưng dung lượng file rất nhẹ, tối ưu cho web hiện đại.
    + Ogg/Theora (.ogv): Một định dạng mã nguồn mở (hiện nay ít dùng hơn hai loại trên nhưng vẫn được tính là format chuẩn).
3. Thuộc tính alt trên `<img>` và viết alt
- Công dụng:
    + Mô tả hình ảnh cho người dùng sử dụng trình đọc màn hình (Screen Reader).
    + Hiển thị văn bản thay thế nếu ảnh bị lỗi hoặc không tải được.
    + Giúp SEO Google hiểu nội dung bức ảnh là gì để xếp hạng tìm kiếm.
- Viết alt cho 3 trường hợp cụ thể:
    + Ảnh sản phẩm iPhone 16: alt="iPhone 16 màu xanh mòng két nhìn từ mặt lưng với cụm camera kép nằm dọc"
    + Ảnh trang trí (decorative): alt=""
    + Ảnh biểu đồ doanh thu Q1/2026: alt="Biểu đồ cột doanh thu Quý 1 năm 2026, cho thấy sự tăng trưởng mạnh mẽ trong tháng 3 với mức đạt đỉnh 2 tỷ VNĐ"

Câu A5
1. Khi nào dùng thẻ `<img>`
    - khi hình ảnh là một phần không thể tách rời hoặc mang tính chất trang trí cho nội dung xung quanh. Nếu bỏ tấm ảnh này đi, đoạn văn hoặc chức năng đó có thể bị mất đi ý nghĩa hoặc trông rất kỳ cục. Khi dùng thẻ `<img>` ta không cần chú thích hiển thị bằng chữ bên dưới. Thông tin về ảnh đã được giải thích rõ trong đoạn văn ngay trước/sau đó.
    - Ví dụ thực tế: Logo của trang web nằm trên thanh điều hướng (Navbar). Bạn chỉ cần ảnh và alt="Logo công ty", không cần để chú thích "Đây là logo" dưới ảnh đó.
2. Khi nào dùng `<figure>` và `<figcaption>`
    - khi hình ảnh là một đơn vị nội dung độc lập (Self-contained). Bạn có thể di chuyển khối này đi chỗ khác (ví dụ: chuyển xuống cuối bài hoặc sang một trang phụ lục) mà không làm ảnh hưởng đến dòng chảy của nội dung chính. Khi dùng `<figure>` chúng ta phải có nhãn chú thích `<figcaption>` để mô tả nội dung của ảnh.
    - Ví dụ thực tế: Hình ảnh trong 1 bài báo, phía dưới cần ghi mô tả tổng quát về bức ảnh và nguồn của bức ảnh đó.


Bài B1
- Giải thích vì sao HTML không thể validate confirm_password
    1. Phạm vi kiểm tra bị cô lập. Các thuộc tính validation của HTML như required, parttern,... chỉ có thể kiểm tra giá trị bên trong chính nó.
    2. Thiếu logic so sánh. HTML không có bộ xử lý để thực hiện các phép tính logic hoặc so sánh giữa các biến. Để làm được điều này, trình duyệt cần một thực thể có khả năng "đọc" giá trị từ hai nơi và "đối chiếu" chúng — đó chính là vai trò của JavaScript.

