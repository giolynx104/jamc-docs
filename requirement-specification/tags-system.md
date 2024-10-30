# Hệ thống quản lý tags

## 1. Giới hạn quyền tạo tags

### Điểm tín chỉ và quyền tạo tag
- Chỉ người dùng có điểm tín chỉ cao mới có quyền tạo tag mới
- Khuyến khích những người dùng có uy tín, đã đóng góp tích cực cho cộng đồng
- Những người dùng khác sẽ phải sử dụng các tag đã có sẵn

### Quy trình xác nhận tag mới
- Người dùng phải đề xuất tag mới
- Admin hoặc giáo viên sẽ duyệt yêu cầu
- Giúp kiểm soát số lượng tag mới và tránh trùng lặp

## 2. Tự động kiểm tra và gợi ý tag

### Gợi ý tag tự động
- Hệ thống tự động gợi ý các tag đã tồn tại dựa trên từ khóa nhập vào
- Giúp giảm thiểu việc tạo ra các tag tương tự nhau

### Từ điển tag
- Xây dựng danh sách các tag phổ biến và đã được phê duyệt trước
- Người dùng chỉ có thể chọn từ danh sách hoặc tạo tag mới theo quy định

## 3. Giới hạn số lượng tags

### Ngưỡng tạo tag
- Đặt ngưỡng tối đa cho số lượng tag mới mỗi người dùng có thể tạo
- Ví dụ: 1-2 tag mới mỗi tuần
- Giúp kiểm soát số lượng tag phát sinh và ngăn việc tạo tràn lan

## 4. Quản lý tag trùng lặp và sai

### Gộp tag trùng lặp
- Phát hiện và gộp các tag tương tự (ví dụ: "Toán học" và "Math")
- Thay thế tự động bằng một tag chuẩn duy nhất

### Sửa lỗi chính tả
- Tự động sửa các lỗi chính tả phổ biến trong tag
- Cảnh báo người dùng khi nhập tag mới có thể là lỗi chính tả

## 5. Theo dõi và xóa tag không sử dụng

### Xóa tag tự động
- Theo dõi việc sử dụng các tag
- Tự động xóa tag không được sử dụng sau một thời gian
- Giữ cho database gọn gàng

## Cơ chế tạo tag gợi ý

### Quy trình gợi ý và tạo tag
1. Gợi ý các tag tương tự đã tồn tại
2. Kiểm tra quyền hạn của người dùng
3. Cho phép tạo tag mới với quy trình xác nhận (nếu đủ điều kiện)

## Cấu trúc cơ sở dữ liệu
