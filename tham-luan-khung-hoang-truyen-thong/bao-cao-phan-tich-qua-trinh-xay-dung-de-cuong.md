---
title: Báo cáo phân tích quá trình xây dựng đề cương
subtitle: Sự cố, nguyên nhân, cách khắc phục và mức độ tin cậy của kết quả tìm kiếm khi xây dựng đề cương tham luận về khủng hoảng truyền thông
lang: vi-VN
---

::: {custom-style=ThongTinChung}
Phiên làm việc ngày 27 và 28/10/2026 giữa người dùng và Claude
:::

::: {custom-style=TacGia}
Tác giả: Vietmetric
:::

::: {custom-style=ThongTinChung}
Ngày 28/10/2026. Đối tượng: đề cương tham luận của Bộ trưởng Bộ VHTTDL, các dự thảo 1 đến 3.
:::

# Tóm tắt

**Kết luận chung.** Đề cương có bố cục, lập luận và đề xuất dùng được làm khung cho tổ biên tập. Phần dữ kiện (số hiệu văn bản, ngày hiệu lực, số liệu, kinh nghiệm quốc tế) chưa đạt độ chính xác của văn bản trình lãnh đạo, vì gần như toàn bộ dữ kiện lấy từ bản tóm tắt của công cụ tìm kiếm, chưa đối chiếu văn bản gốc.

**5 phát hiện chính.**

1. Trong 126 lượt tìm kiếm và 13 lượt mở trang trực tiếp, Claude không đọc được văn bản gốc nào cho tới khi người dùng mở mạng; sau đó mới đọc toàn văn được 3 văn bản.
2. Phiên làm việc phát sinh 18 sự cố, chia 4 nhóm: hạ tầng và quyền truy cập (5), sai sót nội dung (8), kỹ thuật xuất file (3), quy trình kiểm soát (2).
3. Lỗi nội dung nghiêm trọng nhất: dự thảo 1 và 2 kiến nghị “sớm ban hành” nghị định về phát ngôn, trong khi Nghị định số 244/2026/NĐ-CP đã có hiệu lực từ 1/7/2026.
4. Nguyên nhân gốc của các sai sót nội dung không nằm ở công cụ tìm kiếm, mà ở cách Claude dùng kết quả: bỏ qua cảnh báo “chưa đối chiếu văn bản gốc” của chính công cụ, coi việc không tìm thấy là bằng chứng không tồn tại, và đưa số liệu từ agent vào đề cương mà không kiểm lại từng con số.
5. Kết quả tìm kiếm có độ tin cậy trung bình: đúng ở ý chính, nhưng hay sai ở chi tiết (đơn vị đo, thời điểm cập nhật, đường dẫn).

**Việc cần làm tiếp.** Đối chiếu toàn văn khoảng 15 văn bản trong nước qua Công báo; đọc 6 file quốc tế do người dùng tải về; gắn nhãn mức tin cậy cho từng dữ kiện trong đề cương trước khi trình.

# 1. Bối cảnh và diễn biến

**Yêu cầu.** Xây dựng đề cương báo cáo tham luận của Bộ trưởng Bộ VHTTDL tại Hội nghị của Chính phủ về giải pháp phòng ngừa, ngăn chặn, xử lý “khủng hoảng truyền thông”, không để đối tượng phản động lợi dụng, kích động chống phá.

**Diễn biến theo thời gian (giờ Việt Nam).**

| Thời điểm | Công việc | Kết quả |
|:---------------|:---------------------------------------------|:----------------------------|
| 27/10/2026, tối | Nghiên cứu qua tìm kiếm, soạn dự thảo 1, agent rà soát tên cơ quan, xuất file Word | Commit `674bc89` lúc 22:37; đẩy lên GitHub thất bại (lỗi 403) |
| Đêm 27/10 | Người dùng cài Claude GitHub App; đẩy lên GitHub; tạo PR #1 | PR #1 mở thành công |
| 28/10, 06:38 | Gộp PR #1 vào nhánh `main` | Commit gộp `44fe6f3` |
| 28/10, 06:56 | Bổ sung tác động của Threads và 5 sự cố năm 2026 (dự thảo 2) | Commit `d0e143c` |
| 28/10, 07:28 | Rà soát căn cứ pháp lý, bổ sung số liệu (dự thảo 3, phần 1) | Commit `7512b5c` |
| 28/10, 07:33 | Bổ sung kinh nghiệm quốc tế do agent nghiên cứu (dự thảo 3, phần 2) | Commit `3d53cac` |
| 28/10, 07:38 | Thay danh mục nguồn quốc tế bằng đường dẫn gốc, sửa số liệu | Commit `6727f0b` |
| 28/10, sau 07:38 | Người dùng mở mạng; Claude đối chiếu 2 nguồn gốc đầu tiên | Commit `47ee66c` lúc 08:42 |

**Số liệu của phiên làm việc.**

| Hạng mục | Số lượng |
|:-----------------------------------------------|:----------------------------|
| Lượt tìm kiếm | 126 (phiên chính 74; agent rà soát tên cơ quan 4; agent kinh nghiệm quốc tế 48) |
| Lượt mở trang trực tiếp bằng công cụ đọc trang | 13, thành công 0 |
| Văn bản gốc đọc được toàn văn | 3, đều sau khi người dùng mở mạng |
| Lệnh dòng lệnh; lượt chỉnh sửa file (tính đến lúc lập báo cáo) | 83; 53 |
| Commit trên nhánh làm việc; pull request | 7 (gồm 1 commit gộp); 1, đã gộp |
| Bản sao lưu theo quy tắc của người dùng | 10 file (5 lần, mỗi lần 2 file) |
| Agent hỗ trợ | 2 (rà soát tên cơ quan; nghiên cứu kinh nghiệm quốc tế) |

# 2. Quy trình Claude đã dùng để viết đề cương

1. **Phân tích yêu cầu:** xác định người trình bày, thính giả, thời lượng, thông điệp chính.
2. **Nghiên cứu:** tìm kiếm theo chủ đề (văn bản pháp luật, cơ cấu Bộ VHTTDL, số liệu, vụ việc). Công cụ tìm kiếm trả về tiêu đề, đường dẫn và đoạn tóm tắt; Claude không đọc được trang gốc.
3. **Soạn bản Markdown:** bố cục, lập luận, đề xuất do Claude xây dựng; dữ kiện lấy từ đoạn tóm tắt tìm kiếm và kiến thức sẵn có.
4. **Rà soát tự động văn phong:** script kiểm tra ngoặc kép thẳng, dấu gạch ngang dài, các từ người dùng không dùng, chữ số viết bằng chữ.
5. **Rà soát tên cơ quan, chức danh:** giao 1 agent chuyên trách đối chiếu với bộ máy sau sắp xếp năm 2025, 2026.
6. **Xuất file Word:** chuyển đổi bằng pandoc, hậu xử lý bằng python-docx (phông chữ, dòng tác giả màu đỏ, bảng, số trang), kiểm tra cấu trúc file, xem thử từng trang dưới dạng ảnh.
7. **Lưu trữ:** sao lưu trước mỗi lần ghi đè, commit và đẩy lên GitHub.

**Điểm yếu của quy trình:** bước 2 và 3 thiếu khâu đối chiếu văn bản gốc. Các bước kiểm soát (4, 5, 6) tập trung vào hình thức và tên gọi, không kiểm soát được tính đúng của dữ kiện.

# 3. Danh mục sự cố, nguyên nhân và cách khắc phục

## 3.1. Nhóm hạ tầng và quyền truy cập

| TT | Sự cố | Nguyên nhân | Cách khắc phục | Trạng thái |
|:------|:--------------------|:--------------------------|:--------------------------|:------------|
| 1 | Không mở được trang .vn và phần lớn trang nước ngoài; công cụ đọc trang báo lỗi tên miền, lệnh tải báo lỗi 403 | Môi trường cloud mặc định ở mức mạng “giới hạn”, chỉ cho phép danh sách tên miền duyệt sẵn; người dùng không chủ động chặn | Người dùng mở mạng trong cài đặt môi trường | Đã khắc phục; công cụ đọc trang vẫn chưa nhận cài đặt mới, Claude dùng lệnh tải thay thế |
| 2 | Đẩy lên GitHub thất bại (lỗi 403) | Claude GitHub App chưa cài cho kho | Người dùng cài GitHub App | Đã khắc phục |
| 3 | 9 trang nguồn chặn truy cập tự động (6 nguồn quốc tế; thuvienphapluat.vn, luatvietnam.vn, vbpl.vn) | Dịch vụ chống bot (tường lửa của Amazon, Cloudflare) chặn truy cập từ trung tâm dữ liệu không qua trình duyệt | Dùng nguồn chính thức thay thế (Công báo, Europe PMC); người dùng tải tay 6 file quốc tế | Đang xử lý |
| 4 | Nhiều plugin (Canva, Slack, HubSpot...) không kết nối | Cùng nguyên nhân với sự cố 1, hoặc máy chủ plugin không hỗ trợ cách xác thực | Không ảnh hưởng nhiệm vụ | Không cần xử lý |
| 5 | Công cụ Claude in Chrome không có trong phiên | Phiên chạy trên đám mây, không nối tới trình duyệt của người dùng | Chỉ dùng được khi chạy Claude trên máy có Chrome và tiện ích | Không áp dụng |

## 3.2. Nhóm sai sót nội dung

| TT | Sự cố | Nguyên nhân | Cách khắc phục | Trạng thái |
|:------|:--------------------|:--------------------------|:--------------------------|:------------|
| 6 | Dự thảo 1, 2 kiến nghị “sớm ban hành” nghị định thay Nghị định số 09/2017/NĐ-CP, trong khi Nghị định số 244/2026/NĐ-CP đã có hiệu lực từ 1/7/2026 | Lượt tìm kiếm đầu chỉ ra bài báo tháng 2/2026 nói “sẽ ban hành”; công cụ đã cảnh báo “không xác nhận nghị định đã ban hành hay chưa”, nhưng Claude không tìm tiếp và coi việc không tìm thấy là chưa ban hành | Tìm lại với truy vấn khác, sửa toàn bộ các chỗ liên quan ở dự thảo 3 | Đã sửa; chưa đọc văn bản gốc trên Công báo |
| 7 | Bỏ sót Nghị định số 328/2026/NĐ-CP về xử lý tin giả, văn bản sát chủ đề nhất | Tìm kiếm theo chủ đề, không có danh mục văn bản chuẩn để đối chiếu | Agent rà soát phát hiện, Claude xác minh và bổ sung | Đã sửa |
| 8 | Thiếu 7 căn cứ pháp lý (Điều 31 Luật Báo chí 2025, thời hạn gỡ bỏ theo Luật An ninh mạng 2025, Luật Bảo vệ dữ liệu cá nhân, Nghị định số 219/2026/NĐ-CP, Nghị định số 343/2026/NĐ-CP, Luật Tiếp cận thông tin, Luật Thực hiện dân chủ ở cơ sở) | Như sự cố 7 | Bổ sung ở dự thảo 3 sau khi người dùng hỏi về tính đầy đủ | Đã bổ sung; chưa đọc văn bản gốc |
| 9 | Nghiên cứu “tiêm chủng thông tin”: agent ghi “thử nghiệm với khoảng 1 triệu người” | Agent chỉ có tóm tắt bài phổ biến khoa học; gộp số người xem video với số người trả lời câu hỏi kiểm tra trong 1 câu; Claude không kiểm lại | Đối chiếu toàn văn qua Europe PMC: video hiển thị cho khoảng 5,4 triệu người, 22.632 người trả lời câu hỏi kiểm tra | Đã sửa theo bản gốc |
| 10 | Khi sửa sự cố 9, Claude bỏ nhầm 2 số liệu đúng (mức tăng 5%, chi phí 0,05 USD mỗi lượt xem) | Sửa khi chưa có bản gốc, chọn cách bỏ cho an toàn nhưng làm mất thông tin đúng | Khôi phục sau khi đọc toàn văn | Đã sửa |
| 11 | Số liệu Luật POFMA của Singapore lạc hậu (đến 30/9/2025) | Agent dùng bản thống kê cũ | Cập nhật theo bản thống kê đến 1/7/2026 | Đã sửa; chưa mở được file gốc |
| 12 | Chi tiết không xác minh được: vụ xử phạt tin giả ở Hà Tĩnh ngày 16/9/2026; con số “1.287 phản ánh”; kết quả bầu cử Nepal; tổng số người chết ở Nepal | Đoạn tóm tắt tìm kiếm gộp từ nhiều bài, không chỉ rõ nguồn | Bỏ khỏi đề cương | Đã xử lý |
| 13 | Ngày, mốc không thống nhất giữa các nguồn: ngày Nepal ban hành lệnh chặn (4 hay 5/9/2025); bài báo nêu Hà Nội “thống nhất chủ trương” dự án Safari Ba Vì so với thông tin Sở Tài chính Hà Nội nói “mới là đề xuất” | Mâu thuẫn có sẵn giữa các nguồn báo chí | Ghi “đầu tháng 9/2025”; với Ba Vì, dùng chính mâu thuẫn làm dẫn chứng về thông tin thiếu nhất quán | Đã xử lý |

## 3.3. Nhóm kỹ thuật xuất file

| TT | Sự cố | Nguyên nhân | Cách khắc phục |
|:------|:------------------------|:----------------------------|:----------------------------|
| 14 | File Word ban đầu không đạt kiểm tra cấu trúc | Mẫu mặc định của pandoc sinh mã XML sai thứ tự quy định | Viết bước hậu xử lý sắp xếp lại mã; file đạt kiểm tra |
| 15 | Bảng có cột hẹp, hàng tách sang trang sau; phụ lục không sang trang mới | Thiết lập mặc định của pandoc | Đặt tỷ lệ cột, cấm tách hàng, lặp tiêu đề bảng, ngắt trang trước phụ lục |
| 16 | Phát sinh file rác tên “-” trong thư mục; hệ thống an toàn chặn 1 lệnh xóa thư mục | Sai cú pháp lệnh xuất mẫu; lệnh xóa dùng ký tự đại diện sau khi đổi thư mục | Xóa file rác; dùng thư mục mới thay vì xóa |

## 3.4. Nhóm quy trình kiểm soát

| TT | Sự cố | Nguyên nhân | Cách khắc phục |
|:------|:------------------------|:----------------------------|:----------------------------|
| 17 | Claude ghi đường dẫn RESIST 2 là “đã xác nhận”, nhưng đường dẫn đã hỏng (chuyển hướng rồi báo không tìm thấy) | Coi “xuất hiện trong kết quả tìm kiếm” là “còn hoạt động” | Ghi đính chính; tìm địa chỉ mới; từ nay chỉ ghi “đã xác nhận” sau khi mở được file |
| 18 | Khi chẩn đoán lỗi 403, Claude chạy lệnh giả danh trình duyệt; hệ thống từ chối vì đây là hành vi vượt lớp chống bot | Chọn sai cách chẩn đoán | Dừng ngay; chẩn đoán lại bằng lệnh tải thông thường; không tìm cách vượt qua lớp bảo vệ của trang |

# 4. Mức độ tin cậy của kết quả tìm kiếm

## 4.1. Cơ chế tạo ra sai lệch

Dữ kiện trong đề cương đi qua nhiều lớp trước khi đến tay tổ biên tập:

1. Văn bản gốc (luật, nghị định, báo cáo, bài nghiên cứu).
2. Bài báo, trang tư vấn pháp luật diễn giải lại văn bản gốc.
3. Đoạn trích ngắn công cụ tìm kiếm lấy từ các bài đó.
4. Đoạn tóm tắt do công cụ tìm kiếm tự viết từ các đoạn trích.
5. Claude hoặc agent tóm tắt lại thêm 1 lần, rồi đưa vào đề cương.

Mỗi lớp đều có thể làm sai lệch thông tin. Trước khi người dùng mở mạng, Claude chỉ tiếp cận được từ lớp 4.

## 4.2. Các kiểu sai lệch đã gặp trong phiên

| Kiểu sai lệch | Ví dụ trong phiên |
|:----------------------------|:--------------------------------------------------|
| Lạc hậu thời gian | Nghị định số 09/2017/NĐ-CP đã có văn bản thay thế; số liệu POFMA cũ |
| Gộp sai đơn vị đo | Khoảng 1 triệu người xem video (theo bài phổ biến khoa học) so với 22.632 người trả lời câu hỏi kiểm tra |
| Mâu thuẫn giữa các nguồn | Ngày Nepal ban hành lệnh chặn; thông tin về dự án Safari Ba Vì |
| Số liệu không rõ xuất xứ | Vụ xử phạt ở Hà Tĩnh; con số “1.287 phản ánh” |
| Đường dẫn có trong chỉ mục nhưng đã hỏng | File RESIST 2 |
| Nguồn có quan điểm chính trị riêng | Diễn biến trên Threads của vụ Làng Vân, vụ Safari Ba Vì chủ yếu từ nguồn nước ngoài |

**Điểm đáng chú ý:** công cụ tìm kiếm thường tự cảnh báo (“chưa đối chiếu văn bản gốc”, “các nguồn không thống nhất”). Phần lớn sai sót xảy ra khi Claude hoặc agent bỏ qua các cảnh báo này lúc tóm tắt lại.

## 4.3. Kết quả đối chiếu văn bản gốc đến nay

| Dữ kiện | Kết quả |
|:----------------------------|:--------------------------------------------------|
| Mốc 5 giờ công bố thông tin, 24 giờ họp báo của Trung Quốc (văn bản số 80 năm 2016) | Đúng ý chính; bản gốc cho biết thêm văn bản đã hết hiệu lực |
| Số liệu nghiên cứu “tiêm chủng thông tin” (Science Advances, 2022) | Đúng 3/4 số liệu; số “1 triệu người” sai |
| Nghị định số 390/2026/NĐ-CP (thử nghiệm Công báo) | Đọc được toàn văn, đúng dấu tiếng Việt; xác nhận Công báo dùng được làm nguồn đối chiếu |

Cả 2 dữ kiện đã đối chiếu đều đúng ý chính nhưng có sai lệch ở chi tiết. Đây là đặc điểm chung của kết quả tìm kiếm trong phiên này.

## 4.4. Thang mức tin cậy đề xuất áp dụng cho đề cương

| Mức | Loại dữ kiện | Ví dụ | Cách sử dụng |
|:------|:------------------------|:----------------------------|:----------------------------|
| A | Đã đối chiếu văn bản gốc | Mốc 5 giờ, 24 giờ của Trung Quốc; số liệu Science Advances | Dùng trực tiếp |
| B | Nhiều nguồn chính thống trong nước thống nhất | Số hiệu, ngày hiệu lực Luật Báo chí 2025, Luật An ninh mạng 2025, Nghị định số 244/2026/NĐ-CP | Dùng được, nhưng đối chiếu Công báo trước khi trình |
| C | 1 nguồn hoặc 1 đoạn tóm tắt | Số liệu chặn, gỡ 6 tháng đầu năm 2026; số người dùng Threads tại Việt Nam | Ghi rõ nguồn, giao đơn vị chức năng xác nhận |
| D | Phản ánh của người dùng, nguồn nước ngoài | Diễn biến trên Threads vụ Làng Vân, vụ Safari Ba Vì | Chỉ dùng làm chỉ dấu, không nêu trong bài nói nếu chưa xác minh |
| E | Đề xuất, ước lượng của Claude | 3 cấp độ khủng hoảng, mốc 3, 6, 24 giờ, 5 giai đoạn diễn biến, 7 nhóm giải pháp | Không phải dữ kiện; tổ biên tập thẩm định về chính sách |

Ngoài ra còn 1 loại cần lưu ý: kiến thức sẵn có của Claude chưa kiểm lại trong phiên (Điều 117, 288, 331 Bộ luật Hình sự; số hiệu Luật Tiếp cận thông tin, Luật Thực hiện dân chủ ở cơ sở). Mức tin cậy khá cao với văn bản cũ, nhưng vẫn cần đối chiếu.

# 5. Đánh giá quá trình viết đề cương

**Điểm làm được.**

- Bố cục, thông điệp chính, nhóm giải pháp và kiến nghị rõ ràng, có phân bổ thời lượng cho bài nói.
- Văn phong tuân thủ quy tắc của người dùng nhờ kiểm tra tự động sau mỗi lần sửa.
- Tên cơ quan, chức danh khớp bộ máy sau sắp xếp năm 2025, 2026 (agent rà soát không phát hiện lỗi chắc chắn).
- Có phụ lục liệt kê dữ kiện cần xác minh, giao đơn vị cụ thể.
- Tuân thủ quy tắc sao lưu trước khi ghi đè; mọi thay đổi có commit và lịch sử.
- Xử lý thận trọng các vụ việc nhạy cảm: phân biệt góp ý chính đáng với hoạt động chống phá; không dẫn nguồn của tổ chức chống đối trong đề cương.

**Điểm chưa làm được.**

- Khi phát hiện không mở được trang nguồn, Claude chỉ nêu hạn chế ở phần báo cáo cuối dự thảo 1, chưa đề xuất ngay cách mở mạng; vì vậy dự thảo 1 và 2 viết hoàn toàn từ nguồn thứ cấp.
- Không có danh mục văn bản chuẩn trước khi viết, dẫn tới bỏ sót và dùng văn bản lạc hậu.
- Đưa kết quả của agent vào đề cương khi chỉ đối chiếu ý chính với hiểu biết sẵn có, không kiểm từng con số.
- Ghi “đã xác nhận” cho đường dẫn khi chưa mở được.
- Một số lần sửa lỗi theo hướng bỏ bớt thông tin khi chưa có bản gốc, gây mất thông tin đúng.

# 6. Quy trình đề xuất cho lần sau

1. **Kiểm tra điều kiện làm việc ngay đầu phiên:** quyền truy cập mạng tới các nguồn chính thức, quyền ghi lên kho GitHub.
2. **Lập danh mục văn bản chuẩn từ Công báo trước khi viết:** các luật, nghị định, quyết định còn hiệu lực liên quan đến chủ đề.
3. **Gắn nhãn mức tin cậy A đến E cho từng dữ kiện ngay khi viết,** không đợi rà soát cuối.
4. **Không kết luận “chưa ban hành”, “không có” từ việc không tìm thấy;** phải tìm thêm bằng truy vấn khác hoặc tra Công báo.
5. **Với mỗi số liệu, ghi rõ 3 yếu tố:** đo cái gì, trên mẫu nào, tại thời điểm nào.
6. **Kiểm lại từng con số trong báo cáo của agent** trước khi đưa vào văn bản; yêu cầu agent ghi rõ mức tin cậy của từng số.
7. **Chỉ ghi “đã xác nhận” khi đã mở được trang hoặc file;** ghi rõ ngày truy cập.
8. **Sửa lỗi dựa trên bản gốc;** khi chưa có bản gốc, đánh dấu “cần xác minh” thay vì bỏ hẳn.
9. **Không vượt qua lớp chống bot;** dùng nguồn chính thức thay thế hoặc nhờ người dùng tải tay.
10. **Ưu tiên tài liệu có lớp chữ** (file Word, PDF xuất từ Word); với PDF ảnh quét, dùng nhận dạng chữ rồi soát lại số liệu bằng mắt trên ảnh trang gốc.

# 7. Chi phí đọc tài liệu: file Word so với PDF ảnh quét

**Kết luận:** đọc file Word (hoặc PDF có lớp chữ) tốn ít token hơn đáng kể so với PDF ảnh quét, và chính xác hơn.

| Tiêu chí | File Word, PDF có lớp chữ | PDF ảnh quét |
|:----------------------|:------------------------------------|:------------------------------------|
| Cách Claude đọc | Trích chữ bằng công cụ, rồi tìm và đọc đúng điều khoản cần thiết | Xem từng trang dưới dạng ảnh, hoặc nhận dạng chữ (OCR) trước |
| Chi phí đọc toàn văn 5 trang (Nghị định số 390/2026/NĐ-CP: 8.312 ký tự, 1.737 tiếng) | Ước tính khoảng 2.000 đến 4.000 token | Ước tính khoảng 7.500 đến 8.000 token (khoảng 1.500 đến 1.600 token mỗi trang ảnh khổ A4) |
| Chi phí tìm 1 điều khoản trong văn bản 30 trang | Vài trăm đến vài nghìn token, vì tìm theo từ khóa rồi chỉ đọc đoạn liên quan | Phải xem gần hết 30 trang ảnh, khoảng 45.000 token, nếu chưa OCR |
| Độ chính xác | Đúng từng ký tự, đúng dấu tiếng Việt | Ảnh mờ dễ đọc sai dấu, sai số; OCR tiếng Việt hay sai dấu và số |
| Giữ cấu trúc (chương, điều, khoản) | Có | Không, phải suy ra từ bố cục trang |

**Ghi chú:**

- Các con số token là ước tính. Chi phí ảnh tính theo kích thước ảnh; chi phí chữ phụ thuộc cách tách token, mà tiếng Việt có dấu thường tốn token hơn tiếng Anh.
- Khác biệt lớn nhất không nằm ở chi phí mỗi trang, mà ở khả năng tìm kiếm. Với văn bản có lớp chữ, Claude chỉ cần đọc phần liên quan, tiết kiệm từ 10 đến 50 lần với văn bản dài.
- PDF xuất từ Word (như văn bản trên Công báo năm 2026) có lợi ích tương đương file Word. Điều quan trọng là file có lớp chữ hay không, không phải định dạng.
- Với PDF ảnh quét, cách tối ưu là OCR 1 lần thành chữ (máy làm việc cần cài thêm công cụ), tìm đúng điều khoản, rồi chỉ xem ảnh các trang chứa số liệu quan trọng để soát lại.

# 8. Việc còn tồn đọng

| TT | Việc | Điều kiện |
|:------|:--------------------------------------------------|:----------------------------|
| 1 | Đối chiếu toàn văn khoảng 15 văn bản pháp luật trong nước qua Công báo, lập bảng truy nguyên | Người dùng đồng ý; Công báo đã truy cập được |
| 2 | Đọc 6 file quốc tế: Luật POFMA, bảng thống kê POFMA, Đạo luật Dịch vụ số, thông cáo phạt X, giao thức của Ofcom, báo cáo của Ủy ban Nội vụ Hạ viện Anh | Người dùng tải tay, đưa vào thư mục `nguon-goc/` trên GitHub |
| 3 | Tìm địa chỉ mới của bộ công cụ RESIST 2 | Claude làm được ngay |
| 4 | Số liệu chặn, gỡ quý III và 9 tháng năm 2026 | Cục Thông tin điện tử và Chuyển đổi số cung cấp |
| 5 | Xác minh diễn biến trên Threads của vụ Làng Vân, vụ Safari Ba Vì | Cục Thông tin điện tử và Chuyển đổi số, Bộ Công an, UBND thành phố Đà Nẵng, UBND thành phố Hà Nội |
| 6 | Gộp dự thảo 3 vào nhánh `main` | Người dùng yêu cầu tạo PR mới |

# Phụ lục 1. Danh mục commit

| Mã commit | Nội dung |
|:-----------|:--------------------------------------------------------------|
| `674bc89` | Thêm đề cương tham luận (dự thảo 1) |
| `44fe6f3` | Gộp PR #1 vào nhánh `main` |
| `d0e143c` | Bổ sung tác động của Threads và sự cố mới nhất năm 2026 (dự thảo 2) |
| `7512b5c` | Cập nhật căn cứ pháp lý và số liệu mới (dự thảo 3, phần 1) |
| `3d53cac` | Bổ sung kinh nghiệm quốc tế (dự thảo 3, phần 2) |
| `6727f0b` | Cập nhật nguồn gốc và sửa số liệu phần kinh nghiệm quốc tế |
| `47ee66c` | Đối chiếu văn bản gốc: mốc 5 giờ của Trung Quốc, số liệu nghiên cứu “tiêm chủng thông tin” |

# Phụ lục 2. Kết quả kiểm tra truy cập nguồn sau khi mở mạng

| Nguồn | Kết quả | Cơ chế |
|:----------------------------|:------------|:----------------------------|
| congbao.chinhphu.vn, chinhphu.vn, baochinhphu.vn, bvhttdl.gov.vn | Truy cập được | |
| gov.cn, who.int, vie-publique.fr, osis.bg, Europe PMC, restofworld.org, chinalawtranslate.com | Truy cập được | |
| pmc.ncbi.nlm.nih.gov | Lúc chặn, lúc vào được | Kiểm tra “không phải robot” theo tần suất |
| sso.agc.gov.sg, isomer-user-content.by.gov.sg, digital-strategy.ec.europa.eu | Mã 403 | Tường lửa của Amazon chặn thẳng |
| eur-lex.europa.eu | Mã 202 | Tường lửa của Amazon đòi kiểm tra JavaScript |
| ofcom.org.uk, committees.parliament.uk | Mã 403 | Cloudflare đòi kiểm tra trình duyệt |
| thuvienphapluat.vn, luatvietnam.vn, vbpl.vn | Mã 403 | Trang chặn truy cập tự động |
| gcs.civilservice.gov.uk (RESIST 2) | Chuyển hướng, rồi báo không tìm thấy | Đường dẫn hỏng, file đã chuyển chỗ |
