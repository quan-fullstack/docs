# LOGIN

# CUSTOMER (khách)

## 1. Mục quản lý oads

### 1.1. Trang tạo mới oads

- section 1 - `nhập` thông tin liên kết
- section 2 - `nhập` thông tin doanh nghiệp
- section 3 - `nhập` thông tin các nhân
- section 4 - `nhập` thông tin TKQC
- section 5 - Hướng dẫn tạo (FAQs)

### 1.2. Trang xem danh sách oads đã tạo

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách. Các action trong bảng:
  - `nút chi tiết` -> Trang chi tiết
  - `nút sửa oads` (trạng thái reject mới hiện nút) -> Trang chi tiết

### 1.3. Trang sửa oads

- section 1 - Hiện lý do reject hiện tại(khi trạng thái reject)
- section 2 - Hiện chi tiết
- section 3 - `nút cập nhật` (khi trạng thái reject)
- section 4 - Lịch sử duyệt

## 2. Mục quản lý Ví

### 2.1. Trang tổng quan số dư trong ví

- section 1 - Tổng quan số dư, số đóng băng, `nút tạo recharge`
- section 2 - Biểu đồ, `nút lọc` theo tháng

### 2.2. Trang tạo recharge

- Chuyển tiền VND:
  - section 1 - `Chọn` loại tiền
  - section 2 - `Chọn` bank nhận tiền
  - section 3 - `Chọn` tài khoản bank nhận tiền
  - section 4 - `Nhập` số tiền
  - section 5 - `Xác nhận thanh toán` - hiển thị lại các thông tin đã nhập
  - section 6 - `Quét QR`
  - section 7 - Thông báo kết quả
- Chuyển tiền USD
  - section 1 - `Chọn` loại tiền
  - section 2 - `Chọn` bank nhận tiền
  - section 3 - `Chọn` tài khoản bank nhận tiền
  - section 4 - `Xác nhận đã chuyển tiền` - hiện form nhập bill, số tiền đã chuyển, thời gian chuyển
  - section 5 - `Bấm hoàn thành`

### 2.3. Trang xem danh sách Recharge đã tạo

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách. Action trong bảng:
  - `nút khiếu nại` (trạng thái reject mới hiện nút) -> Trang khiếu nại
  - `nút chi tiết` -> Trang chi tiết

### 2.4. Trang khiếu nại (cũng là trang chi tiết)

- section 1 - Hiện lý do reject (khi trạng thái reject)
- section 2 - `Nhập khiếu nại` (khi trạng thái reject)
- section 3 - Hiện chi tiết recharge
- section 4 - Lịch sử duyệt

## 3. Mục quản lý aads

### 3.1. Trang xem danh sách aads

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách, các action trong bảng

  - `nút sửa aads name` -> popup sửa aads name
  - `nút copy aads id` -> gọi hàm copy aads id
  - `nút topup` -> popup topup
  - `nút fund` -> popup fund
  - `nút clear` -> popup clear
  - `nút bind` -> popup bind
  - `nút unbind` -> popup unbind
  - `nút pixel` -> popup pixel

## 4. Mục quản lý cá nhân

### 4.1. Trang thông tin các nhân

- section 1 - Các thông tin không được sửa (username, role)
- section 2 - Các thông tin có thể sửa (email, mật khẩu, sđt ...)

### 4.2. Trò chuyện trực tuyến

### 4.3. Thông báo

# CONTENT (CT)

## 1. Mục quản lý oads của khách

### 1.1. Trang xem danh sách oads đã tạo

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách. Các action trong bảng:
  - `nút xét duyệt` -> Trang xét duyệt oads
  - `nút xem log` lịch sử xét duyệt-> Trang xét duyệt oads

### 2.2. Trang xét duyệt oads

- section 1
  - `nút review`
  - `nút approved`
  - `nút reject` -> popup nhập lý do reject
- section 2 - Hiện lý do từ chối hiện tại (nếu có)
- section 3 - Hiện chi tiết
- section 4 - Lịch sử duyệt

## 2. Mục quản lý cá nhân

### 2.1. Trang thông tin các nhân

- section 1 - Các thông tin không được sửa (username, role)
- section 2 - Các thông tin có thể sửa (email, mật khẩu, sđt ...)

### 2.2. Trò chuyện trực tuyến

### 2.3. Thông báo

# CUSTOMER SERVICES (CS)

## 1. Mục quản lý oads của khách

### 1.1. Trang xem danh sách oads đã tạo

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách. Các action trong bảng:
  - `nút xét duyệt` -> Trang xét duyệt oads
  - `nút xem log` lịch sử xét duyệt-> Trang xét duyệt oads

### 2.2. Trang xét duyệt oads

- section 1 - Các nút xét duyệt oads
  - `nút review`
  - `nút approved` -> popup nhập phí, thuế
  - `nút reject` -> popup nhập lý do reject
- section 2 - Hiện lý do từ chối hiện tại (nếu có)
- section 3 - Hiện chi tiết
- section 4 - Lịch sử duyệt

## 2. Mục quản lý aads của khách

### 2.1. Trang xem danh sách aads

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách, các action trong bảng

  - `nút sửa aads name` -> popup sửa aads name
  - `nút copy aads id` -> gọi hàm copy aads id
  - `nút topup` -> popup topup
  - `nút fund` -> popup fund
  - `nút clear` -> popup clear
  - `nút bind` -> popup bind
  - `nút unbind` -> popup unbind
  - `nút pixel` -> popup pixel

## 3. Mục quản lý ví của khách

### 3.1. Trang tổng quan ví khách

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách

  ```
  1 STT - 2 Tên khách - 3 số dư - 4 đóng bằng - 5 Danh sách recharge - 6 Add fund
  ```

### 3.2 Trang xem danh sách Recharge đã tạo

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách, `nút chi tiết` -> Trang chi tiết

### 3.4. Trang chi tiết recharge

- section 1 - Hiện lý do reject (khi trạng thái reject)
- section 2 - Hiện chi tiết recharge
- section 3 - Lịch sử duyệt

### 3.5. Trang xem danh sách fund đã tạo

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách, `nút chi tiết` -> Trang chi tiết

### 3.6. Trang chi tiết fund

- section 1 - Hiện lý do reject (khi trạng thái reject)
- section 2 - Hiện chi tiết fund
- section 3 - Lịch sử duyệt

## 4. Mục quản lý cá nhân

### 4.1. Trang thông tin các nhân

- section 1 - Các thông tin không được sửa (username, role)
- section 2 - Các thông tin có thể sửa (email, mật khẩu, sđt ...)

### 4.2. Trò chuyện trực tuyến

### 4.3. Thông báo

# SALE

## 1. Mục quản lý oads của khách

### 1.1 Trang tạo mới oads

- section 1 - `nhập` thông tin liên kết
- section 2 - `nhập` thông tin doanh nghiệp
- section 3 - `nhập` thông tin các nhân
- section 4 - `nhập` thông tin TKQC
- section 5 - `chọn` khách hàng
- section 6 - Hướng dẫn tạo (FAQs)

### 1.2. Trang xem danh sách oads đã tạo

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách. Các action trong bảng:
  - `nút chi tiết` -> Trang chi tiết
  - `nút sửa oads` (trạng thái reject mới hiện nút) -> Trang chi tiết

### 1.3. Trang sửa oads

- section 1 - Hiện lý do reject hiện tại(khi trạng thái reject)
- section 2 - Hiện chi tiết
- section 3 - `nút cập nhật` (khi trạng thái reject)
- section 4 - Lịch sử duyệt

## 2. Mục quản lý aads của khách

### 2.1. Trang xem danh sách aads

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách, các action trong bảng

  - `nút sửa aads name` -> popup sửa aads name
  - `nút copy aads id` -> gọi hàm copy aads id
  - `nút topup` -> popup topup
  - `nút fund` -> popup fund
  - `nút clear` -> popup clear
  - `nút bind` -> popup bind
  - `nút unbind` -> popup unbind
  - `nút pixel` -> popup pixel

## 3. Mục quản lý ví của khách

### 3.1. Trang tổng quan ví khách

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách

  ```
  1 STT - 2 Tên khách - 3 số dư - 4 đóng bằng - 5 Danh sách recharge - 6 Add recharge - 7 Add fund
  ```

### 3.2. Trang tạo recharge cho khách

- Chọn khách hàng
- Chuyển tiền VND:
  - section 1 - `Chọn` loại tiền
  - section 2 - `Chọn` bank nhận tiền
  - section 3 - `Chọn` tài khoản bank nhận tiền
  - section 4 - `Nhập` số tiền
  - section 5 - `Xác nhận thanh toán` - hiển thị lại các thông tin đã nhập
  - section 6 - `Quét QR`
  - section 7 - Thông báo kết quả
- Chuyển tiền USD
  - section 1 - `Chọn` loại tiền
  - section 2 - `Chọn` bank nhận tiền
  - section 3 - `Chọn` tài khoản bank nhận tiền
  - section 4 - `Xác nhận đã chuyển tiền` - hiện form nhập bill, số tiền đã chuyển, thời gian chuyển
  - section 5 - `Bấm hoàn thành`

### 3.3. Trang xem danh sách Recharge của khách

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách, `nút chi tiết` -> Trang chi tiết

### 3.4. Trang chi tiết recharge của khách

- section 1 - Hiện lý do reject (khi trạng thái reject)
- section 2 - Hiện chi tiết recharge
- section 3 - Lịch sử duyệt

### 3.5. Trang xem danh sách fund đã tạo

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách, `nút chi tiết` -> Trang chi tiết

### 3.6. Trang chi tiết fund

- section 1 - Hiện lý do reject (khi trạng thái reject)
- section 2 - Hiện chi tiết fund
- section 3 - Lịch sử duyệt

## 4. Mục quản lý tài khoản khách hàng

### 4.1. Trang xem danh sách khách hàng

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách, `nút chi tiết` -> Trang chi tiết

### 4.2. Cập nhật thông tin khách

- section 1 - Các thông tin không được sửa (username, role)
- section 2 - Các thông tin có thể sửa (email, mật khẩu, sđt ...)

## 5. Mục quản lý cá nhân

### 5.1. Trang thông tin các nhân

- section 1 - Các thông tin không được sửa (username, role)
- section 2 - Các thông tin có thể sửa (email, mật khẩu, sđt ...)

### 5.2. Trò chuyện trực tuyến

### 5.3. Thông báo

# KẾ TOÁN (KT)

## 1. Mục quản lý aads của khách (chỉ xem)

### 1.1. Trang xem danh sách aads của khách

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách

## 2. Mục quản lý ví của khách

### 2.1. Trang tổng quan ví khách

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách

  ```
  1 STT - 2 Tên khách - 3 số dư - 4 đóng bằng - 5 Danh sách recharge
  ```

### 2.3. Trang xem danh sách Recharge đã tạo

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách, `nút xét duyệt` -> Trang xét duyệt

### 2.4. Trang xét duyệt recharge

- section 1 - Các nút xét duyệt recharge
  - `nút review`
  - `nút approved` -> popup nhập bill, thuế, vat, send, receive, time...
  - `nút reject` -> popup nhập lý do reject
- section 2 - Hiện lý do từ chối hiện tại (nếu có)
- section 3 - Hiện chi tiết
- section 4 - Lịch sử duyệt

### 2.5. Trang xem danh sách Fund đã tạo

- section 1 - Công cụ lọc danh sách
- section 2 - Bảng danh sách, `nút xét duyệt` -> Trang xét duyệt

### 2.6. Trang xét duyệt Fund

- section 1 - Các nút xét duyệt Fund
  - `nút review`
  - `nút approved` -> popup nhập bill đã chuyển
  - `nút reject` -> popup nhập lý do reject
- section 2 - Hiện lý do từ chối hiện tại (nếu có)
- section 3 - Hiện chi tiết
- section 4 - Lịch sử duyệt

## 3. Mục cá nhân

### 3.1. Trang thông tin các nhân

- section 1 - Các thông tin không được sửa (username, role)
- section 2 - Các thông tin có thể sửa (email, mật khẩu, sđt ...)

### 3.2. Trò chuyện trực tuyến

### 3.3. Thông báo
