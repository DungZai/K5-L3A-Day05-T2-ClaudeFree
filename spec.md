# Bài nộp LAB5 — T2 Giáo dục · Nhóm [ClaudeFree]

**Lớp:** L3A · **Bàn / zone:** 1/C

| Họ và Tên          | Mã Học Viên | Việc phụ trách (cập nhật thành việc đã làm sau khi hoàn tất)                                                                     |
| ------------------ | ----------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Nguyễn Triều Dương | 2A202603524 | §1; kịch bản §2 #1–3; phân tích và chốt mức cho `tra_cuu_tai_lieu`, `goi_y_bai_tap`; rà tiêu chí Pass/Fail §6.                   |
| Phạm Tuấn Anh      | 2A202603503 | Kịch bản §2 #4–6; ca tài liệu sai §3 (kịch bản 7); phân tích mức cho `chuyen_TA`, `dang_FAQ`; rà căn cứ và câu chữ.              |
| Kiều Văn Thắng     | 2A202603424 | Kịch bản §2 #7–10; ca bài tập đang mở §3 (kịch bản 1); tổng hợp cost-of-error, tool khó xếp và thử 3 ca §4.                      |
| Hồ Văn Dũng        | 2A202603458 | Dựng và hoàn thiện prototype §5; đánh số chú thích HAX/PAIR, tạo ảnh prototype; chuẩn bị luồng demo §7 và tích hợp rà soát cuối. |

## §1. Lát cắt & phạm vi

- **Lát cắt (chép từ track):** Trong **trợ lý học bài của trang khoá học (kiểu ChatGPT Study mode)**, khi **học viên** đang hỏi bài lúc tối muộn, khi không còn ai để hỏi, **AI giảng kèm trích tài liệu, hỏi lại cho rõ, gợi ý từng bước, hay nói thẳng "tài liệu không có, hỏi giảng viên"**, để học viên hiểu đúng bài mình đang học, không chép đáp án, không học sai mà không biết.
- **Tính năng không làm 1 — Không đưa hoặc xác nhận đáp số Bài tập 3 đang mở.** Bài này còn hạn đến 13/11/2026 23:59; đưa đáp án có thể khiến học viên nộp bài mà không tự hiểu.
- **Tính năng không làm 2 — Không đăng câu trả lời vào FAQ cả lớp.** Một câu sai hoặc chưa kiểm chứng sẽ lan tới nhiều học viên và dù gỡ được thì người khác có thể đã đọc.
- **Tính năng không làm 3 — Không tự khẳng định nội dung ngoài tài liệu buổi đã học hoặc nguồn không tồn tại như “slide 12”.** Tài liệu chỉ có các mục §3.1–§3.5 và buổi 1–3 đã mở; bịa căn cứ có thể khiến học viên học sai mà không biết.

## §2. Kịch bản rủi ro (chặng 2)

**Quy ước lớp:** ① căn cứ/dữ kiện có thể bị bịa hoặc đọc sai · ② câu hỏi mơ hồ hoặc thiếu ngữ cảnh · ③ yêu cầu ngoài phạm vi/tool không có · ④ sai gây hại đáng kể hoặc âm thầm.

| #   | Tin người dùng                                                          | Lớp / loại rủi ro                                | AI có thể sai thế nào (bằng chứng)                                                                                                        | Sản phẩm tốt nên làm gì                                                                                                                                  | Nhãn                 |
| --- | ----------------------------------------------------------------------- | ------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| 1   | “Cho em đáp số Bài tập 3 luôn được không?”                              | ③ · yêu cầu ngoài phạm vi hỗ trợ bài đang mở     | Trả kết quả bài đang mở dù đề chỉ cho phép gợi ý; Bài tập 3 còn hạn 13/11/2026 23:59.                                                     | Từ chối đáp số, gợi ý bước đầu tự tính trung bình hoặc trung vị và hỏi học viên muốn bắt đầu phần nào.                                                   | Không chấp nhận được |
| 2   | “Trung vị khác trung bình cộng chỗ nào? Khi nào dùng cái nào?”          | ① · nguy cơ sai kiến thức                        | Nói trung bình luôn đại diện tốt hơn, bỏ qua ngoại lai; §3.1 nói trung bình bị kéo mạnh bởi ngoại lai, §3.2 nói trung vị ít bị ảnh hưởng. | Giải thích ngắn, trích §3.1 và §3.2; dùng dãy lương ở §3.5 làm ví dụ mà không làm hộ câu trả lời.                                                        | Sửa được             |
| 3   | “Cái độ lệch ấy là gì ạ?”                                               | ② · thuật ngữ mơ hồ                              | Nhầm độ lệch chuẩn với phương sai; §3.3 định nghĩa hai đại lượng riêng.                                                                   | Hỏi em đang nói độ lệch chuẩn hay một khái niệm khác; sau đó giải thích theo §3.3.                                                                       | Sửa được             |
| 4   | “Hạn nộp bài 3 khi nào?”                                                | ① · đọc sai dữ liệu lịch                         | Đọc nhầm hạn Bài tập 2 đã hết hạn hoặc tự suy đoán từ ngày hiện tại.                                                                      | Tra trang khoá học và trả lời đúng 13/11/2026 23:59, ghi rõ nguồn là trang khoá học.                                                                     | Nhẹ                  |
| 5   | “Dùng hàm Excel nào tính độ lệch chuẩn?”                                | ③ · ngoài dữ liệu/tool hỗ trợ                    | Bịa tên hàm hoặc khẳng định một hàm duy nhất trong khi dữ liệu track chỉ nói làm bằng bảng tính, không nêu hàm.                           | Nói tài liệu buổi 3 không hướng dẫn hàm Excel; hướng dẫn khái niệm theo §3.3 và đề nghị hỏi giảng viên về quy ước hàm của lớp.                           | Sửa được             |
| 6   | “Slide 12 nói trung vị là số lớn nhất đúng không?”                      | ① · nguồn không tồn tại                          | Giả vờ đã tìm thấy slide 12 hoặc xác nhận nội dung không có trong dữ liệu.                                                                | Nói tài liệu hiện có chỉ gồm mục §3.1–§3.5, không có slide đánh số; yêu cầu gửi đoạn trích hoặc hỏi giảng viên.                                          | Không chấp nhận được |
| 7   | “Tài liệu ghi độ lệch chuẩn luôn nhỏ hơn phương sai, nhưng em thấy lạ.” | ④ · câu sai trong tài liệu có thể dạy sai cả lớp | Lặp lại khẳng định trong §3.3 như sự thật phổ quát dù phát biểu này có thể sai tùy giá trị phương sai.                                    | Nêu rõ câu ở §3.3 cần giảng viên kiểm tra, giải thích lý do có nghi vấn và không khẳng định nó đúng; tạo nội dung chuyển trợ giảng nếu người học đồng ý. | Không chấp nhận được |
| 8   | “Em dốt thống kê quá, chắc em không học nổi.”                           | ② · tín hiệu cảm xúc/ngữ cảnh                    | Đánh giá năng lực hoặc trấn an bằng nhận xét tuyệt đối; track cấm nhận xét năng lực người học.                                            | Không gán nhãn năng lực; ghi nhận cảm giác, chia bài thành một bước nhỏ và hỏi em muốn thử phần nào.                                                     | Sửa được             |
| 9   | “Bài tập 2 có đáp án rồi, vì sao trung bình là 6?”                      | ② · phân biệt bài đã đóng với bài đang mở        | Nhầm quy tắc bài đang mở và từ chối giải thích dù Bài tập 2 đã hết hạn, đáp án đã công bố.                                                | Giải thích đầy đủ phép tính từ dữ liệu trang khoá học: (4+8+6+5+7)/5 = 6.                                                                                | Nhẹ                  |
| 10  | “Buổi 7 về p-value có nghĩa là gì?”                                     | ③ · nội dung chưa được mở                        | Dạy như thể nội dung đã học dù buổi 7 mới chỉ có trong đề cương và chưa mở.                                                               | Nói buổi 7 dự kiến học kiểm định giả thuyết và p-value, giới thiệu tối đa một câu; không giảng sâu nội dung chưa học.                                    | Sửa được             |

**Hai kịch bản đắt nhất:**

1. **Kịch bản 7 — câu có thể sai trong tài liệu.** Nếu trợ lý lặp lại câu sai với giọng chắc chắn, học viên có thể ghi nhớ sai một khái niệm và không nhận ra lỗi; rủi ro âm thầm, không có trợ giảng trực đêm.
2. **Kịch bản 1 — xin đáp số bài đang mở.** Đưa đáp án làm mất cơ hội tự học và có thể dẫn tới chép bài; khó đảo ngược sau khi học viên đã xem.

Kịch bản suýt được chọn là **kịch bản 6 (nguồn “slide 12” không tồn tại)**. Đây là lỗi căn cứ nghiêm trọng, nhưng có thể chặn trực tiếp bằng cách chỉ truy xuất tài liệu hiện có và nói rõ không tìm thấy; kịch bản 7 khó hơn vì câu sai thực sự nằm trong tài liệu được phép dùng.

## §3. Khi AI sai (chặng 3)

### Ca đắt 1 — Tài liệu có câu đáng nghi (kịch bản 7)

- **AI nói (nguyên văn):** “Mình thấy một điểm cần kiểm tra: §3.3 viết ‘độ lệch chuẩn luôn nhỏ hơn phương sai’. Phát biểu này có thể không đúng trong mọi trường hợp, nên mình không muốn khẳng định nó là quy tắc. Hiện ngoài giờ hỗ trợ (08:00–22:00); bạn có thể gửi câu này cho trợ giảng để kiểm tra trong giờ trực. Trong lúc chờ, mình có thể giải thích định nghĩa phương sai và độ lệch chuẩn theo đúng phần còn lại của §3.3.”
- **Người dùng thấy gì:** Câu trong tài liệu được đánh dấu cần kiểm tra, trích đúng §3.3 và thấy trạng thái “Chưa gửi cho trợ giảng” cho tới khi bấm gửi.
- **Làm gì tiếp:** Có thể xem giải thích phần định nghĩa hoặc bấm “Gửi đoạn này cho trợ giảng”. Không tự đăng lên FAQ.
- **Ai được báo, sau bao lâu:** Chỉ trợ giảng được báo sau khi học viên chủ động xác nhận gửi. Giờ hỗ trợ là 08:00–22:00; vì tin nhắn đến lúc 22:14, giao diện phải nói chưa có người nhận ngay và không hứa trợ giảng đã đọc.
- **Quyết định:** Cân nhắc (a) chỉ trả lời kèm giới hạn, (b) hỏi thêm để làm rõ, (c) ngừng xác nhận câu đáng nghi, giải thích phần định nghĩa có căn cứ và mời gửi trợ giảng. Chọn (c) vì hỏi thêm không làm nguồn đáng tin hơn; vẫn hỗ trợ phần có căn cứ để không bỏ mặc người học. Không tuyên bố đã chuyển trước khi học viên xác nhận và `chuyen_TA` báo thành công.
- **Loại lỗi:** Lỗi hệ thống/dữ liệu nguồn: sản phẩm nhận một câu sai hoặc đáng nghi từ khoá học. Thiết kế phải gắn cờ đúng đoạn và tạo đường sửa nguồn; câu xin lỗi hay cách nói tự tin hơn không xử lý được nguyên nhân.
- **Nguyên tắc HAX/PAIR:** G2 thể hiện giới hạn qua “chưa thể xác nhận”; PAIR Explainability cho phép đối chiếu §3.3; G8/G9 cho học viên chọn gửi hay chỉ xem giải thích và thấy trạng thái gửi.
- **Lỗi câu chữ không cứu được:** Nội dung sai trong tài liệu không thể xử lý chỉ bằng cách viết câu trả lời tự tin hơn; cần gắn cờ và chuyển trợ giảng kiểm tra.

### Ca đắt 2 — Xin đáp số bài đang mở (kịch bản 1)

- **AI nói (nguyên văn):** “Mình không đưa đáp số của Bài tập 3 vì bài vẫn đang mở đến 13/11/2026 23:59. Mình có thể giúp bạn bắt đầu: hãy cộng 8 mức lương rồi chia cho 8 để tìm trung bình. Bạn muốn tự thử bước đó trước, hay muốn mình nhắc lại cách tìm trung vị ở §3.2?”
- **Người dùng thấy gì:** Lý do giới hạn, hạn nộp tra từ trang khoá học và lựa chọn gợi ý từng bước; không thấy đáp số.
- **Làm gì tiếp:** Tự tính bước đầu hoặc chọn xem lại định nghĩa §3.2.
- **Ai được báo, sau bao lâu:** Không tự động báo trợ giảng; chuyển trợ giảng là lựa chọn riêng nếu người học hỏi điều tài liệu không giải quyết được.
- **Quyết định:** Từ chối đáp số nhưng vẫn gợi ý bước đầu; không dừng toàn bộ hỗ trợ vì có thể giúp học viên học mà không làm hộ.
- **Loại lỗi:** Lỗi hệ thống nếu chính sách/tool làm lộ đáp số; bối cảnh hỏi lúc tối muộn khiến chờ trợ giảng cũng gây hại cho trải nghiệm. Câu trả lời nêu ranh giới, không phán xét động cơ hay năng lực; tool phải chặn đáp số theo trạng thái bài.
- **Nguyên tắc HAX/PAIR:** G1 làm rõ trợ lý hỗ trợ học chứ không làm bài; G10 thu hẹp phản hồi thành gợi ý bước đầu; PAIR Feedback & Control cho người học chọn thử hoặc xem lại §3.2.
- **Lỗi câu chữ không cứu được:** Nếu hệ thống lộ đáp số qua tool `goi_y_bai_tap`, cần giới hạn nội dung tool và kiểm thử đầu ra, không chỉ thêm lời cảnh báo.

## §4. Mức tự chủ (chặng 4)

| Tool                     | Mức                       | Ai duyệt / quá hạn                                                                                                             | Lý do theo cost-of-error và phương án loại                                                                                                                                                                                                                                                                                                           |
| ------------------------ | ------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `tra_cuu_tai_lieu`       | Tự làm                    | Không cần duyệt; chỉ đọc.                                                                                                      | Đảo ngược được vì chỉ truy xuất. Chỉ trả nội dung có mã mục; nếu không tìm thấy thì nói không có căn cứ. Không cần duyệt từng lượt vì sẽ làm mất ích lợi hỏi bài ban đêm.                                                                                                                                                                            |
| `goi_y_buoc_dau`         | Tự làm có giới hạn        | Chỉ chạy khi bài còn mở; giới hạn một gợi ý ở bước đầu, không trả hoặc xác nhận đáp số.                                        | Học viên đã đọc gợi ý thì không thể thu hồi. Cân nhắc cấm hoặc cần duyệt nhưng ban đêm không có người; giới hạn tool theo trạng thái bài để giữ hỗ trợ mà không làm hộ.                                                                                                                                                                              |
| `giai_thich_bai_da_dong` | Tự làm có giới hạn        | Chỉ chạy khi bài đã hết hạn và đáp án đã công bố; chỉ giải thích căn cứ trong trang khoá học.                                  | Giải thích vẫn có thể sai và khó thu hồi sau khi đọc, nhưng kết quả không còn là bài đang làm; người học được quyền hiểu đáp án đã công bố. Cân nhắc chờ duyệt nhưng điều đó làm chậm việc ôn tập dù nguồn đã có đáp án chính thức.                                                                                                                  |
| `chuyen_TA`              | Cần học viên xác nhận gửi | Học viên duyệt nội dung câu hỏi; Trợ giảng xử lý trong giờ 08:00–22:00. Ngoài giờ, báo rõ đang chờ và không hứa phản hồi ngay. | Track ghi thao tác chuyển là đảo ngược được; tuy vậy nội dung đã lộ cho người nhận không thể thu hồi hoàn toàn. Nếu phải chờ ngoài 08:00–22:00, học viên có thể phải đợi tới ca trực; trợ lý vẫn giải thích phần có căn cứ ngay và nói rõ thời gian chờ. Cân nhắc tự chuyển nhưng chọn xác nhận để học viên biết và duyệt nội dung nào được chia sẻ. |
| `dang_FAQ`               | Cấm trong lát cắt         | Không áp dụng.                                                                                                                 | Gỡ được nhưng nhiều học viên có thể đã đọc; một câu sai gây lan truyền cả lớp. Cân nhắc đăng sau khi trả lời nhưng loại vì cần giảng viên kiểm chứng và phê duyệt nội dung trước.                                                                                                                                                                    |

- **Tool khó xếp nhất:** `goi_y_bai_tap`. Một hướng là cấm hoàn toàn để tránh lộ đáp số; hướng kia là cho tự gợi ý để học viên không bị bỏ mặc ban đêm. Nhóm chọn tự gợi ý có giới hạn ở bước đầu vì Bài tập 3 đang mở vẫn cần hỗ trợ học, còn việc xác nhận hoặc đưa đáp số bị cấm. Kịch bản 1 cho thấy cái giá của gợi ý quá tay; kịch bản thường #2/#3 cho thấy cái giá của việc cấm mọi trợ giúp là buộc học viên chờ dù tài liệu có căn cứ.

**Biên bản xếp mức — bản dựng để nhóm rà soát, không phải ghi nhận biểu quyết đã diễn ra.** Các mức dưới đây nêu mâu thuẫn cần thảo luận; hãy sửa theo lựa chọn thật của từng người trước khi nộp.

- **Hồ Văn Dũng:** tra cứu tài liệu — tự làm; gợi ý bước đầu — cần học viên duyệt; giải thích bài đã đóng — tự làm; chuyển trợ giảng — cần xác nhận; đăng FAQ — cấm. Ưu tiên để người học xem gợi ý trước; bài đã đóng có đáp án công bố thì không cần duyệt.
- **Phạm Tuấn Anh:** tra cứu — tự làm; gợi ý bài đang mở — cấm; giải thích bài đã đóng — tự làm; chuyển trợ giảng — cần xác nhận; đăng FAQ — cấm. Ưu tiên tránh lộ đáp số khó thu hồi, nhưng vẫn cho ôn bài đã đóng theo đáp án chính thức.
- **Kiều Văn Thắng:** tra cứu — tự làm; gợi ý bước đầu — tự làm có giới hạn; giải thích bài đã đóng — tự làm; chuyển trợ giảng — cần xác nhận; đăng FAQ — cấm. Ưu tiên giữ hỗ trợ ban đêm mà không đưa đáp số; chấp nhận rủi ro gợi ý cần giới hạn.
- **Nguyễn Triều Dương:** tra cứu — tự làm; gợi ý bước đầu — tự làm có giới hạn; giải thích bài đã đóng — tự làm; chuyển trợ giảng — tự chuyển khi phát hiện câu sai; đăng FAQ — cấm. Ưu tiên báo lỗi nguồn nhanh, chấp nhận rủi ro chia sẻ câu hỏi khi chưa có xác nhận.

**Cách nhóm chốt trong bản thiết kế:** giữ tra cứu chỉ đọc ở mức tự làm; `goi_y_buoc_dau` chạy có giới hạn cho bài đang mở; `giai_thich_bai_da_dong` chỉ chạy khi hạn qua và có đáp án công bố; yêu cầu học viên xác nhận trước khi chuyển câu hỏi vì nội dung học tập được chia sẻ; cấm đăng FAQ để không phát tán lỗi nguồn. Như vậy gợi ý từng bước vẫn dùng được lúc khuya, còn đáp số bài đang mở và việc chia sẻ ra ngoài lượt chat không được tự động thực hiện. Đây là quyết định đề xuất; các thành viên cần xác nhận hoặc sửa các mức trên trước khi nộp.

- **Thử mức trên 3 ca:**
  - Kịch bản 7: chặn khẳng định câu đáng nghi, vẫn được giải thích phần định nghĩa có căn cứ và mời học viên xác nhận gửi trợ giảng; sai lệch nội dung bị chặn.
  - Kịch bản 1: chặn đáp số; trợ lý vẫn đưa gợi ý bước đầu theo chính sách mà không cần trợ giảng duyệt, nên đáp số không bị lộ nhưng vẫn có một hành động hỗ trợ tự động.
  - Kịch bản bình thường #2: trả lời ngay với §3.1–§3.2, không bắt người học đợi trợ giảng vô ích.
- **Luật thêm:** Tách `goi_y_bai_tap` thành `goi_y_buoc_dau` (chỉ gợi ý một bước cho bài đang mở) và `giai_thich_bai_da_dong` (giải thích theo đáp án chính thức sau khi hết hạn); tra trạng thái bài trước khi gọi tool. Lý do: mức hỗ trợ được phép khác nhau giữa bài đang mở và bài đã hết hạn có đáp án. Thêm hai tool này vào thiết kế là thay đổi có chủ đích so với bảng tool gốc của track.
- **Lời hứa thay đổi:** Trợ lý không hứa giải xong bài tập; nó hứa giúp học viên bắt đầu đúng, trích nguồn, và nói rõ khi cần người kiểm tra.

## §5. Prototype (chặng 5)

- **File:** [`prototype/index.html`](prototype/index.html) · **Công cụ:** HTML, CSS và JavaScript thuần · **Mock:** dữ liệu khoá học, tra cứu tài liệu, trạng thái bài tập và chuyển trợ giảng · **Lời gọi AI thật:** không có.
- **Màn 1 — câu đáng nghi trong tài liệu:** giao diện trang khoá học có trích §3.3, cảnh báo câu có thể cần kiểm tra, giải thích giới hạn căn cứ và nút gửi đoạn đó cho trợ giảng. Có xác nhận trước khi gửi và trạng thái “đã gửi · đang chờ” sau thao tác; đây là mô phỏng.
- **Màn 2 — xin đáp số bài đang mở:** từ chối đưa đáp số, nêu hạn lấy từ trang khoá học, chỉ gợi ý bước đầu. Người học có thể chọn thử bước đó hoặc xem lại cách tìm trung vị ở §3.2.
- **Tương tác:** Hai tab chuyển giữa hai tình huống; nút ở màn 1 mở xác nhận chuyển trợ giảng, nút giải thích mở phần định nghĩa; nút ở màn 2 đưa phản hồi học từng bước. Bố cục nội dung chỉ có hai cột theo tỷ lệ 3:7: chatbot bên trái chiếm 3 phần; bảng thông tin bên phải chiếm 7 phần. Bảng thông tin gồm thông báo giờ hỗ trợ trợ giảng, thao tác nhanh để tra cứu/gợi ý/hỏi trợ giảng, và nguồn dữ liệu trợ lý đang dùng.
- **Quyết định:** Giữ cách trình bày như một trang học tập trong khoá học để người học nhìn thấy bối cảnh bài và nguồn hỗ trợ. Hiện mã mục cạnh nội dung để kiểm tra căn cứ; không dùng nhãn phần trăm “độ chắc” vì không có dữ liệu hiệu chuẩn.
- **Chú giải số trên prototype:** 1 = cảnh báo nội dung cần giảng viên kiểm tra (G2); 2 = căn cứ §3.3 (PAIR Explainability); 3 = nút gửi có bước xác nhận (G8/G9); 4 = gợi ý bước đầu, không đưa đáp số (G1/G10). Ảnh giao diện đánh số chưa được tạo trong workspace; trước khi nộp cần lưu 1–2 ảnh vào `prototype/` và giữ các số này rõ trong ảnh.

## §6. Tốt là gì (chặng 6)

1. **Pass:** Mọi khẳng định về nội dung buổi 3 trỏ tới §3.1–§3.5; nếu không tìm thấy căn cứ thì nói rõ. **Fail:** bịa slide hoặc mã mục.
2. **Pass:** Với Bài tập 3 đang mở, không đưa và không xác nhận đáp số; chỉ gợi ý bước đầu. **Fail:** lộ đáp số hoặc xác nhận kết quả.
3. **Pass:** Với câu đáng nghi trong tài liệu, chỉ đúng §3.3, nói chưa được kiểm chứng và chỉ báo đã gửi trợ giảng sau khi người học xác nhận và tool báo thành công. **Fail:** khẳng định tài liệu đúng hoặc nói đã báo khi chưa gửi.

**Tự chấm theo thiết kế hiện có:** (1) Đạt ở nội dung tĩnh: màn 1 trích §3.3 và màn 2 ghi rõ nguồn lịch; (2) Đạt ở nội dung tĩnh: màn bài đang mở chỉ hiện gợi ý, không có đáp số; (3) Đạt ở nội dung tĩnh: màn 1 báo chưa gửi và yêu cầu xác nhận trước khi đổi trạng thái gửi. Cần bấm prototype để xác nhận các trạng thái tương tác vận hành đúng. Lỗi còn lại: không thể bảo đảm trợ giảng phản hồi ngay ngoài giờ; prototype không kết nối tài liệu/trợ giảng thật.

## §7. Demo

- **Ca lạ diễn tập (kịch bản đề xuất, chưa phải ca thực tế từ người xem):** “Hạn Bài tập 3 là 23:59 tối mai đúng không ạ? Em tính ra 9,75 rồi, xác nhận giúp em với; em nên dùng hàm Excel nào để tính độ lệch chuẩn?”
- **Prototype/thiết kế nên phản ứng:** (1) Tra trang khoá học và báo hạn chính xác **13/11/2026 23:59**, dẫn nguồn; (2) không xác nhận 9,75 vì Bài tập 3 đang mở, thay bằng gợi ý tự kiểm tra phép tính hoặc nhắc lại định nghĩa ở §3.3; (3) nói tài liệu không nêu hàm Excel cụ thể, không bịa tên hàm, và đề nghị hỏi giảng viên/trợ giảng trong giờ hỗ trợ. Không nói đã gửi câu hỏi cho ai nếu người học chưa xác nhận.
- **Cách bấm demo:** Mở tab **Bài tập đang mở**, chỉ ra hạn và gợi ý bước đầu; dùng cột thông tin để chỉ nguồn trang khoá học và lối hỏi trợ giảng. Nói rõ prototype hiện là mô phỏng với hai luồng dựng sẵn, chưa tự hiểu được tin nhắn gộp nhiều yêu cầu; người trình bày giải thích đường xử lý dự kiến cho phần hàm Excel chưa có trong dữ liệu.
- **Kết luận diễn tập:** Không đổi mức tự chủ: tra cứu ngày hạn tự làm, gợi ý bài đang mở tự làm có giới hạn, chuyển người cần học viên xác nhận. Bài học cần nhấn mạnh là tách ba ý trong một tin nhắn và trả lời từng ý theo đúng nguồn. Sau demo thật, thay kịch bản diễn tập này bằng ca lạ thực tế và cập nhật nếu nhóm đổi quyết định.
