PHẦN A

Câu A1

| Position | Vẫn chiếm chỗ trong flow? | Tham chiếu vị trí | Cuộn theo trang? | Use case |
|----------|---------------------------|-------------------|------------------|----------|
| `static` | Có | Mặc định(không tham chiếu vị trí) | Có | Mặc định |
| `relative` | Có | Vị trí gốc của nó | Có | Làm anchor cho absolute con, dịch nhẹ |
| `absolute` | Không | Thẻ cha gần nhất có position khác static | Có | Badge, dropdown, tooltip |
| `fixed` | Không | Viewport | Không | Chat button, header cố định |
| `sticky` | Có-Không | Viewport(khi dính) | Có(đến khi hết phạm vi thẻ cha) | Sticky header, sidebar |

1. Khi nào absolute tham chiếu body?
- Phần tử mang position: absolute sẽ tham chiếu đến body (thực tế là Initial Containing Block) khi tất cả các thẻ cha bao quanh nó đều có position: static (mặc định) hoặc nó không nằm trong bất kỳ thẻ cha nào khác ngoài thẻ `<body>`.
2. Khi nào absolute tham chiếu parent?
- Nó sẽ tham chiếu đến thẻ cha khi thẻ cha đó được thiết lập một giá trị position khác mặc định (thường là người ta dùng position: relative cho thẻ cha để làm "mỏ neo").
3. Khái niệm "Nearest positioned ancestor" là gì?
- Cụm từ này có nghĩa là "Phần tử tổ tiên gần nhất có thiết lập vị trí".

    + Ancestor (Tổ tiên): Có thể là cha, ông, hoặc các cấp cao hơn bao ngoài phần tử đó.

    + Positioned: Là bất kỳ phần tử nào có thuộc tính position được gán giá trị khác static (như relative, absolute, fixed, hoặc sticky).

Câu A2

Trường hợp 1:
```
_________________________________________
| | Item 1 | Item 2 | Item 3 | Item 4 | |
| | (25%)  | (25%)  | (25%)  | (25%)  | |
_________________________________________
```

Trường hợp 2:

```
_________________________________________
|  _______   _______                    |
| | Item 1| | Item 2|  <- Hàng 1        |
|  -------   -------                    |
|  _______   _______                    |
| | Item 3| | Item 4|  <- Hàng 2        |
|  -------   -------                    |
|  _______   _______                    |
| | Item 5| | Item 6|  <- Hàng 3        |
|  -------   -------                    |
_________________________________________
```

Trường hợp 3:

```
_________________________________________________
|                                               |
| _______             _______             _______ |
| |Item 1|           |Item 2 |           |Item 3 || <- Căn giữa dọc
| -------             -------             ------- |
|                                               |
_________________________________________________
```

Trường hợp 4:

```
_____________________________________________________________
|  _______            ________________            _______   |
| | 200px |  (20px)  |      1fr       |  (20px)  | 200px |  |
| |Item 1 |   gap    |     Item 2     |   gap    |Item 3 |  |
|  -------            ----------------            -------   |
_____________________________________________________________
```

Trường hợp 5:

```
_________________________________________
|  _______   _______   _______          |
| | Item 1| | Item 2| | Item 3| Hàng 1  |
|  -------   -------   -------          |
|  _______   _______   _______          |
| | Item 4| | Item 5| | Item 6| Hàng 2  |
|  -------   -------   -------          |
|  _______                              |
| | Item 7|                     Hàng 3  |
|  -------                              |
_________________________________________
```

PHẦN C

Câu C1

1. Navigation bar ngang (logo + menu + buttons)
- Lựa chọn: Flexbox
- Giải thích: Thanh điều hướng là kiểu bố cục một chiều (theo trục ngang). Flexbox cho phép bạn dễ dàng phân bổ không gian giữa các phần tử bằng justify-content: space-between và căn chỉnh tất cả các mục thẳng hàng theo chiều dọc bằng align-items: center.
2. Lưới ảnh Instagram (3 cột đều nhau, số ảnh không biết trước)
- Lựa chọn: Grid.
- Giải thích: Đây là bố cục hai chiều chuẩn (cả hàng và cột). Với Grid, bạn chỉ cần thiết lập grid-template-columns: repeat(3, 1fr) một lần; khi có thêm ảnh mới, chúng sẽ tự động rơi xuống hàng dưới mà vẫn giữ đúng kích thước và khoảng cách cột.
3. Layout blog: main content + sidebar
- Lựa chọn: Grid
- Giải thích: Đây là việc xây dựng "khung xương" lớn (macro layout) cho trang web. Grid giúp bạn kiểm soát tỷ lệ giữa nội dung chính và thanh bên một cách chính xác (ví dụ: grid-template-columns: 3fr 1fr) và rất tiện lợi khi cần thay đổi vị trí của chúng trên thiết bị di động.
4. Footer với 4 cột thông tin
- Lựa chọn: Kết hợp cả 2
- Giải thích:
    + Sử dụng Grid để chia khung tổng của Footer thành 4 phần bằng nhau một cách nhanh gọn.
    + Sử dụng Flexbox bên trong từng cột để sắp xếp các danh sách liên kết hoặc icon theo chiều dọc/ngang và căn chỉnh chúng chính xác.
5. Card sản phẩm (ảnh trên, text giữa, nút dưới — nút luôn dính đáy)
- Lựa chọn: Flexbox
- Giải thích: Card là bố cục một chiều theo chiều dọc. Bằng cách sử dụng display: flex với flex-direction: column, bạn có thể áp dụng margin-top: auto cho nút bấm. Kỹ thuật này sẽ đẩy nút xuống sát đáy card bất kể phần văn bản ở giữa dài hay ngắn, tạo sự đồng nhất cho cả hàng sản phẩm.

Câu C2

Lỗi 1: Card không đều chiều cao - nút "mua" bị nhảy xuống
- Nguyên nhân: Mặc định các thẻ .card có chiều cao phụ thuộc vào nội dung bên trong(text dài hay ngắn). Nếu card 1 có tiêu đề 1 dòng và card 2 có tiêu đề 2 dòng, nút bấm sẽ bị lệch nhau.
- Cách sửa: Biến mỗi .card thành một flex container theo chiều dọc và sử dụng margin-top: auto cho nút bấm để đẩy nó xuống đáy.
```css
.card-container {
    display: flex;
    flex-wrap: wrap;
}

.card {
    width: 30%;
    margin: 1.5%;
    display: flex;
    flex-direction: column;
}

.card .btn {
    padding: 10px;
    margin-top: auto; 
}
```

Lỗi 2: Items không nằm giữa cả ngang lẫn dọc trong container 100vh
- Nguyên nhân: Thuộc tính text-align: center chỉ có tác dụng căn giữa văn bản theo chiều ngang. Trong Flexbox, để căn giữa một item theo cả hai chiều trong cha, bạn cần sử dụng các thuộc tính căn chỉnh của chính Flexbox.
- Cách sửa: Thêm justify-content và align-items vào container cha.
```css
.hero {
    height: 100vh;
    display: flex;
    /* Code sửa */
    justify-content: center; /* Căn giữa theo chiều ngang (trục chính) */
    align-items: center;     /* Căn giữa theo chiều dọc (trục phụ) */
}

.hero-content {
    text-align: center;
}
```

Lỗi 3: Sidebar bị co lại khi content quá dài
- Nguyên nhân: Mặc định trong Flexbox, thuộc tính flex-shrink có giá trị là 1. Điều này có nghĩa là khi không gian không đủ, các item sẽ tự động bị "bóp" lại để vừa với container. Sidebar dù có width: 250px vẫn bị ép lại bởi phần content chiếm ưu thế.
- Cách sửa: Thiết lập flex-shrink: 0 cho sidebar để ngăn chặn việc bị co lại.
```css
.layout {
    display: flex;
}

.sidebar {
    width: 250px;
    /* Code sửa: Không cho phép sidebar co lại */
    flex-shrink: 0; 
}

.content {
    flex: 1; /* Chiếm toàn bộ phần còn lại */
}
```

