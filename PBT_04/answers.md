Câu 1

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

Câu 2

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