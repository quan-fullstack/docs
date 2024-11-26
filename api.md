## 1. Tạo yêu cầu mở TKQC (gọi tắt oads)

`1. Tạo oads`

- endpoint: `/oads/create`
- params:
  ```
  bc_id        :
  oads_platform: chọn từ `/platform`
  oads_type    : Loại TKQC [Nhà QC, Nhà phân tích]
  oads_name    :
  oads_shop    : Link shop hoặc ID tiktok shop
  oads_timezone: chọn từ `/timezone`
  oads_country : chọn từ `/country`
  oads_industry: chọn từ `/industry`
  oads_currency: chọn từ `/currency`
  oads_quantity: số lượng oads muốn mở
  company_code : Mã số kinh doanh
  company_name :
  company_file : Thông tin doanh nghiệp (Ảnh hoặc file)
  customer_id  : Sale mở hộ khách hàng này.
  ```

`2. Lấy danh sách nền tảng`

- endpoint: `/platform`
- params:
- response:
  ```
  [
    {id: 1, name: 'Tiktok', ...},
    {id: 2, name: 'Google', ...},
  ]
  ```

`3. Lấy danh sách tiền tệ`

- endpoint: `/currency`
- params:
- response:

  ```
  [
    {id: 1, name: 'VNĐ', ...},
    {id: 2, name: 'USD', ...},
  ]
  ```

`4. Lấy danh sách country`

- endpoint: `/country`
- params:
- response:
  ```
  [
    {id: 1, name: 'Việt nam', ...},
    {id: 2, name: 'Trung quốc', ...},
  ]
  ```

`5. Lấy danh sách industry`

- endpoint: `/industry`
- params:
- response
  ```
  [
    {id: 1, name: 'Thời trang', ...},
    {id: 2, name: 'Mỹ phẩm', ...},
  ]
  ```

`6. Lấy danh sách khách hàng thuộc quyền quản lý của sale`

- endpoint: `/sale_own_customer`
- params:
- response:
  ```
  [
    {user_id, username, fullname, ...},
    {user_id, username, fullname, ...}
  ]
  ```

## 2. Cập nhật yêu cầu mở TKQC

`1. Lấy chi tiết oads`

- endpoint: `/oads/info`
- params:
  ```
  oads_id
  ```
- response:

  ```
  bc_id
  oads_platform
  oads_type
  oads_name
  oads_shop
  oads_timezone
  oads_country
  oads_industry
  oads_currency
  oads_quantity
  company_code
  company_name
  company_file
  logs: [
    {
      id:
      status: trạng thái oads
      reject_note: Lý do từ chối
      create_at:
      action_user: người thực hiện
      action_user_role: role người thực hiện
    },
    ....
  ]
  ```

`2. Cập nhật oads`

- endpoint: `/oads/update`
- params:
  ```
  oads_id
  bc_id
  oads_platform
  oads_type
  oads_name
  oads_shop
  oads_timezone
  oads_country
  oads_industry
  oads_currency
  oads_quantity
  company_code
  company_name
  company_file
  ```

## 3. Theo dõi oads

`1. Lấy danh sách oads`

- endpoint: `/oads`
- params:
  ```
  platform
  status
  stime
  ettime
  company_name
  oads_name
  customer_id: D giành cho sale, ct, cs, admin tìm kiếm theo mã khách hàng
  ```
- response

`2. CT xét duyệt hoặc CS xét duyệt`

- endpoint: `/oads/review`
- params
  ```
  oads_id
  new_status
  reject_note  : mô tả lỗi nếu từ chối (bắt buộc)
  reject_attach: đính kèm ảnh hoặc file lỗi nếu từ chối
  service_fee  : bổ sung phí dịch vụ nếu new_status = CS_APPROVED
  vat          : bổ sung thuế nếu new_status = CS_APPROVED
  rebate       : bổ sung chiết khấu nếunew_status = CS_APPROVED
  ```
- response:

## 4. Nạp tiền vào ví (gọi là recharge)

`1. Lấy danh sách ngân hàng nhận tiền`

- endpoint: `/bank/receive`
- params:
  ```
  curreny: Chọn từ `/currency`
  ```
- response:
  ```
  [
    {
      bank_id  : id hệ thống quy định
      holder   : chủ tài khoản
      number   : số tài khoản
      bank     : tên ngân hàng
      brand    : chi nhánh
      bic      : mã định danh của ngân hàng được sử dụng trong các giao dịch quốc tế
      brand_bic: mã chi nhánh quy định quốc tế
      currency : loại tiền giao dịch (VND/USD,...)
      note     : ghi chú thêm do admin viết
    },
    ...
  ]
  ```

`2. Tạo recharge USD`

- endpoint: `/wallet/recharge/usd`
- params:

  ```
  bank_id: chọn từ `/bank/receive`
  send      : số tiền chuyển vào tài khoản ngân hàng (chưa tính phí)
  bill      : Ảnh giao dịch thành công
  trans_id  : Mã giao dịch thành công
  trans_time: Thời gian giao dịch thành công

  ```

- response

`3. Tạo recharge VND (BE xử lý với API bên thứ 3)`

- Tạo QR:
  - endpoint: `/vnpay/qr_create` ví dụ recharge qua vnpay
  - params:
    ```
    send   : số tiền chuyển vào tài khoản ngân hàng (chưa tính phí)
    bank_id: ngân hàng nhận tiền (từ bank_id hệ thống truy xuất ra các thông tin cần thiết)
    BE cần những tham số gì nữa a?
    ```
  - response:
    ```
    mã qr
    ```
- Socket hoặc Long Polling lắng nghe tiến trình xử lý:
  - endpoint: `socket...`
  - response

## 5. Theo dõi recharge

`1. Lấy danh sách recharge`

- endpoint: `/wallet/recharge`
- params:

  ```
  status: pendding/reviewing/reject/approve
  stime
  etime
  customer_id: giành cho sale, cs, kt, admin tìm kiếm theo mã khách hàng
  currency: loại tiền giao dịch chọn từ `/bank/receive`
  bank_number: tài khoản ngân hàng nhận tiền chọn từ `/bank/receive`
  ```

- response
  ```
  [
    {
      recharge_id  : mã giao dịch hệ thống
      customer_name:
      customer_id  :
      currency     : loại tiền giao dịch
      send         : tiền khách chuyển vào tài khoản ngân hàng
      receive      : tiền ngân hàng thực nhận (bị tính phí)
      service_fee  : phí dịch vụ
      vat          :
      up_wallet    : tiền thực cộng vào ví của khách. up_wallet = receive - service_fee - vat
      trans_time   :
      approved_time: thời gian kế toán approve
      bank_name    :
      bank_number  :
      status       :
      trans_id     : mã giao dịch
    },
    ...
  ]
  ```

`2. Kế toán xét duyệt recharge`

- endpoint: `/wallet/recharge/review`
- params

  ```
  recharge_id
  status

  Nếu từ chối xét duyệt KT gửi 2 params sau:
  reject_note  : KT nhập lý do từ chối
  reject_attach: KT đính kém lý do từ chối (ko bắt buộc)

  Nếu đông ý xét duyệt KT gửi 6 params sau:
  send       : nhập lại số tiền khách gửi vào ngân hàng
  recive     : nhập lại số tiền ngân hàng thực nhận
  attach_bill: upload ảnh đã nhận được tiền
  bank_number: nhập lại tài khoản nhận tiền, chọn từ `/bank/receive`
  service_fee: nhập phí dịch vụ
  vat        : nhập VAT
  ```

  Ví dụ: khách chuyển 100tr vào bank, bank thu 1%, hệ thống thu 2%, vat 5%:  
  `send` : 100tr  
  `recive`: 99tr
  `service_fee` : 2%
  `vat` : 5%
  `=>` số tiền thực cộng vào ví (up_wallet): 100tr - 1tr - 2tr - 5tr = 92tr.

- response

`3. Khiếu nại`

- endpoint: `/wallet/recharge/complaint`
- params
  ```
  recharge_id
  note: lý do khiếu nại
  attach: đính kèm nếu có
  ```
- response

## 6. Quản lý ví

`1. Lấy tổng quan: số dư / đóng băng`

- endpoint: `wallet/overview`
- params:
  ```
  cutomer_id: giành cho sale, cs, kt, admin tìm kiếm theo mã khách hàng
  ```
- response
  ```
  {
    balance: {
      vnd: 1000000
      usd: 200000
    },
    freeze: {
      vnd: 1000000
      usd: 200000
    },
  }
  ```

`2. Lấy danh sách topup`

- topup là chỉ hành động nạp tiền từ ví vào TKQC
- endpoint: `wallet/topup-aads`
- params:
  ```
  cutomer_id: giành cho sale, cs, kt, admin tìm kiếm theo mã khách hàng
  stime
  etime
  ```
- response

  ```
  [
    {
      trans_id      : Mã giao dịch
      topup_send    : số tiền trừ khỏi ví
      topup_receive : số tiền cộng vào TKQC
      service_fee   :
      vat           :
      aads_id       :
      aads_name     :
      aads_platform :
      balance_before: số dư trong ví trước khi topup
      balance_after : số dư trong ví sau khi topup
    },
    ...

  ]
  ```

## 7. Theo dõi tài khoản quảng cáo (ads account viết tắt aads)

`1. Lấy danh sách TKQC (aads)`

- endpoint: `/aads`
- params

  ```
  platform
  aads_stime
  aads_etime
  aads_name
  aads_id:
  aads_company
  aads_status: trạng thái TKQC (active/freeze/ban/out of money) key status do nền tảng quy định.
  cutomer_id: giành cho sale, ct, cs, kt, admin tìm kiếm theo mã khách hàng

  ```

- response

  ```
  [
    {
    aads_id
    aads_name
    aads_company
    aads_platform
    aads_currency
    aads_balance: số dư còn lại của TKQC (từ api tiktok)
    aads_spent: số tiền đã chi tiêu (từ api tiktok)
    aads_status:trạng thái hiện tại (từ api tiktok)
    },
    ...
  ]

  ```

`2. Nạp tiền từ ví vào TKQC (hành động này gọi là topup)`

- endpoint: `/aads/topup`
- params

  ```
  aads_id
  topup_send: số tiền muốn topup (trừ khỏi ví)
  topup_receive: số tiền cộng vào TKQC.

  Ví dụ:
  Khách muốn topup 100$ thì trừ khỏi ví 100$ (topup_send)
  Nếu phí dịch vụ 2%, vat 5% thì tiền cộng TKQC = 100$ - 2$ - 5$ = 97$ (topup_receive)
  Phí và thuế do CS nhập lúc Approved yêu cầu mở TKQC (xem lại api `/oads/review`)
  ```

- response

`3. Rút tiền từ TKQC về ví (Fund)`

- Áp dụng cho TKQC đang `active` hoặc `freeze`. Khách tùy chỉnh số tiền muốn rút.
- API tiktok xử lý trừ tiền TKQC trước, thành công hệ thống xử lý cộng tiền vào ví.
- endpoint: `/aads/fund`
- params

  ```
  aads_id
  fund_send: số tiền muốn rút (trừ vào TKQC)
  fund_receive: fund_receive = fund_send + hoàn phí dịch vụ + hoàn vat (cộng vào ví)
  ```

- response

`4. Clear số dư từ TKQC về ví.`

- Áp dụng cho TKQC đang bị `ban`.
- Mặc định sẽ rút toàn bộ số dư còn lại của TKQC về ví
- phải thông qua KT xét duyệt, thành công mới cộng tiền vào ví (tiền cộng vào ví = tiền clear + hoàn phí + hoàn vat)
- endpoint: `/aads/clear`
- params

  ```
  aads_id
  ```

- response

`5. Thao tác liên kết TKQC với BC (Business center)`

- endpoint: `/aads/bindbc`
- param
  ```
  aads_id
  bcid
  ```
- response

`6. Thao tác hủy liên kết TKQC với BC (Business center)`

- endpoint: `/aads/unbindbc`
- param
  ```
  aads_id
  bcid
  ```
- response

`7. Thao tác TKQC thực hiện pixcel auth`

- endpoint: `/aads/unbindbc`
- param
  ```
  aads_id
  pixcel_id
  auth: true = đồng ý auth pixcel, 0 = hủy auth pixcel
  ```
- response
