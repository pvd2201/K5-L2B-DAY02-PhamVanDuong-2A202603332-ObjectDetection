# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` |Xe ô tô chủ yếu dùng để chở người, có kích thước nhỏ hoặc trung bình. |Sedan, hatchback, SUV, coupe.|
| `truck` |Xe tải dùng để vận chuyển hàng hóa hoặc thực hiện nhiệm vụ chuyên dụng, có kết cấu thùng hàng hoặc thiết bị chuyên dụng. |Xe tải thùng, xe ben, xe đầu kéo, xe cứu hộ, xe cẩu. |
| `bus` |Xe cơ giới được thiết kế chủ yếu để chở nhiều hành khách, thường có khoang hành khách lớn và nhiều hàng ghế. |Xe buýt thành phố, xe khách, xe buýt trường học. |
| `van` |Xe có khoang phía sau kín, liền với cabin, thường dùng để chở hàng hoặc một nhóm hành khách nhỏ.|xe van giao hàng, limosine, transit,... có kích thước lớn hơn car nhưng nhỏ hơn bus. |

## Quy tắc chung

- Box bám sát vật thể nghĩa là: Bounding box phải bao quanh toàn bộ phần phương tiện nhìn thấy được, không lấy quá nhiều nền xung quanh và không cắt mất phần xe đang nhìn thấy.
- Vật thể bị che khuất: Vẫn gán nhãn nếu có đủ đặc điểm nhận diện phương tiện. Bounding box bao quanh phần nhìn thấy, không tự ước lượng phần bị che.
- Vật thể bị cắt bởi rìa ảnh: Vẫn gán nhãn nếu xác định được loại phương tiện. Bounding box kéo đến rìa ảnh, không vượt ra ngoài khung hình.
- Vật thể rất nhỏ/mơ hồ: Chỉ gán nhãn khi có đủ bằng chứng để xác định lớp. Nếu không thể phân biệt đáng tin cậy, ghi nhận là trường hợp không chắc chắn.

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_007` |Những xe ở phía trái của box CAR 145 |Không tự gán nhãn, hỏi giảng viên |Car mơ hồ với van/minivan, không có đủ bằng chứng nhận diện |
| `drive_009` |Một chiếc xe nằm giữa hai box TRUCK 198 và CAR 195 |Không tự gán nhãn, hỏi giảng viên |Car mơ hồ với van/minivan, không có đủ bằng chứng nhận diện |
| `drive_011` |Có hai chiếc xe màu trằng nằm phía bên phải của box CAR 252 |Không tự gán nhãn, hỏi giảng viên | Car mơ hồ với van/minivan, không có đủ bằng chứng nhận diện |
