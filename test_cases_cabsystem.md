# TEST CASE – CAB SYSTEM

## 1. Thông tin chung

Tài liệu này tổng hợp toàn bộ **100 Test Case** cho 5 Test Scenario nghiệp vụ cốt lõi của CAB System.

Cấu trúc mỗi Test Case gồm 8 cột:

- **Test Case ID**: Mã định danh duy nhất.
- **Test Scenario**: Scenario mà Test Case đang kiểm thử.
- **Test Case**: Trường hợp kiểm thử cụ thể.
- **Preconditions**: Điều kiện tiên quyết trước khi thực hiện.
- **Test Steps**: Các bước thực hiện kiểm thử.
- **Test Data**: Dữ liệu đầu vào sử dụng để kiểm thử.
- **Expected Result**: Kết quả hệ thống mong đợi.
- **Priority**: Mức độ ưu tiên.

> **Lưu ý:** SRS chưa quy định cụ thể Min/Max Length và regex chính thức cho mọi field. Các Test Case Boundary/Format liên quan đến những giới hạn này là test design đề xuất; khi triển khai thực tế cần thay bằng giới hạn chính thức của UI/API/database.

---

# 2. Test Scenario 01 – Đăng ký và đăng nhập tài khoản khách hàng

**Scenario:** Kiểm tra chức năng đăng ký tài khoản và đăng nhập của khách hàng.

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_LOGIN_001 | Đăng ký & đăng nhập | Đăng ký tài khoản với toàn bộ thông tin hợp lệ | Chưa tồn tại tài khoản | 1. Mở Đăng ký<br>2. Nhập thông tin<br>3. Nhấn Đăng ký | Name: Nguyễn Văn A<br>Email: user01@gmail.com<br>Phone: 0912345678<br>Password: User@123 | Tài khoản được tạo thành công | High |
| TC_LOGIN_002 | Đăng ký & đăng nhập | Đăng nhập bằng tài khoản và mật khẩu hợp lệ | Tài khoản đã tồn tại | 1. Mở Login<br>2. Nhập username/password<br>3. Login | user01 / User@123 | Đăng nhập thành công và chuyển vào hệ thống | High |
| TC_LOGIN_003 | Đăng ký & đăng nhập | Đăng nhập sai mật khẩu | Tài khoản tồn tại | Nhập username đúng, password sai | user01 / Wrong@123 | Không cho đăng nhập, hiển thị thông báo lỗi | High |
| TC_LOGIN_004 | Đăng ký & đăng nhập | Đăng nhập bằng tài khoản không tồn tại | Không có user này | Nhập username/password | unknown01 / User@123 | Không đăng nhập, báo tài khoản không tồn tại hoặc thông tin không hợp lệ | High |
| TC_LOGIN_005 | Đăng ký & đăng nhập | Đăng ký với email đã tồn tại | Email đã được sử dụng | Nhập form đăng ký | Email: user01@gmail.com | Không tạo tài khoản mới, báo email đã tồn tại | High |
| TC_LOGIN_006 | Đăng ký & đăng nhập | Đăng ký với số điện thoại đã tồn tại | SĐT đã tồn tại | Nhập form | Phone: 0912345678 | Không tạo tài khoản mới, báo SĐT đã tồn tại | High |
| TC_LOGIN_007 | Đăng ký & đăng nhập | Để trống toàn bộ form đăng ký | Đang ở trang đăng ký | Không nhập gì → Submit | Name=""; Email=""; Phone=""; Password="" | Hiển thị lỗi tại các trường bắt buộc | High |
| TC_LOGIN_008 | Đăng ký & đăng nhập | Bỏ trống họ tên | Đang ở trang đăng ký | Nhập các trường khác → Submit | Name="" | Không đăng ký thành công, yêu cầu nhập họ tên | Medium |
| TC_LOGIN_009 | Đăng ký & đăng nhập | Bỏ trống email | Đang ở trang đăng ký | Nhập các trường khác → Submit | Email="" | Không đăng ký, báo email bắt buộc | Medium |
| TC_LOGIN_010 | Đăng ký & đăng nhập | Bỏ trống số điện thoại | Đang ở trang đăng ký | Nhập các trường khác → Submit | Phone="" | Không đăng ký, báo SĐT bắt buộc | Medium |
| TC_LOGIN_011 | Đăng ký & đăng nhập | Bỏ trống mật khẩu | Đang ở trang đăng ký | Nhập các trường khác → Submit | Password="" | Không đăng ký, báo mật khẩu bắt buộc | High |
| TC_LOGIN_012 | Đăng ký & đăng nhập | Email sai format | Đang ở trang đăng ký | Nhập email sai → Submit | user01gmail.com | Hệ thống từ chối email không hợp lệ | High |
| TC_LOGIN_013 | Đăng ký & đăng nhập | Số điện thoại sai format | Đang ở trang đăng ký | Nhập SĐT chữ/ký tự đặc biệt | 09AB123456 | Hệ thống từ chối SĐT sai format | High |
| TC_LOGIN_014 | Đăng ký & đăng nhập | Mật khẩu ở mức độ dài tối thiểu được hệ thống cho phép | Đang ở trang đăng ký | Nhập password tại ngưỡng tối thiểu → Submit | Password theo ngưỡng Min Length của hệ thống | Nếu đạt rule → đăng ký thành công | Medium |
| TC_LOGIN_015 | Đăng ký & đăng nhập | Mật khẩu vượt quá giới hạn cho phép | Đang ở trang đăng ký | Nhập password vượt Max Length | Password dài vượt giới hạn hệ thống | Không đăng ký, báo dữ liệu không hợp lệ | Medium |
| TC_LOGIN_016 | Đăng ký & đăng nhập | Họ tên ở biên độ dài tối đa | Đang ở trang đăng ký | Nhập tên tại Max Length | Name = chuỗi đúng Max Length | Dữ liệu được xử lý đúng theo giới hạn hệ thống | Low |
| TC_LOGIN_017 | Đăng ký & đăng nhập | Login bỏ trống username | Tại Login | Để username trống → Login | Username="" | Báo username bắt buộc | High |
| TC_LOGIN_018 | Đăng ký & đăng nhập | Login bỏ trống password | Tại Login | Để password trống → Login | Password="" | Báo password bắt buộc | High |
| TC_LOGIN_019 | Đăng ký & đăng nhập | Login với username/password chứa khoảng trắng không hợp lệ | Tài khoản tồn tại | Nhập dữ liệu có space sai vị trí | ` user01 ` / ` User@123 ` | Hệ thống xử lý/chuẩn hóa hoặc từ chối theo rule; không tạo phiên sai | Medium |
| TC_LOGIN_020 | Đăng ký & đăng nhập | Tài khoản bị khóa cố gắng đăng nhập | Tài khoản có trạng thái Locked/Inactive | Nhập tài khoản bị khóa → Login | user_locked / User@123 | Không cho đăng nhập và thông báo tài khoản không được phép sử dụng | High |

---

# 3. Test Scenario 02 – Tài xế cập nhật phương tiện và chuyển sang Available

**Scenario:** Kiểm tra điều kiện hồ sơ, phương tiện và trạng thái hoạt động của tài xế.

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_DRIVER_001 | Driver Available | Tài xế có hồ sơ và xe hợp lệ chuyển sang Available | Driver đã đăng nhập, có xe hợp lệ | Mở trạng thái → chọn Available | Driver01; Vehicle hợp lệ | Trạng thái chuyển thành Available | High |
| TC_DRIVER_002 | Driver Available | Tài xế không có xe cố gắng chuyển Available | Driver đăng nhập, chưa có vehicle | Chọn Available | Driver01; Vehicle=None | Hệ thống từ chối chuyển Available | High |
| TC_DRIVER_003 | Driver Available | Tài xế có thông tin xe đầy đủ | Driver đã đăng nhập | Nhập thông tin xe → Save | Plate: 51A-12345; Type: Sedan | Xe được lưu và gắn đúng tài xế | High |
| TC_DRIVER_004 | Driver Available | Cập nhật xe với biển số đã tồn tại | Xe có biển số này đã tồn tại | Nhập plate trùng | 51A-12345 | Hệ thống từ chối dữ liệu trùng/không hợp lệ | High |
| TC_DRIVER_005 | Driver Available | Để trống biển số xe | Driver đang quản lý vehicle | Xóa plate → Save | Plate="" | Không lưu, báo trường bắt buộc | High |
| TC_DRIVER_006 | Driver Available | Để trống loại xe | Driver đang quản lý vehicle | Xóa Vehicle Type → Save | Type="" | Không lưu, báo bắt buộc | High |
| TC_DRIVER_007 | Driver Available | Biển số xe sai format | Driver có quyền sửa xe | Nhập biển số sai | ABC123XYZ | Hệ thống từ chối format biển số không hợp lệ | Medium |
| TC_DRIVER_008 | Driver Available | Số điện thoại tài xế sai format | Driver tồn tại | Cập nhật phone | 09AB123456 | Không lưu thông tin sai format | Medium |
| TC_DRIVER_009 | Driver Available | Email tài xế sai format | Driver tồn tại | Cập nhật email | drivergmail.com | Không lưu và báo email không hợp lệ | Medium |
| TC_DRIVER_010 | Driver Available | Không nhập dữ liệu xe | Driver đăng nhập | Mở form xe → Save | Plate=""; Type=""; Brand=""; Model="" | Hệ thống từ chối lưu | High |
| TC_DRIVER_011 | Driver Available | Driver chuyển từ Offline sang Available | Driver có vehicle hợp lệ | Chọn Offline → Available | Status=Available | Trạng thái được cập nhật | High |
| TC_DRIVER_012 | Driver Available | Driver chuyển từ Available sang Offline | Driver đang Available | Chọn Offline | Status=Offline | Driver không còn trong danh sách khả dụng | High |
| TC_DRIVER_013 | Driver Available | Driver chuyển Available khi đang thực hiện chuyến | Driver đang có chuyến active | Chọn Available | Active Ride exists | Hệ thống không cho chuyển sang trạng thái nhận chuyến nếu vi phạm rule | High |
| TC_DRIVER_014 | Driver Available | Giá trị status không hợp lệ | Driver đăng nhập | Gửi request status ngoài enum | Status=ABC | Hệ thống từ chối dữ liệu | High |
| TC_DRIVER_015 | Driver Available | Vehicle type là giá trị rỗng/blank | Driver đang nhập vehicle | Nhập khoảng trắng → Save | Type="   " | Hệ thống coi như rỗng và từ chối | Medium |
| TC_DRIVER_016 | Driver Available | Plate tại độ dài tối thiểu hợp lệ | Form vehicle mở | Nhập plate theo Min Length | Plate theo boundary system | Nếu hợp lệ → lưu thành công | Low |
| TC_DRIVER_017 | Driver Available | Plate vượt độ dài tối đa | Form vehicle mở | Nhập plate quá dài | Chuỗi > Max Length | Hệ thống từ chối hoặc validation lỗi | Low |
| TC_DRIVER_018 | Driver Available | Không đăng nhập nhưng truy cập cập nhật status | Driver chưa login | Mở API/UI update status | No Session | Hệ thống yêu cầu xác thực | High |
| TC_DRIVER_019 | Driver Available | Tài khoản driver bị khóa cập nhật status | Driver Locked | Login/update status | driver_locked | Không được sử dụng chức năng | High |
| TC_DRIVER_020 | Driver Available | Cập nhật vehicle của driver khác | Driver A đăng nhập | Gửi vehicle_id thuộc Driver B | vehicle_id=B | Hệ thống từ chối do không có quyền | High |

---

# 4. Test Scenario 03 – Khách hàng tạo yêu cầu đặt xe và lựa chọn tài xế/xe

**Scenario:** Kiểm tra luồng khách hàng tạo yêu cầu, xem danh sách tài xế khả dụng và lựa chọn tài xế/phương tiện.

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_BOOKING_001 | Tạo yêu cầu & chọn tài xế | Tạo yêu cầu với dữ liệu hợp lệ | Customer đã login | Nhập pickup → destination → vehicle type → Submit | Pickup: Q1; Destination: Q3; Type: Sedan | Request được tạo thành công | High |
| TC_BOOKING_002 | Tạo yêu cầu & chọn tài xế | Chọn tài xế Available | Request đã tạo, có Available driver | Mở danh sách → chọn driver | Driver01 = Available | Driver được lựa chọn | High |
| TC_BOOKING_003 | Tạo yêu cầu & chọn tài xế | Chọn phương tiện hợp lệ của driver | Request tồn tại | Chọn driver → chọn vehicle | Vehicle01 thuộc Driver01 | Vehicle được chọn đúng | High |
| TC_BOOKING_004 | Tạo yêu cầu & chọn tài xế | Tạo yêu cầu không nhập pickup | Customer login | Bỏ trống pickup → Submit | Pickup="" | Không tạo request, báo bắt buộc | High |
| TC_BOOKING_005 | Tạo yêu cầu & chọn tài xế | Tạo yêu cầu không nhập destination | Customer login | Bỏ trống destination | Destination="" | Không tạo request | High |
| TC_BOOKING_006 | Tạo yêu cầu & chọn tài xế | Không chọn loại xe | Customer login | Không chọn vehicle type → Submit | Type="" | Không tạo request | High |
| TC_BOOKING_007 | Tạo yêu cầu & chọn tài xế | Không nhập bất kỳ dữ liệu nào | Customer login | Submit form rỗng | Pickup=""; Destination=""; Type="" | Hiển thị validation cho các field bắt buộc | High |
| TC_BOOKING_008 | Tạo yêu cầu & chọn tài xế | Pickup và destination giống nhau | Customer login | Nhập cùng địa điểm | Q1 → Q1 | Hệ thống từ chối nếu rule không cho phép cùng điểm | Medium |
| TC_BOOKING_009 | Tạo yêu cầu & chọn tài xế | Chỉ có đúng 1 driver Available | Có 1 Available driver | Tạo request → xem list | Driver01 = Available | Danh sách chứa đúng 1 driver | High |
| TC_BOOKING_010 | Tạo yêu cầu & chọn tài xế | Không có driver Available | Không có driver Available | Tạo request | Available Drivers=0 | Request được tạo/chuyển trạng thái chờ; không hiển thị driver lựa chọn | High |
| TC_BOOKING_011 | Tạo yêu cầu & chọn tài xế | Có nhiều driver Available | Có nhiều driver | Tạo request → xem list | D01, D02, D03 Available | Hiển thị các driver khả dụng | High |
| TC_BOOKING_012 | Tạo yêu cầu & chọn tài xế | Driver Offline không xuất hiện | Driver Offline tồn tại | Mở danh sách | D01=Offline | D01 không xuất hiện | High |
| TC_BOOKING_013 | Tạo yêu cầu & chọn tài xế | Driver Unavailable không xuất hiện | Driver Unavailable tồn tại | Mở danh sách | D01=Unavailable | D01 không xuất hiện | High |
| TC_BOOKING_014 | Tạo yêu cầu & chọn tài xế | Pickup sai format/dữ liệu không hợp lệ | Customer login | Nhập pickup bất thường | @@@### | Hệ thống từ chối hoặc yêu cầu địa điểm hợp lệ | Medium |
| TC_BOOKING_015 | Tạo yêu cầu & chọn tài xế | Destination sai format | Customer login | Nhập destination không hợp lệ | @@@### | Validation lỗi | Medium |
| TC_BOOKING_016 | Tạo yêu cầu & chọn tài xế | Pickup ở boundary độ dài tối thiểu | Customer login | Nhập pickup tại Min Length | 1 ký tự theo rule triển khai | Hệ thống xử lý đúng giới hạn | Low |
| TC_BOOKING_017 | Tạo yêu cầu & chọn tài xế | Pickup vượt boundary độ dài tối đa | Customer login | Nhập pickup quá dài | > Max Length | Không chấp nhận dữ liệu vượt giới hạn | Low |
| TC_BOOKING_018 | Tạo yêu cầu & chọn tài xế | Chọn tài xế nhưng không chọn xe | Request tồn tại | Chọn Driver → bỏ Vehicle → Confirm | Driver01; Vehicle="" | Không xác nhận/gán request nếu vehicle là bắt buộc | High |
| TC_BOOKING_019 | Tạo yêu cầu & chọn tài xế | Chọn xe không thuộc tài xế đã chọn | Có nhiều driver/vehicle | Chọn D01 → gửi vehicle của D02 | Driver=D01; Vehicle=D02 | Hệ thống từ chối do vehicle không thuộc driver | High |
| TC_BOOKING_020 | Tạo yêu cầu & chọn tài xế | Một request cố gắng gán nhiều driver/vehicle | Request đã có assignment | Gửi cập nhật assignment lần 2 | D01/V01 → D02/V02 | Không cho một request có nhiều driver/vehicle tại cùng thời điểm | High |

---

# 5. Test Scenario 04 – Tài xế không còn khả dụng trước khi khách hàng xác nhận

**Scenario:** Kiểm tra việc xác thực lại trạng thái tài xế ngay trước khi khách hàng xác nhận lựa chọn.

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_DRIVERSEL_001 | Driver unavailable | Driver vẫn Available khi confirm | Customer đã tạo request | Chọn driver → Confirm | D01=Available | Request được gán D01 | High |
| TC_DRIVERSEL_002 | Driver unavailable | Driver chuyển Unavailable trước Confirm | Customer đang chọn D01 | D01 đổi status → Customer Confirm | D01: Available → Unavailable | Confirm bị từ chối | High |
| TC_DRIVERSEL_003 | Driver unavailable | Driver chuyển Offline trước Confirm | Customer đang chọn D01 | D01 đổi Offline → Confirm | D01=Offline | Hệ thống từ chối lựa chọn | High |
| TC_DRIVERSEL_004 | Driver unavailable | Driver được request khác gán trước Confirm | Customer A đang chọn D01 | Customer B gán D01 trước | D01 assigned to B | Customer A không được gán D01 | High |
| TC_DRIVERSEL_005 | Driver unavailable | Refresh danh sách sau khi driver unavailable | D01 vừa unavailable | Refresh list | D01=Unavailable | D01 không còn trong danh sách | High |
| TC_DRIVERSEL_006 | Driver unavailable | Danh sách mới có driver thay thế | D01 unavailable, D02 available | Confirm → refresh | D01 unavailable; D02 available | D02 xuất hiện để lựa chọn | High |
| TC_DRIVERSEL_007 | Driver unavailable | Không còn driver nào sau khi driver được chọn mất trạng thái | Chỉ có D01 | D01 unavailable → Confirm | D01 only | Thông báo không có driver khả dụng | High |
| TC_DRIVERSEL_008 | Driver unavailable | Driver status bị thiếu/null | Request đang chọn D01 | Xác nhận khi status null | status=null | Hệ thống không cho confirm | High |
| TC_DRIVERSEL_009 | Driver unavailable | Driver ID rỗng khi confirm | Request exists | Submit confirm không có driver | driver_id="" | Validation lỗi, không gán | High |
| TC_DRIVERSEL_010 | Driver unavailable | Vehicle ID rỗng khi confirm | Driver đã chọn | Confirm không vehicle | vehicle_id="" | Không hoàn tất assignment | High |
| TC_DRIVERSEL_011 | Driver unavailable | Chọn driver không tồn tại | Request exists | Gửi driver_id giả | driver_id=999999 | Hệ thống báo driver không tồn tại | High |
| TC_DRIVERSEL_012 | Driver unavailable | Chọn vehicle không tồn tại | Request exists | Gửi vehicle_id giả | vehicle_id=999999 | Hệ thống từ chối | High |
| TC_DRIVERSEL_013 | Driver unavailable | Driver không khớp vehicle | D01 và V02 thuộc D02 | Chọn D01 + V02 | D01/V02 | Không cho assignment | High |
| TC_DRIVERSEL_014 | Driver unavailable | Chọn driver ở boundary danh sách = 1 driver | Chỉ D01 available | Chọn D01 → Confirm | 1 Available Driver | Assignment thành công | Medium |
| TC_DRIVERSEL_015 | Driver unavailable | Danh sách có 0 driver | Không có Available Driver | Mở selection | 0 drivers | Hiển thị trạng thái không có driver khả dụng | High |
| TC_DRIVERSEL_016 | Driver unavailable | Danh sách có số lượng lớn driver | Có nhiều drivers | Mở selection | N drivers theo giới hạn hệ thống | Danh sách hiển thị/phân trang đúng | Medium |
| TC_DRIVERSEL_017 | Driver unavailable | Confirm nhiều lần cùng một request | Request đã được gán | Nhấn Confirm liên tục | D01/V01 | Không tạo assignment trùng hoặc dữ liệu trùng | High |
| TC_DRIVERSEL_018 | Driver unavailable | Gửi status giả để bypass Available | API/UI request | Thay status bằng giá trị khác | status="Available " hoặc ABC | Server validation từ chối | High |
| TC_DRIVERSEL_019 | Driver unavailable | Hai khách hàng cùng chọn một driver gần như đồng thời | D01 Available | Customer A/B cùng Confirm | A→D01; B→D01 | Chỉ một request được gán D01; request còn lại bị từ chối/cập nhật | High |
| TC_DRIVERSEL_020 | Driver unavailable | Driver quay lại Available sau khi confirm thất bại | D01 unavailable tại thời điểm confirm | Fail confirm → D01 Available lại → Refresh | D01 Unavailable → Available | Danh sách mới hiển thị D01 và có thể lựa chọn lại | Medium |

---

# 6. Test Scenario 05 – Tài xế nhận chuyến, cập nhật trạng thái và hoàn thành

**Scenario:** Kiểm tra vòng đời chuyến từ lúc tài xế nhận chuyến đến khi hoàn thành và lưu lịch sử.

| Test Case ID | Test Scenario | Test Case | Preconditions | Test Steps | Test Data | Expected Result | Priority |
|---|---|---|---|---|---|---|---|
| TC_TRIP_001 | Nhận & hoàn thành chuyến | Driver nhận request hợp lệ | Request đã được gán cho driver | Driver mở request → Accept | Ride R01; Driver D01 | Request được gán/xác nhận cho D01 | High |
| TC_TRIP_002 | Nhận & hoàn thành chuyến | Driver từ chối request | Request đang chờ driver | Driver chọn Reject | Ride R01 | Request vẫn tồn tại và có thể xử lý tiếp | High |
| TC_TRIP_003 | Nhận & hoàn thành chuyến | Driver cập nhật sang đã đến điểm đón | Driver đã nhận chuyến | Chọn trạng thái | ARRIVED_PICKUP | Trạng thái được lưu | High |
| TC_TRIP_004 | Nhận & hoàn thành chuyến | Driver cập nhật đã đón khách | Driver đã đến pickup | Chọn trạng thái | PASSENGER_PICKED_UP | Trạng thái được cập nhật | High |
| TC_TRIP_005 | Nhận & hoàn thành chuyến | Driver cập nhật đang di chuyển | Đã đón khách | Chọn trạng thái | IN_PROGRESS | Khách hàng thấy trạng thái cập nhật | High |
| TC_TRIP_006 | Nhận & hoàn thành chuyến | Driver cập nhật hoàn thành | Trip đang thực hiện | Chọn Complete | COMPLETED | Chuyến được hoàn thành và lưu thời gian hoàn thành | High |
| TC_TRIP_007 | Nhận & hoàn thành chuyến | Cập nhật status đúng thứ tự | Trip active | ARRIVED → PICKED_UP → IN_PROGRESS → COMPLETED | Chuỗi trạng thái hợp lệ | Tất cả trạng thái được ghi nhận đúng | High |
| TC_TRIP_008 | Nhận & hoàn thành chuyến | Bỏ qua trạng thái trung gian | Trip mới nhận | Chuyển trực tiếp COMPLETED | Current=ASSIGNED | Hệ thống chấp nhận hoặc từ chối theo state rule triển khai | Medium |
| TC_TRIP_009 | Nhận & hoàn thành chuyến | Driver không được gán cố gắng cập nhật trip | Request thuộc D02 | D01 update status | D01 ≠ assigned driver | Hệ thống từ chối | High |
| TC_TRIP_010 | Nhận & hoàn thành chuyến | Cập nhật trạng thái khi không đăng nhập | Driver chưa login | Gọi update status | No session | Yêu cầu authentication | High |
| TC_TRIP_011 | Nhận & hoàn thành chuyến | Cập nhật trạng thái bằng ride_id không tồn tại | Driver login | Gửi ride_id giả | 999999 | Báo trip không tồn tại | High |
| TC_TRIP_012 | Nhận & hoàn thành chuyến | Trạng thái chuyến rỗng | Driver được gán | Gửi status="" | status="" | Validation lỗi | High |
| TC_TRIP_013 | Nhận & hoàn thành chuyến | Trạng thái chuyến sai format/enum | Driver được gán | Gửi giá trị không hợp lệ | status=ABC | Hệ thống từ chối | High |
| TC_TRIP_014 | Nhận & hoàn thành chuyến | Driver đang chạy chuyến A nhận thêm chuyến B | D01 đang active Ride A | Mở Ride B → Accept | A=IN_PROGRESS; B=PENDING | Không cho D01 nhận B | High |
| TC_TRIP_015 | Nhận & hoàn thành chuyến | Driver từ chối một request | Request pending | Reject | R01=PENDING | Request không bị xóa, có thể xử lý tiếp | High |
| TC_TRIP_016 | Nhận & hoàn thành chuyến | Cập nhật trạng thái completed hai lần | Ride đã completed | Gửi Complete lần 2 | R01=COMPLETED | Không tạo cập nhật/lịch sử trùng | Medium |
| TC_TRIP_017 | Nhận & hoàn thành chuyến | Khách hàng theo dõi trạng thái sau khi driver nhận | Driver accepted | Customer mở trip | R01 | Trạng thái hiển thị Đã có tài xế/trạng thái tương ứng | High |
| TC_TRIP_018 | Nhận & hoàn thành chuyến | Khách hàng thấy trạng thái đang thực hiện | Driver đang IN_PROGRESS | Customer refresh | R01=IN_PROGRESS | Hiển thị đúng trạng thái đang thực hiện | High |
| TC_TRIP_019 | Nhận & hoàn thành chuyến | Khách hàng thấy chuyến hoàn thành trong lịch sử | Trip completed | Customer mở History | R01=COMPLETED | Chuyến xuất hiện trong lịch sử của chính customer | High |
| TC_TRIP_020 | Nhận & hoàn thành chuyến | Người dùng xem lịch sử của customer khác | Customer A login | Truy vấn ride của B | customer_A ≠ customer_B | Không được xem dữ liệu lịch sử của B | High |
