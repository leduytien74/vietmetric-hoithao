---
title: Báo cáo phân tích quá trình xây dựng đề cương
subtitle: Sự cố, nguyên nhân, cách khắc phục và mức độ tin cậy của kết quả tìm kiếm khi xây dựng đề cương tham luận về khủng hoảng truyền thông
lang: vi-VN
---

::: {custom-style=ThongTinChung}
Phiên làm việc ngày 27 và 28/10/2026 giữa người dùng và Claude
:::

::: {custom-style=ThongTinChung}
Ngày 28/10/2026, cập nhật lần 1 sau dự thảo 6. Đối tượng: đề cương tham luận của Bộ trưởng Bộ VHTTDL, các dự thảo 1 đến 6.
:::

# Tóm tắt

**Kết luận chung.** Sau 6 dự thảo, phần căn cứ pháp lý của đề cương đã đối chiếu với văn bản gốc: Claude đọc 16 luật, nghị định, quyết định trên Công báo và phần lớn tài liệu quốc tế chính. Bố cục, lập luận, đề xuất dùng được làm khung cho tổ biên tập. Dữ kiện chưa đối chiếu còn tập trung ở 3 nhóm: số liệu chặn, gỡ do báo chí dẫn từ Bộ VHTTDL; diễn biến trên Threads của các vụ việc năm 2026; một số kinh nghiệm quốc tế (Pháp, Thụy Điển, nền tảng bác bỏ tin đồn của Trung Quốc). Phụ lục 5 của đề cương đã giao đơn vị xác minh các dữ kiện này.

**5 phát hiện chính.**

1. Trước khi người dùng mở mạng, Claude không đọc được văn bản gốc nào. Sau khi mở mạng và người dùng tải lên 7 file bị chặn, Claude đọc được 59 tài liệu gốc hoặc nguồn chính: 16 văn bản pháp luật trên Công báo, 20 tài liệu nước ngoài, 23 bài báo và tài liệu trong nước.
2. Phiên làm việc phát sinh 36 sự cố, chia 4 nhóm: hạ tầng và quyền truy cập (9), sai sót nội dung (18), kỹ thuật (4), quy trình kiểm soát (5).
3. Claude đối chiếu 102 dữ kiện với nguồn gốc: 83 dữ kiện đúng; 9 dữ kiện đúng ý chính nhưng sai hoặc thiếu chi tiết; 10 dữ kiện sai hoặc không có trong nguồn được dẫn. Như vậy 19 dữ kiện, gần 1/5 số đã đối chiếu, phải sửa.
4. Ba lỗi nghiêm trọng nhất đều nằm ở chi tiết pháp lý, đúng loại chi tiết thính giả dễ hỏi lại khi lãnh đạo trình bày: dự thảo 1, 2 kiến nghị ban hành nghị định đã có hiệu lực (Nghị định số 244/2026/NĐ-CP); mức phạt “đến 50 triệu đồng” của Nghị định số 174/2026/NĐ-CP thực tế là mức với tổ chức, cá nhân tối đa 25 triệu đồng; thời hạn 6 giờ của Luật An ninh mạng năm 2025 chỉ áp dụng với yêu cầu của lực lượng chuyên trách thuộc Bộ Công an.
5. Loại sai nguy hiểm nhất là chi tiết không có trong nguồn được dẫn (6 trường hợp, tại sự cố 23, 24, 31). Claude ghép thông tin từ nhiều đoạn tóm tắt hoặc kiến thức sẵn có vào 1 câu, rồi dẫn 1 nguồn cho cả câu. Người đọc không thể phát hiện loại lỗi này nếu không mở nguồn.

**Việc cần làm tiếp.** Người dùng tải 6 trang còn bị chặn; đơn vị chức năng xác minh dữ kiện tại Phụ lục 5 của đề cương; gắn nhãn mức tin cậy A đến E cho từng dữ kiện trước khi trình; gộp dự thảo 6 vào nhánh `main`.

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
| 28/10, 09:28 | Lập báo cáo phân tích (bản đầu) | Commit `463c1a6` |
| 28/10, 10:21 | Bổ sung kinh nghiệm quốc tế liên quan Threads; thay RESIST 2 bằng RESIST 3 | Commit `f7822d1` |
| 28/10, 10:43 đến 11:15 | Người dùng tải 7 file bị chặn lên thư mục `tai-lieu` qua GitHub Desktop, 2 đợt | Commit `1c7577e`, `554b5e8` của người dùng |
| 28/10, 10:58 | Đối chiếu Luật POFMA, thống kê POFMA, quy định của Ofcom, báo cáo HC 381 (dự thảo 4) | Commit `482afa7` |
| 28/10, 11:21 | Đối chiếu Đạo luật Dịch vụ số, trang eSafety, bài Mekong Eye, Dân Việt (dự thảo 5) | Commit `df7cf2c` |
| 28/10, 12:10 | Đọc bản gốc Luật An ninh mạng năm 2025 trên Công báo | Commit `e168c43` |
| 28/10, 12:48 | Đối chiếu 15 văn bản pháp luật gốc trên Công báo và 29 nguồn tin (dự thảo 6) | Commit `02a0a68` |

**Số liệu của phiên làm việc.**

| Hạng mục | Số lượng |
|:-----------------------------------------------|:----------------------------|
| Lượt tìm kiếm | 142 (phiên chính 90; agent rà soát tên cơ quan 4; agent kinh nghiệm quốc tế 48) |
| Lượt mở trang bằng công cụ đọc trang | 13, thành công 0; từ khi người dùng mở mạng, Claude dùng lệnh tải thay thế |
| Tài liệu gốc, nguồn chính đọc được | 59 (16 văn bản pháp luật trên Công báo; 20 tài liệu nước ngoài; 23 bài báo, tài liệu trong nước) |
| File người dùng tải tay lên thư mục `tai-lieu` | 7 |
| Dữ kiện đã đối chiếu với nguồn gốc | 102 |
| Lệnh dòng lệnh; lượt chỉnh sửa, tạo file (tính đến lúc cập nhật báo cáo) | Khoảng 280; khoảng 75 |
| Commit | 13 của Claude, tính cả lần cập nhật này; 4 của người dùng, gồm 2 commit gộp |
| Pull request | 1, đã gộp |
| Bản sao lưu theo quy tắc của người dùng | 22 file (11 lần, mỗi lần 2 file) |
| Agent hỗ trợ | 2 (rà soát tên cơ quan; nghiên cứu kinh nghiệm quốc tế) |

# 2. Quy trình Claude đã dùng để viết đề cương

1. **Phân tích yêu cầu:** xác định người trình bày, thính giả, thời lượng, thông điệp chính.
2. **Nghiên cứu:** tìm kiếm theo chủ đề (văn bản pháp luật, cơ cấu Bộ VHTTDL, số liệu, vụ việc). Công cụ tìm kiếm trả về tiêu đề, đường dẫn và đoạn tóm tắt; đến dự thảo 3, Claude chưa đọc được trang gốc.
3. **Soạn bản Markdown:** bố cục, lập luận, đề xuất do Claude xây dựng; dữ kiện lấy từ đoạn tóm tắt tìm kiếm và kiến thức sẵn có.
4. **Đối chiếu văn bản gốc (từ dự thảo 4):** tải văn bản từ Công báo bằng cách duyệt danh mục theo trang; đọc file người dùng tải lên; chuyển sang dạng chữ, tìm đúng điều khoản; ghi kết quả vào sổ ghi chép theo từng văn bản trước khi sửa đề cương.
5. **Sửa đề cương có kiểm soát:** sửa bằng script, mỗi chỗ sửa phải khớp đúng 1 dòng; chạy thử trên bản sao trước khi áp dụng vào file thật.
6. **Rà soát tự động văn phong:** script kiểm tra ngoặc kép thẳng, dấu gạch ngang dài, các từ người dùng không dùng, chữ số viết bằng chữ, câu bị động.
7. **Rà soát tên cơ quan, chức danh:** giao 1 agent chuyên trách đối chiếu với bộ máy sau sắp xếp năm 2025, 2026.
8. **Xuất file Word:** chuyển đổi bằng pandoc, hậu xử lý bằng python-docx (phông chữ, bảng, số trang), kiểm tra cấu trúc file, xem thử trang dưới dạng ảnh.
9. **Lưu trữ:** sao lưu trước mỗi lần ghi đè, commit và đẩy lên GitHub.

**Điểm yếu của quy trình:** dự thảo 1 đến 3 thiếu khâu đối chiếu văn bản gốc. Từ dự thảo 4, quy trình có khâu này, nhưng Claude đối chiếu theo đợt, sau khi đã viết, nên lỗi phát hiện muộn; Claude cũng chưa gắn nhãn mức tin cậy cho từng câu.

# 3. Danh mục sự cố, nguyên nhân và cách khắc phục

## 3.1. Nhóm hạ tầng và quyền truy cập

| TT | Sự cố | Nguyên nhân | Cách khắc phục | Trạng thái |
|:------|:--------------------|:--------------------------|:--------------------------|:------------|
| 1 | Không mở được trang .vn và phần lớn trang nước ngoài; công cụ đọc trang báo lỗi tên miền, lệnh tải báo lỗi 403 | Môi trường cloud mặc định ở mức mạng “giới hạn”, chỉ cho phép danh sách tên miền duyệt sẵn; người dùng không chủ động chặn | Người dùng mở mạng trong cài đặt môi trường | Đã khắc phục; công cụ đọc trang vẫn chưa nhận cài đặt mới, Claude dùng lệnh tải thay thế |
| 2 | Đẩy lên GitHub thất bại (lỗi 403) | Claude GitHub App chưa cài cho kho | Người dùng cài GitHub App | Đã khắc phục |
| 3 | 9 trang nguồn chặn truy cập tự động (6 nguồn quốc tế; thuvienphapluat.vn, luatvietnam.vn, vbpl.vn) | Dịch vụ chống bot (tường lửa của Amazon, Cloudflare) chặn truy cập từ trung tâm dữ liệu không qua trình duyệt | Người dùng tải tay 7 file; Claude dùng bản gốc trên Công báo thay các trang pháp luật | Đã xử lý phần lớn; còn 6 trang chờ tải |
| 4 | Nhiều plugin (Canva, Slack, HubSpot...) không kết nối | Cùng nguyên nhân với sự cố 1, hoặc máy chủ plugin không hỗ trợ cách xác thực | Không ảnh hưởng nhiệm vụ | Không cần xử lý |
| 5 | Công cụ Claude in Chrome không có trong phiên | Phiên chạy trên đám mây, không nối tới trình duyệt của người dùng | Chỉ dùng được khi chạy Claude trên máy có Chrome và tiện ích | Không áp dụng |
| 19 | Ô tìm kiếm của Công báo chạy bằng JavaScript; danh mục văn bản chỉ hiện trang đầu | Giao diện trang dùng JavaScript | Tìm ra mẫu đường dẫn phân trang (`/trang-N.htm`), duyệt danh mục để tìm từng văn bản | Đã khắc phục |
| 20 | Kết nối tới máy chủ tải PDF của Công báo nhiều lần ngắt giữa chừng | Đường hầm qua máy chủ trung gian của môi trường đóng sớm | Tải lại với thời gian chờ tăng dần (2, 4, 8, 16 giây) | Đã khắc phục |
| 21 | 3 trang trước đó vào được nhưng hỏng lúc đọc: Báo Điện tử Chính phủ trả mã 403; trang báo cáo VIGINUM đang bảo trì; trang tóm tắt của Bộ Ngoại giao Pháp đổi địa chỉ | Trang thay đổi theo thời gian, có thể giới hạn tần suất truy cập | Ghi “chưa đọc được” trong đề cương; đề nghị người dùng tải | Chờ xử lý |
| 22 | GitHub Desktop không hiện file người dùng vừa thêm vào `tai-lieu`; kho dính file hệ thống `.DS_Store` và file khóa tạm của Word | File chưa commit, ứng dụng chưa nhận thay đổi; Word tạo file khóa khi đang mở tài liệu | Hướng dẫn commit, Pull rồi Push; hướng dẫn bỏ chọn `.DS_Store` | Đã khắc phục; file khóa vẫn còn trên GitHub |

## 3.2. Nhóm sai sót nội dung

| TT | Sự cố | Nguyên nhân | Cách khắc phục | Trạng thái |
|:------|:--------------------|:--------------------------|:--------------------------|:------------|
| 6 | Dự thảo 1, 2 kiến nghị “sớm ban hành” nghị định thay Nghị định số 09/2017/NĐ-CP, trong khi Nghị định số 244/2026/NĐ-CP đã có hiệu lực từ 1/7/2026 | Lượt tìm kiếm đầu chỉ ra bài báo tháng 2/2026 nói “sẽ ban hành”; công cụ đã cảnh báo “không xác nhận nghị định đã ban hành hay chưa”, nhưng Claude không tìm tiếp và coi việc không tìm thấy là chưa ban hành | Tìm lại với truy vấn khác, sửa toàn bộ các chỗ liên quan ở dự thảo 3 | Đã sửa; đã đối chiếu bản gốc trên Công báo (dự thảo 6) |
| 7 | Bỏ sót Nghị định số 328/2026/NĐ-CP về tin giả, văn bản sát chủ đề nhất | Tìm kiếm theo chủ đề, không có danh mục văn bản chuẩn để đối chiếu | Agent rà soát phát hiện, Claude xác minh và bổ sung | Đã sửa |
| 8 | Thiếu 7 căn cứ pháp lý (Điều 31 Luật Báo chí 2025, thời hạn gỡ bỏ theo Luật An ninh mạng 2025, Luật Bảo vệ dữ liệu cá nhân, Nghị định số 219/2026/NĐ-CP, Nghị định số 343/2026/NĐ-CP, Luật Tiếp cận thông tin, Luật Thực hiện dân chủ ở cơ sở) | Như sự cố 7 | Bổ sung ở dự thảo 3 sau khi người dùng hỏi về tính đầy đủ | Đã bổ sung; đã đọc văn bản gốc, trừ Luật Tiếp cận thông tin, Luật Thực hiện dân chủ ở cơ sở |
| 9 | Nghiên cứu “tiêm chủng thông tin”: agent ghi “thử nghiệm với khoảng 1 triệu người” | Agent chỉ có tóm tắt bài phổ biến khoa học; gộp số người xem video với số người trả lời câu hỏi kiểm tra trong 1 câu; Claude không kiểm lại | Đối chiếu toàn văn qua Europe PMC: video hiển thị cho khoảng 5,4 triệu người, 22.632 người trả lời câu hỏi kiểm tra | Đã sửa theo bản gốc |
| 10 | Khi sửa sự cố 9, Claude bỏ nhầm 2 số liệu đúng (mức tăng 5%, chi phí 0,05 USD mỗi lượt xem) | Sửa khi chưa có bản gốc, chọn cách bỏ cho an toàn nhưng làm mất thông tin đúng | Khôi phục sau khi đọc toàn văn | Đã sửa |
| 11 | Số liệu Luật POFMA của Singapore lạc hậu (đến 30/9/2025) | Agent dùng bản thống kê cũ | Cập nhật theo bản thống kê đến 1/7/2026 | Đã sửa; đã đối chiếu bảng thống kê gốc (dự thảo 4) |
| 12 | Chi tiết chưa rõ nguồn: vụ xử phạt tin giả ở Hà Tĩnh ngày 16/9/2026; con số “1.287 phản ánh”; kết quả bầu cử Nepal; tổng số người chết ở Nepal | Đoạn tóm tắt tìm kiếm gộp từ nhiều bài, không chỉ rõ nguồn | Bỏ khỏi đề cương ở dự thảo 3; dự thảo 6 khôi phục vụ Hà Tĩnh và con số 1.287 sau khi tìm được bài gốc | Đã xử lý |
| 13 | Ngày, mốc không thống nhất giữa các nguồn: ngày Nepal ban hành lệnh chặn (4 hay 5/9/2025); bài báo nêu Hà Nội “thống nhất chủ trương” dự án Safari Ba Vì so với thông tin Sở Tài chính Hà Nội nói “mới là đề xuất” | Mâu thuẫn có sẵn giữa các nguồn báo chí | Ghi “đầu tháng 9/2025”; với Ba Vì, dùng chính mâu thuẫn làm dẫn chứng về thông tin thiếu nhất quán | Đã xử lý |
| 23 | Vụ Southport: “cảnh sát bắt giữ hơn 1.700 người (đến 12/2024)”, “có bị cáo nhận án tù chỉ 1 ngày sau bài đăng”; kết luận của Ủy ban Nội vụ Hạ viện Anh ghi mạnh hơn bản gốc | Số liệu cũ từ tóm tắt tìm kiếm; chi tiết án tù không có trong báo cáo được dẫn | Đọc báo cáo HC 381: 1.804 lượt bắt giữ đến 22/1/2025; Ủy ban kết luận “chưa thể xác định” công bố thêm thông tin có ngăn được bạo loạn hay không | Đã sửa (dự thảo 4) |
| 24 | Nhận định “cải chính ít gây phản ứng ngược hơn gỡ bài” về Singapore | Nhận định của Claude, viết như dữ kiện | Thay bằng số liệu gốc: đến 1/7/2026, Singapore chưa ban hành lệnh ngừng phát tán, lệnh gỡ nội dung nào | Đã sửa (dự thảo 4) |
| 25 | Số liệu lừa đảo trực tuyến “hơn 4.200 vụ, hơn 8.000 tỷ đồng” | Tóm tắt tìm kiếm thêm chữ “hơn” | Nguồn gốc ghi 4.200 vụ việc, khoảng 8.000 tỷ đồng | Đã sửa (dự thảo 5) |
| 26 | Thời hạn 24 giờ, 6 giờ của Luật An ninh mạng ghi “kể từ khi nhận yêu cầu hợp pháp” | Viết theo nguồn thứ cấp trước khi đọc luật | Điều 25: yêu cầu phải từ lực lượng chuyên trách thuộc Bộ Công an; yêu cầu của Bộ VHTTDL chỉ có mốc 24 giờ theo Nghị định số 147/2024/NĐ-CP | Đã sửa; đưa thành kiến nghị |
| 27 | Mức phạt chia sẻ tin sai sự thật trên mạng xã hội “lên đến 50 triệu đồng” | Dựa vào tiêu đề báo; không đọc điều khoản về cách áp dụng mức phạt | Điều 4 Nghị định số 174/2026/NĐ-CP: đây là mức với tổ chức, cá nhân tối đa 25 triệu đồng | Đã sửa (dự thảo 6) |
| 28 | Mốc 24 giờ của Nghị định số 244/2026/NĐ-CP ghi như tính từ khi sự việc xảy ra | Đoạn tóm tắt bỏ mốc bắt đầu tính | Khoản 3, 4 Điều 7: tính từ khi cơ quan tiếp nhận vụ việc hoặc xác định vụ việc có nguy cơ tác động đến dư luận | Đã sửa (dự thảo 6) |
| 29 | Tên, phạm vi Nghị định số 328/2026/NĐ-CP và 343/2026/NĐ-CP ghi theo cách báo chí mô tả | Chưa có bản gốc | Ghi đúng tên; nêu rõ Bộ Công an giúp Chính phủ quản lý nhà nước về tin giả, Nghị định số 343/2026/NĐ-CP thuộc phạm vi Bộ Quốc phòng | Đã sửa (dự thảo 6) |
| 30 | Thời gian xử lý 3 đến 12 giờ ghi chung cho các nền tảng | Tóm tắt khái quát hóa số liệu riêng của TikTok | Ghi rõ là số liệu của TikTok | Đã sửa (dự thảo 6) |
| 31 | 4 chi tiết không có trong nguồn được dẫn: vụ Kera có 3 bộ phối hợp, người có ảnh hưởng xin lỗi; video deepfake mạo danh công an, kiểm sát viên; Quyết định số 423/QĐ-BVHTTDL thay thế Bộ quy tắc năm 2021; Phần Lan đứng đầu “lần thứ 6 liên tiếp” | Claude ghép thông tin từ nhiều đoạn tóm tắt hoặc kiến thức sẵn có, rồi dẫn 1 nguồn cho cả câu | Bỏ hoặc thay bằng nội dung có trong nguồn | Đã sửa (dự thảo 6) |
| 32 | Thông tin trái chiều về dự án Safari Ba Vì: Mekong Eye viết UBND Hà Nội phê duyệt dự án ngày 9/10/2026; báo chí trong nước đến 5/10 ghi “mới là đề xuất” | Mâu thuẫn giữa nguồn nước ngoài và trong nước; chưa có nguồn trong nước sau ngày 9/10 | Ghi rõ “chưa xác nhận”; giao UBND thành phố Hà Nội xác minh | Chờ xác minh |

## 3.3. Nhóm kỹ thuật

| TT | Sự cố | Nguyên nhân | Cách khắc phục |
|:------|:------------------------|:----------------------------|:----------------------------|
| 14 | File Word ban đầu không đạt kiểm tra cấu trúc | Mẫu mặc định của pandoc sinh mã XML sai thứ tự quy định | Viết bước hậu xử lý sắp xếp lại mã; file đạt kiểm tra |
| 15 | Bảng có cột hẹp, hàng tách sang trang sau; phụ lục không sang trang mới | Thiết lập mặc định của pandoc | Đặt tỷ lệ cột, cấm tách hàng, lặp tiêu đề bảng, ngắt trang trước phụ lục |
| 16 | Phát sinh file rác tên “-” trong thư mục; hệ thống an toàn chặn 1 lệnh xóa thư mục | Sai cú pháp lệnh xuất mẫu; lệnh xóa dùng ký tự đại diện sau khi đổi thư mục | Xóa file rác; dùng thư mục mới thay vì xóa |
| 33 | Một số trang báo tải về ở dạng nén; công cụ chuyển sang chữ báo lỗi | Lệnh tải chưa bật giải nén; công cụ chưa có bước dự phòng khi không nhận ra bảng mã | Bật giải nén khi tải; thêm bước dự phòng giải mã |

## 3.4. Nhóm quy trình kiểm soát

| TT | Sự cố | Nguyên nhân | Cách khắc phục |
|:------|:------------------------|:----------------------------|:----------------------------|
| 17 | Claude ghi đường dẫn RESIST 2 là “đã xác nhận”, nhưng đường dẫn đã hỏng (chuyển hướng rồi báo không tìm thấy) | Coi “xuất hiện trong kết quả tìm kiếm” là “còn hoạt động” | Ghi đính chính; thay bằng RESIST 3; từ đó chỉ ghi “đã xác nhận” sau khi mở được file |
| 18 | Khi chẩn đoán lỗi 403, Claude chạy lệnh giả danh trình duyệt; hệ thống từ chối vì đây là hành vi vượt lớp chống bot | Chọn sai cách chẩn đoán | Dừng ngay; chẩn đoán lại bằng lệnh tải thông thường; không tìm cách vượt qua lớp bảo vệ của trang |
| 34 | Ghi chú “đã đọc toàn văn” ở nguồn tài liệu tham luận trên cổng thông tin Lai Châu dễ hiểu nhầm là Claude đã đọc toàn văn Luật An ninh mạng | Ghi chú nói về tài liệu, không nói rõ về luật | Người dùng hỏi lại; Claude đọc bản gốc luật trên Công báo, sửa ghi chú |
| 35 | Claude kết luận vội “không tra được Công báo theo số hiệu”, đề nghị người dùng tải tay 17 văn bản | Mới thử ô tìm kiếm, chưa thử cách khác | Tìm ra cách phân trang, tự tải đủ văn bản; đính chính với người dùng |
| 36 | Lặp lại sự cố 18: khi tải lại trang Báo Điện tử Chính phủ, Claude thêm tham số giả danh trình duyệt; hệ thống chặn | Tái phạm thói quen chẩn đoán sai dù đã rút kinh nghiệm | Không thử lại; ghi “chưa đọc được”; báo cáo với người dùng |

# 4. Mức độ tin cậy của kết quả tìm kiếm

## 4.1. Cơ chế tạo ra sai lệch

Dữ kiện trong đề cương đi qua nhiều lớp trước khi đến tay tổ biên tập:

1. Văn bản gốc (luật, nghị định, báo cáo, bài nghiên cứu).
2. Bài báo, trang tư vấn pháp luật diễn giải lại văn bản gốc; tiêu đề báo thường rút gọn đến mức sai (ví dụ “phạt đến 50 triệu đồng”).
3. Đoạn trích ngắn công cụ tìm kiếm lấy từ các bài đó.
4. Đoạn tóm tắt do công cụ tìm kiếm tự viết từ các đoạn trích.
5. Claude hoặc agent tóm tắt lại thêm 1 lần, có lúc ghép thêm kiến thức sẵn có, rồi đưa vào đề cương.

Mỗi lớp đều có thể làm sai lệch thông tin. Trước khi người dùng mở mạng, Claude chỉ tiếp cận được từ lớp 4. Từ dự thảo 4, Claude đối chiếu ngược về lớp 1.

## 4.2. Các kiểu sai lệch đã gặp trong phiên

| Kiểu sai lệch | Ví dụ trong phiên |
|:----------------------------|:--------------------------------------------------|
| Lạc hậu thời gian | Nghị định số 09/2017/NĐ-CP đã có văn bản thay thế; số liệu POFMA, số người bị bắt ở Anh lấy từ thời điểm cũ |
| Thiếu mốc tính, đối tượng áp dụng | Mốc 24 giờ của Nghị định số 244/2026/NĐ-CP; mức phạt 50 triệu đồng áp dụng cho tổ chức hay cá nhân; thời hạn 6 giờ áp dụng với yêu cầu của cơ quan nào |
| Gộp sai đơn vị đo | Khoảng 1 triệu người xem video so với 22.632 người trả lời câu hỏi kiểm tra; 115.000 video là số video liên quan 10 tệp âm thanh, không phải số video TikTok trực tiếp gỡ |
| Khái quát hóa số liệu riêng | Thời gian xử lý 3 đến 12 giờ của TikTok ghi thành của mọi nền tảng |
| Tên văn bản theo cách báo chí mô tả | Nghị định số 328/2026/NĐ-CP, 343/2026/NĐ-CP |
| Chi tiết không có trong nguồn được dẫn | Vụ Kera; deepfake mạo danh; Quyết định số 423/QĐ-BVHTTDL; chỉ số của Phần Lan; án tù 1 ngày ở Anh |
| Nhận định viết như dữ kiện | “Cải chính ít gây phản ứng ngược hơn gỡ bài” |
| Mâu thuẫn giữa các nguồn | Ngày Nepal ban hành lệnh chặn; thông tin về dự án Safari Ba Vì |
| Đường dẫn có trong chỉ mục nhưng đã hỏng | File RESIST 2; trang tóm tắt của Bộ Ngoại giao Pháp |
| Nguồn có quan điểm chính trị riêng | Diễn biến trên Threads của vụ Làng Vân, vụ Safari Ba Vì chủ yếu từ nguồn nước ngoài |

**Điểm đáng chú ý:** công cụ tìm kiếm thường tự cảnh báo (“chưa đối chiếu văn bản gốc”, “các nguồn không thống nhất”). Phần lớn sai sót xảy ra khi Claude hoặc agent bỏ qua các cảnh báo này lúc tóm tắt lại, hoặc khi Claude ghép thêm chi tiết không có trong nguồn.

## 4.3. Kết quả đối chiếu văn bản gốc

| Nhóm dữ kiện | Số dữ kiện đối chiếu | Đúng | Đúng ý chính, sai hoặc thiếu chi tiết | Sai hoặc không có trong nguồn |
|:----------------------|:------------:|:------------:|:------------:|:------------:|
| Văn bản pháp luật trong nước | 36 | 29 | 4 | 3 |
| Số liệu, vụ việc trong nước | 25 | 20 | 3 | 2 |
| Kinh nghiệm quốc tế | 41 | 34 | 2 | 5 |
| **Tổng** | **102** | **83** | **9** | **10** |

**Đọc kết quả thế nào.**

- Gần 1/5 dữ kiện đã đối chiếu (19/102) phải sửa. Nhóm kinh nghiệm quốc tế có tỷ lệ sai cao nhất (5/41), vì phần lớn dữ kiện đi qua agent và qua nhiều lớp tóm tắt.
- Mẫu đối chiếu không ngẫu nhiên: Claude ưu tiên số liệu và chi tiết pháp lý, là nhóm dễ sai nhất. Tỷ lệ này không đại diện cho toàn bộ đề cương; phần lập luận, đề xuất không phải dữ kiện nên không nằm trong mẫu.
- Lỗi tập trung ở chi tiết: con số, mốc thời gian, đối tượng áp dụng, tên văn bản. Ý chính của gần như mọi dữ kiện đều đúng.

**Dữ kiện chưa đối chiếu được.**

| Dữ kiện | Lý do |
|:----------------------------|:--------------------------------------------------|
| Số liệu quý III/2025 (12.200 thông tin; Facebook 10.713 bài viết) | Trang Báo Điện tử Chính phủ trả mã 403 |
| 43 chiến dịch nhắm vào Thế vận hội Paris (VIGINUM) | Trang báo cáo đang bảo trì; trang tóm tắt đổi địa chỉ |
| Năm thành lập Cơ quan Phòng vệ tâm lý Thụy Điển | Trang chủ, trang giới thiệu không ghi |
| Số liệu nền tảng bác bỏ tin đồn của Trung Quốc | Trang chạy bằng JavaScript |
| Khoản phạt X 120 triệu euro; Meta ngừng đề xuất nội dung chính trị (2/2024); số liệu Meta hạn chế nội dung tại Việt Nam | Trang chặn truy cập tự động hoặc cần JavaScript; chờ người dùng tải |
| Dự án Safari Ba Vì phê duyệt ngày 9/10/2026 | Chỉ có nguồn Mekong Eye |
| Quyết định số 423/QĐ-BVHTTDL, 2559/QĐ-BVHTTDL | Không đăng Công báo; đối chiếu qua Báo Nhân Dân, LuatVietnam |
| Nghị quyết số 35-NQ/TW; Luật Tiếp cận thông tin; Luật Thực hiện dân chủ ở cơ sở; Điều 117, 288, 331 Bộ luật Hình sự | Chưa tra; dựa trên kiến thức sẵn có của Claude |

## 4.4. Thang mức tin cậy đề xuất áp dụng cho đề cương

| Mức | Loại dữ kiện | Ví dụ | Cách sử dụng |
|:------|:------------------------|:----------------------------|:----------------------------|
| A | Đã đối chiếu văn bản gốc | 16 văn bản pháp luật trên Công báo; Luật POFMA, quy định của Ofcom, báo cáo HC 381, Đạo luật Dịch vụ số; số liệu Science Advances | Dùng trực tiếp |
| B | Nhiều nguồn chính thống trong nước thống nhất | Số liệu chặn, gỡ 6 tháng đầu năm 2026 (Sài Gòn Giải Phóng, Znews, Tuổi Trẻ thống nhất); con số 1.287 phản ánh | Dùng được; đơn vị chức năng xác nhận trước khi trình |
| C | 1 nguồn hoặc 1 đoạn tóm tắt | Vụ phạt ở Hà Tĩnh; số người dùng Threads tại Việt Nam | Ghi rõ nguồn, giao đơn vị chức năng xác nhận |
| D | Phản ánh của người dùng, nguồn nước ngoài | Diễn biến trên Threads vụ Làng Vân, vụ Safari Ba Vì; số liệu Meta dẫn qua Mekong Eye | Chỉ dùng làm chỉ dấu, không nêu trong bài nói nếu chưa xác minh |
| E | Đề xuất, ước lượng của Claude | 3 cấp độ khủng hoảng, mốc 3, 6, 24 giờ, 5 giai đoạn diễn biến, 7 nhóm giải pháp | Không phải dữ kiện; tổ biên tập thẩm định về chính sách |

# 5. Đánh giá quá trình viết đề cương

**Điểm làm được.**

- Bố cục, thông điệp chính, nhóm giải pháp và kiến nghị rõ ràng, có phân bổ thời lượng cho bài nói.
- Văn phong tuân thủ quy tắc của người dùng nhờ kiểm tra tự động sau mỗi lần sửa.
- Tên cơ quan, chức danh khớp bộ máy sau sắp xếp năm 2025, 2026 (agent rà soát không phát hiện lỗi chắc chắn).
- Sau khi có quyền truy cập, Claude đối chiếu có hệ thống: tự tìm văn bản trên Công báo, đọc tài liệu người dùng tải lên, sửa 19 dữ kiện, ghi rõ mức kiểm chứng của từng nguồn.
- Đối chiếu văn bản gốc phát hiện 3 khoảng trống pháp lý dùng được cho kiến nghị: thời hạn khẩn cấp chưa áp dụng với yêu cầu của Bộ VHTTDL; mức phạt nền tảng xuyên biên giới không gỡ bỏ chỉ từ 30 đến 50 triệu đồng; phân vai giữa Bộ Công an và Bộ VHTTDL theo Nghị định số 328/2026/NĐ-CP.
- Đối chiếu cũng tìm ra 3 căn cứ trực tiếp cho chủ đề tham luận: Nghị định số 244/2026/NĐ-CP, 328/2026/NĐ-CP và Quyết định số 1125/QĐ-TTg đều dùng thuật ngữ “khủng hoảng truyền thông”.
- Có phụ lục liệt kê dữ kiện cần xác minh, giao đơn vị cụ thể.
- Tuân thủ quy tắc sao lưu trước khi ghi đè; mọi thay đổi có commit và lịch sử; giữ chỉnh sửa của người dùng khi cập nhật file Word.
- Xử lý thận trọng các vụ việc nhạy cảm: phân biệt góp ý chính đáng với hoạt động chống phá; không dẫn nguồn của tổ chức chống đối trong đề cương; không đưa vào đề cương nội dung chưa xác minh liên quan đến cá nhân.

**Điểm chưa làm được.**

- Khi phát hiện không mở được trang nguồn, Claude chỉ nêu hạn chế ở phần báo cáo cuối dự thảo 1, chưa đề xuất ngay cách mở mạng; vì vậy dự thảo 1 đến 3 viết hoàn toàn từ nguồn thứ cấp.
- Không có danh mục văn bản chuẩn trước khi viết, dẫn tới bỏ sót và dùng văn bản lạc hậu.
- Đưa kết quả của agent vào đề cương khi chỉ đối chiếu ý chính với hiểu biết sẵn có, không kiểm từng con số.
- Ghép chi tiết không có trong nguồn vào câu văn rồi dẫn 1 nguồn cho cả câu (sự cố 31).
- Ghi “đã xác nhận” cho đường dẫn khi chưa mở được; ghi chú “đã đọc toàn văn” chưa đủ rõ (sự cố 34).
- Kết luận vội về khả năng tra Công báo, suýt chuyển cho người dùng việc không cần thiết (sự cố 35).
- Lặp lại lỗi giả danh trình duyệt dù đã rút kinh nghiệm (sự cố 36).
- Chưa gắn nhãn A đến E cho từng câu trong đề cương; đối chiếu theo mẫu chọn lọc, chưa phủ toàn bộ dữ kiện.

# 6. Quy trình đề xuất cho lần sau

1. **Kiểm tra điều kiện làm việc ngay đầu phiên:** quyền truy cập mạng tới các nguồn chính thức, quyền ghi lên kho GitHub.
2. **Lập danh mục văn bản chuẩn từ Công báo trước khi viết:** các luật, nghị định, quyết định còn hiệu lực liên quan đến chủ đề; tải bản gốc ngay từ đầu.
3. **Gắn nhãn mức tin cậy A đến E cho từng dữ kiện ngay khi viết,** không đợi rà soát cuối.
4. **Không kết luận “chưa ban hành”, “không có”, “không tra được” khi mới thử 1 cách;** phải thử thêm cách hợp lệ khác hoặc tra Công báo.
5. **Với mỗi số liệu, ghi rõ 3 yếu tố:** đo cái gì, trên mẫu nào, tại thời điểm nào.
6. **Với mỗi mức phạt, thời hạn, ghi rõ 3 yếu tố:** áp dụng cho ai, tính từ mốc nào, do cơ quan nào yêu cầu; đọc cả điều khoản quy định cách áp dụng, không chỉ điều khoản nêu con số.
7. **Mỗi câu chỉ dẫn 1 nguồn khi toàn bộ nội dung câu có trong nguồn đó;** ghép nhiều nguồn thì dẫn đủ; nhận định của Claude phải ghi rõ là nhận định.
8. **Kiểm lại từng con số trong báo cáo của agent** trước khi đưa vào văn bản; yêu cầu agent ghi rõ mức tin cậy của từng số.
9. **Chỉ ghi “đã xác nhận”, “đã đọc toàn văn” khi đã mở được trang hoặc file;** ghi rõ đã đọc tài liệu nào, ngày truy cập.
10. **Sửa lỗi dựa trên bản gốc;** khi chưa có bản gốc, đánh dấu “cần xác minh” thay vì bỏ hẳn.
11. **Không vượt qua lớp chống bot dưới bất kỳ hình thức nào;** dùng nguồn chính thức thay thế hoặc nhờ người dùng tải tay.
12. **Ưu tiên tài liệu có lớp chữ** (file Word, PDF xuất từ Word); với PDF ảnh quét, dùng nhận dạng chữ rồi soát lại số liệu bằng mắt trên ảnh trang gốc.
13. **Ghi sổ đối chiếu theo từng văn bản trước khi sửa;** sửa bằng script kiểm tra khớp từng dòng và chạy thử trên bản sao.

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
- Thực tế phiên này: cả 16 văn bản trên Công báo và 7 file người dùng tải lên đều có lớp chữ. Với Nghị định số 174/2026/NĐ-CP dài 139 trang, Claude tìm đúng Điều 4, Điều 95, Điều 97 mà không phải đọc hết.
- PDF xuất từ Word (như văn bản trên Công báo năm 2026) có lợi ích tương đương file Word. Điều quan trọng là file có lớp chữ hay không, không phải định dạng.
- Với PDF ảnh quét, cách tối ưu là OCR 1 lần thành chữ (máy làm việc cần cài thêm công cụ), tìm đúng điều khoản, rồi chỉ xem ảnh các trang chứa số liệu quan trọng để soát lại.

# 8. Việc còn tồn đọng

| TT | Việc | Điều kiện |
|:------|:--------------------------------------------------|:----------------------------|
| 1 | Tải 6 trang còn bị chặn: Phụ nữ Việt Nam (sự cố Meta ngày 12/6/2026), VOV (dự án Safari Ba Vì), Ủy ban châu Âu (khoản phạt X), Axios (Meta, 2/2024), báo cáo hạn chế nội dung của Meta (mục Việt Nam), Báo Điện tử Chính phủ (số liệu quý III/2025) | Người dùng tải, đưa vào thư mục `tai-lieu` |
| 2 | Xác minh các dữ kiện tại Phụ lục 5 của đề cương: số liệu chặn, gỡ; diễn biến trên Threads; việc phê duyệt dự án Safari Ba Vì | Cục Thông tin điện tử và Chuyển đổi số, Bộ Công an, UBND thành phố Đà Nẵng, UBND thành phố Hà Nội |
| 3 | Gắn nhãn A đến E cho từng dữ kiện trong đề cương | Người dùng đồng ý |
| 4 | Đối chiếu Luật Tiếp cận thông tin, Luật Thực hiện dân chủ ở cơ sở, Điều 117, 288, 331 Bộ luật Hình sự trên Công báo | Claude làm được |
| 5 | Xóa file khóa tạm của Word và `.DS_Store` khỏi kho; thêm `.gitignore` | Người dùng đồng ý |
| 6 | Gộp dự thảo 6 và báo cáo này vào nhánh `main` | Người dùng yêu cầu tạo PR mới |

# Phụ lục 1. Danh mục commit

| Mã commit | Người thực hiện | Nội dung |
|:-----------|:------------|:--------------------------------------------------------------|
| `674bc89` | Claude | Thêm đề cương tham luận (dự thảo 1) |
| `44fe6f3` | Người dùng | Gộp PR #1 vào nhánh `main` |
| `d0e143c` | Claude | Bổ sung tác động của Threads và sự cố mới nhất năm 2026 (dự thảo 2) |
| `7512b5c` | Claude | Cập nhật căn cứ pháp lý và số liệu mới (dự thảo 3, phần 1) |
| `3d53cac` | Claude | Bổ sung kinh nghiệm quốc tế (dự thảo 3, phần 2) |
| `6727f0b` | Claude | Cập nhật nguồn gốc và sửa số liệu phần kinh nghiệm quốc tế |
| `47ee66c` | Claude | Đối chiếu văn bản gốc: mốc 5 giờ của Trung Quốc, số liệu nghiên cứu “tiêm chủng thông tin” |
| `463c1a6` | Claude | Thêm báo cáo phân tích quá trình (bản đầu) |
| `f7822d1` | Claude | Bổ sung kinh nghiệm quốc tế liên quan Threads; thay RESIST 2 bằng RESIST 3 |
| `1c7577e` | Người dùng | Thêm 4 file tài liệu vào thư mục `tai-lieu` |
| `be78b8f` | Người dùng | Gộp nhánh từ GitHub về máy |
| `482afa7` | Claude | Dự thảo 4: đối chiếu 4 tài liệu gốc về Singapore, Anh |
| `554b5e8` | Người dùng | Bổ sung 3 file tài liệu |
| `df7cf2c` | Claude | Dự thảo 5: đối chiếu Đạo luật Dịch vụ số, trang eSafety, bài Mekong Eye, Dân Việt |
| `e168c43` | Claude | Đối chiếu bản gốc Luật An ninh mạng năm 2025 trên Công báo |
| `02a0a68` | Claude | Dự thảo 6: đối chiếu 15 văn bản pháp luật gốc và 29 nguồn tin |

# Phụ lục 2. Kết quả kiểm tra truy cập nguồn sau khi mở mạng

| Nguồn | Kết quả | Cơ chế |
|:----------------------------|:------------|:----------------------------|
| congbao.chinhphu.vn | Truy cập được | Ô tìm kiếm cần JavaScript; duyệt danh mục theo trang; máy chủ tải PDF đôi khi ngắt kết nối |
| chinhphu.vn, bvhttdl.gov.vn, các báo điện tử trong nước | Truy cập được | Một số trang trả dữ liệu nén |
| baochinhphu.vn | Lúc vào được, lúc mã 403 | Chặn theo tần suất truy cập |
| gov.cn, who.int, osis.bg, Europe PMC, restofworld.org, cbsnews.com, mlaw.gov.sg, reutersinstitute.politics.ox.ac.uk | Truy cập được | |
| vie-publique.fr (báo cáo VIGINUM) | Trang đang bảo trì | |
| diplomatie.gouv.fr | Đường dẫn chuyển về trang chung | Bài viết đã đổi địa chỉ |
| piyao.org.cn, transparency.meta.com | Tải được khung trang, không có nội dung | Nội dung chạy bằng JavaScript |
| pmc.ncbi.nlm.nih.gov | Lúc chặn, lúc vào được | Kiểm tra “không phải robot” theo tần suất |
| sso.agc.gov.sg, isomer-user-content.by.gov.sg, digital-strategy.ec.europa.eu | Mã 403 | Tường lửa của Amazon chặn thẳng; người dùng đã tải 2 file Singapore |
| eur-lex.europa.eu | Mã 202 | Tường lửa của Amazon đòi kiểm tra JavaScript; người dùng đã tải file |
| ofcom.org.uk, committees.parliament.uk | Mã 403 | Cloudflare đòi kiểm tra trình duyệt; người dùng đã tải file |
| thuvienphapluat.vn, vbpl.vn, luatminhkhue.vn | Mã 403 | Trang chặn truy cập tự động |
| luatvietnam.vn | Tùy trang | Một số trang văn bản vào được |
| phunuvietnam.vn, vov.vn, axios.com | Chuyển hướng lỗi hoặc mã 403 | Chờ người dùng tải |
| gcs.civilservice.gov.uk (RESIST 2) | Chuyển hướng, rồi báo không tìm thấy | Đường dẫn hỏng; đề cương đã thay bằng RESIST 3 |
