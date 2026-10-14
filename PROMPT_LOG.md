# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

- **Họ và tên:** LÊ MẠNH HOÀN
- **MSSV:** 526000153
- **Tên đề tài Website:** Vị Miền Nam — Landing page giới thiệu đặc sản miền Nam Việt Nam
- **Công cụ AI đã sử dụng:** GitHub Copilot trong VS Code

## 1. Yêu cầu ban đầu (System/Initial Prompt)

> Tôi là chuyên gia lập trình viên về thiết kế web. Hãy làm dự án Landing Page giới thiệu về đồ ăn đặc sản của miền Nam Việt Nam. Website phải sử dụng Semantic HTML5 với tối thiểu các thành phần `header`, `nav`, `main`, `section` hoặc `article`, `footer`; sử dụng CSS Variables trong `:root` để quản lý màu sắc, font chữ và spacing; áp dụng Flexbox hoặc Grid cho responsive; tích hợp Animate.css cho các phần tử chính và AOS cho hiệu ứng xuất hiện khi cuộn. Tự viết hiệu ứng `:hover` và `:focus` cho nút bấm, thẻ bài viết. Chỉ sử dụng Semantic HTML5 và CSS cho cấu trúc, giao diện.

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)

### Lần 1: Dựng khung Semantic HTML & CSS Variable

- **Prompt đã dùng:** Đây là nhóm yêu cầu trong prompt ban đầu, không phải một prompt riêng: dựng landing page giới thiệu món ăn đặc sản miền Nam Việt Nam; dùng đúng Semantic HTML5 (`header`, `nav`, `main`, `section`/`article`, `footer`), CSS Variables và Flexbox/Grid responsive.
- **Kết quả AI tạo ra:** Xây dựng nội dung trang “Vị Miền Nam” với phần hero, câu chuyện ẩm thực, các thẻ đặc sản, trích dẫn, điểm đến và liên hệ. Các món tiêu biểu ban đầu gồm lẩu riêu hải sản, bánh xèo và cơm tấm. Phần chân trang có thông tin liên hệ và bản quyền.
- **Nhận xét & Tinh chỉnh của SV:** Sau khi AI tạo trang, rà soát yêu cầu ngữ nghĩa: trang có `header`, `nav`, `main`, nhiều `section`, các `article` cho món ăn và `footer`. Các màu sắc, font chữ, khoảng cách được quản lý bằng CSS Variables; bố cục chuyển đổi theo kích thước màn hình.

### Lần 2: Tích hợp thư viện Animate.css & AOS

- **Prompt đã dùng:** Đây cũng là nhóm yêu cầu trong prompt ban đầu, không phải một prompt riêng: tích hợp Animate.css cho tiêu đề, nội dung hero và nút kêu gọi hành động; tích hợp AOS cho các phần nội dung xuất hiện khi cuộn; viết hiệu ứng hover/focus bằng CSS.
- **Kết quả AI tạo ra:** Animate.css được dùng cho phần mở đầu của hero. AOS được gắn vào các section, hình ảnh và vùng nội dung, đồng thời được khởi tạo với thời lượng 750 ms, chỉ chạy một lần và có độ lệch cuộn. CSS bổ sung trạng thái hover/focus và hỗ trợ `prefers-reduced-motion`.
- **Thách thức gặp phải:** AOS cần được nạp và khởi tạo thì các thuộc tính `data-aos` mới tạo hiệu ứng. Tệp thư viện được tải từ CDN, vì vậy hiệu ứng phụ thuộc kết nối mạng.
- **Cách sửa prompt (Debug prompt):** Trong phiên làm việc này không có prompt debug riêng. AI nạp thư viện, gọi `AOS.init(...)` sau khi tải script và kiểm tra trên trình duyệt; kết quả xác nhận AOS đã tải. Giao diện cũng được kiểm tra ở kích thước mobile, không bị tràn ngang. Nếu tiếp tục tinh chỉnh, có thể yêu cầu cụ thể: “Kiểm tra AOS trên trình duyệt; đảm bảo stylesheet và script được nạp đúng thứ tự, khởi tạo sau khi script sẵn sàng, rồi xác nhận hiệu ứng cuộn hoạt động.”

### Lần 3: Bổ sung món ăn và điều chỉnh carousel theo màn hình

- **Prompt đã dùng:** “Hãy thêm cho tôi 3 món ăn nữa, đối với màn hình đủ rộng thì không cần sau 5s hiện món ăn khác.”
- **Kết quả AI tạo ra:** Bổ sung gỏi cuốn, hủ tiếu Mỹ Tho và bánh khọt, kèm ảnh, nguồn/giấy phép và danh sách nguyên liệu ở mặt sau thẻ. Màn hình rộng hiển thị cả sáu món trong lưới tĩnh; màn hình nhỏ tiếp tục carousel, lần lượt chuyển món theo chu kỳ 5 giây.
- **Nhận xét & Tinh chỉnh của SV:** Kiểm tra ảnh và nội dung nguyên liệu, xác nhận cả sáu ảnh tải thành công. Kiểm tra giao diện desktop hiển thị đủ sáu món mà không tự chạy, và giao diện hẹp tiếp tục chuyển món sau 5 giây.

## 3. Đánh giá cá nhân về quá trình Vibe Coding

- **AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?** AI giúp dựng nhanh cấu trúc landing page, viết nội dung mẫu, tạo hệ thống CSS responsive và kết nối các hiệu ứng thư viện. Nhờ vậy có thể dành thời gian rà soát ngữ nghĩa HTML, giao diện trên màn hình nhỏ và khả năng truy cập.
- **Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web?** Prompt nên mô tả rõ chủ đề, cấu trúc HTML bắt buộc, công nghệ được phép sử dụng và hành vi mong muốn. Với thư viện hiệu ứng, cần nói rõ cả bước nạp thư viện, cách khởi tạo và vị trí áp dụng. Sau khi AI tạo mã, cần tự kiểm tra kết quả hiển thị thực tế, responsive, trạng thái focus và các phụ thuộc bên ngoài thay vì chỉ dựa vào mã được sinh ra.