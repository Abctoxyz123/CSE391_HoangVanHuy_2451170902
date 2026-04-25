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