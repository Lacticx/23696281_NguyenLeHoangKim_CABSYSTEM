# CAB System - Test Cases

Tổng cộng **50 test case** cho 5 test scenario nghiệp vụ của MVP.

> Cấu trúc: Test Case ID, Test Scenario, Test Case, Preconditions, Test Steps, Test Data, Expected Result, Priority.


## 1. Đăng ký và đăng nhập tài khoản khách hàng

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-LOGIN-001 | Đăng ký và đăng nhập tài khoản khách hàng | [Positive] Đăng ký tài khoản với đầy đủ thông tin hợp lệ | Khách hàng chưa có tài khoản | 1. Mở màn hình Đăng ký<br>2. Nhập họ tên<br>3. Nhập email<br>4. Nhập số điện thoại<br>5. Nhập password<br>6. Nhấn Đăng ký | Họ tên: Nguyễn Văn A<br>Email: nguyenvana@gmail.com<br>Phone: 0901234567<br>Password: Abc@12345 | Tài khoản được tạo thành công và thông báo đăng ký thành công | High |
| TC-LOGIN-002 | Đăng ký và đăng nhập tài khoản khách hàng | [Positive] Đăng nhập bằng tài khoản hợp lệ | Tài khoản đã tồn tại và đang hoạt động | 1. Mở Login<br>2. Nhập email/username<br>3. Nhập password<br>4. Nhấn Login | Username: nguyenvana@gmail.com<br>Password: Abc@12345 | Đăng nhập thành công và chuyển vào hệ thống | High |
| TC-LOGIN-003 | Đăng ký và đăng nhập tài khoản khách hàng | [Negative] Đăng ký bằng email/số điện thoại đã tồn tại | Đã tồn tại tài khoản dùng email hoặc phone trên | 1. Mở Đăng ký<br>2. Nhập thông tin<br>3. Nhấn Đăng ký | Email: nguyenvana@gmail.com | Hệ thống từ chối đăng ký và thông báo tài khoản/email/số điện thoại đã tồn tại | High |
| TC-LOGIN-004 | Đăng ký và đăng nhập tài khoản khách hàng | [Negative] Đăng nhập với mật khẩu sai | Tài khoản tồn tại | 1. Mở Login<br>2. Nhập username đúng<br>3. Nhập password sai<br>4. Nhấn Login | Username: nguyenvana@gmail.com<br>Password: Wrong@123 | Không đăng nhập; hiển thị thông báo thông tin đăng nhập không hợp lệ | High |
| TC-LOGIN-005 | Đăng ký và đăng nhập tài khoản khách hàng | [Boundary] Password tại giới hạn tối thiểu hệ thống cho phép | Màn hình đăng ký đang hoạt động | 1. Nhập các thông tin hợp lệ<br>2. Nhập password đúng số ký tự tối thiểu<br>3. Nhấn Đăng ký | Password: tại ngưỡng min theo validation hệ thống | Nếu đạt đúng ngưỡng thì hệ thống chấp nhận và tạo tài khoản | Medium |
| TC-LOGIN-006 | Đăng ký và đăng nhập tài khoản khách hàng | [Boundary] Password vượt giới hạn tối đa hệ thống cho phép | Màn hình đăng ký đang hoạt động | 1. Nhập thông tin hợp lệ<br>2. Nhập password dài hơn giới hạn<br>3. Nhấn Đăng ký | Password: vượt max theo validation | Hệ thống từ chối dữ liệu và thông báo lỗi | Medium |
| TC-LOGIN-007 | Đăng ký và đăng nhập tài khoản khách hàng | [Rỗng] Bỏ trống email/username | Đang ở màn hình đăng ký hoặc Login | 1. Để trống email/username<br>2. Nhập các trường còn lại<br>3. Submit | Username: rỗng | Hệ thống không cho tiếp tục và yêu cầu nhập username/email | High |
| TC-LOGIN-008 | Đăng ký và đăng nhập tài khoản khách hàng | [Rỗng] Bỏ trống password | Đang ở màn hình Login | 1. Nhập username<br>2. Không nhập password<br>3. Nhấn Login | Password: rỗng | Hệ thống không cho đăng nhập và hiển thị lỗi trường bắt buộc | High |
| TC-LOGIN-009 | Đăng ký và đăng nhập tài khoản khách hàng | [Format] Email không đúng định dạng | Đang ở màn hình đăng ký | 1. Nhập thông tin<br>2. Nhập email sai format<br>3. Submit | Email: nguyenvana@ | Hệ thống từ chối email không hợp lệ | Medium |
| TC-LOGIN-010 | Đăng ký và đăng nhập tài khoản khách hàng | [Format] Số điện thoại chứa ký tự không hợp lệ | Đang ở màn hình đăng ký | 1. Nhập thông tin<br>2. Nhập phone sai format<br>3. Submit | Phone: 09AB123456 | Hệ thống từ chối và yêu cầu nhập số điện thoại đúng format | Medium |

## 2. Tài xế cập nhật phương tiện và chuyển sang Available

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-DRIVER-001 | Tài xế cập nhật phương tiện và chuyển sang Available | [Positive] Cập nhật thông tin xe hợp lệ | Tài xế đã đăng nhập | 1. Mở Quản lý phương tiện<br>2. Nhập thông tin xe<br>3. Nhấn Lưu | Plate: 51A-123.45<br>Type: Sedan<br>Brand: Toyota<br>Model: Vios | Thông tin xe được lưu và gắn đúng tài xế | High |
| TC-DRIVER-002 | Tài xế cập nhật phương tiện và chuyển sang Available | [Positive] Chuyển sang Available khi đã có xe hợp lệ | Tài xế có hồ sơ và xe hợp lệ | 1. Mở trạng thái<br>2. Chọn Available<br>3. Xác nhận | Driver: DRV001<br>Vehicle: 51A-123.45 | Trạng thái chuyển thành Available và tài xế xuất hiện trong danh sách khả dụng | High |
| TC-DRIVER-003 | Tài xế cập nhật phương tiện và chuyển sang Available | [Negative] Chuyển Available khi chưa có phương tiện hợp lệ | Tài xế chưa có xe hợp lệ | 1. Mở trạng thái<br>2. Chọn Available<br>3. Xác nhận | Driver: DRV002<br>Vehicle: None | Hệ thống từ chối chuyển Available và yêu cầu bổ sung xe hợp lệ | High |
| TC-DRIVER-004 | Tài xế cập nhật phương tiện và chuyển sang Available | [Negative] Cập nhật xe nhưng thông tin không hợp lệ | Tài xế đã đăng nhập | 1. Mở quản lý xe<br>2. Nhập dữ liệu sai<br>3. Lưu | Plate: XYZ<br>Type: không được hỗ trợ | Hệ thống không lưu hoặc báo lỗi dữ liệu xe | High |
| TC-DRIVER-005 | Tài xế cập nhật phương tiện và chuyển sang Available | [Boundary] Chọn loại xe ở giá trị cuối cùng trong danh sách hỗ trợ | Tài xế đã đăng nhập | 1. Mở quản lý xe<br>2. Chọn loại xe cuối danh sách<br>3. Lưu | Vehicle type: loại cuối trong danh sách hệ thống | Hệ thống chấp nhận nếu loại xe nằm trong danh sách hỗ trợ | Medium |
| TC-DRIVER-006 | Tài xế cập nhật phương tiện và chuyển sang Available | [Boundary] Chuyển Available ngay sau khi xe vừa được lưu | Xe vừa cập nhật thành công | 1. Lưu xe<br>2. Ngay lập tức mở trạng thái<br>3. Chọn Available | Driver: DRV001 | Hệ thống kiểm tra dữ liệu xe đã lưu và cho phép Available | Medium |
| TC-DRIVER-007 | Tài xế cập nhật phương tiện và chuyển sang Available | [Rỗng] Bỏ trống biển số xe | Đang ở form phương tiện | 1. Để trống plate<br>2. Nhập các trường còn lại<br>3. Lưu | Plate: rỗng | Không lưu và yêu cầu nhập biển số | High |
| TC-DRIVER-008 | Tài xế cập nhật phương tiện và chuyển sang Available | [Rỗng] Bỏ trống loại xe | Đang ở form phương tiện | 1. Nhập plate<br>2. Không chọn vehicle type<br>3. Lưu | Vehicle type: rỗng | Không lưu và yêu cầu chọn loại xe | High |
| TC-DRIVER-009 | Tài xế cập nhật phương tiện và chuyển sang Available | [Format] Biển số xe sai format | Đang ở form phương tiện | 1. Nhập biển số sai định dạng<br>2. Nhập dữ liệu còn lại<br>3. Lưu | Plate: 51@ABC#123 | Hệ thống từ chối biển số sai format | Medium |
| TC-DRIVER-010 | Tài xế cập nhật phương tiện và chuyển sang Available | [Format] Email/số điện thoại tài xế sai format | Tài xế đang sửa hồ sơ | 1. Mở hồ sơ<br>2. Nhập email/phone sai format<br>3. Lưu | Email: driver@<br>Phone: 09AB123456 | Hệ thống từ chối dữ liệu sai format | Medium |

## 3. Tạo yêu cầu và lựa chọn tài xế/xe

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-BOOKING-001 | Tạo yêu cầu và lựa chọn tài xế/xe | [Positive] Tạo yêu cầu đặt xe với dữ liệu hợp lệ | Khách hàng đã đăng nhập | 1. Mở đặt xe<br>2. Nhập điểm đón<br>3. Nhập điểm đến<br>4. Chọn loại xe<br>5. Nhấn Tạo yêu cầu | Pickup: 123 Nguyễn Huệ, Q1<br>Destination: Landmark 81<br>Type: Sedan | Yêu cầu được tạo thành công với trạng thái ban đầu và hiển thị danh sách tài xế/xe | High |
| TC-BOOKING-002 | Tạo yêu cầu và lựa chọn tài xế/xe | [Positive] Chọn tài xế và phương tiện đang Available | Đã tạo yêu cầu; có tài xế Available | 1. Xem danh sách<br>2. Chọn tài xế<br>3. Chọn xe<br>4. Xác nhận | Driver: DRV001<br>Vehicle: 51A-123.45 | Tài xế và xe được gán thành công cho yêu cầu | High |
| TC-BOOKING-003 | Tạo yêu cầu và lựa chọn tài xế/xe | [Negative] Chưa đăng nhập nhưng tạo yêu cầu | Khách hàng chưa đăng nhập | 1. Mở màn hình đặt xe<br>2. Nhập thông tin<br>3. Nhấn tạo yêu cầu | Pickup/Destination hợp lệ | Hệ thống từ chối và yêu cầu khách hàng đăng nhập | High |
| TC-BOOKING-004 | Tạo yêu cầu và lựa chọn tài xế/xe | [Negative] Không có tài xế Available | Khách hàng đã đăng nhập; không có driver Available | 1. Nhập dữ liệu chuyến<br>2. Tạo yêu cầu | Driver Available: 0 | Yêu cầu được tạo theo trạng thái chờ; không cho chọn tài xế không khả dụng | High |
| TC-BOOKING-005 | Tạo yêu cầu và lựa chọn tài xế/xe | [Boundary] Chỉ nhập vừa đủ các dữ liệu bắt buộc | Khách hàng đã đăng nhập | 1. Nhập đúng các trường bắt buộc<br>2. Không nhập trường không bắt buộc<br>3. Submit | Pickup + Destination + Vehicle Type vừa đủ | Hệ thống chấp nhận và tạo yêu cầu thành công | Medium |
| TC-BOOKING-006 | Tạo yêu cầu và lựa chọn tài xế/xe | [Boundary] Chọn tài xế khả dụng duy nhất | Chỉ có 1 driver Available phù hợp | 1. Tạo yêu cầu<br>2. Mở danh sách<br>3. Chọn driver duy nhất<br>4. Xác nhận | Available driver: DRV001 | Hệ thống hiển thị đúng driver duy nhất và cho phép gán | High |
| TC-BOOKING-007 | Tạo yêu cầu và lựa chọn tài xế/xe | [Rỗng] Bỏ trống điểm đón | Đã đăng nhập | 1. Không nhập pickup<br>2. Nhập destination<br>3. Chọn loại xe<br>4. Submit | Pickup: rỗng | Hệ thống không tạo yêu cầu và yêu cầu nhập điểm đón | High |
| TC-BOOKING-008 | Tạo yêu cầu và lựa chọn tài xế/xe | [Rỗng] Bỏ trống điểm đến | Đã đăng nhập | 1. Nhập pickup<br>2. Không nhập destination<br>3. Chọn loại xe<br>4. Submit | Destination: rỗng | Hệ thống không tạo yêu cầu và yêu cầu nhập điểm đến | High |
| TC-BOOKING-009 | Tạo yêu cầu và lựa chọn tài xế/xe | [Format] Loại xe không nằm trong danh sách được hỗ trợ | Đã đăng nhập | 1. Nhập pickup/destination<br>2. Gửi vehicle type không hợp lệ<br>3. Submit | Vehicle type: Airplane | Hệ thống từ chối giá trị không được hỗ trợ | Medium |
| TC-BOOKING-010 | Tạo yêu cầu và lựa chọn tài xế/xe | [Format] Driver ID/Vehicle ID sai định dạng khi gửi request | Khách hàng đã tạo yêu cầu | 1. Chọn tài xế/xe hoặc gửi request qua API<br>2. Truyền ID sai kiểu dữ liệu | driver_id: ABC123<br>vehicle_id: XYZ | Hệ thống từ chối request và trả lỗi dữ liệu đầu vào | Medium |

## 4. Tài xế không còn khả dụng trước xác nhận

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-DRIVERSEL-001 | Tài xế không còn khả dụng trước xác nhận | [Positive] Tài xế vẫn Available khi xác nhận | Đã có yêu cầu; driver Available | 1. Chọn driver<br>2. Chọn vehicle<br>3. Xác nhận | Driver: DRV001<br>Status: Available | Hệ thống xác nhận và gán driver + vehicle | High |
| TC-DRIVERSEL-002 | Tài xế không còn khả dụng trước xác nhận | [Positive] Danh sách mới vẫn hiển thị đúng tài xế Available | Có nhiều driver; một driver thay đổi trạng thái | 1. Refresh danh sách<br>2. Kiểm tra driver | DRV001 = Available<br>DRV002 = Available | Chỉ các driver Available được hiển thị | High |
| TC-DRIVERSEL-003 | Tài xế không còn khả dụng trước xác nhận | [Negative] Tài xế chuyển Unavailable trước khi xác nhận | Driver ban đầu Available | 1. Khách chọn DRV001<br>2. DRV001 chuyển Unavailable<br>3. Khách nhấn Xác nhận | DRV001: Available → Unavailable | Hệ thống từ chối lựa chọn và thông báo driver không còn khả dụng | High |
| TC-DRIVERSEL-004 | Tài xế không còn khả dụng trước xác nhận | [Negative] Tài xế đã nhận request khác | Driver ban đầu Available | 1. Khách chọn driver<br>2. Driver được gán request khác<br>3. Khách xác nhận request cũ | DRV001 đã bận | Hệ thống không gán driver lần hai | High |
| TC-DRIVERSEL-005 | Tài xế không còn khả dụng trước xác nhận | [Boundary] Driver đổi trạng thái đúng thời điểm khách nhấn Confirm | Driver đang Available | 1. Chọn driver<br>2. Đồng thời đổi status driver<br>3. Nhấn Confirm | Available → Unavailable | Hệ thống dùng trạng thái tại thời điểm kiểm tra cuối; nếu Unavailable thì từ chối gán | High |
| TC-DRIVERSEL-006 | Tài xế không còn khả dụng trước xác nhận | [Boundary] Chỉ còn một driver và driver đó vừa Unavailable | Có duy nhất 1 driver Available | 1. Chọn driver<br>2. Driver chuyển Unavailable<br>3. Confirm | Available drivers: 1 → 0 | Không gán driver; hệ thống hiển thị danh sách mới hoặc trạng thái không còn driver khả dụng | High |
| TC-DRIVERSEL-007 | Tài xế không còn khả dụng trước xác nhận | [Rỗng] Không chọn tài xế nhưng nhấn Confirm | Đã tạo yêu cầu | 1. Mở danh sách driver<br>2. Không chọn driver<br>3. Confirm | Driver: rỗng | Hệ thống không cho xác nhận và yêu cầu chọn tài xế | High |
| TC-DRIVERSEL-008 | Tài xế không còn khả dụng trước xác nhận | [Rỗng] Không chọn phương tiện | Đã chọn driver | 1. Chọn driver<br>2. Không chọn vehicle<br>3. Confirm | Vehicle: rỗng | Hệ thống không gán request và yêu cầu chọn phương tiện | High |
| TC-DRIVERSEL-009 | Tài xế không còn khả dụng trước xác nhận | [Format] Driver ID không đúng kiểu dữ liệu | Đã tạo yêu cầu | 1. Gửi request xác nhận<br>2. Truyền driver_id sai format | driver_id: DRV@001 | Hệ thống từ chối request | Medium |
| TC-DRIVERSEL-010 | Tài xế không còn khả dụng trước xác nhận | [Format] Vehicle ID không đúng kiểu dữ liệu | Đã tạo yêu cầu | 1. Chọn driver hợp lệ<br>2. Gửi vehicle_id sai format | vehicle_id: CAR#01 | Hệ thống từ chối request và không tạo liên kết sai | Medium |

## 5. Tài xế nhận và hoàn thành chuyến

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC-TRIP-001 | Tài xế nhận và hoàn thành chuyến | [Positive] Tài xế chấp nhận chuyến được gán | Request đã được gán cho DRV001 | 1. Tài xế mở danh sách yêu cầu<br>2. Chọn request<br>3. Nhấn Chấp nhận | Driver: DRV001<br>Ride: RIDE001 | Request được xác nhận và gán cho driver | High |
| TC-TRIP-002 | Tài xế nhận và hoàn thành chuyến | [Positive] Cập nhật chuyến đến trạng thái hoàn thành | Tài xế đã nhận chuyến | 1. Cập nhật trạng thái chuyến theo quá trình<br>2. Xác nhận hoàn thành | Đã có tài xế → Đang thực hiện → Hoàn thành | Trạng thái được lưu đúng và khách hàng nhìn thấy trạng thái mới | High |
| TC-TRIP-003 | Tài xế nhận và hoàn thành chuyến | [Negative] Tài xế không được gán cố cập nhật chuyến | RIDE001 thuộc DRV001 | 1. Đăng nhập DRV002<br>2. Gửi yêu cầu cập nhật RIDE001 | Driver: DRV002<br>Ride: RIDE001 | Hệ thống từ chối vì DRV002 không phải driver được gán | High |
| TC-TRIP-004 | Tài xế nhận và hoàn thành chuyến | [Negative] Tài xế đang có chuyến hoạt động cố nhận thêm chuyến | DRV001 đang thực hiện RIDE001 | 1. Mở request mới RIDE002<br>2. Nhấn Chấp nhận | Active trip: RIDE001<br>New: RIDE002 | Hệ thống từ chối không cho nhận thêm chuyến | High |
| TC-TRIP-005 | Tài xế nhận và hoàn thành chuyến | [Boundary] Chuyển từ Đang thực hiện sang Hoàn thành | Chuyến đang ở trạng thái Đang thực hiện | 1. Mở trạng thái<br>2. Chọn Hoàn thành<br>3. Xác nhận | Status: Đang thực hiện → Hoàn thành | Hệ thống cho phép hoàn tất và lưu thời gian completed | High |
| TC-TRIP-006 | Tài xế nhận và hoàn thành chuyến | [Boundary] Đã Hoàn thành nhưng cố cập nhật trạng thái lần nữa | RIDE001 đã Hoàn thành | 1. Mở RIDE001<br>2. Chọn trạng thái khác<br>3. Submit | Hoàn thành → Đang thực hiện | Hệ thống từ chối thay đổi trạng thái của chuyến đã hoàn thành | High |
| TC-TRIP-007 | Tài xế nhận và hoàn thành chuyến | [Rỗng] Không truyền trạng thái chuyến | Driver được gán hợp lệ | 1. Mở cập nhật trạng thái<br>2. Không chọn status<br>3. Submit | Status: rỗng | Hệ thống không cập nhật và yêu cầu chọn trạng thái | High |
| TC-TRIP-008 | Tài xế nhận và hoàn thành chuyến | [Rỗng] Không truyền Ride ID | Đã đăng nhập tài xế | 1. Gửi request cập nhật<br>2. Bỏ trống ride_id | ride_id: rỗng | Hệ thống từ chối request vì thiếu ID chuyến | High |
| TC-TRIP-009 | Tài xế nhận và hoàn thành chuyến | [Format] Gửi trạng thái không nằm trong tập trạng thái hệ thống | Driver được xác thực | 1. Gửi update status<br>2. Truyền giá trị ngoài danh sách | Status: CANCELLED_UNKNOWN | Hệ thống từ chối trạng thái không hợp lệ | Medium |
| TC-TRIP-010 | Tài xế nhận và hoàn thành chuyến | [Format] Ride ID sai định dạng | Driver đã đăng nhập | 1. Gửi request cập nhật<br>2. Truyền ride_id không đúng kiểu | ride_id: RIDE@001 | Hệ thống từ chối request và không làm thay đổi dữ liệu chuyến | Medium |
