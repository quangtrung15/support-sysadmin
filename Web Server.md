# Web Server
***
## 1 Khái niệm cơ bản về Web Server
### 1.1  Định nghĩa Web Server 
- Web Server (Máy chủ web) là phần mềm và phần cứng sử dụng HTTP và các giao thức khác để phản hồi các yêu cầu của khách hàng được thực hiện qua World Wide Web.
- Nhiệm vụ chính của nó là hiển thị nội dung trang web, chẳng hạn như văn bản, hình ảnh, video và ứng dụng, cho người dùng bằng cách lưu trữ, xử lý và phân phối các trang web.
- Máy chủ web cũng được sử dụng trong lưu trữ web, tức là lưu trữ dữ liệu cho các trang web và ứng dụng dựa trên web.
- Máy chủ web động so với máy chủ web tĩnh: Máy chủ web có thể được sử dụng để phục vụ nội dung tĩnh hoặc động. 
	* Tĩnh đề cập đến nội dung được hiển thị nguyên trạng, trong khi nội dung động có thể được cập nhật và thay đổi. Máy chủ web tĩnh bao gồm máy tính và phần mềm HTTP. Nó được coi là tĩnh vì máy chủ gửi các tệp được lưu trữ đã viết sẵn nguyên trạng đến trình duyệt. Ngoài ra, mọi người dùng đều thấy cùng một nội dung vì máy chủ chỉ phân phối các tệp đã lưu trữ. Không có xử lý phía máy chủ, tương tác cơ sở dữ liệu hoặc tạo nội dung động, dành riêng cho người dùng theo thời gian thực.
	* Trình duyệt web động bao gồm máy chủ web và phần mềm khác, chẳng hạn như máy chủ ứng dụng và cơ sở dữ liệu. Nó được coi là động vì máy chủ ứng dụng có thể được sử dụng để cập nhật bất kỳ tệp được lưu trữ nào trước khi chúng được gửi đến trình duyệt. Máy chủ web có thể tạo nội dung bằng cách yêu cầu nội dung đó theo thời gian thực từ cơ sở dữ liệu cơ bản. Ngoài ra, nội dung này được phân phối dựa trên thông tin đầu vào cụ thể của người dùng hoặc các biến khác.
	* Điều này giúp có thể phân phối các tính năng tương tác trên trang web, chẳng hạn như biểu mẫu đăng nhập và giỏ hàng. Các tính năng này được tạo động và tức thời, có thể nâng cao trải nghiệm của người dùng. Tuy nhiên, tính linh hoạt tăng lên của quy trình này cũng làm cho việc thiết kế và triển khai trở nên phức tạp hơn.
### 1.2  Vai trò của Web Server trong mô hình client-server.
- Web server đóng vai trò là một máy chủ (server) chuyên biệt trong mô hình client-server, chịu trách nhiệm chính trong việc:
	* Lưu trữ các tệp tin của website: Web server là nơi lưu trữ tất cả các thành phần tạo nên một trang web, bao gồm các tệp HTML, CSS, JavaScript, hình ảnh, video và các tài liệu khác.
	* Tiếp nhận yêu cầu từ client (trình duyệt web): Khi người dùng truy cập một trang web thông qua trình duyệt (client), trình duyệt sẽ gửi một yêu cầu (request) đến web server chứa trang web đó. Yêu cầu này thường là một yêu cầu HTTP (Hypertext Transfer Protocol).
	* Xử lý yêu cầu: Web server nhận yêu cầu và xử lý nó. Quá trình xử lý có thể bao gồm việc tìm kiếm tệp tin được yêu cầu, xử lý các đoạn mã phía máy chủ (server-side scripting) nếu có, và chuẩn bị dữ liệu để gửi trả lại cho client.
	* Gửi phản hồi (response) đến client: Sau khi xử lý yêu cầu, web server gửi một phản hồi (response) trở lại trình duyệt. Phản hồi này thường bao gồm các tệp tin của trang web (ví dụ: mã HTML) và các thông tin khác để trình duyệt có thể hiển thị trang web cho người dùng. Giao thức HTTP được sử dụng cho việc giao tiếp này.
	* Đảm bảo khả năng truy cập: Web server hoạt động liên tục và được kết nối với mạng internet để đảm bảo rằng người dùng có thể truy cập vào các trang web mà nó lưu trữ bất kỳ lúc nào.
	* Quản lý kết nối đồng thời: Một web server mạnh mẽ có khả năng xử lý đồng thời nhiều yêu cầu từ nhiều client khác nhau một cách hiệu quả.
	* Cung cấp các dịch vụ khác: Ngoài việc phục vụ các tệp tĩnh, web server hiện đại còn có thể tích hợp với các application server và cơ sở dữ liệu để cung cấp các trang web và ứng dụng web động, phức tạp hơn.
### 1.3  Cách thức hoạt động (nhận request, xử lý, trả response).
- Cách thức hoạt động của web server (trong việc nhận request, xử lý và trả response) có thể được mô tả theo các bước sau:
1. Nhận Request (Receiving the Request):
	* Người dùng nhập URL: Quá trình bắt đầu khi người dùng nhập một địa chỉ web (URL - Uniform Resource Locator) vào thanh địa chỉ của trình duyệt web (client) hoặc nhấp vào một liên kết.
	* Trình duyệt phân tích URL: Trình duyệt phân tích URL để xác định giao thức (ví dụ: HTTP, HTTPS), tên miền (ví dụ: www.example.org), và đường dẫn tài nguyên cụ thể (ví dụ: /what-is-a-web-server-working-and-architecture/).
	* Trình duyệt tìm kiếm địa chỉ IP: Trình duyệt sử dụng Hệ thống Tên miền (DNS - Domain Name System) để dịch tên miền thành địa chỉ IP tương ứng của web server.
	* Trình duyệt thiết lập kết nối TCP/IP: Sau khi có địa chỉ IP, trình duyệt thiết lập một kết nối TCP/IP (Transmission Control Protocol/Internet Protocol) với web server trên cổng mặc định cho HTTP (thường là cổng 80) hoặc HTTPS (thường là cổng 443).
	* Trình duyệt gửi HTTP Request: Khi kết nối được thiết lập, trình duyệt gửi một yêu cầu HTTP (HTTP request) đến web server. Yêu cầu này bao gồm:
	* Phương thức HTTP: Xác định hành động mà client muốn thực hiện (ví dụ: GET để lấy dữ liệu, POST để gửi dữ liệu, PUT để cập nhật dữ liệu, DELETE để xóa dữ liệu).
	* Đường dẫn tài nguyên: Xác định tài nguyên cụ thể mà client yêu cầu (ví dụ: /index.html, /images/logo.png).
	* Phiên bản HTTP: Xác định phiên bản giao thức HTTP đang được sử dụng (ví dụ: HTTP/1.1, HTTP/2).
	* Tiêu đề (Headers): Cung cấp thông tin bổ sung về yêu cầu, chẳng hạn như loại trình duyệt, ngôn ngữ ưu tiên, cookie, v.v.
2. Xử lý Request (Processing the Request):
	* Web server nhận yêu cầu: Web server lắng nghe các yêu cầu đến trên các cổng được chỉ định. Khi nhận được một yêu cầu HTTP từ client, nó sẽ bắt đầu quá trình xử lý.
	* Web server phân tích yêu cầu: Web server phân tích yêu cầu HTTP để xác định tài nguyên được yêu cầu, phương thức HTTP và các tiêu đề khác.
	* Web server tìm kiếm tài nguyên: Web server tìm kiếm tài nguyên được yêu cầu trong hệ thống tệp tin của nó.
	* Xử lý phía máy chủ (nếu cần): Nếu yêu cầu liên quan đến một tài nguyên động (ví dụ: một trang PHP, Python, Node.js), web server có thể chuyển yêu cầu này đến một application server hoặc một trình thông dịch (interpreter) tương ứng để xử lý logic nghiệp vụ, truy vấn cơ sở dữ liệu, v.v. Application server sau đó sẽ tạo ra nội dung động.
	* Tạo HTTP Response: Sau khi tìm thấy tài nguyên (hoặc sau khi application server xử lý và trả về dữ liệu), web server tạo ra một phản hồi HTTP (HTTP response). Phản hồi này bao gồm:
	* Phiên bản HTTP: Phiên bản giao thức HTTP được sử dụng.
	* Mã trạng thái (Status Code): Một mã số ba chữ số cho biết kết quả của yêu cầu (ví dụ: 200 OK cho thành công, 404 Not Found cho không tìm thấy, 500 Internal Server Error cho lỗi máy chủ).
	* Thông báo trạng thái (Status Message): Một mô tả ngắn gọn về mã trạng thái (ví dụ: OK, Not Found, Internal Server Error).
	* Tiêu đề (Headers): Cung cấp thông tin bổ sung về phản hồi, chẳng hạn như loại nội dung (Content-Type), độ dài nội dung (Content-Length), thông tin về máy chủ, cookie, v.v.
	* Phần thân (Body): Chứa nội dung thực tế của tài nguyên được yêu cầu (ví dụ: mã HTML của trang web, hình ảnh, dữ liệu JSON). Đối với các yêu cầu thành công (ví dụ: GET), phần thân sẽ chứa dữ liệu được yêu cầu. Đối với một số phản hồi lỗi, phần thân có thể chứa thông báo lỗi.
3. Trả Response (Sending the Response):
	* Web server gửi HTTP Response: Web server gửi phản hồi HTTP trở lại trình duyệt (client) thông qua kết nối TCP/IP đã thiết lập.
	* Trình duyệt nhận Response: Trình duyệt nhận phản hồi HTTP từ web server.
	* Trình duyệt xử lý Response: Trình duyệt phân tích phản hồi, bao gồm mã trạng thái, tiêu đề và phần thân.
	* Trình duyệt hiển thị nội dung: Dựa trên nội dung trong phần thân (thường là mã HTML), trình duyệt sẽ hiển thị trang web cho người dùng. Nếu phản hồi bao gồm các tài nguyên khác (ví dụ: CSS, JavaScript, hình ảnh), trình duyệt sẽ gửi các yêu cầu riêng biệt cho các tài nguyên này và hiển thị trang web hoàn chỉnh.
	* Kết nối đóng (thường): Sau khi gửi và nhận hoàn tất phản hồi (đối với HTTP/1.1 trở về trước), kết nối TCP/IP thường sẽ bị đóng. HTTP/2 và các phiên bản mới hơn có thể duy trì kết nối để xử lý nhiều yêu cầu và phản hồi hiệu quả hơn.
## 2. Các loại Web Server phổ biến
### 2.1 Apache HTTP Server (đặc điểm, ưu nhược điểm).
- Apache HTTP Server là một máy chủ web mã nguồn mở và miễn phí được viết bởi Apache Software Foundation (ASF). Đây là một trong những máy chủ web được sử dụng rộng rãi nhất, phục vụ hàng triệu trang web trên nhiều nền tảng khác nhau như Linux, Windows và macOS, và là một phần không thể thiếu của ngăn xếp LAMP (Linux, Apache, MySQL, PHP), thường được sử dụng để lưu trữ và phát triển web.
- Apache sử dụng mô hình máy khách-máy chủ để xử lý các yêu cầu HTTP và HTTPS khi người dùng nhập địa chỉ trang web:
	* Người dùng nhập địa chỉ trang web vào trình duyệt web của họ.
	* Trình duyệt thực hiện yêu cầu HTTP đến máy chủ web.
	* Apache thực hiện yêu cầu và tìm nạp tài liệu được yêu cầu (HTML, CSS, hình ảnh, v.v.).
	* Apache trả về phản hồi cho trình duyệt web của người dùng.
	* Trình duyệt hiển thị trang web.
- Apache lắng nghe HTTP trên cổng 80 và HTTPS trên cổng 443.
- Các tính năng của máy chủ web Apache: Máy chủ web Apache cung cấp một số tính năng khiến nó trở thành lựa chọn tuyệt vời cho dịch vụ lưu trữ web và quản lý máy chủ.
	* Xử lý các tệp tĩnh
	* Các mô-đun động có thể tải
	* Lập chỉ mục tự động
	* .htaccess
	* Khả năng tương thích IPv6
	* Hỗ trợ hỗ trợ HTTP/2
	* Kết nối FTP
	* Nén và giải nén Gzip
	* Load Balancing 
	* Hỗ trợ các ngôn ngữ tập lệnh Perl, PHP, Lua
	* Bandwidth throttling
	* Theo dõi phiên
	* Rewrite URL
	* Định vị địa lý dựa trên địa chỉ IP
- Ưu điểm 
    * Miễn phí và mã nguồn mở: Apache là phần mềm mã nguồn mở
    * Phổ biến và ổn định: Web server này được sử dụng rộng rãi trên toàn thế giới và đã tồn tại trong nhiều năm.
    * Đa nền tảng: Apache có thể chạy trên nhiều hệ điều hành, bao gồm Linux, Windows, macOS và nhiều hệ điều hành khác.
    * Mở rộng và linh hoạt: Web server này hỗ trợ nhiều module mà bạn có thể bật hoặc tắt để tùy chỉnh chức năng của máy chủ web.
    * Bảo mật: Apache cung cấp nhiều tùy chọn bảo mật và có cộng đồng đông đảo hỗ trợ cho việc cập nhật bảo mật và vá lỗi một cách nhanh chóng.
    * Hỗ trợ cho nhiều ngôn ngữ lập trình: Web server này hỗ trợ nhiều ngôn ngữ lập trình, bao gồm PHP, Python, Ruby và nhiều ngôn ngữ khác, giúp bạn xây dựng ứng dụng web đa dạng.
    * Cộng đồng lớn: Apache có một cộng đồng người dùng và phát triển lớn. Điều này có nghĩa là bạn có thể tìm thấy nhiều tài liệu hướng dẫn, tài liệu tham khảo và hỗ trợ từ cộng đồng khi gặp vấn đề.
- Nhược điểm 
	* Tiêu tốn nhiều tài nguyên: Web server này có thể tiêu tốn nhiều tài nguyên hệ thống, đặc biệt là khi phải xử lý đồng thời nhiều yêu cầu. Điều này có thể dẫn đến tình trạng sử dụng bộ nhớ và CPU cao, đặc biệt trong các trường hợp tải đột ngột.
	* Khả năng mở rộng hạn chế: Web server này không luôn hoạt động tốt khi phải xử lý hàng ngàn yêu cầu đồng thời. Trong các trường hợp cần mở rộng quy mô, cấu hình và tinh chỉnh cần được thực hiện kỹ lưỡng.
	* Không hỗ trợ HTTP/2 mặc định: Trong phiên bản cơ bản, Web server này không hỗ trợ giao thức HTTP/2 mà thay vào đó sử dụng HTTP/1.1. Mặc dù bạn có thể cấu hình để sử dụng HTTP/2, nhưng điều này đòi hỏi thêm công việc cài đặt và cấu hình.
	* Cấu hình phức tạp: Cấu hình Apache có thể phức tạp, đặc biệt đối với người mới bắt đầu. Việc cài đặt và tinh chỉnh máy chủ Apache có thể đòi hỏi kiến thức kỹ thuật sâu và thời gian.
	* Sự cố và lỗi phát triển chậm: Một số lỗi và vấn đề bảo mật có thể phát triển và được vá chậm hơn so với các máy chủ web khác. Điều này đòi hỏi cẩn trọng khi cập nhật và duyệt các bản vá bảo mật.
	* Hiệu năng bị ảnh hưởng bởi mô-đun thứ ba: Web server này sử dụng nhiều mô-đun bên ngoài để cung cấp các tính năng bổ sung. Sự kết hợp của nhiều mô-đun này có thể ảnh hưởng đến hiệu năng và tính ổn định của máy chủ.
	* Yêu cầu kiến thức kỹ thuật: Để cấu hình và quản lý máy chủ Apache hiệu quả, bạn cần có kiến thức kỹ thuật về nền tảng hệ điều hành và mạng, cũng như về cấu hình máy chủ web.
### 2.2 Nginx (kiến trúc event-driven, hiệu suất cao).
- nginx ("engine x") là một máy chủ web HTTP, proxy đảo ngược, bộ đệm nội dung, bộ cân bằng tải, máy chủ proxy TCP/UDP và máy chủ proxy thư điện tử. 
- Được viết ban đầu bởi Igor Sysoev và phân phối theo giấy phép BSD 2 điều khoản.
- Nổi tiếng về tính linh hoạt và hiệu suất cao với mức sử dụng tài nguyên thấp, nginx là:
	* Máy chủ web phổ biến nhất trên thế giới
	* Một trong những image Docker phổ biến nhất
	* Là nền tảng cung cấp sức mạnh cho nhiều Ingress Controller cho Kubernetes.
- NGINX dẫn đầu về hiệu suất web và tất cả là nhờ cách phần mềm được thiết kế. Trong khi nhiều máy chủ web và máy chủ ứng dụng sử dụng kiến ​​trúc dựa trên luồng hoặc quy trình đơn giản, NGINX nổi bật với kiến ​​trúc điều khiển sự kiện tinh vi cho phép mở rộng quy mô lên hàng trăm nghìn kết nối đồng thời trên phần cứng hiện đại.
- Kiến trúc Nginx: 
* NGINX sử dụng một mô hình tiến trình có thể dự đoán và được điều chỉnh phù hợp với các tài nguyên phần cứng hiện có:
	* Master process - Hoạt động như bộ điều khiển trung tâm và chịu trách nhiệm khởi động, dừng và khởi chạy các Worker processes.
	* Worker processes - Các quy trình này chạy logic NGINX cốt lõi và chịu trách nhiệm xử lý kết nối, chuyển tiếp yêu cầu, cân bằng tải, v.v.
	* Cache loader - Quy trình này chịu trách nhiệm tải siêu dữ liệu được lưu trong bộ nhớ đệm vào bộ nhớ khi Nginx khởi động.
	* Cache manager - Định kỳ kiểm tra thư mục bộ đệm và giải phóng dung lượng bằng cách xóa các mục đã hết hạn.
	* Shared memory - Giao tiếp giữa các quy trình diễn ra thông qua bộ nhớ dùng chung. Nó cũng được sử dụng để lưu vào bộ đệm và quản lý trạng thái dùng chung như trạng thái cân bằng tải.
- ![image](https://github.com/user-attachments/assets/8de8850d-9e39-4a03-8cd6-dfed9e31ce69)
- NGINX nổi bật với kiến ​​trúc event-driven cho phép mở rộng tới hàng trăm nghìn kết nối đồng thời trên phần cứng hiện đại.
- Worker Process tuân theo mô hình event-driven, sử dụng cơ chế như epoll (trên Linux) để xử lý nhiều kết nối đồng thời trên một luồng (thread) duy nhất.
	* A. Khởi tạo và chờ sự kiện
		* Khởi tạo: Sau khi được Master Process tạo ra, Worker Process đọc thông tin cấu hình từ tệp cấu hình Nginx và thiết lập vòng lặp sự kiện (event loop) để theo dõi các kết nối mới, các yêu cầu I/O, hoặc các tác vụ cần xử lý.
		* Chờ sự kiện: Worker Process đăng ký các sự kiện cần theo dõi (như kết nối mới, dữ liệu đến, hoặc ghi dữ liệu xong) với hệ thống thông qua cơ chế epoll.
	* B. Xử lý kết nối
		* Nhận sự kiện từ epoll: Khi có sự kiện (như một yêu cầu mới từ client), epoll thông báo cho Worker Process và Worker Process xử lý sự kiện đó ngay lập tức.
		* Không chặn kết nối: Worker Process không chặn khi chờ dữ liệu hoặc tài nguyên. Nếu dữ liệu chưa sẵn sàng (ví dụ: chưa đọc xong body yêu cầu), Worker Process tạm ngừng và tiếp tục xử lý các kết nối khác trong hàng đợi.
		* Xử lý song song: Dù mỗi Worker Process chỉ chạy một luồng nhưng nó có thể xử lý hàng nghìn kết nối đồng thời bằng cách xen kẽ giữa các sự kiện trong vòng lặp.
	* C. Xử lý yêu cầu
		* Phân tích yêu cầu: Phân tích cú pháp HTTP request (headers, method, URL, v.v.), kiểm tra tính hợp lệ và thực hiện các bước được chỉ định trong cấu hình.
		* Thực hiện nhiệm vụ: Phục vụ nội dung tĩnh, proxy request đến backend server, hoặc xử lý SSL/TLS.
	* D. Gửi phản hồi
		* Chuẩn bị phản hồi: Tạo HTTP response với status code, headers, và body.
		* Gửi phản hồi: Ghi dữ liệu qua socket hoặc gửi từng phần nếu dữ liệu lớn (chunked response).
	* E. Kết thúc hoặc giữ kết nối
		* Sau khi xử lý xong, Worker Process sẽ đóng kết nối nếu không có yêu cầu tiếp theo hoặc giữ kết nối mở nếu HTTP keep-alive được bật.
- Đặc điểm của Nginx
	* Kiến trúc tinh vi: Asynchronous, event-driven, xử lý hiệu quả nhiều kết nối đồng thời, phản hồi nhanh.
	* Phân phối nội dung tĩnh hiệu quả: Tốc độ cao, quản lý đồng thời nhiều kết nối, trải nghiệm người dùng nhanh hơn.
	* Sử dụng tài nguyên tối ưu: Tiêu thụ tài nguyên tối thiểu, lý tưởng cho lưu lượng truy cập cao.
	* Phân phối yêu cầu thông minh: Reverse proxy, tối ưu hóa thời gian phản hồi, cân bằng tải, chống quá tải máy chủ.
	* Hiệu suất và khả năng mở rộng vượt trội: Xử lý kết nối và yêu cầu độc đáo, phục vụ nhanh nội dung tĩnh, quản lý tốt lưu lượng truy cập tăng đột biến.- Ưu điểm của Nginx
- Ưu điểm:
	* Hiệu suất cao: Tốc độ vượt trội, phân phối nhanh nội dung tĩnh, cải thiện trải nghiệm người dùng và giảm thời gian tải trang.
	* Sử dụng tài nguyên thấp: Kiến trúc bất đồng bộ, xử lý nhiều kết nối với mức tiêu thụ bộ nhớ tối thiểu, lựa chọn kinh tế cho nhiều mô hình lưu trữ.
	* Khả năng mở rộng: Thích ứng linh hoạt với lưu lượng truy cập tăng, đảm bảo hiệu suất ổn định khi nhu cầu cao. 
	* Cân bằng tải: Phân phối hiệu quả yêu cầu đến giữa các máy chủ, chống quá tải và tối ưu hóa sử dụng tài nguyên, tạo môi trường web ổn định và phản hồi nhanh.
- Nhược điểm: Mặc dù NGINX có nhiều ưu điểm nổi bật, việc cân nhắc các nhược điểm tiềm ẩn cũng rất quan trọng:
	* Cấu hình phức tạp: Một số người dùng nhận thấy cấu hình của NGINX phức tạp hơn so với các máy chủ web khác. Việc cấu hình cho các yêu cầu cụ thể có thể gây khó khăn cho những người chưa quen với thiết lập của nó.
	* Hạn chế xử lý nội dung động gốc: Mặc dù vượt trội trong việc phục vụ nội dung tĩnh, NGINX có thể yêu cầu các cấu hình bổ sung để xử lý nội dung động tối ưu. Thiết lập bổ sung này có thể được coi là một nhược điểm đối với những người dùng tìm kiếm một giải pháp đơn giản hơn.
### 2.3 Microsoft IIS (dành cho Windows Server).
- Internet Information Services, hay còn gọi là IIS, là một máy chủ web của Microsoft chạy trên hệ điều hành Windows và được sử dụng để trao đổi nội dung web tĩnh và động với người dùng internet. IIS có thể được dùng để lưu trữ, triển khai và quản lý các ứng dụng web sử dụng các công nghệ như ASP.NET và PHP.
- IIS sử dụng nhiều giao thức khác nhau để giao tiếp và trao đổi dữ liệu với các máy khách hoặc máy tính từ xa, chẳng hạn như HTTP, SMTP và FTP. Là một sản phẩm cốt lõi của Windows, IIS được tích hợp sẵn trong Windows Server và chạy trên hệ điều hành Windows.
- Cách IIS hoạt động:  Một máy chủ web IIS hoạt động như một máy chủ web linh hoạt, dạng mô-đun, xử lý các yêu cầu từ máy khách (thường là HTTP và HTTPS) và gửi lại các phản hồi thích hợp. Dưới đây là một quy trình đơn giản hóa về cách nó hoạt động:
	* Xử lý yêu cầu: Máy chủ IIS lắng nghe trên các cổng được chỉ định (80 cho HTTP và 443 cho HTTPS) và chuyển các yêu cầu đến từ máy khách đến đúng website hoặc ứng dụng.
	* Application pools (vùng ứng dụng): Mỗi yêu cầu được quản lý bởi một tiến trình worker bên trong một application pool. Các application pool này cô lập các ứng dụng web khác nhau để tăng cường bảo mật và hiệu suất.
	* Modules (mô-đun): IIS sử dụng các mô-đun cho các tác vụ cụ thể như xác thực, viết lại URL và nén. Các mô-đun này có thể được bật hoặc tắt tùy thuộc vào cấu hình máy chủ của bạn.
	* Phản hồi: Sau khi xử lý, máy chủ IIS gửi nội dung được yêu cầu (ví dụ: HTML, tệp tin hoặc thông báo lỗi) trở lại trình duyệt của máy khách.
- ![image](https://github.com/user-attachments/assets/ed022b22-0050-487c-97b2-586cfab26165)
- Các tính năng chính của IIS:
	* Hỗ trợ gốc .NET/ASP.NET: Tối ưu cho ứng dụng Microsoft.
	* Tích hợp Visual Studio: Phát triển web hiệu quả.
	* Application Pool: Cô lập ứng dụng, tăng bảo mật và ổn định.
	* Khả năng mở rộng: Xử lý lưu lượng lớn với cân bằng tải.
	* Bảo mật: Nhiều phương pháp xác thực, mã hóa SSL, lọc yêu cầu, hạn chế IP.
	* Viết lại URL: Tối ưu SEO và quản lý URL.
	* Nén: Giảm băng thông, tăng tốc tải trang.
	* Quản lý tập trung: Dễ dàng quản lý nhiều máy chủ IIS.
	* Bộ nhớ đệm động: Cải thiện tốc độ phản hồi.
	* Hỗ trợ đa dạng công nghệ: Tương thích PHP và nhiều ngôn ngữ khác.
- Ưu điểm 
	* Tích hợp sâu với Windows, mang lại hiệu suất và tương thích tốt.
	* Giao diện IIS Manager trực quan, giúp quản lý dễ dàng.
	* Hỗ trợ nhiều giao thức và tính năng bảo mật, quản lý quan trọng.
	* Kiến trúc module mở rộng, linh hoạt tùy biến theo nhu cầu.
	* Hiệu suất ổn định, đáng tin cậy cho các ứng dụng .NET.
	* Cộng đồng hỗ trợ lớn và tài liệu phong phú, dễ tìm kiếm giúp đỡ.
- Nhược điểm 
	* Tối ưu nhất cho Windows Server, có chi phí bản quyền.
	* Có thể phức tạp cho người mới làm quen với web server.
	* Là mục tiêu tấn công tiềm năng, cần cập nhật bảo mật thường xuyên.
	* Kém linh hoạt hơn một số web server mã nguồn mở trong tùy chỉnh sâu.
	* Yêu cầu tài nguyên hệ thống đáng kể khi tải lớn hoặc ứng dụng phức tạp.
### 2.4 Lighttpd, Caddy, LiteSpeed (các lựa chọn khác).
#### 2.4.1 Lighttpd
- Lighttpd là một phần mềm máy chủ web mã nguồn mở. Nó được thiết kế đặc biệt cho các môi trường có tài nguyên hạn chế vì nó tiêu thụ CPU và RAM rất ít. Nó cũng phù hợp cho cả hệ điều hành Windows và Linux (OS)
- Lighttpd là một máy chủ web an toàn, nhanh chóng, tuân thủ các tiêu chuẩn và rất linh hoạt, được tối ưu hóa cho các môi trường hiệu suất cao. Nó có mức tiêu thụ bộ nhớ rất thấp so với các máy chủ web khác và chú trọng đến việc giảm tải cho CPU. Bộ tính năng nâng cao của nó (FastCGI, CGI, xác thực, nén đầu ra, viết lại URL và nhiều hơn nữa) khiến lighttpd trở thành phần mềm máy chủ web hoàn hảo cho mọi máy chủ đang gặp vấn đề về tải trọng.
- Được phát hành lần đầu năm 2003 bởi Jan Kneschke, một nhà phát triển phần mềm người Đức. Kneschke ban đầu viết phần mềm này để chứng minh rằng một máy chủ có thể xử lý 10.000 kết nối đồng thời, hay còn được gọi là vấn đề c10k.
- Lighttpd hỗ trợ FastCGI, CGI và SCGI. Nhờ đó, bạn có thể sử dụng phần mềm máy chủ này với các ứng dụng được viết bằng bất kỳ ngôn ngữ lập trình nào, bao gồm: PHP, Python, Perl, Ruby, Lua.
- Ưu điểm 
	* Sử dụng tối thiểu CPU, RAM và các tài nguyên khác.
	* Hỗ trợ tất cả các ngôn ngữ lập trình.
	* Là mã nguồn mở và miễn phí sử dụng.
- Nhược điểm 
	* Không phổ biến bằng các tùy chọn phần mềm khác, vì vậy bạn sẽ tìm thấy ít hỗ trợ từ cộng đồng và tài liệu hơn.
	* Thiếu các tính năng nâng cao và các mô-đun tùy chỉnh so với các phần mềm máy chủ khác.
	* Lighttpd có những lợi thế về hiệu suất hạn chế đối với các trang web lớn hơn.
#### 2.4.2 Caddy 
- Caddy là một máy chủ web hiện đại, mã nguồn mở, được thiết kế để đơn giản, hiệu quả và dễ dàng di chuyển. Nó nổi tiếng với khả năng hỗ trợ HTTPS tự động, cấu hình dễ dàng thông qua Caddyfile và khả năng mở rộng thông qua các plugin. Caddy đóng vai trò là một nền tảng để phục vụ các ứng dụng web, API và các dịch vụ khác, và nó được xây dựng tập trung vào việc đơn giản hóa quản lý máy chủ web.
- Caddy về cơ bản là một hệ thống quản lý cấu hình có thể chạy nhiều ứng dụng khác nhau như một máy chủ HTTP, trình quản lý chứng chỉ TLS, các tiện ích PKI và hơn thế nữa. Nó có thể được mở rộng bằng các plugin được gọi là các mô-đun cấu hình.
- Caddy sở hữu một reverse proxy HTTP mạnh mẽ và linh hoạt, API cấu hình trực tuyến và một máy chủ tệp tĩnh mạnh mẽ, sẵn sàng cho môi trường production, đồng thời phục vụ tất cả các trang web qua HTTPS theo mặc định với chứng chỉ TLS tự động.
- Caddy nổi bật với:
	* HTTPS tự động: Tự động quản lý chứng chỉ TLS miễn phí.
	* HTTP/3: Hỗ trợ giao thức web mới nhất cho tốc độ cao.
	* Cấu hình đơn giản: Sử dụng Caddyfile dễ đọc và viết.
	* Mở rộng linh hoạt: Kiến trúc module cho phép thêm tính năng.
	* API mạnh mẽ: Cung cấp khả năng điều khiển server động.
	* Đa nền tảng: Chạy trên nhiều hệ điều hành khác nhau.
	* Nhẹ và độc lập: Một file thực thi duy nhất, không cần phụ thuộc ngoài.
	* Quản lý tài nguyên tự động: Tối ưu hóa hiệu suất server.
	* Hỗ trợ Virtual Hosts: Dễ dàng quản lý nhiều website trên một server.
	* Cân bằng tải: Phân phối lưu lượng truy cập đến nhiều backend.
	* Reverse Proxy: Chuyển tiếp yêu cầu đến các server khác.
	* Phục vụ file tĩnh hiệu quả: Tối ưu cho việc cung cấp nội dung tĩnh.
	* Hiển thị Markdown: Tự động render file Markdown thành trang web.
	* Hỗ trợ WebSockets: Cho phép ứng dụng real-time.
	* Ghi log chi tiết: Theo dõi hoạt động của server.
	* Xuất metrics: Giám sát hiệu suất server dễ dàng.
	* Hỗ trợ gRPC: Cho giao tiếp hiệu suất cao giữa các dịch vụ.
- Ưu điểm:
	* Dễ sử dụng: Cấu hình đơn giản với Caddyfile, tự động quản lý HTTPS.
	* Linh hoạt: Kiến trúc module cho phép mở rộng tính năng.
	* Hiệu suất cao: Hỗ trợ HTTP/3 và quản lý tài nguyên hiệu quả.
	* Tự động HTTPS: Tích hợp sẵn Let's Encrypt, dễ dàng có chứng chỉ TLS miễn phí.
	* Đa năng: Hỗ trợ nhiều giao thức, có thể hoạt động như reverse proxy, load balancer.
	* Nhẹ và độc lập: Một file chạy duy nhất, không cần phụ thuộc ngoài.
	* API mạnh mẽ: Cho phép điều khiển và cấu hình server động.
	* Chạy đa nền tảng: Hoạt động tốt trên Windows, macOS, Linux.
- Nhược điểm:
	* Thiếu tài liệu: Có thể gặp khó khăn khi tìm kiếm thông tin chi tiết hoặc các ví dụ nâng cao.
	* Bộ tính năng hạn chế: So với các web server lâu đời và phổ biến như Nginx hay Apache, số lượng module và tính năng tích hợp sẵn có thể ít hơn.
	* Cộng đồng nhỏ hơn: Cộng đồng người dùng và nhà phát triển có thể nhỏ hơn, dẫn đến ít tài nguyên và hỗ trợ từ cộng đồng hơn.
#### 2.4.3 LiteSpeed
- LiteSpeed Web Server (LSWS) là một máy chủ web hiệu suất cao, an toàn, dễ sử dụng và có thể được dùng để thay thế trực tiếp cho máy chủ web Apache. Nó có thể xử lý hàng ngàn kết nối đồng thời với mức tiêu thụ bộ nhớ nhỏ và dễ dàng ngăn chặn các cuộc tấn công.
- LiteSpeed Web Server nổi bật với:
	* Hiệu suất cao: Nhờ kiến trúc hướng sự kiện (event-driven), I/O bất đồng bộ và LSAPI tối ưu.
	* Cache mạnh mẽ (LSCache): Tăng tốc đáng kể cho các ứng dụng động như WordPress.
	* Bảo mật toàn diện (LSWAF): Tường lửa ứng dụng web tích hợp, chống DDoS và brute-force.
	* Hỗ trợ giao thức mới nhất: HTTP/3 và HTTP/2 cho tốc độ truyền tải nhanh hơn.
	* Dễ quản lý: Giao diện WebAdmin trực quan và cài đặt một chạm cho nhiều ứng dụng.
	* Khả năng mở rộng: Phục vụ tốt cho cả lưu lượng truy cập nhỏ và lớn.
	* Tương thích Apache: Hỗ trợ rewrite rules (.htaccess).
- Ưu điểm LiteSpeed :
	* Nhanh hơn Apache.
	* Chịu tải tốt hơn.
	* Cache tích hợp (LSCache) mạnh.
	* Bảo mật tốt hơn.
	* Tiết kiệm tài nguyên.
	* Hỗ trợ HTTP/3.
	* PHP nhanh hơn (LSAPI).
	* Dễ dùng với control panel.
- Nhược điểm LiteSpeed :
	* Tốn phí (cần license).
	* Cộng đồng nhỏ hơn.
	* Tương thích module Apache có thể hạn chế.	
### 2.5 So sánh mã nguồn mở và thương mại
| Tính năng                     | Web Server Mã Nguồn Mở (Ví dụ: Apache, Nginx, Lighttpd, Caddy)                                              | Web Server Thương Mại (Ví dụ: Microsoft IIS, LiteSpeed Enterprise)                         |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| Chi phí                   | Thường miễn phí sử dụng, có thể có chi phí cho module/hỗ trợ nâng cao                                       | Yêu cầu chi phí bản quyền cho phiên bản đầy đủ hoặc tính năng nâng cao                     |
| Cộng đồng & Hỗ trợ        | Cộng đồng lớn, nhiều diễn đàn, tài liệu, đóng góp từ người dùng; hỗ trợ không chính thức, dựa vào cộng đồng | Cộng đồng có thể nhỏ hơn; hỗ trợ thương mại chuyên nghiệp từ nhà cung cấp                  |
| Tính linh hoạt & Tùy biến | Mã nguồn mở, cho phép tùy chỉnh sâu vào lõi; nhiều module/extension từ cộng đồng                            | Ít linh hoạt hơn trong tùy chỉnh lõi; tính năng thường giới hạn trong phạm vi nhà cung cấp |
| Hỗ trợ nền tảng           | Thường đa nền tảng (Linux, Windows, macOS, BSD)                                                             | Có thể tối ưu hóa hoặc ưu tiên một số nền tảng nhất định                                   |
| Dễ sử dụng & Quản lý      | Cấu hình có thể phức tạp (file cấu hình), đòi hỏi kiến thức kỹ thuật                                        | Thường có giao diện đồ họa (GUI) trực quan, dễ quản lý hơn                                 |
| Hiệu suất                 | Hiệu suất tốt, cần tối ưu hóa cấu hình và lựa chọn module; kiến trúc event-driven cho hiệu suất cao         | Hiệu suất thường được tối ưu hóa sẵn, đặc biệt với các tính năng độc quyền                 |
| Bảo mật                   | Dựa vào cộng đồng phát hiện và vá lỗi; cần cấu hình bảo mật cẩn thận                                        | Cập nhật bảo mật thường xuyên từ nhà cung cấp; tích hợp các tính năng bảo mật              |
| Khả năng mở rộng          | Rất tốt thông qua module/plugin từ cộng đồng và khả năng tự phát triển                                      | Khả năng mở rộng phụ thuộc vào kiến trúc và module/plugin do nhà cung cấp cung cấp         |
| Tích hợp hệ sinh thái     | Tích hợp rộng rãi với nhiều phần mềm và công nghệ nhờ cộng đồng lớn                                         | Tích hợp sâu với hệ sinh thái của nhà cung cấp                                             |
| Tính ổn định & Độ tin cậy | Đã được kiểm chứng qua thời gian, rất ổn định                                                               | Thường rất ổn định và được hỗ trợ chuyên nghiệp                                            |

## 3. Giao thức và Công nghệ liên quan
### 3.1 Giao thức 
#### 3.1.1 HTTP/HTTPS (cơ chế request/response, status codes).
- HTTP (Hypertext Transfer Protocol) là một giao thức (quy tắc truyền tin) để trao đổi thông tin giữa máy chủ Web và trình duyệt Web. 
- HTTPS là HTTP có thêm mã hóa và xác thực. Sự khác biệt duy nhất giữa hai giao thức này là HTTPS sử dụng TLS (SSL) để mã hóa các yêu cầu và phản hồi HTTP thông thường, cũng như ký điện tử vào các yêu cầu và phản hồi đó. Do đó, HTTPS an toàn hơn nhiều so với HTTP.
- ![image](https://github.com/user-attachments/assets/23fb337f-a6cf-4d15-b096-c0781748d78e)
- Cơ chế request/response
	* Request 
	-  là một thông điệp được gửi bởi một máy khách (client) đến một máy chủ (server), yêu cầu một tài nguyên cụ thể. Nó bao gồm một dòng yêu cầu (request line), các tiêu đề (headers) và tùy chọn là một phần thân (body). Một HTTP client gửi một HTTP request đến server dưới dạng một thông điệp yêu cầu.
	- ![image](https://github.com/user-attachments/assets/9c1467b9-804d-4ff5-96b8-f2d4f7fb414b)
	- Các thành phần của một yêu cầu HTTP gồm:
		* Dòng yêu cầu (Request-line): <Phương thức> <URI yêu cầu> <Phiên bản HTTP>
		* Các trường tiêu đề (header) (General|Request|Entity): Theo sau là dấu CRLF .
		* Một dòng trống: (Tức là một dòng không có gì đứng trước CRLF) báo hiệu kết thúc các trường tiêu đề.
		* Phần thân thông điệp (message-body): Tùy chọn
	- Request-Line bao gồm 3 thông tin đó là:
		* Method: là phương thức mà HTTP Request này sử dụng, chỉ định hành động sẽ được thực hiện trên tài nguyên được xác định bởi URI yêu cầu đã cho. Phương thức này phân biệt chữ hoa chữ thường và luôn phải được viết bằng chữ hoa. Bảng sau liệt kê tất cả các phương thức được hỗ trợ trong HTTP/1.1:
			| Phương thức | Mô tả                                                                                                                                                                                                           |
			| ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
			| GET         | Phương thức GET được sử dụng để truy xuất thông tin từ máy chủ đã cho bằng cách sử dụng một URI đã cho. Các yêu cầu sử dụng GET chỉ nên truy xuất dữ liệu và không nên có bất kỳ tác động nào khác đến dữ liệu. |
			| HEAD        | Tương tự như GET, nhưng nó chỉ truyền dòng trạng thái và phần tiêu đề.                                                                                                                                          |
			| POST        | Một yêu cầu POST được sử dụng để gửi dữ liệu đến máy chủ, ví dụ: thông tin khách hàng, tải tệp lên, v.v. bằng cách sử dụng các biểu mẫu HTML.                                                                   |
			| PUT         | Thay thế tất cả các biểu diễn hiện tại của tài nguyên đích bằng nội dung đã tải lên.                                                                                                                            |
			| DELETE      | Xóa tất cả các biểu diễn hiện tại của tài nguyên đích được chỉ định bởi URI.                                                                                                                                    |
			| CONNECT     | Thiết lập một đường hầm đến máy chủ được xác định bởi một URI đã cho.                                                                                                                                           |
			| OPTIONS     | Mô tả các tùy chọn giao tiếp cho tài nguyên đích.                                                                                                                                                               |
			| TRACE       | Thực hiện một kiểm tra vòng lặp thông báo dọc theo đường dẫn đến tài nguyên đích.                                                                                                                               |                                                                                                                                                                                       |
		* URI(Uniform Resource Identifier): là địa chỉ định danh của tài nguyên yêu cầu sẽ được áp dụng. 
			| Method            | Description                                                                                                                                                                                                                                                  |
			| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
			| Asterisk (*) form | Được sử dụng khi HTTP request không áp dụng cho một tài nguyên cụ thể mà cho server nói chung. Chỉ dùng với các phương thức như `OPTIONS`.  <br> Ví dụ: `OPTIONS * HTTP/1.1`                                                                                 |
			| Absolute form     | Dùng khi HTTP request được gửi đến một proxy. Proxy sẽ chuyển tiếp request hoặc phản hồi từ cache.  <br> Ví dụ: `GET https://www.example.com/tailwind_css/index.htm HTTP/1.1`                                                                                |
			| Origin form       | Dạng phổ biến nhất, dùng khi client gửi request trực tiếp đến origin server.  <br> Ví dụ:  <br> `GET /tailwind_css/index.htm HTTP/1.1` <br> `Host: www.example.com` <br> Lưu ý: Đường dẫn tuyệt đối không được để trống; nếu không có thì phải dùng `/`. |
			| Authority form    | Chỉ dùng với phương thức `CONNECT`, thường trong kết nối qua proxy đến máy chủ khác.  <br> Ví dụ: `CONNECT www.example.com:443 HTTP/1.1`                                                                                                                     |

		* HTTP version: là phiên bản HTTP đang sử dụng.
	- Tiếp theo là các trường request-header, cho phép client gửi thêm các thông tin bổ sung về thông điệp HTTP request và về chính client. Một số trường thông dụng như:
		* Accept: loại nội dung có thể nhận được từ thông điệp response. Ví dụ: text/plain, text/html…
		* Accept-Encoding: các kiểu nén được chấp nhận. Ví dụ: gzip, deflate, xz, exi…
		* Connection: tùy chọn điều khiển cho kết nối hiện thời. Ví dụ: keep-alive, Upgrade…
		* Cookie: thông tin HTTP Cookie từ server.
		* User-Agent: thông tin về user agent của người dùng.
	- Ví dụ 1 HTTP Request : HTTP Request nhằm lấy trang hello.htm từ máy chủ web đang chạy trên example.com:
		```
		GET /hello.htm HTTP/1.1
		User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
		Host: www.example.com
		Accept-Language: en-us
		Accept-Encoding: gzip, deflate
		Connection: Keep-Alive
		```
			* GET: Đây là phương thức HTTP, chỉ định hành động mà máy khách muốn thực hiện (trong trường hợp này là lấy dữ liệu).
			* /hello.htm: Đây là URI yêu cầu, xác định tài nguyên cụ thể mà máy khách muốn truy cập trên máy chủ.
			* HTTP/1.1: Đây là phiên bản giao thức HTTP mà máy khách đang sử dụng.
			* User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT): Đây là một tiêu đề yêu cầu, cung cấp thông tin về trình duyệt (tác nhân người dùng) đang gửi yêu cầu.
			* Host: www.example.com: Đây là một tiêu đề yêu cầu quan trọng, chỉ định tên miền của máy chủ mà máy khách đang muốn kết nối. Điều này đặc biệt quan trọng khi một máy chủ duy nhất phục vụ nhiều trang web.
			* Accept-Language: en-us: Đây là một tiêu đề yêu cầu, cho biết ngôn ngữ mà máy khách ưu tiên (trong trường hợp này là tiếng Anh của Mỹ).
			* Accept-Encoding: gzip, deflate: Đây là một tiêu đề yêu cầu, cho biết các phương pháp nén mà máy khách có thể xử lý. Máy chủ có thể sử dụng một trong các phương pháp này để nén phản hồi, giúp giảm kích thước dữ liệu truyền đi.
			* Connection: Keep-Alive: Đây là một tiêu đề yêu cầu, gợi ý cho máy chủ duy trì kết nối TCP sau khi gửi phản hồi đầu tiên, cho phép các yêu cầu tiếp theo có thể được gửi qua cùng một kết nối, giảm độ trễ.
	* Response 
	- là phản hồi mà máy chủ đã xử lý dữ liệu được gửi từ máy khách và trả lại cho máy khách. Khi bạn gửi yêu cầu đến máy chủ, quá trình xử lý theo phương thức được thực hiện trên máy chủ và kết quả xử lý sẽ được trả về.
	- ![image](https://github.com/user-attachments/assets/07176621-6d98-4434-bb37-f87a6cb8907d)
	- Các thành phần của 1 HTTP Response: 
		* Dòng trạng thái (Status-line): `<Phiên bản HTTP> <Mã trạng thái> <Mô tả trạng thái>`
		* Không hoặc nhiều trường tiêu đề (header) (General|Response|Entity)
		* Một dòng trống: (Tức là một dòng không có gì đứng trước CRLF) báo hiệu kết thúc các trường tiêu đề.
		* Phần thân thông điệp (message-body): Tùy chọn. 
	- Status-Line: Một dòng trạng thái bao gồm phiên bản giao thức, theo sau là một mã trạng thái số và cụm từ mô tả trạng thái tương ứng. Các thành phần được phân tách bằng ký tự khoảng trắng.
		* Phiên bản HTTP: Máy chủ hỗ trợ phiên bản HTTP 1.1 sẽ trả về thông tin phiên bản sau:`HTTP-Version = HTTP/1.1`
		* Mã trạng thái (Status Code):  Mã trạng thái là một số nguyên có 3 chữ số, trong đó chữ số đầu tiên của Mã trạng thái xác định lớp phản hồi và hai chữ số cuối không có vai trò phân loại. Có 5 giá trị cho chữ số đầu tiên:
			| Mã trạng thái | Mô tả                                                                         |
			| ------------- | ----------------------------------------------------------------------------- |
			| 1xx           | Thông tin: Yêu cầu đã được nhận và quá trình đang tiếp tục.                   |
			| 2xx           | Thành công: Hành động đã được nhận, hiểu và chấp nhận thành công.             |
			| 3xx           | Chuyển hướng: Cần thực hiện hành động tiếp theo để hoàn thành yêu cầu.        |
			| 4xx           | Lỗi máy khách: Yêu cầu chứa cú pháp không chính xác hoặc không thể thực hiện. |
			| 5xx           | Lỗi máy chủ: Máy chủ không thể thực hiện một yêu cầu có vẻ hợp lệ.            |
	- Response Header Fields Các trường tiêu đề phản hồi: Các trường tiêu đề phản hồi cho phép máy chủ truyền thêm thông tin về phản hồi mà không thể đặt trong Dòng trạng thái. Các trường tiêu đề này cung cấp thông tin về máy chủ và về quyền truy cập tiếp theo vào tài nguyên được xác định bởi URI yêu cầu.
		* Accept-Ranges
		* Age
		* ETag
		* Location
		* Proxy-Authenticate
		* Retry-After
		* Server
		* Vary
		* WWW-Authenticate
	- Ví dụ 1 HTTP Respone: HTTP Respone cho yêu cầu lấy trang hello.htm từ máy chủ web đang chạy trên example.com:
		```
		HTTP/1.1 200 OK
		Date: Mon, 27 Jul 2009 12:28:53 GMT
		Server: Apache/2.2.14 (Win32)
		Last-Modified: Wed, 22 Jul 2009 19:15:56 GMT
		Content-Length: 88
		Content-Type: text/html
		Connection: Closed
		```
			* HTTP/1.1: Phiên bản giao thức HTTP mà máy chủ đang sử dụng.
			* 200 OK: Mã trạng thái HTTP cho biết yêu cầu đã thành công. 200 là mã trạng thái thành công và OK là cụm từ mô tả trạng thái tương ứng.
			* Date: Mon, 27 Jul 2009 12:28:53 GMT: Tiêu đề phản hồi Date chỉ ra ngày và giờ (theo giờ GMT) mà phản hồi được tạo ra.
			* Server: Apache/2.2.14 (Win32): Tiêu đề phản hồi Server cung cấp thông tin về phần mềm máy chủ web đang được sử dụng (trong trường hợp này là Apache phiên bản 2.2.14 trên Windows).
			* Last-Modified: Wed, 22 Jul 2009 19:15:56 GMT: Tiêu đề phản hồi Last-Modified chỉ ra ngày và giờ sửa đổi cuối cùng của tài nguyên được yêu cầu.
			* Content-Length: 88: Tiêu đề phản hồi Content-Length chỉ định kích thước (tính bằng byte) của phần thân thông điệp (trong trường hợp này là 88 byte).
			* Content-Type: text/html: Tiêu đề phản hồi Content-Type chỉ định kiểu MIME của dữ liệu trong phần thân thông điệp (trong trường hợp này là văn bản HTML).
			* Connection: Closed: Tiêu đề phản hồi Connection cho biết kết nối TCP sẽ bị đóng sau khi truyền xong phản hồi này.
- Bảng các Status Code 

* 1xx - Informational

| Mã  | Tên                 | Mô tả                                                                        |
| --- | ------------------- | ---------------------------------------------------------------------------- |
| 100 | Continue            | Máy chủ đã nhận được phần đầu yêu cầu, client nên tiếp tục gửi phần còn lại. |
| 101 | Switching Protocols | Máy chủ đồng ý chuyển giao thức như yêu cầu.                                 |
| 102 | Processing          | Máy chủ đã nhận yêu cầu nhưng chưa hoàn thành xử lý.                         |
| 103 | Early Hints         | Cung cấp thông tin trước khi phản hồi chính được gửi.                        |

---

* 2xx - Success

| Mã  | Tên                           | Mô tả                                             |
| --- | ----------------------------- | ------------------------------------------------- |
| 200 | OK                            | Yêu cầu thành công và phản hồi theo yêu cầu.      |
| 201 | Created                       | Yêu cầu thành công và tài nguyên mới đã được tạo. |
| 202 | Accepted                      | Yêu cầu đã được chấp nhận nhưng chưa được xử lý.  |
| 203 | Non-Authoritative Information | Phản hồi không đến từ nguồn gốc.                  |
| 204 | No Content                    | Thành công, không có nội dung trả về.             |
| 205 | Reset Content                 | Yêu cầu client reset view.                        |
| 206 | Partial Content               | Trả về một phần tài nguyên.                       |
| 207 | Multi-Status                  | Trạng thái đa phần (WebDAV).                      |
| 208 | Already Reported              | Đã được báo cáo trước đó.                         |
| 226 | IM Used                       | Thành công sau khi áp dụng các bản sửa đổi.       |
---

* 3xx - Redirection

| Mã  | Tên                | Mô tả                                           |
| --- | ------------------ | ----------------------------------------------- |
| 300 | Multiple Choices   | Nhiều phản hồi khả dĩ.                          |
| 301 | Moved Permanently  | Tài nguyên chuyển vĩnh viễn.                    |
| 302 | Found              | Tạm thời chuyển hướng.                          |
| 303 | See Other          | Chuyển hướng bằng GET.                          |
| 304 | Not Modified       | Không có thay đổi.                              |
| 305 | Use Proxy          | Dùng proxy (deprecated).                        |
| 306 | Switch Proxy       | Không sử dụng nữa.                              |
| 307 | Temporary Redirect | Tạm thời chuyển hướng, giữ nguyên phương thức.  |
| 308 | Permanent Redirect | Chuyển hướng vĩnh viễn, giữ nguyên phương thức. |
---

* 4xx - Client Error

| Mã  | Tên                             | Mô tả                               |
| --- | ------------------------------- | ----------------------------------- |
| 400 | Bad Request                     | Yêu cầu sai cú pháp.                |
| 401 | Unauthorized                    | Cần xác thực.                       |
| 402 | Payment Required                | Dành cho thanh toán (chưa sử dụng). |
| 403 | Forbidden                       | Không có quyền truy cập.            |
| 404 | Not Found                       | Không tìm thấy tài nguyên.          |
| 405 | Method Not Allowed              | Phương thức không được hỗ trợ.      |
| 406 | Not Acceptable                  | Không có định dạng nào phù hợp.     |
| 407 | Proxy Authentication Required   | Cần xác thực proxy.                 |
| 408 | Request Timeout                 | Hết thời gian yêu cầu.              |
| 409 | Conflict                        | Xung đột trạng thái tài nguyên.     |
| 410 | Gone                            | Tài nguyên đã bị xóa.               |
| 411 | Length Required                 | Thiếu trường Content-Length.        |
| 412 | Precondition Failed             | Điều kiện không thỏa mãn.           |
| 413 | Payload Too Large               | Yêu cầu quá lớn.                    |
| 414 | URI Too Long                    | URI quá dài.                        |
| 415 | Unsupported Media Type          | Loại phương tiện không được hỗ trợ. |
| 416 | Range Not Satisfiable           | Phạm vi không thỏa mãn.             |
| 417 | Expectation Failed              | Không đáp ứng được Expect.          |
| 418 | I'm a teapot                    | Mã đùa từ RFC 2324.                 |
| 421 | Misdirected Request             | Gửi sai máy chủ.                    |
| 422 | Unprocessable Entity            | Không xử lý được (WebDAV).          |
| 423 | Locked                          | Tài nguyên bị khóa.                 |
| 424 | Failed Dependency               | Phụ thuộc bị lỗi.                   |
| 425 | Too Early                       | Yêu cầu quá sớm.                    |
| 426 | Upgrade Required                | Cần nâng cấp giao thức.             |
| 428 | Precondition Required           | Yêu cầu cần điều kiện.              |
| 429 | Too Many Requests               | Quá nhiều yêu cầu.                  |
| 431 | Request Header Fields Too Large | Header quá lớn.                     |
| 451 | Unavailable For Legal Reasons   | Bị chặn vì lý do pháp lý.           |
---

* 5xx - Server Error

| Mã  | Tên                             | Mô tả                            |
| --- | ------------------------------- | -------------------------------- |
| 500 | Internal Server Error           | Lỗi không xác định từ máy chủ.   |
| 501 | Not Implemented                 | Chưa được hỗ trợ.                |
| 502 | Bad Gateway                     | Gateway lỗi.                     |
| 503 | Service Unavailable             | Dịch vụ tạm thời không khả dụng. |
| 504 | Gateway Timeout                 | Gateway hết thời gian.           |
| 505 | HTTP Version Not Supported      | Phiên bản HTTP không hỗ trợ.     |
| 506 | Variant Also Negotiates         | Lỗi do server cấu hình sai.      |
| 507 | Insufficient Storage            | Không đủ dung lượng lưu trữ.     |
| 508 | Loop Detected                   | Phát hiện vòng lặp (WebDAV).     |
| 510 | Not Extended                    | Cần mở rộng thêm yêu cầu.        |
| 511 | Network Authentication Required | Yêu cầu xác thực mạng.           |

#### 3.1.2 SSL/TLS (bảo mật, chứng chỉ số).
- SSL（Secure Sockets Layer）/TLS（Transport Layer Security）là kỹ thuật mã hóa truyền tin trên internet. Sử dụng SSL/TLS , bằng việc mã hóa data truyền tin giữa máy tính và server thì có thể phòng tránh bên thứ ba nghe trộm hoặc giả mạo data.
- SSL/TLS sử dụng các chứng chỉ để thiết lập một liên kết được mã hóa giữa máy chủ và máy khách. Điều này cho phép các thông tin nhạy cảm như chi tiết thẻ tín dụng được truyền một cách an toàn qua internet.
- Chứng chỉ Transport Layer Security (TLS) - thường được biết đến là SSL hoặc chứng chỉ số - là nền tảng của một internet an toàn. Chứng chỉ TLS/SSL bảo vệ các kết nối internet bằng cách mã hóa dữ liệu được gửi giữa trình duyệt của bạn, trang web bạn đang truy cập và máy chủ của trang web. Chúng đảm bảo rằng dữ liệu được truyền riêng tư, không bị sửa đổi, mất mát hoặc đánh cắp.
- Chứng chỉ chứa một khóa công khai để xác thực danh tính của trang web và cho phép truyền dữ liệu đã mã hóa thông qua mật mã bất đối xứng, hay còn gọi là mật mã khóa công khai. Khóa riêng tư tương ứng được giữ bí mật trên máy chủ.
- Cơ chế hoạt động: Chứng chỉ SSL/TLS xác thực danh tính và kích hoạt các kết nối được mã hóa thông qua quá trình SSL/TLS handshake (bắt tay SSL/TLS):
	* Máy khách yêu cầu truy cập vào một tài nguyên được bảo vệ, chẳng hạn như trang đăng nhập.
	* Máy chủ phản hồi bằng cách gửi chứng chỉ SSL của nó, bao gồm cả khóa công khai.
	* Máy khách xác minh rằng chứng chỉ hợp lệ và đáng tin cậy. Điều này đảm bảo máy chủ là xác thực.
	* Máy khách tạo ra một khóa phiên đối xứng và mã hóa nó bằng khóa công khai của máy chủ. Điều này truyền khóa phiên một cách an toàn đến máy chủ.
	* Máy chủ giải mã khóa phiên bằng khóa riêng tư của nó.
	* Cả hai bên sử dụng khóa phiên đối xứng để mã hóa và giải mã tất cả dữ liệu được truyền.
	- Quá trình bắt tay này cho phép hai bên thương lượng một kênh được mã hóa mà không cần chia sẻ thông tin nhạy cảm qua các kênh không an toàn. Phiên được mã hóa bảo vệ dữ liệu trong quá trình truyền giữa máy khách và máy chủ.
- ![image](https://github.com/user-attachments/assets/1bea9f7f-c123-45b5-9a4d-8184f529977f)
- Các loại chứng chỉ SSL/TLS :
	- Theo mức độ xác thực:
		* EV (Extended Validation): Mức xác thực cao nhất, kiểm tra nghiêm ngặt tổ chức, hiển thị thông tin công ty trên trình duyệt, tin cậy cao cho giao dịch nhạy cảm.
		* OV (Organization Validated): Mức xác thực trung bình, cần chứng minh quyền sở hữu domain và thông tin công ty, phù hợp cho doanh nghiệp xây dựng lòng tin.
		* DV (Domain Validated): Mức xác thực thấp nhất, chỉ cần xác minh quyền sở hữu domain qua email/điện thoại, chi phí thấp, phù hợp cho website thông tin.
	- Theo loại domain hỗ trợ:
		* Single Domain: Chỉ bảo vệ một domain hoặc subdomain duy nhất.
		* Wildcard: Bảo vệ một domain và tất cả các subdomain của nó.
		* Multi-Domain: Bảo vệ nhiều domain khác nhau thuộc cùng một chủ sở hữu.
		
#### 3.1.3 WebSocket, HTTP/2, QUIC (giao thức hiện đại).
- WebSocket 
	- là một giao thức truyền thông máy tính (computer communication protocol), cung cấp các kênh liên lạc dạng full-duplex (song công) qua một kết nối TCP.
	- hỗ trợ giao tiếp hai chiều giữa client và server bằng cách sử dụng một TCP socket để tạo một kết nối hiệu quả và ít tốn kém.
	- WebSocket mới trong HTML5 là một kỹ thuật Ajax ngược. Sockets cho phép các kênh giao tiếp song song hai chiều và hiện được hỗ trợ bởi nhiều trình duyệt (Firefox, Google Chrome và Safari). Các kết nối được mở thông qua các yêu cầu HTTP (HTTP request) được gọi là các ràng buộc Sockets với các tiêu đề đặc biệt. 
	- Kết nối được duy trì để bạn có thể đọc và ghi dữ liệu bằng JavaScript như thể bạn đang sử dụng các socket TCP thuần túy. Dữ liệu được gửi qua giao thức HTTP (thường được sử dụng trong các kỹ thuật Ajax) chứa rất nhiều dữ liệu không cần thiết trong tiêu đề. 
	- ![image](https://github.com/user-attachments/assets/31a25a00-994b-4142-be00-f469f9ede339)
	- WebSocket hoạt động qua ba bước chính:
		1. Thiết lập kết nối WebSocket
			* Khởi tạo yêu cầu: Máy khách (client) gửi một yêu cầu HTTP đến máy chủ, trong đó có tiêu đề Upgrade để yêu cầu chuyển đổi từ giao thức HTTP sang WebSocket.
			* Phản hồi từ máy chủ: Nếu máy chủ hỗ trợ WebSocket, nó sẽ phản hồi với một thông báo xác nhận việc nâng cấp kết nối, cho phép thiết lập một kết nối WebSocket.
		2. Truyền dữ liệu qua WebSockets
			* Giao tiếp hai chiều: Sau khi kết nối được thiết lập, cả máy khách và máy chủ có thể gửi và nhận dữ liệu bất kỳ lúc nào mà không cần thực hiện yêu cầu HTTP mới.
			* Dữ liệu dạng khung: Dữ liệu được truyền qua WebSocket được đóng gói trong các frames, có thể chứa dữ liệu văn bản hoặc nhị phân.
		3. Đóng kết nối WebSocket: Kết nối WebSocket được duy trì cho đến khi một trong hai bên quyết định đóng nó. Khi kết nối bị đóng, quá trình truyền dữ liệu kết thúc.
	- Ưu điểm
		- WebSockets cung cấp khả năng giao tiếp hai chiều mạnh mẽ, có độ trễ thấp và dễ xử lý lỗi. Không cần phải có nhiều kết nối như phương pháp Comet long-polling và cũng không có những nhược điểm như Comet streaming.
		- API cũng rất dễ sử dụng trực tiếp mà không cần bất kỳ các tầng bổ sung nào, so với Comet, thường đòi hỏi một thư viện tốt để xử lý kết nối lại, thời gian chờ timeout, các Ajax request (yêu cầu Ajax), các tin báo nhận và các dạng truyền tải tùy chọn khác nhau (Ajax long-polling và jsonp polling).
	- Nhược điểm
		- Nó là một đặc tả mới của HTML5, nên nó vẫn chưa được tất cả các trình duyệt hỗ trợ.
		- Không có phạm vi yêu cầu nào. Do WebSocket là một TCP socket chứ không phải là HTTP request, nên không dễ sử dụng các dịch vụ có phạm vi-yêu cầu, như SessionInViewFilter của Hibernate. Hibernate là một framework kinh điển cung cấp một bộ lọc xung quanh một HTTP request. Khi bắt đầu một request, nó sẽ thiết lập một contest (chứa các transaction và liên kết JDBC) được ràng buộc với luồng request. Khi request đó kết thúc, bộ lọc hủy bỏ contest này.
- HTTP/2 
	- HTTP/2 là phiên bản chính thức tiếp theo của giao thức HTTP, nhằm cải thiện tốc độ tải trang và hiệu suất khi duyệt web.
	- ![image](https://github.com/user-attachments/assets/a60b42dc-249e-4f87-8860-e38ddfbb86c6)
	- Các đặc điểm của HTTP/2
		- Header compression: HTTP/2 nén các thông tin ở phần đầu của dữ liệu và làm giảm kích thước của chúng, giúp trang web tải nhanh hơn và quá trình trao đổi thông tin giữa máy chủ web và người dùng diễn ra nhanh hơn.
		- ![image](https://github.com/user-attachments/assets/1d9156ef-48d9-4b0a-8558-f4dbf3591fa4)
		- Multiplexing : Nó giảm thời gian chờ bằng cách cho phép gửi và nhận nhiều yêu cầu cùng một lúc.
		- ![image](https://github.com/user-attachments/assets/6e0861ed-39bc-4f38-942e-8e41e42e9f26)
		- Stream prioritization: HTTP/2 có một đặc điểm giúp máy chủ phân chia tài nguyên mạng dựa trên nhu cầu của người dùng. Quá trình này cải thiện trải nghiệm người dùng bằng cách hiển thị những phần quan trọng nhất của trang web nhanh nhất có thể.
		- ![image](https://github.com/user-attachments/assets/2549c03e-283c-4722-a3ab-9b3f4dff0d8e)
		- Binary framing layer: Giao thức HTTP/2 sử dụng dữ liệu dạng số (0 và 1) thay vì các lệnh dạng chữ. Một giao thức dùng dữ liệu dạng số thường hiệu quả hơn và ít gây ra lỗi hơn. Nó giúp giảm thời gian chờ và bảo vệ tốt hơn trước các nguy cơ bảo mật so với cách dùng dữ liệu dạng chữ.
		- ![image](https://github.com/user-attachments/assets/09c444f5-47d7-42cb-9207-9e8b29aa0a55)
		- Server push: Giao thức HTTP/2 cho phép máy chủ tự động gửi các tài nguyên đến người dùng mà không cần người dùng phải yêu cầu trước. Điều này giúp tăng hiệu quả và giảm thời gian tải trang.
		- ![image](https://github.com/user-attachments/assets/7012ae5d-b730-402f-81f2-ee05b877186b)
			* Ví dụ: Ngay khi Client request index.html ngay lập tức, Server sẽ trả về index.html và cả style.css nữa, điều này có thể thực hiện do cơ chế single connection, single origin được nhắc tới ở trên. Và trình duyệt có thể render trang web ngay lập tức thay vì chờ đợi request thứ 2 cho style.css dược phản hồi.
		- Increased security: HTTP/2 được hỗ trợ thông qua các kết nối đã được mã hóa.
	- Ưu điểm: 
		* Tăng tốc độ: Truyền tải song song (multiplexing), nén header, server push giúp tải trang nhanh hơn đáng kể.
		* Bảo mật hơn: Thường đi kèm HTTPS, tăng cường mã hóa.
		* Hiệu quả hơn: Giảm nhu cầu các kỹ thuật tối ưu hóa phức tạp như image sprites, domain sharding.
	- Nhược điểm :
		* Phức tạp hơn: Triển khai và gỡ lỗi khó hơn.
		* Tốn tài nguyên hơn: Máy chủ có thể cần nhiều CPU, RAM hơn.
		* Vấn đề tương thích: Trình duyệt cũ có thể không hỗ trợ.
- QUIC 
	- QUIC (Quick UDP Internet Connections) là một giao thức truyền tải mạng được phát triển bởi Google nhằm cải thiện hiệu suất của các ứng dụng sử dụng kết nối Internet, đặc biệt là các ứng dụng web và truyền phát video. QUIC được thiết kế để thay thế giao thức TCP, cung cấp các lợi ích về tốc độ và hiệu suất mà TCP không thể đáp ứng đầy đủ trong môi trường Internet hiện đại.
	- Các đặc điểm chính của QUIC
		* Sử dụng UDP: QUIC hoạt động trên giao thức UDP (User Datagram Protocol), thay vì TCP (Transmission Control Protocol), giúp giảm độ trễ của các kết nối mạng.
		* Giảm độ trễ kết nối: Với QUIC, quá trình thiết lập kết nối diễn ra nhanh hơn, thường chỉ yêu cầu một bước trao đổi dữ liệu duy nhất, thay vì nhiều bước như TCP + TLS.
			- ![image](https://github.com/user-attachments/assets/c2063ae7-12c4-42d4-a1de-c5c5b19672d0)
		* Tích hợp bảo mật: QUIC tích hợp các tính năng của TLS 1.3 (Transport Layer Security) để mã hóa dữ liệu trong suốt quá trình truyền, đảm bảo bảo mật mà không cần thêm một bước thiết lập mã hóa riêng biệt.
		* Khả năng khôi phục nhanh chóng: Khi xảy ra mất gói dữ liệu, QUIC chỉ cần yêu cầu truyền lại các gói bị mất thay vì phải thiết lập lại toàn bộ kết nối như TCP.
		* Tối ưu hóa cho đa luồng: QUIC hỗ trợ truyền dữ liệu đồng thời trên nhiều luồng (streams) mà không gây cản trở nhau khi xảy ra lỗi, cải thiện hiệu suất cho các trang web và ứng dụng phức tạp.
	- QUIC và HTTP/3 : 
		* QUIC là một phần của HTTP/3, phiên bản giao thức HTTP mới nhất. HTTP/3 thay thế giao thức TCP của phiên bản trước đó, HTTP/2, bằng QUIC. Sự kết hợp giữa QUIC và HTTP/3 mang lại nhiều lợi ích cho việc truyền tải dữ liệu trên internet.
		* Sự thay thế của HTTP/3: HTTP/3 thay thế giao thức TCP bằng QUIC để tận dụng những ưu điểm của giao thức mới này như tăng tốc độ và tính bảo mật.
		* Ưu điểm khi sử dụng HTTP/3 với QUIC: Khi sử dụng HTTP/3 với QUIC, việc truyền tải dữ liệu trở nên nhanh chóng và hiệu quả hơn bao giờ hết. Sự kết hợp này giúp tối ưu hóa việc tải nội dung của trang web và giảm thiểu thời gian tải trang.
	- Bên cạnh đó QUIC tồn tạn những hạn chế như: 
		* Sự chấp nhận hạn chế: QUIC vẫn còn tương đối mới và không phải tất cả các hệ thống hoặc tường lửa đều hỗ trợ đầy đủ.
		* Dự phòng TCP: Một số triển khai có thể yêu cầu dự phòng về TCP nếu QUIC không được hỗ trợ, làm tăng thêm sự phức tạp.
		* Không kiểm tra gói tin: Việc mã hóa trong QUIC gây khó khăn cho quản trị viên mạng trong việc kiểm tra hoặc giám sát lưu lượng truy cập, có khả năng ảnh hưởng đến bảo mật và nỗ lực khắc phục sự cố.
		* Sử dụng CPU cao hơn: QUIC có thể yêu cầu nhiều tài nguyên CPU hơn so với TCP do cơ chế mã hóa và kiểm soát tắc nghẽn của nó.
		* Phụ thuộc vào UDP: QUIC dựa trên UDP, một giao thức không kết nối, và có thể dễ bị tấn công DDoS dựa trên UDP.
		* Khả năng tương thích hạn chế: QUIC không tương thích với tất cả các thiết bị mạng và tường lửa, có khả năng yêu cầu người dùng định cấu hình thiết bị của họ.
#### 3.1.4 CGI, FastCGI, WSGI (giao tiếp giữa server và ứng dụng).
- CGI 
	- CGI là viết tắt của Common Gateway Interface, tạm dịch là giao diện cổng chung. CGI cung cấp một phần mềm trung gian giữa các máy chủ với cơ sở dữ liệu và nguồn thông tin bên ngoài. Trong đó máy chủ HTTP và 1 CGI script sẽ chịu trách nhiệm phản hồi yêu cầu từ người dùng.
		* Máy chủ đảm nhận quản lý các kết nối, việc thực hiện truyền dữ liệu đi và các vấn đề liên quan đến yêu cầu từ người dùng.
		* CGI script chịu trách nhiệm xử lý các vấn đề của ứng dụng như truy cập vào dữ liệu và xử lý các tài liệu.
	- Các tính năng của CGI
		* CGI là một tiêu chuẩn được phát triển với định hướng rõ ràng và có rất nhiều sự hỗ trợ.
		* CGI là một công nghệ được kết nối với ngôn ngữ HTML.
		* CGI script thường được viết bằng các ngôn ngữ như C, Perl nhưng cũng có thể là một shell script đơn giản.
		* Nếu tạo một bộ nhớ đệm có tốc độ nhanh, CGI là một trong những phương pháp tối ưu nhất.
		* Cho đến thời điểm hiện tại, CGI vẫn đang rất tương thích với các trình duyệt hiện đại, dù đã phát triển từ những năm 1990.	
	- CGI là một giao thức trao đổi giữa máy chủ web và các ứng dụng cổng (gateway application) như PHP, Python,…
		- ![image](https://github.com/user-attachments/assets/2b3f8350-dc6e-44b9-b902-7e3bf16748a0)
		- Trong thực tế CGI sẽ hoạt động như sau:
			* Máy trạm gửi yêu cầu đến máy chủ web, máy chủ web nhận yêu cầu và chuyển tiếp cho ứng dụng cổng. CGI sẽ thực thi một câu lệnh tương ứng phù hợp với ứng dụng đó.
			* Các thông tin chi tiết về yêu cầu được ứng dụng truyền qua bằng các biến môi trường, trong khi đó dữ liệu bằng các phương pháp POST hoặc PUT sẽ được truyền qua các cổng nhập tiêu chuẩn. Tức là CGI xử lý dữ liệu của nó song song với dữ liệu chính.
			* Ứng dụng sẽ viết nội dung cần trả lời để máy chủ trả thông tin về cho người yêu cầu.
		- Quá trình này khá đơn giản và hiệu quả. Tuy nhiên, hình thức này dần bộc lộ một số hạn chế như:
			* Một yêu cầu sẽ tạo ra một tiến trình làm việc độc lập. Bộ nhớ và các thông tin không được lưu lại sau mỗi phiên, sẽ được tạo lại sao mỗi phiên.
			* Một tiến trình mới sẽ tiêu tốn rất nhiều tài nguyên của hệ thống. Nếu trong một thời điểm một loạt yêu cầu được sinh ra sẽ làm máy chủ quá tải ngay lập tức.
			* Trong trường hợp máy chủ một nơi, ứng dụng nằm trên một máy tính khác sẽ tạo ra nhiều khó khăn.
	- Ưu điểm
		* Code sẵn có để áp dụng vào phần mềm của bạn mà không phải code lại từ đầu.
		* CGI mạnh mẽ tương thích hầu hết với các ngôn ngữ và bất cứ nền tảng nào, miễn chúng có những đặc điểm kỹ thuật phù hợp.
		* Các tác vụ nâng cao vốn khó trong Java giờ có thể thực hiện dễ dàng hơn với CGI.
	- Nhược điểm
		* CGI rất tốn thời gian để xử lý.
		* Không lưu lại cache sau mỗi lần tải lại trang.
		* Mỗi lần tải lại sẽ tốn thêm thời gian do phải tải lại các chương trình vào bộ nhớ.
- FastCGI
	- là một giao thức nhị phân để kết nối các chương trình tương tác với một máy chủ web. Nó là một biến thể của CGI ra đời trước đó. Mục tiêu chính của FastCGI là giảm phát sinh liên quan đến việc kết nối giữa máy chủ web và các chương trình CGI, cho phép máy chủ xử lý nhiều yêu cầu trang web hơn trong một đơn vị thời gian.
	- Những ưu điểm của FastCGI bao gồm:
		* Hiệu suất: Các tiến trình FastCGI hoạt động liên tục - chúng được tái sử dụng để xử lý nhiều yêu cầu. Điều này giải quyết vấn đề hiệu suất của CGI là phải tạo tiến trình mới cho mỗi yêu cầu.
		* Đơn giản, dễ dàng chuyển đổi từ CGI: Thư viện ứng dụng FastCGI (được mô tả ở trang 9) giúp đơn giản hóa việc chuyển đổi các ứng dụng CGI hiện có. Các ứng dụng được xây dựng bằng thư viện ứng dụng cũng có thể chạy như các chương trình CGI, để tương thích ngược với các máy chủ Web cũ.
		* Độc lập ngôn ngữ: Giống như CGI, các ứng dụng FastCGI có thể được viết bằng bất kỳ ngôn ngữ nào, không chỉ các ngôn ngữ được hỗ trợ bởi API của nhà cung cấp.
		* Cô lập tiến trình: Một ứng dụng FastCGI bị lỗi không thể làm sập hoặc làm hỏng máy chủ chính hoặc các ứng dụng khác. Một ứng dụng FastCGI độc hại không thể đánh cắp bất kỳ bí mật nào (chẳng hạn như khóa phiên cho mã hóa) từ máy chủ Web.
		* Không độc quyền: FastCGI được hỗ trợ trong tất cả các sản phẩm máy chủ của Open Market, và sự hỗ trợ đang được phát triển cho các máy chủ Web khác, bao gồm các máy chủ Apache và NCSA miễn phí, cũng như các máy chủ thương mại từ Microsoft và Netscape.
		* Độc lập kiến trúc: Giao diện FastCGI không bị ràng buộc với một kiến trúc máy chủ cụ thể. Bất kỳ máy chủ Web nào cũng có thể triển khai giao diện FastCGI. Ngoài ra, FastCGI không áp đặt bất kỳ kiến trúc nào lên ứng dụng: các ứng dụng có thể là đơn luồng hoặc đa luồng, bất kể kiến trúc luồng của máy chủ Web.
		* Hỗ trợ điện toán phân tán: FastCGI cung cấp khả năng chạy các ứng dụng từ xa, điều này hữu ích cho việc phân tán tải và quản lý các trang Web bên ngoài.
	- Chức năng FastCGI cung cấp rất giống với chức năng mà CGI cung cấp. 
		- Quá trình xử lý yêu cầu CGI cơ bản diễn ra như sau:
			* Với mỗi yêu cầu, máy chủ tạo một tiến trình mới và tiến trình đó tự khởi tạo.
			* Máy chủ Web truyền thông tin yêu cầu (chẳng hạn như máy chủ từ xa, tên người dùng, tiêu đề HTTP, v.v.) cho chương trình CGI trong các biến môi trường.
			* Máy chủ Web gửi bất kỳ dữ liệu đầu vào nào của máy khách (chẳng hạn như các giá trị trường do người dùng nhập từ biểu mẫu HTML) đến đầu vào chuẩn của chương trình CGI.
			* Chương trình CGI ghi bất kỳ đầu ra nào cần trả về cho máy khách vào đầu ra chuẩn. Thông tin lỗi được ghi vào lỗi chuẩn sẽ được máy chủ Web ghi lại.
			* Khi tiến trình CGI kết thúc, yêu cầu hoàn tất.
		- FastCGI về mặt khái niệm rất giống với CGI, với hai điểm khác biệt chính:
			* Các tiến trình FastCGI hoạt động liên tục: sau khi hoàn thành một yêu cầu, chúng chờ một yêu cầu mới thay vì thoát.
			* Thay vì sử dụng các biến môi trường và pipes của hệ điều hành, FastCGI ghép nhiều thông tin môi trường, đầu vào chuẩn, đầu ra và lỗi qua một kết nối song công toàn phần duy nhất. Điều này cho phép các chương trình FastCGI chạy trên các máy từ xa, sử dụng kết nối TCP giữa máy chủ Web và ứng dụng FastCGI.
		- Quá trình xử lý yêu cầu trong một ứng dụng FastCGI đơn luồng diễn ra như sau:
			* Máy chủ Web tạo các tiến trình ứng dụng FastCGI để xử lý các yêu cầu. Các tiến trình có thể được tạo khi khởi động hoặc tạo theo yêu cầu
			* Chương trình FastCGI tự khởi tạo và chờ một kết nối mới từ máy chủ Web.
			* Khi có yêu cầu từ máy khách, máy chủ Web mở một kết nối đến tiến trình FastCGI. Máy chủ gửi thông tin biến môi trường CGI và đầu vào chuẩn qua kết nối này.
			* Tiến trình FastCGI gửi thông tin đầu ra chuẩn và lỗi trở lại máy chủ qua cùng một kết nối.
			* Khi tiến trình FastCGI đóng kết nối, yêu cầu hoàn tất. Sau đó, tiến trình FastCGI chờ một kết nối khác từ máy chủ Web.
	- Bên cạnh đó FastCGI tồn tại những nhược điểm như :
		* Tăng độ phức tạp trong cấu hình FastCGI có thể phức tạp hơn trong việc cấu hình và quản lý so với CGI, đặc biệt khi thiết lập các nhóm tiến trình và xử lý kết nối.
		* Tiềm ẩn vấn đề về bộ nhớ Mặc dù FastCGI giảm việc tiêu thụ tài nguyên so với CGI, nó vẫn có thể tiêu thụ một lượng bộ nhớ đáng kể nếu không được cấu hình đúng cách hoặc nếu yêu cầu bộ nhớ của ứng dụng cao.
		* Phức tạp trong gỡ lỗi Việc gỡ lỗi các ứng dụng FastCGI có thể khó khăn hơn so với việc gỡ lỗi các ứng dụng CGI do các tiến trình hoạt động liên tục và cần phải hiểu sự tương tác giữa máy chủ web và ứng dụng FastCGI.
- WSGI 
	- WSGI (Web Server Gateway Interface) là một tiêu chuẩn trong Python dùng để định nghĩa giao tiếp giữa máy chủ web và các ứng dụng web.
	- WSGI là một đặc tả kỹ thuật định nghĩa một giao diện tiêu chuẩn giữa các máy chủ web và các ứng dụng hoặc framework web Python (WSGI là một tiêu chuẩn Python được mô tả chi tiết trong [PEP 3333](https://peps.python.org/pep-3333/)). Nó đóng vai trò như một cầu nối, cho phép giao tiếp giữa một máy chủ web (như Nginx hoặc Apache) và các ứng dụng Python, giúp các nhà phát triển xây dựng các ứng dụng web có khả năng mở rộng và hiệu quả.
	- WSGI đóng vai trò then chốt bởi vì nó tiêu chuẩn hóa cách các ứng dụng web giao tiếp với máy chủ, cho phép các nhà phát triển chuyển đổi giữa các máy chủ web và framework khác nhau mà không cần thay đổi mã ứng dụng. Sự linh hoạt này đặc biệt quan trọng trong môi trường sản xuất, nơi các máy chủ khác nhau có thể được sử dụng để xử lý yêu cầu, cân bằng tải và triển khai ứng dụng.
	- Cách WSGI hoạt động:  Hãy hình dung bạn có một ứng dụng web được phát triển bằng Django hoặc Flask và nó được triển khai trên một máy chủ web (ví dụ: Apache, Nginx). Máy chủ web này nhận các yêu cầu từ nhiều người dùng khác nhau. Ngoài việc phục vụ các tệp tĩnh và thực hiện caching, máy chủ web còn có thể được sử dụng như một bộ cân bằng tải để xử lý nhiều ứng dụng khi cần mở rộng.Vấn đề đặt ra là: Làm thế nào máy chủ web có thể tương tác với ứng dụng Python? Để giải quyết vấn đề này, cần có một trung gian để thực hiện giao tiếp giữa máy chủ web và ứng dụng Python. Tiêu chuẩn cho việc giao tiếp này chính là WSGI (Web Server Gateway Interface).
		- Quy trình hoạt động của WSGI:
			- ![image](https://github.com/user-attachments/assets/b746a8f4-687d-4dd3-859c-73136b97f7c6)
			* Máy chủ web nhận yêu cầu: Khi một người dùng gửi yêu cầu đến ứng dụng web, máy chủ web sẽ là nơi đầu tiên tiếp nhận yêu cầu này.
			* Máy chủ web chuyển yêu cầu đến WSGI Container: Thay vì trực tiếp giao tiếp với ứng dụng Python, máy chủ web sẽ gửi yêu cầu (hoặc giao tiếp) với một WSGI container.
			* WSGI Container làm trung gian: WSGI container là một chương trình (ví dụ: Gunicorn, uWSGI) được cài đặt trên máy chủ. Nó đóng vai trò là cầu nối giữa máy chủ web và ứng dụng Python. WSGI container tuân theo tiêu chuẩn PEP 3333, đảm bảo khả năng tương thích.
			* WSGI Container gọi ứng dụng Python: Ứng dụng Python cung cấp một đối tượng "callable" (có thể gọi được), chứa các chức năng để xử lý yêu cầu. WSGI container sẽ gọi đối tượng này, truyền các thông tin cần thiết về yêu cầu (như các biến môi trường).
			* Ứng dụng Python xử lý yêu cầu: Ứng dụng Python nhận thông tin từ WSGI container, thực hiện các xử lý logic cần thiết để đáp ứng yêu cầu.
			* Ứng dụng Python trả về phản hồi cho WSGI Container: Sau khi xử lý, ứng dụng Python trả về một đối tượng chứa dữ liệu phản hồi (ví dụ: nội dung HTML, dữ liệu JSON).
			* WSGI Container chuyển phản hồi đến máy chủ web: WSGI container nhận phản hồi từ ứng dụng Python và định dạng nó theo cách mà máy chủ web có thể hiểu được. Sau đó, nó chuyển phản hồi này trở lại máy chủ web.
			* Máy chủ web gửi phản hồi cho người dùng: Cuối cùng, máy chủ web nhận được phản hồi từ WSGI container và gửi nó trở lại trình duyệt web của người dùng.
	- Ưu điểm
		* WSGI cung cấp tiêu chuẩn thống nhất để giao tiếp giữa máy chủ web và ứng dụng Python
		* Có thể dễ dàng chuyển đổi giữa các máy chủ web mà không cần thay đổi logic ứng dụng
		* Tích hợp middleware để thêm nhiều tính năng mở rộng như logging, caching, xác thực,…mà không cần thay đổi ứng dụng
		* Có tính tương thích rộng với các framework Python như Flask, Django,…
		* Không phụ thuộc vào bất cứ Framework nào
		* Mang lại hiệu suất cao khi kết hợp với các WSGI Server như Gunicorn hoặc uWSGI
		* Cộng đồng hỗ trợ rộng lớn.
	- Hạn chế
		* WSGI không hỗ trợ các yêu cầu bất đồng bộ
		* Cần cấu hình phức tạp để triển khai ứng dụng WSGI với hiệu suất cao
		* Không phù hợp với các ứng dụng yêu cầu xử lý I/O cao
		* Phụ thuộc vào middleware để mở rộng các tính năng
		* Lỗi thời trong các hệ thống hiện đại sử dụng các giao thức như HTTP/2
### 3.2 Các công nghệ liên quan 
#### 3.2.1 Các mô hình xử lý yêu cầu: 
- Prefork và Worker trong Apache 
	- Trong quá trình xử lý Multitasking thường có hai kỹ thuật chính đó là dựa vào process và thread, hay còn gọi là multiprocessing và multithreading.
		* Multiprocessing : tạo ra nhiều process và cùng xử lý một cách riêng lẽ.
		* Multithreading : tạo ra nhiều thread trong một process để xử lý, dùng chung bộ nhớ với các thread khác.
	- Multi-Processing Modules (MPMs) là module cho phép apache xử lý theo kiểu multitasking, mà mỗi tasking ở đây có thể hiểu là những requests mà apache phải xử lý. 
	- Có hai loại MPM (Multi-Processing Modules) chính mà Apache sử dụng là: 
		* Prefork MPM 
		* Worker MPM 
	- Prefork MPM 
		* Là một trong những MPM lâu đời và ổn định của Apache.
		* Hoạt động bằng cách tạo một tiến trình riêng biệt cho mỗi kết nối.
		* Khởi tạo một số lượng tiến trình ban đầu và tạo thêm khi có yêu cầu mới.
		* Ưu tiên sự ổn định vì lỗi ở một tiến trình không ảnh hưởng đến các tiến trình khác.
		* Mục đích chính là cung cấp bảo mật và ổn định bằng cách xử lý mỗi kết nối trong một môi trường cách ly.
		* Có thể tốn kém hơn về tiêu thụ tài nguyên (CPU, bộ nhớ) so với các MPM khác.
		* Vẫn là một lựa chọn hợp lệ, đặc biệt trong các hệ thống cũ hoặc khi bảo mật là ưu tiên hàng đầu.
			- ![image](https://github.com/user-attachments/assets/5e03946e-3b0e-4348-a796-84568e42ae7a)
		* Ưu điểm 
			- Bảo mật cao: Tiến trình độc lập, lỗi không lan.
			- Ổn định: Sập tiến trình không ảnh hưởng server.
			- Dễ cấu hình: Thiết lập đơn giản.
			- Tương thích rộng: Hỗ trợ nhiều OS và phần cứng cũ.
			- Dễ gỡ lỗi: Theo dõi lỗi dễ dàng do tiến trình riêng biệt.
		* Nhược điểm lớn nhất chính là việc tạo ra quá nhiều các process sẽ chiếm dụng lượng RAM lớn.
	- Worker MPM 
		* Là một module của Apache sử dụng mô hình đa tiến trình và đa luồng.
		* Có khả năng xử lý nhiều kết nối đồng thời hơn trong khi tiêu thụ ít tài nguyên hơn so với Prefork MPM. Đây là một lợi thế lớn cho các trang web và ứng dụng có lưu lượng truy cập cao.
		* Sử dụng tài nguyên hệ thống hiệu quả hơn bằng cách cho phép mỗi bộ xử lý chạy nhiều luồng.
		* Mục đích chính là cải thiện hiệu suất bằng cách tối ưu hóa tài nguyên máy chủ.
		* Mỗi luồng có thể xử lý một yêu cầu độc lập, cho phép máy chủ phục vụ nhiều người dùng đồng thời hơn.
		* Mô hình này giúp tăng hiệu quả tổng thể của máy chủ, đặc biệt là giảm mức sử dụng bộ nhớ.
		* Là một giải pháp lý tưởng cho các ứng dụng web phục vụ nội dung động và sử dụng kết nối cơ sở dữ liệu.
			- ![image](https://github.com/user-attachments/assets/a53fd0d5-cc4b-46fb-8389-40f1b47dea1d)
		* Ưu điểm 
			- Nhiều kết nối đồng thời: Xử lý nhiều người dùng hơn.
			- Ít tài nguyên: Tiết kiệm RAM.
			- Hiệu suất cao: Phản hồi nhanh hơn.
			- Tối ưu nội dung động: Phù hợp web phức tạp.
			- Khởi động/dừng nhanh: Tiết kiệm thời gian.
		* Nhược điểm 
			- Nếu một thread có vấn đề hoặc là bị crash thì các thread khác trong process cũng có thể bị crash và process sẽ bị crash theo.
			- Các thread có thể sử dụng chung vùng nhớ cho nên có thể gây ảnh hưởng lẫn nhau
	- So sánh Prefork/Worker 
		| Tiêu chí                        | MPM Prefork                                                       | MPM Worker                                                            |
		| ------------------------------- | ----------------------------------------------------------------- | --------------------------------------------------------------------- |
		| Kiểu xử lý                  | Đa tiến trình (mỗi tiến trình xử lý một kết nối)                  | Đa tiến trình và đa luồng (mỗi tiến trình có nhiều luồng xử lý)       |
		| Sử dụng tài nguyên          | Tiêu thụ bộ nhớ cao do mỗi tiến trình độc lập                     | Tiết kiệm bộ nhớ hơn nhờ chia sẻ bộ nhớ giữa các luồng                |
		| Tính ổn định                | Cao, lỗi trong một tiến trình không ảnh hưởng đến tiến trình khác | Thấp hơn, lỗi trong một luồng có thể ảnh hưởng đến tiến trình         |
		| Tương thích mô-đun          | Hỗ trợ tốt cho mô-đun không an toàn với đa luồng như `mod_php`    | Yêu cầu mô-đun phải an toàn với đa luồng                              |
		| Hiệu suất với lưu lượng cao | Kém hơn, vì phải tạo nhiều tiến trình mới cho mỗi kết nối         | Tốt hơn, có thể xử lý nhiều kết nối đồng thời với ít tài nguyên hơn   |
		| Khả năng mở rộng            | Hạn chế, do số lượng tiến trình cố định                           | Cao hơn, có thể tạo thêm luồng khi cần thiết                          |
		| Trường hợp sử dụng          | Trang web có lưu lượng thấp, yêu cầu tính ổn định cao             | Trang web có lưu lượng cao, yêu cầu hiệu suất và khả năng mở rộng tốt |

- Event-driven 
	- Kiến trúc hướng sự kiện (Event-driven architecture - EDA) là một mô hình kiến trúc phần mềm trong đó các thành phần hoặc dịch vụ của hệ thống giao tiếp với nhau chủ yếu thông qua việc sản xuất và tiêu thụ các sự kiện.
	- Các "sự kiện" (event) này có thể là các hành động người dùng, cập nhật dữ liệu, hoặc các thông báo từ các hệ thống khác. EDA giúp tạo ra các hệ thống linh hoạt, mở rộng và dễ tích hợp.
	- EDA dựa trên nguy- Kiến trúc hướng sự kiện bao gồm các nhà sản xuất sự kiện tạo ra luồng sự kiện, các đơn vị tiêu thụ sự kiện lắng nghe các sự kiện này và các kênh sự kiện chuyển sự kiện từ nhà sản xuất đến đơn vị tiêu thụ.ên lý phát hiện và phản hồi các event. Một event có thể là bất cứ điều gì xảy ra trong hệ thống, chẳng hạn như người dùng nhấp chuột, một gói tin đến từ mạng, hoặc một thay đổi trạng thái trong cơ sở dữ liệu. 
	- Các thành phần chính của EDA bao gồm:
		- Event Producers: Các thành phần phát sinh event: Đây là các đối tượng hoặc thành phần trong hệ thống phát sinh ra các event. Ví dụ, một nút bấm trong giao diện người dùng có thể phát sinh event khi người dùng nhấn vào nó.
		- Event Consumers: Các thành phần lắng nghe và xử lý event: Đây là các đối tượng hoặc thành phần lắng nghe các event và thực hiện hành động tương ứng khi event xảy ra. Ví dụ, khi một nút bấm được nhấn, listener có thể thực hiện một hàm xử lý để cập nhật giao diện người dùng.
		- Event Channels: Các kênh truyền event giữa producers và consumers.Đây là trung gian truyền tải event từ producers đến consumers. Nó có thể là một cơ chế đơn giản như một hàm callback hoặc phức tạp hơn như một hệ thống hàng đợi thông điệp.
	- Kiến trúc hướng sự kiện bao gồm các Event Producers tạo ra luồng sự kiện, các Event Consumers lắng nghe các sự kiện này và các Event Channels chuyển sự kiện từ Event Producers đến Event Consumers.
	- EDA có thể sử dụng hai mô hình chính: mô hình publish/subscribe và mô hình event stream.
		* Pub/sub: Một event được đăng ký bởi nhiều Event Consumers. Khi một event được publish, nó gửi event đến từng Event Consumers. Sau khi một event được nhận, nó không thể được publish lại và những Event Consumers mới sẽ không thấy event đó.
			- ![image](https://github.com/user-attachments/assets/ceed0783-5893-43cb-9c6b-fcfad6d7fe92)
		* Event Stream: Các event được ghi vào log. Các event được sắp xếp theo thứ tự nhất định. Clients không đăng ký vào Event Channels, thay vào đó, một client có thể đọc từ bất kỳ phần nào của channels. Client có trách nhiệm thay đổi vị trí đọc event trong channels. Điều đó có nghĩa là một client có thể tham gia bất cứ lúc nào và có thể phát lại các event.
			- ![image](https://github.com/user-attachments/assets/ff801507-e729-483e-8ee1-d05368402afc)
	- Các hình thức xử lí event: Có thể phân ra thành 3 nhóm chính như dưới đây:
		- Xử lí event rời rạc (Discrete event processing): Ví dụ như khi post một bài đăng lên mạng xã hội. Một trong số đặc trưng của việc xử lí event rời rạc đó là sự hiện diện của một event không hề liên quan đến các events khác và hoàn toàn có thể được xử lí độc lập.
		- Event stream processing: Xử lí các event theo luồng, có tính đến thứ tự của các events, khi mà event hiện tại có liên quan đến event trong quá khứ. Một ví dụ tiêu biểu đó là các events thay đổi lên business entity. Các events này sẽ được xử lí theo một thứ tự nhất định, sau đó sẽ lưu business entity data vào trong database. Consumer cũng cần tránh tình trạng đồng thời thay đổi lên cùng một record của database khiến cho dữ liệu không được nhất quán.
		- Complex event processing: Complex event processing (CEP) định danh và đưa ra các event pattern phức tạp dựa trên một chuỗi các event đơn giản. Ta lấy ví dụ về CEP cho việc theo dõi nhiệt độ và khói từ các cảm biến để phát hiện xem có xảy ra hoả hoạn hay không. Dữ liệu về nhiệt độ ở một thời điểm có thể không mang quá nhiều ý nghĩa nhưng với một "cụm nhiệt độ" cũng với tỉ lệ thay đổi nhiệt độ thì ta hoàn toàn có thể phán đoán được rằng liệu có đang xảy ra hoả hoạn hay không.
	-  Phân loại dựa trên cấu trúc liên kết (topology) giữa các component trong hệ thống với nhau, bao gồm 2 mô hình phổ biến:
		- Broker topology: Các thành phần phát ra các sự kiện cho toàn bộ hệ thống (broadcast). Các thành phần khác (Consumer) sẽ tự quyết định hành động dựa trên sự kiện đó hoặc bỏ qua. Không có sự điều phối hoặc quản lý tập trung.
			* Cấu trúc này có độ độc lập rất cao, giúp mang lại khả năng mở rộng, khả năng phản hồi và khả năng chịu lỗi của các thành phần.
			* Không có thành phần nào "sở hữu" hay nhận biết trạng thái của một giao dịch nghiệp vụ nhiều bước, và các hành động được thực hiện không đồng bộ. Do đó, các giao dịch phân tán có rủi ro vì không có cách nào tích hợp để khởi động lại hoặc phát lại.
		- Mediator topology:  Có một trình điều phối sự kiện (event mediator) trung tâm. Trình điều phối này quản lý và kiểm soát luồng sự kiện. Các thành phần chỉ phát ra "lệnh" (commands) đến các kênh được chỉ định (thường là hàng đợi tin nhắn). Trình điều phối sẽ nhận các lệnh này và quyết định xử lý hoặc chuyển tiếp chúng. Trình điều phối duy trì trạng thái, xử lý lỗi và khả năng khởi động lại.
			* Cấu trúc này mang lại khả năng kiểm soát tốt hơn, xử lý lỗi phân tán tốt hơn và tiềm năng đạt được tính nhất quán dữ liệu tốt hơn.
			* Cấu trúc này làm tăng sự phụ thuộc giữa các thành phần, và trình điều phối sự kiện có thể trở thành một nút thắt cổ chai hoặc một vấn đề về độ tin cậy.
	- Lợi ích của EDA
		- Độc lập cao: Producer và Consumer không phụ thuộc lẫn nhau.
		- Dễ mở rộng: Dễ dàng thêm Consumer mới mà không ảnh hưởng hệ thống.
		- Phản hồi nhanh: Xử lý sự kiện tức thì.
		- Linh hoạt & phân tán: Thích nghi tốt với tải thay đổi.
		- Dễ dàng scale: chúng ta có thể dễ dàng phân các events vào các substream khác nhau và xử lí chúng một cách song song cũng như thêm các consumers để có thể kịp thời xử lí số lượng lớn các events.
	- Nhược điểm 
		- Phức tạp trong xử lý luồng sự kiện: Xử lý các luồng sự kiện có thể phức tạp và đòi hỏi kỹ năng cao về quản lý trạng thái, xử lý song song và đồng bộ hóa. Việc đảm bảo tính nhất quán và đúng đắn trong các xử lý sự kiện cũng là một thách thức.
		- Khả năng mở rộng của hệ thống message broker: Việc sử dụng một hệ thống message broker để truyền tải sự kiện có thể tạo ra điểm bottleneck và làm giảm hiệu suất hệ thống nếu hệ thống message broker không được thiết kế để mở rộng tốt.
		- Đảm bảo tính nhất quán dữ liệu: Trong một hệ thống EDA, việc đảm bảo tính nhất quán của dữ liệu giữa các microservices có thể là một vấn đề khó khăn. Điều này đặc biệt đúng khi xảy ra các vấn đề về đồng bộ hóa dữ liệu giữa các bản sao hoặc khi có lỗi xảy ra trong quá trình xử lý sự kiện.
		- Độ trễ (Latency): Xử lý sự kiện trong một hệ thống EDA có thể gây ra độ trễ so với các phương pháp truyền thống, đặc biệt khi sự kiện phải được truyền qua một hệ thống message broker.
- Nginx Approach — Event-Driven
	- Không giống các máy chủ truyền thống tạo một tiến trình hoặc luồng riêng cho mỗi yêu cầu, Nginx hoạt động theo cơ chế khác. Mỗi tiến trình worker (tiến trình làm việc) của Nginx sẽ lắng nghe các sự kiện được tạo ra từ những yêu cầu mới đến.
	- Khi một worker chấp nhận yêu cầu kết nối và bắt đầu xử lý, điểm mấu chốt là: thay vì chặn (blocking) hoặc chờ đợi phản hồi trong quá trình thao tác Mạng (network) và Đĩa (disk) (còn gọi là I/O), worker đó sẽ ngay lập tức chấp nhận một yêu cầu kết nối khác từ hàng chờ, hoặc tiếp tục xử lý các yêu cầu mà quá trình I/O của chúng đã hoàn tất và đang chờ bước thực thi tiếp theo.
	- ![image](https://github.com/user-attachments/assets/5d225174-1cfd-4bcb-87fc-d9984c749073)

#### 3.2.2 Module/Plugin
- Các module mở rộng Apache: Chức năng của Server Apache hầu hết được mở rộng nhờ các module. List các [Apache Module](https://httpd.apache.org/docs/2.4/mod/). Một vài module thông dụng của Apache: 
	- mod_rewrite
		- là một module mở rộng của Server Apache HTTP, nếu có nạp và sử dụng module này nó cho phép bạn viết lại Url. Chức năng chính của nó là ánh xạ một địa chỉ URL đến một vị trí file cụ thể của Server, tuy nhiên bạn có thể làm nhiều hơn thế như chuyển hướng, chặn truy cập ... rewrite_module phân tích yêu cầu gửi đến bằng cách sử dụng biểu thức chính quy
		- hoạt động trên toàn bộ đường dẫn URL bao gồm các data được nhập trên URL. Các rewrite rule có thể được định nghĩa trong các file httpd.conf trên hệ thống, file .htaccess trên source. Các rewrite rule có thể dẫn đến truy vấn theo chuỗi, khởi chạy chương trình nội bộ, gửi request ra bên ngoài hệ thống, hoặc gọi các proxy nội bộ.
		- Module này gồm các chỉ thị để bạn sử dụng như RewriteBase, RewriteCond, RewriteRule ... để sử dụng nó trong httpd.conf hoặc trong file .htaccess
		* Nếu chọn viết trong .htaccess, thì các Rewrite có hiệu lực trên thư mục đặt file đó. Khi Apache truy cập đến bất kỳ thư mục con nào thì nó cũng tìm xem trong thư mục đó có file .htaccess không để nạp vào. Viết cách này khá linh hoạt, nhưng đôi khi làm chậm một chút, nếu có thể ở cấu hình VirtualHost tắt hẳn .htaccess bằng chỉ thị AllowOverride None để chỉ viết trong cấu hình Apache httpd.conf
		* Các quy tắc ReWrite viết trong httpd.conf ở các Directory của VirtualHost, kết quả thì cũng tương tự viết trong .htaccess, nó nhanh hơn vì các luật ReWrite Apache không phải tìm vào nạp mỗi khi truy cập, viết xong phải khởi động lại Apache để có hiệu lực
			| Chỉ thị       | Cú pháp                                      | Mô tả                                                                                                                 |
			| ------------- | -------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
			| RewriteEngine | `RewriteEngine On` hoặc `Off`                | Bật hoặc tắt chức năng rewrite. Mặc định không bật cho tất cả thư mục, phải khai báo trong từng thư mục muốn sử dụng. |
			|               |                                              | Mỗi thư mục sử dụng Rewrite cần khai báo `RewriteEngine On` ở đầu file `.htaccess`.                                   |
			| RewriteBase   | `RewriteBase URL-path`                       | Thiết lập URL cơ sở (base path) cho các luật rewrite trong thư mục hiện tại.                                          |
			| RewriteRule   | `RewriteRule Pattern Substitution [flags]`   | Định nghĩa luật thay đổi URL. `Pattern` là biểu thức chính quy, `Substitution` là URL thay thế nếu khớp.              |
			|               |                                              | Ví dụ:                                                                                                            |
			|               |                                              | `RewriteRule ^welcome\.html$ /html/index.html [L]`                                                                    |
			|               |                                              | Nếu truy cập `/welcome.html`, Apache sẽ truy cập thực tế `/html/index.html` trên hệ thống.                            |
			|               |                                              | `^welcome\.html$`: Mẫu URL cần khớp (dùng biểu thức chính quy).                                                       |
			|               |                                              | `/html/index.html`: Đường dẫn thay thế nếu khớp.                                                                      |
			|               |                                              | `[L]`: Cờ (flag) báo dừng sau khi áp dụng rule này.                                                                   |
			| RewriteCond   | `RewriteCond TestString CondPattern [flags]` | Áp điều kiện cho `RewriteRule` ngay bên dưới nó. Nếu điều kiện đúng thì `RewriteRule` mới được áp dụng.               |
			|               |                                              | Dùng để kiểm tra URL, phương thức HTTP, biến môi trường, user agent, v.v.                                             |
			|               |                                              | [flags]: Cờ thiết lập cho RewriteCond                                                                             |
			|               |                                              | - `[OR]`: Toán tử “hoặc” để kết nối nhiều điều kiện (mặc định là AND)                                                 |
			|               |                                              | - `[NC]`: Không phân biệt chữ hoa – thường                                                                            |
			|               |                                              | CondPattern: Mẫu là biểu thức chính quy để kiểm tra sự phù hợp với TestString                                     |
			|               |                                              | - `-s`: Kiểm tra TestString là file tồn tại trên đĩa                                                                  |
			|               |                                              | - `-d`: Kiểm tra là thư mục                                                                                           |
			|               |                                              | - `-l`: Kiểm tra là symbolic link                                                                                     |
			|               |                                              | TestString: Chuỗi chứa giá trị cần kiểm tra                                                                       |
			|               |                                              | - Viết dưới dạng `%{TÊN_BIẾN}` như `%{QUERY_STRING}`, `%{REMOTE_ADDR}`, `%{REQUEST_METHOD}`, ...                      |
			|               |                                              | - Biến môi trường: `%{ENV:ten_bien}`                                                                                  |
			|               |                                              | - Header HTTP: `%{HTTP:Header_Name}`                                                                                  |

		- Một số rule rewrite cơ bản
			* Chuyển hướng URL: Sử dụng khi xóa (đổi địa chỉ) một URL trên website, nhưng muốn khi người dùng truy cập vào sẽ tự chuyển sang một trang khác, Chuyển sang một domain mới
				```
				RewriteEngine On
				#Chuyển hướng 1 URL cụ thể
				RewriteEngine  on
				RewriteRule    "^/url-cu\.html$"  "url-moi.html"  [R=301]
				#Chuyển hướng thư mục news sang domain (server mới)
				RewriteRule   "^/docs/(.+)"  "http://new.example.com/docs/$1"  [R,L]
				```
			* Chuyển hướng các yêu cầu không tồn tại về trang chủ
				```
				RewriteCond %{REQUEST_FILENAME} !-f
				RewriteCond %{REQUEST_FILENAME} !-d
				RewriteRule . / [R=301]
				```	
					* RewriteCond %{REQUEST_FILENAME} !-f: Chỉ áp dụng quy tắc nếu yêu cầu không phải là một file tồn tại trên server.
					* RewriteCond %{REQUEST_FILENAME} !-d: Và tiếp tục chỉ áp dụng nếu yêu cầu không phải là một thư mục tồn tại trên server.
					* RewriteRule . / [R=301]: Chuyển hướng vĩnh viễn (301) bất kỳ yêu cầu nào thỏa mãn hai điều kiện trên về trang chủ của website.
- mod_ssl
	- là một module của Apache HTTP Server cung cấp khả năng mã hóa SSL/TLS, cho phép máy chủ Apache hỗ trợ giao thức HTTPS. Module này sử dụng thư viện OpenSSL để thực hiện mã hóa và giải mã dữ liệu, đảm bảo tính bảo mật cho thông tin truyền tải giữa máy chủ và người dùng.
	- Các chỉ thị quan trọng trong mod_ssl
		- SSLENGINE: Bật/Tắt sử dụng module
		- SSLCertificateFile: Định nghĩa đường dẫn đến chứng chỉ SSL.
		- SSLCertificateKeyFile: Định nghĩa đường dẫn đến khóa riêng.
		- SSLCertificateChainFile: Định nghĩa đường dẫn đến chứng chỉ trung gian.
		- SSLCipherSuite: Xác định bộ mã hóa được phép sử dụng.
		- SSLProtocol: Chỉ định các phiên bản giao thức SSL/TLS được hỗ trợ.
		- SSLPassPhraseDialog: Cấu hình cách Apache yêu cầu mật khẩu khi đọc khóa riêng được mã hóa.
	- Module này enable bằng lệnh `sudo a2enmod ssl`
	- Sử dụng Module này để cấu hình SSL/TLS cho apache2 với chứng chỉ được cấp từ các CA như Let's Encrypt
	- Có thể tự sinh chứng chỉ SSL tự ký bằng OpenSSL và sử dụng module này để cấu hình cho Apache (Test)
		* Sinh chứng chỉ 
		```
		sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/apache-selfsigned.key -out /etc/ssl/certs/apache-selfsigned.crt
		```
		* Chỉnh sửa file cấu hình apache 
		```
		sudo nano /etc/apache2/sites-available/default-ssl.conf
		```
		* Thêm các cấu hình SSL 
		```
		SSLEngine on 
		SSLCertificateFile /etc/ssl/certs/apache-selfsigned.crt 
		SSLCertificateKeyFile /etc/ssl/private/apache-selfsigned.key
		```
- mod_security 
	- là module bảo mật của apache2 nó hoạt động bằng cách kiểm tra các yêu cầu được gửi đến máy chủ web theo thời gian thực dựa trên một bộ quy tắc được xác định trước, ngăn chặn các cuộc tấn công ứng dụng web điển hình như XSS và SQL Injection.
	- ban đầu là một mô-đun của Apache và sau đó phát triển thành một tường lửa ứng dụng web hoàn chỉnh.
	- Module này có thể được cài bằng lệnh `sudo apt install libapache2-mod-security2`
	- Enable Module này trong file cấu hình của apache `SecRuleEngine On` 
-  Các module mở rộng Nginx: NGINX được xây dựng từ nhiều mô-đun nhỏ, mỗi mô-đun đảm nhiệm một chức năng riêng. Điều này giúp NGINX nhỏ gọn, nhanh và dễ tùy chỉnh. Một vài module trong nginx: 
	- ngx_http_core_module
		- ngx_http_core_module trong Nginx là mô-đun nền tảng để xử lý HTTP. Nó cung cấp chức năng cốt lõi để xử lý các yêu cầu, bao gồm cấu hình cài đặt máy chủ, định nghĩa các trang lỗi và quản lý dữ liệu yêu cầu và phản hồi. Mô-đun này là cơ bản để Nginx hoạt động như một máy chủ HTTP.
		- Chức năng chính
			* Quản lý Virtual Hosts: Cấu hình nhiều `server` block với các chỉ thị như `listen` và `server_name`.
			* Điều hướng yêu cầu: Xử lý các URI qua `location` và hỗ trợ khớp chính xác, wildcard, và regex.
			* Phục vụ nội dung tĩnh: Dùng `root` và `alias` để chỉ định thư mục chứa tệp tĩnh.
			* Quản lý lỗi và bảo mật: Tùy chỉnh trang lỗi với `error_page`, kiểm soát truy cập và xác thực với `auth_basic`.
			* Cấu hình hiệu suất: Tối ưu hóa hiệu suất với các chỉ thị như `keepalive_timeout`, `sendfile`, và `tcp_nopush`.
			* MIME types và bộ đệm: Xác định loại MIME với `types`, tối ưu bộ đệm với `open_file_cache`.
		- Một vài chỉ thị cấu hình của module 
			* `server { ... }` : Thiết lập cấu hình cho một máy chủ ảo. 
				- Ví dụ 
					```
					server {
					listen      80;
					server_name example.org www.example.org;
					}
					```
			* `listen address:port;`: Đặt địa chỉ và cổng cho IP, hoặc đường dẫn cho một socket UNIX-domain mà máy chủ sẽ chấp nhận các yêu cầu trên đó. Có thể chỉ định cả địa chỉ và cổng, hoặc chỉ địa chỉ hoặc chỉ cổng. Một địa chỉ cũng có thể là một hostname, ví dụ:
				- Ví dụ 
					```
					listen 127.0.0.1:8000;
					listen 127.0.0.1;
					listen 8000;
					listen *:8000;
					listen localhost:8000;
					```
			* `client_max_body_size`: Đặt kích thước tối đa cho phần thân yêu cầu từ client được phép. Nếu kích thước trong một yêu cầu vượt quá giá trị đã cấu hình, lỗi 413 (Request Entity Too Large) sẽ được trả về cho client. 
				- Ví dụ
					```
					client_max_body_size 1m;
					```	
			* `error_page`: Xác định URI (đường dẫn) sẽ hiển thị cho các lỗi được chỉ định. Giá trị URI có thể chứa các biến.
				- Ví dụ 
					```
					error_page 404             /404.html;
					error_page 500 502 503 504 /50x.html;
					error_page 404 =301 http://example.com/notfound.html;
					```
	- ngx_http_access_module
		- là module cho phép giới hạn quyền truy cập đối với các địa chỉ client nhất định. Quyền truy cập cũng có thể được giới hạn theo mật khẩu, kết quả của một subrequest, hoặc theo JWT. Việc giới hạn quyền truy cập đồng thời theo địa chỉ và mật khẩu được kiểm soát bởi chỉ thị satisfy.
		- Module gồm 2 directives cơ bản là `allow`, `deny` để thực hiện cấu hình.
		- Ví dụ: Cấ hình quyền truy cập chỉ được phép cho các mạng IPv4 10.1.1.0/16 và 192.168.1.0/24 (loại trừ địa chỉ 192.168.1.1), và cho mạng IPv6 2001:0db8::/32
			```
			location / {
			deny 192.168.1.1;
			allow 192.168.1.0/24;
			allow 10.1.1.0/16;
			allow 2001:0db8::/32;
			deny all;
			}
			```
	- ngx_http_rewrite_module 
		- Cung cấp các công cụ để thay đổi URL, định tuyến lại yêu cầu (redirect), và điều kiện xử lý dựa trên các biểu thức chính quy (regex).
		- Gồm các chỉ thị break, if, return, rewrite, rewrite_log và set được xử lý theo thứ tự:
			- Các chỉ thị của mô-đun này được chỉ định ở cấp độ máy chủ (server level) được thực thi tuần tự;
			- Lặp đi lặp lại:
				- Một vị trí (location) được tìm kiếm dựa trên URI của yêu cầu;
				- Các chỉ thị của mô-đun này được chỉ định bên trong vị trí tìm thấy sẽ được thực thi tuần tự;
				- Vòng lặp được lặp lại nếu URI của yêu cầu đã được viết lại, nhưng không quá 10 lần.
		- Ví dụ: Sử dụng rewrite để thay đổi đường dẫn và phần mở rộng của tệp, sau đó trả về lỗi 403 cho các yêu cầu không phù hợp
			```
			server {
				...
				rewrite ^(/download/.*)/media/(.*)\..*$ $1/mp3/$2.mp3 last;
				rewrite ^(/download/.*)/audio/(.*)\..*$ $1/mp3/$2.ra last;
				return 403;
				...
			}
			```
	- ngx_http_ssl_module 	
		- Cung cấp sự hỗ trợ cần thiết cho HTTPS. Module này yêu cầu thư viện OpenSSL 
		- Gồm nhiều chỉ thị khác nhau nổi bật cần chú ý:  ssl_certificate, ssl_certificate_key, ssl_protocols phục vụ cấu hình SSL/TLS cơ bản 
		- Ví dụ: Cấu hình Nginx để phục vụ nội dung qua HTTPS, bật mã hóa SSL.
			```
			ssl_protocols TLSv1 TLSv1.1 TLSv1.2 TLSv1.3;
			ssl_ciphers AES128-SHA:AES256-SHA:RC4-SHA:DES-CBC3-SHA:RC4-MD5;
			ssl_certificate /usr/local/nginx/conf/cert.pem;
			ssl_certificate_key /usr/local/nginx/conf/cert.key;
			```
	- ngx_http_proxy_module
		- Cho phép chuyển tiếp các yêu cầu đến một máy chủ khác.
		- Gồm nhiều chỉ thị khác nhau 
			* proxy_pass: Chỉ định URL backend để chuyển tiếp yêu cầu. `proxy_pass http://backend_server;`
			* proxy_set_header: Thiết lập lại các header HTTP khi chuyển tiếp yêu cầu. `proxy_set_header Host $host;`
			* proxy_redirect: Điều chỉnh URL trong header Location và Refresh. `proxy_redirect http://backend/ http://$host/;`
			* proxy_http_version: Xác định phiên bản HTTP khi giao tiếp với backend. `proxy_http_version 1.1;`
			* proxy_cache: Kích hoạt bộ nhớ cache cho các phản hồi từ backend. `proxy_cache my_cache;`
		- Ví dụ cầu hình : Chuyển tiếp các yêu cầu từ client đến một máy chủ backend đang chạy trên localhost:8000. Thiết lập lại các header:
			* Host: Chứa tên miền gốc của yêu cầu.
			* X-Real-IP: Chứa địa chỉ IP thật của client gửi yêu cầu.
			```
			location / {
				proxy_pass http://localhost:8000;
				proxy_set_header Host $host;
				proxy_set_header X-Real-IP $remote_addr;
			}
			```
	- Chi tiết về các module của Nginx tại [Nginx Modules Reference](https://www.f5.com/pdf/reference-guide/nginx-modules-reference.pdf)
## 4. Cấu hình và Triển khai Web Server
### 4.1  Cấu hình virtual host (host nhiều website trên một server).
- Virtual Hosts (còn được gọi là Virtual Hosting) là một kỹ thuật trong việc quản lý các trang web trên một máy chủ web duy nhất. Điều này cho phép bạn chạy nhiều trang web khác nhau trên cùng một máy chủ vật lý, mỗi trang web với tên miền riêng, nhưng chúng chia sẻ cùng một địa chỉ IP.
- Phân biệt các loại Virtual Hosts:
	- Name-Based Virtual Host: Đây là phương pháp phổ biến nhất, cho phép nhiều website sử dụng chung một địa chỉ IP. Máy chủ web sẽ dựa vào thông tin trong HTTP Header từ yêu cầu của client để xác định chính xác website cần truy cập. 
	- IP-Based Virtual Host: Đây là phương pháp cơ bản và dễ hiểu nhất trong ba phương pháp quản lý hosting. Mỗi website được gán một địa chỉ IP riêng, giúp máy chủ dễ dàng ánh xạ đúng website tương ứng khi nhận được yêu cầu từ người dùng.
	- Port-Based Virtual Host: Đây là một giải pháp linh hoạt hơn IP-Based, cho phép nhiều website cùng sử dụng một địa chỉ IP hoặc tên miền nhưng được phân biệt thông qua các số Port khác nhau. Mỗi cổng (Port) đại diện cho một website cụ thể. 
- Cách hoạt động cơ bản: Khi một trình duyệt yêu cầu một trang web (ví dụ: www.trangwebcuaban.com), nó sẽ:
	- Phân giải tên miền www.trangwebcuaban.com thành một địa chỉ IP.
	- Gửi yêu cầu HTTP đến địa chỉ IP đó, đồng thời bao gồm tiêu đề Host: www.trangwebcuaban.com.
	- Máy chủ web (Apache, Nginx, v.v.) nhận yêu cầu.
	- Máy chủ kiểm tra tiêu đề Host để xác định trang web nào đang được yêu cầu.
	- Dựa trên cấu hình Virtual Host đã được định nghĩa, máy chủ sẽ phục vụ nội dung từ thư mục gốc (document root) tương ứng với tên miền đó.
- Ưu điểm 
	* Tiết kiệm chi phí: Chia sẻ tài nguyên máy chủ giúp giảm chi phí so với máy chủ riêng.
	* Phù hợp cho cá nhân/SMEs: Lý tưởng cho doanh nghiệp nhỏ hoặc cá nhân không cần đầu tư lớn.
	* Giảm tải traffic: Nếu cấu hình tốt, giúp phân bổ lưu lượng hợp lý, tránh nghẽn tài nguyên.
	* Tận dụng tài nguyên: Tối ưu hiệu quả sử dụng máy chủ, tránh lãng phí.
	* Dễ quản lý: Hỗ trợ các công cụ như cPanel, DirectAdmin để quản lý website thuận tiện.
	* Linh hoạt: Lưu trữ nhiều website, mỗi site có thể dùng tên miền riêng.
	* Khả năng mở rộng: Dễ dàng thêm/xóa website mà không cần thay đổi phần cứng.
	* Quản lý độc lập: Mỗi website có thể có cấu hình riêng, không ảnh hưởng lẫn nhau.
- Nhược điểm 
	* Hiệu năng hạn chế: Tài nguyên chia sẻ nên dễ bị giảm hiệu suất khi một website dùng quá nhiều tài nguyên.
	* Ảnh hưởng lẫn nhau: Nếu một site bị tấn công (như DDoS), các site khác trên cùng server cũng có thể bị ảnh hưởng.
	* Bảo mật thấp hơn: Nhiều website chung môi trường → nguy cơ lây lan khi một site bị xâm nhập.
	* Không phù hợp với ứng dụng nặng: Các hệ thống cần nhiều RAM, CPU hoặc cấu hình đặc biệt thường không hoạt động hiệu quả trên Virtual Hosts.
	* Giới hạn quyền kiểm soát: Không có quyền root, hạn chế khả năng tinh chỉnh hệ thống sâu.
	* Quản lý phức tạp khi mở rộng: Càng nhiều website, việc cập nhật và kiểm tra cấu hình càng rủi ro, dễ sai sót.
	* Ràng buộc tài nguyên: Không tối ưu cho các website có nhu cầu cao về tài nguyên hoặc yêu cầu môi trường độc lập.
- Cấu hình virtual host trên các WebServer phổ biến: Apache2, Nginx, IIS 
- Apache2 : 
	- Apache hỗ trợ VirtualHost. Các virtual host được quản lý bằng file cấu hình tại `/etc/apache2/sites-available/` mỗi file tương ứng với 1 VirtualHost
	- Apache Virtual Host mặc định sẽ là 000-default.conf và default-ssl.conf tương ứng cho http/https. Cấu hình VirtualHost mới cần dựa vào 2 file này. 
	- Ví dụ: Thực hiện tạo 2 VirtualHost cho 2 domain: domain1.com và domain2.com 
		- Copy file cấu hình mẫu 
		```
		cd /etc/apache2/sites-available/
		cp 000-default.conf domain1.conf
		cp 000-default.conf domain2.conf
		```
		- Thực hiện mở file sửa cấu hình 
		```
		nano /etc/apache2/sites-available/domain1.conf
		nano /etc/apache2/sites-available/domain2.conf
		```
		- Cần chú ý tới các thuộc tính cần chỉnh sửa:
			- ServerName: Tại thuộc tính này bạn chỉ cần sửa lại tên thành Domain mà bạn mong muốn, như ví dụ chúng ta đang thực hiện ở trên là domain1.com
			- ServerAdmin: Ở thuộc tính này bạn nên lựa chọn địa chỉ Email chính của mình để có thể quản lý cho Domain mới tạo này.
			- DocumentRoot: Đây là địa chỉ lưu trữ thư mục trang Web của domain ví dụ  /var/www/domain1.com/public_html.
		- Sau khi đã chỉnh sửa thực hiện enable các site đã cấu hình
		```
		sudo a2ensite domain1.conf
		sudo a2ensite domain2.conf
		```
		- Restart Apache2 để áp dụng cấu hình 
		```
		sudo systemctl restart apache2
		```
- Nginx 
- Nginx hỗ trợ VirtualHost. Các VirtualHost được quản lý bởi các file Block có đường dẫn `/etc/nginx/sites-available/` mỗi file tương ứng với 1 VirtualHost
- Mặc định có 1 block file là defautl. Để cấu hình các block mới cần dựa vào file này
- Ví dụ: Tạo 2 file Block cho 2 domain domain1.com và domain2.com 
	- Copy file cấu hình mẫu 
	```
	sudo cp /etc/nginx/sites-available/default /etc/nginx/sites-available/domain1.com
	sudo cp /etc/nginx/sites-available/default /etc/nginx/sites-available/doamin2.com
	```
### 4.2   Thiết lập reverse proxy, load balancing (ví dụ: Nginx làm proxy cho Apache).
reverse proxy
load balancing
### 4.3   Cấu hình caching (giảm tải server).
### 4.4   Tối ưu tốc độ (nén dữ liệu, CDN, HTTP/2).
### 4.5   Tuning thông số: Max connections, keep-alive, worker processes.

5. Bảo mật Web Server
•  Phòng chống DDoS, brute force.
•  Cấu hình firewall (iptables, Cloudflare).
•  Hardening server (tắt dịch vụ không cần thiết, cập nhật bảo mật).
•  Xử lý các lỗ hổng (SQL injection, XSS, CSRF).
6. Hiệu suất và Monitoring
•  Công cụ đo lường hiệu suất (Apache Benchmark, JMeter).
•  Giám sát log (access log, error log).
•  Công cụ phân tích (Prometheus, Grafana, ELK Stack).
________________________________________
7. So sánh Web Server vs Application Server
•  Khi nào dùng web server (phục vụ file tĩnh)?
•  Khi nào cần application server (xử lý logic như Node.js, Tomcat)?
________________________________________
8. Xu hướng hiện đại
•  Serverless (AWS Lambda, Cloud Functions).
•  Container hóa (Docker + Web Server).
•  Edge Computing (xử lý gần người dùng hơn).
9. Thực hành/Tutorials
•  Cài đặt Apache/Nginx trên Linux/Windows.
•  Host một website đơn giản (HTML, PHP).
•  Triển khai HTTPS với Let’s Encrypt.
•  ________________________________________
10. Các vấn đề thường gặp
•  Lỗi 403, 404, 500 và cách khắc phục.
•  Tối ưu database kết hợp web server.
•  Xử lý tải cao (scaling theo chiều ngang/dọc).
11. Công cụ hỗ trợ
•  Công cụ quản lý web server: 
o  cPanel, DA, Plesk
o  Một số panel free
•  Công cụ kiểm tra hiệu suất: 
o  ApacheBench (ab), JMeter, Siege.
•  Công cụ bảo mật: 
o  Nmap, OpenVAS để quét lỗ hổng.
o  ModSecurity cho tường lửa ứng dụng web.
