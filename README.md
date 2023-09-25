# Spring security

## Bảo mật là gì?

Bảo mật là sự hạn chế khả năng lạm dụng tài nguyên và tài sản. Trong lĩnh vực công nghệ thông tin, bảo mật thông tin là việc bảo vệ thông tin khỏi những truy cập trái phép, sử dụng trái phép, tiết lộ trái phép, thay đổi trái phép hoặc phá hủy trái phép.

Bảo mật thông tin bao gồm ba yếu tố chính:

- Bảo mật: Đảm bảo chỉ những người được ủy quyền mới có thể truy cập thông tin.
- Tính toàn vẹn: Đảm bảo thông tin không bị thay đổi hoặc sửa đổi mà không có sự cho phép.
- Khả năng sẵn sàng: Đảm bảo thông tin luôn sẵn sàng khi cần thiết.

## Tại sao lại phải bảo mật thông tin

Bảo mật thông tin trong Spring Security là điều cần thiết vì các ứng dụng Java web thường lưu trữ và xử lý các thông tin nhạy cảm, chẳng hạn như thông tin cá nhân, thông tin tài chính, thông tin thương mại. Nếu thông tin này bị đánh cắp hoặc bị lộ, có thể gây ra những thiệt hại nghiêm trọng cho các tổ chức, cá nhân.

### Ba yếu tố chính khiến bảo mật ứng dụng web trở nên quan trọng là:
- Ngăn chặn việc mất dữ liệu nhạy cảm,
- Nhận ra rằng bảo mật vượt xa việc thử nghiệm
- Bảo vệ danh tiếng của tổ chức và hạn chế tổn thất.
- 
### Hệ lụy của việc một doanh nghiệp bị hack có thể vượt quá ngưỡng tài chính!

Các ứng dụng web có quá nhiều lỗ hổng, mặc dù một số cơ sở luôn có nguy cơ bị tấn công mạng cao hơn những cơ sở khác. Một ngành công nghiệp nổi bật là blockchain và tiền điện tử. Sự an toàn của các ứng dụng web là rất quan trọng cho sự thành công của bất kỳ công ty nào hoạt động trực tuyến. Thành phần nền tảng của nền kinh tế kỹ thuật số là dữ liệu và triển vọng đổi mới cũng như ác ý xung quanh chúng là không thể đo lường được.

Các ứng dụng web dễ bị tấn công từ nhiều vị trí địa lý, quy mô và mức độ phức tạp khác nhau do phạm vi tiếp cận toàn cầu của Internet. Bảo mật trang web, ứng dụng trực tuyến và dịch vụ web như API là mục tiêu chính của bảo mật ứng dụng web.

## Spring security là gì? 


Nói một cách đơn giản, Spring security cung cấp xác thực và ủy quyền cho ứng dụng của chúng ta bằng các bộ lọc servlet đơn giản. Các ứng dụng web dễ bị đe dọa và tấn công về mặt bảo mật vì bất kỳ ai sử dụng Internet đều có thể truy cập được chúng. Có thể tồn tại một số điểm cuối REST có quyền truy cập hạn chế đối với những người dùng cụ thể, ví dụ: cập nhật bản ghi hoặc các hoạt động liên quan đến quản trị viên.

 Spring security hoạt động dựa trên ba khái niệm cốt lõi sau

- Authentication.
- Authorization
- Password Storage
- Servlet Filters

### a, Authorization:
  Đây là bên cạnh việc xác thực. Đối với một ứng dụng đơn giản, việc xác thực người dùng có thể là đủ, nhưng hãy nghĩ về một ứng dụng doanh nghiệp lớn.

Một nhân viên bình thường (ví dụ: Nhân viên tổng đài) có thể chỉ có quyền hạn chế để thực hiện một số hoạt động nhất định. chúng ta không muốn cho phép nhân viên này thực hiện các hoạt động khác
Người quản lý sản phẩm phụ trợ của chúng ta chỉ được phép làm việc trên các sản phẩm. chúng ta không cho phép người quản lý sản phẩm thay đổi thông tin khách hàng hoặc thông tin đặt hàng.
Người quản lý thương mại điện tử có thể làm việc trên cả thông tin khách hàng và đơn đặt hàng nhưng họ không thể thay đổi thông tin sản phẩm.
Quản trị hệ thống có thể thực hiện tất cả các hoạt động.
Với xác thực đơn giản, chúng ta không thể hạn chế người dùng đăng nhập vì chúng ta không có thông tin về đặc quyền hoặc quyền của người dùng. Việc ủy ​​quyền giúp cung cấp thông tin này trước khi người dùng cố gắng truy cập tài nguyên. Đó là một quá trình kiểm soát truy cập, quyết định xem nó có cho phép hiệu trưởng thực hiện một hành động (kiểm soát truy cập → quản trị viên, người dùng, lãnh đạo, người quản lý, nhà thầu, ẩn danh, v.v.) hay không.

### b, Authentication:

Được sử dụng để xác minh xem người dùng có sử dụng ứng dụng hay không bằng cách cung cấp thông tin xác thực hợp lệ được sử dụng để xác minh bạn là ai! Xác thực là thiết lập danh tính của người chính (người dùng, hệ thống, có thể thực hiện một hành động trong ứng dụng).

### c, Password Storage

Đảm bảo rằng mật khẩu của chúng ta được an toàn và khó bị hack là một mục tiêu chính khác của bất kỳ khung bảo mật nào. Giao diện của Spring Security PasswordEncoderthực hiện chuyển đổi một chiều cho mật khẩu (chúng ta không thể giải mã mật khẩu). Spring Security cung cấp một số PasswordEncoder, Dưới đây là danh sách để bạn tham khảo:

- BCryptPasswordEncoder
- Argon2PasswordEncoder
- Pbkdf2PasswordEncoder
- SCryptPasswordEncoder

### d, Servlet Filters
Bảo mật mùa xuân sử dụng các bộ lọc servlet Java để bắt đầu kiểm tra bảo mật cho ứng dụng web của chúng ta.

## Kiến trúc Spring security

  ![image](https://github.com/thangdtph27626/spring-security/assets/109157942/a4c08bd1-d559-47b3-bacc-2f622f4728fe)
