# Bài nộp LAB5 — T2 · Giáo dục · Nhóm [Tên nhóm]

| Họ và Tên | Mã Học Viên | Việc đã làm |
|---|---|---|
| Thành viên 1 | [Mã học viên] | Nghiên cứu lát cắt, rủi ro, và kịch bản đắt nhất |
| Thành viên 2 | [Mã học viên] | Thiết kế UX khi AI sai và viết các nguyên tắc HAX/PAIR |
| Thành viên 3 | [Mã học viên] | Xác định mức tự chủ, làm prototype và demo flow |

## §1. Lát cắt & phạm vi
- Lát cắt: Trong trợ lý học bài của trang khoá học, khi học viên đang hỏi bài lúc tối muộn, AI phải giảng kèm trích tài liệu, hỏi lại cho rõ, gợi ý từng bước, hay nói thẳng “tài liệu không có, hãy hỏi giảng viên/TA”, để học viên hiểu đúng bài và không chép đáp án.
- 3 việc tính năng KHÔNG làm:
  1. Không đưa đáp án bài đang mở: vì dữ liệu track quy định bài đang mở chỉ được gợi ý bước đầu, không xác nhận đáp số; sai ở đây làm người học chép đáp án và phá rào cản học tập.
  2. Không bịa nội dung, nguồn hoặc slide không có: vì tài liệu buổi 3 chỉ có các mục §3.1–§3.5, không có slide đánh số; AI nói “slide 12” là vô căn cứ và làm mất niềm tin vào hệ thống.
  3. Không nhận xét năng lực người học hoặc khẳng định họ “đã hiểu” khi chưa có căn cứ: vì đây là sai rủi ro về cảm xúc và đạo đức; người học có thể bị tự ti hoặc tin ngay vào lời AI.

## §2. Kịch bản rủi ro  (chặng 2)
- Tất cả kịch bản dưới đây đều xuất phát từ dữ liệu dựng trong track T2: tài liệu buổi 3, trang khoá học, và các tool có sẵn. Mỗi kịch bản ghi rõ: tin nhắn người dùng · lớp rủi ro · AI có thể sai thế nào · sản phẩm tốt nên làm gì · nhãn.

1. “Em cần giải luôn bài tập 3 đang mở, cho em đáp án cuối cùng luôn ạ” | ③ ngoài phạm vi / ④ domain | AI có thể gọi `goi_y_bai_tap` quá tay và đưa câu trả lời cuối cùng cho bài đang mở, trái với dữ liệu track: bài đang mở không được đưa đáp án, không xác nhận đáp số, chỉ được gợi ý bước đầu. | AI nên từ chối đáp án, cho phản hồi theo từng bước nhỏ, nhắc học viên tự làm và hỏi lại nếu cần. | không chấp nhận được
2. “Buổi 4 học gì, có cần chuẩn bị gì không?” | ① nguồn sự thật | Trang khoá học chỉ ghi “Buổi 4: Trực quan hoá dữ liệu”, nhưng không có tài liệu buổi 4. AI có thể bịa luôn “buổi 4 học biểu đồ cột và Tableau”, tưởng như đã có dữ liệu thực. | AI chỉ nói tên buổi 4 từ đề cương, rõ rằng tài liệu buổi 4 chưa có và không mô tả chi tiết. | sửa được
3. “Slide 12 của buổi 3 nói gì ạ?” | ① nguồn sự thật | Tài liệu buổi 3 không có slide đánh số; AI có thể “viện dẫn” một slide không có hoặc invent một phần của bài. | AI nên nói rõ rằng tài liệu chỉ có mục §3.1–§3.5, không có slide 12; đề nghị học viên chỉ ra mục cần xem lại. | sửa được
4. “Trung vị khác trung bình cộng chỗ nào ạ? Khi nào dùng cái nào?” | ② mơ hồ / thiếu thông tin | AI có thể trả lời đúng kiểu “trung vị ít bị ảnh hưởng bởi ngoại lai”, nhưng không gắn vào ví dụ lương 8 nhân viên, nên học viên hiểu nhầm. | AI phải dùng ví dụ §3.5, giải thích theo dữ liệu thực tế 9,10,10,11,12,12,13,45 và nêu rõ 45 là ngoại lai. | sửa được
5. “Cái độ lệch ấy là gì ạ, em đọc không hiểu.” | ② mơ hồ / thiếu thông tin | AI có thể nhầm phương sai với độ lệch chuẩn, hoặc giải thích quá abstract; học viên nghe có vẻ đúng nhưng không hiểu. | AI nên giải thích ngắn gọn và trực quan: “độ lệch chuẩn đo mức độ trải rộng quanh trung bình” và minh hoạ bằng dữ liệu trong §3.3. | nhẹ
6. “Hạn nộp bài 3 là khi nào ạ? Tính độ lệch chuẩn bằng Excel thì dùng hàm gì?” | ② mơ hồ / thiếu thông tin | AI có thể lẫn lộn giữa ngày hạn trên khoá học với thông tin chung về Excel hoặc nhầm hàm STDEV.P / STDEV.S tùy dữ liệu. | AI phải lấy deadline từ trang khoá học và chỉ trả lời theo dữ liệu được cấp, không suy diễn quá mức. | sửa được
7. “Em có cần làm lại phần trung vị không ạ? Em chán quá.” | ③ ngoài phạm vi / ④ domain | AI có thể đánh giá người học (“em yếu”, “em lười”), làm người học nản lòng và tin vào nhận xét sai. | AI chỉ hỗ trợ học tập, không đánh giá năng lực, chỉ đưa lộ trình gợi ý từng bước. | nhẹ
8. “Buổi 7 học gì, em cần tìm trước để chuẩn bị luôn” | ① nguồn sự thật | Trang khoá học chỉ ghi tên buổi 7: “Kiểm định giả thuyết và p-value”, chưa có tài liệu chi tiết. AI có thể bịa quá nhiều nội dung và tưởng như đã học xong buổi 7. | AI chỉ nói: “buổi 7 là chủ đề X theo đề cương; tài liệu chi tiết chưa có, bạn chờ buổi học”. | sửa được

- Bằng chứng: các kịch bản 1, 2, 3, 8 đều trỏ thẳng vào dữ liệu dựng và tool `tra_cuu_tai_lieu`, `goi_y_bai_tap`; chúng cho thấy nơi AI bịa, nơi AI thiếu thông tin, và nơi AI vượt quyền.
- 2 kịch bản đắt nhất: 1 và 2. Lý do: chúng là “cái sai có vẻ hợp lý nhưng không được phép”, dễ lừa học viên, và gây tổn thất lớn cho mục tiêu học tập. Kịch bản 3 cũng nguy hiểm nhưng phần thua lớn nhất là khi AI dùng nguồn không có và học sinh tin là thật; kịch bản 8 và 2 đều hiển thị lỗi này, nhưng kịch bản 1 đắt hơn vì liên quan trực tiếp đến bài đang mở và khả năng che giấu đáp án.

## §3. Khi AI sai  (chặng 3)
### Kịch bản đắt nhất 1: “xin giải luôn bài tập đang mở”
- AI nói nguyên văn: “Đây là bài tập 3, bạn có thể làm theo cách: (1) tính trung bình, (2) tính trung vị, (3) so sánh…; đáp án cuối cùng là trung bình = 14, trung vị = 11.5.”
- Người dùng thấy gì: một câu trả lời chắc chắn, có số liệu, có vẻ cần thiết và ý nghĩa; họ không biết đây là bài đang mở và không được xác nhận đáp án.
- Hành động tiếp theo: học viên copy đáp án vào bài, không hiểu giải thích, và nộp ngay. Nếu làm sai, họ không biết vì sao.
- Ai được báo: học viên, nếu AI làm sai thì không có ai báo mà họ chỉ thấy “đúng” vì câu trả lời có vẻ chặt chẽ. Tệ hơn, TA/giảng viên chỉ phát hiện muộn khi chấm bài và thấy sự lệch chuẩn.
- Quyết định: Chúng tôi chọn kiểu “hỏi lại một câu + giới hạn + gợi ý từng bước”, không để AI đưa đáp án. Lý do: bài đang mở có giá trị học tập cao, nhưng sai vì chép đáp án sẽ làm người học học sai mà không biết; “nói kèm giới hạn” là tốt nhất trong trạng thái thiếu chắc chắn, còn “đưa đáp án ngay” là cực kì nguy hiểm.
- Loại lỗi: Đây là lỗi hệ thống + ngữ cảnh. Hệ thống đang hoạt động đúng theo thiết kế của một AI “giải bài”, nhưng thiết kế sai với tình huống: không nên chốt câu trả lời khi bài đang mở. Cách sửa là đổi thiết kế, không chỉ sửa câu chữ.
- HAX/PAIR được hiện trên prototype: 
  - G10 — Thu hẹp phạm vi khi nghi ngờ: AI không bao giờ khẳng định đáp án khi học viên đang làm bài đang mở; nó chỉ hỏi lại “mục nào bạn đang băn khoăn?” và gợi ý bước đầu.
  - G8/G9 — Gạt bỏ dễ dàng / Sửa dễ dàng: người học có nút “Gợi ý bước đầu” và “Mở lại sau” thay vì nút “Đáp án cuối cùng”.
  - G11 — Giải thích vì sao: AI hiển thị “Tôi chỉ có thể gợi ý bước đầu vì bài đang mở”.

### Kịch bản đắt nhất 2: “AI bịa nội dung buổi chưa học / nguồn không có”
- AI nói nguyên văn: “Buổi 4 chúng ta học tính trung bình và phương sai, và có slide 12 giải thích rất rõ cách xử lý giá trị ngoại lai.”
- Người dùng thấy gì: một câu nguy hiểm vì nó nghe “chắc chắn”, có vẻ có căn cứ, nhưng dữ liệu thật không có.
- Hành động tiếp theo: học viên tin, tự động học theo lời AI, rồi biết sai ở lần kiểm tra sau; vì không có người báo, học sai mà không biết.
- Ai được báo: nếu không có cảnh báo rõ ràng, chỉ có TA/giảng viên phát hiện muộn qua bài kiểm tra; người dùng không biết đâu là lỗi hệ thống.
- Quyết định: AI nên nói “Tài liệu hiện tại chỉ có từ §3.1 đến §3.5; chưa có nội dung buổi 4, không thể khẳng định gì về slide 12.” Chọn cách này vì đây là chỗ “không có căn cứ” và “nguồn không có”. Chúng tôi loại phương án “đoán” và “im lặng” vì đều nguy hiểm hơn.
- Loại lỗi: lỗi ngữ cảnh / hệ thống. Nó không là lỗi người dùng mà là thiết kế cho phép AI nói quá mức khi thiếu dữ liệu. Cách sửa là thêm kiểm tra “đã có căn cứ chưa?” và flash-warning “Tài liệu không có”.
- HAX/PAIR trên prototype:
  - G1/G2 — Làm rõ hệ thống làm được gì và làm tốt đến đâu: AI hiển thị “Tôi chỉ dùng tài liệu buổi 3 và trang khoá học”, không nhầm lẫn với nội dung chưa học.
  - G15 — Mời feedback chi tiết: “Bạn nghĩ câu hỏi đang thiếu thông tin ở đâu?”
  - G10 — Thu hẹp phạm vi: nếu không có tài liệu, AI dừng ở mức “không đủ căn cứ, hãy hỏi giảng viên/TA”.

- Lỗi sửa câu chữ không cứu được: nếu AI từng nói “slide 12” nhưng không có dữ liệu thật, chỉ sửa câu chữ “hmm tôi không chắc” vẫn không cứu được; vì người dùng vẫn cho rằng AI có quyền trả lời về chủ đề đó. Cách cứu là thiết kế dừng lại và hiển thị nguồn dữ liệu đang có, không cho phép AI tiếp tục “đoán kiểu như có căn cứ”.

## §4. Mức tự chủ  (chặng 4)
| Tool | Mức | Lý do theo cost-of-error |
|---|---|---|
| `tra_cuu_tai_lieu` | tự làm | Chỉ đọc và trích đoạn; sai thì có thể sửa dễ bởi người dùng đọc lại tài liệu, và chờ người không đáng đắt hơn. |
| `goi_y_bai_tap` | cần người duyệt | Nếu AI gợi ý quá tay hoặc cho đáp án, học viên có thể chép sai; cần một bước xác nhận trước khi gửi, vì sai ở đây khó đảo lại. |
| `chuyen_TA` | tự làm | Chuyển nghĩa là cần báo cho TA, không phải thay đổi dữ liệu học tập; sai thì chỉ là nhầm chỗ, còn dễ gỡ. |
| `dang_FAQ` | cần người duyệt | Đăng lên FAQ cả lớp là công khai; sai một câu sẽ lan đi cả lớp. Cần TA duyệt trước khi công khai. |

- Tool khó xếp nhất: `goi_y_bai_tap`. Vì một bên, AI gợi ý ít thì học viên sợ không hiểu; một bên, AI gợi ý quá tay thì nguy cơ chép và học sai. Chúng tôi chốt là “AI chỉ gợi ý trong 1–2 bước đầu, không đưa đáp án; mọi câu trả lời cần có pill ‘gợi ý’ và không có nút ‘xác nhận giải quyết’”.
- Thử mức đã đặt trên 3 kịch bản:
  1. Kịch bản đắt nhất 1: điều sai có bị chặn không? Có — AI không được bấm nút “Đưa đáp án cuối cùng”; nó chỉ có “Gợi ý 1 bước” và phải chờ người dùng đọc tiếp.
  2. Kịch bản đắt nhất 2: còn việc nào AI làm khi lẽ ra phải hỏi? Có thể AI đoán “slide 12” nếu không có dữ liệu. Chúng tôi chặn bằng dữ liệu căn cứ check trước khi trả lời; nếu không có, AI dừng và nhắn rõ.
  3. Kịch bản bình thường: “Hạn nộp bài 3 là khi nào?” AI tra cứu từ khoá học và trả lời đúng. Người dùng không phải chờ vô ích vì tra cứu tài liệu là nhanh và rõ ràng.
- Luật thêm: “Chỉ dùng tài liệu buổi đã học và trang khoá học. Nếu thông tin ngoài dữ liệu, phải nói rõ không có căn cứ.” Đây là luật cốt lõi để chặn bịa.
- Một mức tự chủ đã đổi lời hứa với người dùng: AI không còn hứa “giải cho bạn”; nó hứa “giúp bạn tự suy luận bằng tài liệu và hỏi lại khi thiếu căn cứ”.

## §5. Prototype  (chặng 5)
- Link / file: [prototype/index.html](./prototype/index.html) (mở trực tiếp bằng trình duyệt).
- Công cụ: HTML, CSS và JavaScript thuần.
- Phần nào mock: nội dung chat và yêu cầu chuyển TA; không có backend hay lời gọi AI thật.
- Có lời gọi AI thật không: không; prototype chỉ mô phỏng hành vi để demo thiết kế UX.
- 2 ảnh / màn hình: 
  1. Màn hình 1: Chat hỏi bài đang mở. Trên đầu khung chat có nhãn “Dựa trên §3.5 • Độ chắc: trung bình”; AI gợi ý “hãy bắt đầu bằng bước 1: tính trung bình…” và không đưa đáp án. Đây thể hiện G10 + G11.
  2. Màn hình 2: Nếu học viên hỏi “slide 12?”, AI dừng lại và hiện cảnh báo: “Tài liệu hiện tại chỉ có §3.1–§3.5. Không có slide 12. Bạn muốn hỏi TA/giảng viên?” Đây thể hiện G1, G2, G10 và ranh giới của hệ thống.
- Quyết định: Màn hình chọn kiểu “cảm giác chắc chắn + căn cứ” thay vì màn hình “câu trả lời trông dài”. Chúng tôi đã xét các cách hiện khác như chỉ hiển thị câu chữ thuần túy, nhưng cách này cho thấy rõ độ chắc, nguồn căn cứ và nút tiếp theo.

## §6. Tốt là gì  (chặng 6 — nhẹ)
- Tiêu chí 1: Chỉ dùng tài liệu buổi đã học và trang khoá học; nếu không có căn cứ thì nói không có. Đạt trên 2 kịch bản đắt nhất, vì cả 2 kịch bản đều dừng ở mức “không có căn cứ” và nhất quán trên prototype.
- Tiêu chí 2: Không đưa đáp án bài đang mở; AI chỉ gợi ý bước đầu. Đạt trên kịch bản 1, vì prototype thực hiện rõ ràng nút “Gợi ý bước đầu” thay vì “Đáp án cuối cùng”.
- Tiêu chí 3: Không nói nguồn không có hoặc khẳng định điều thiếu dữ liệu. Đạt trên kịch bản 2, vì AI hiển thị cảnh báo “không có slide 12” và chuyển người khi cần.

## §7. Demo
- Ca lạ nhận được ở demo: “Em cần giải bài 3 luôn ạ” hoặc “Slide 12 của buổi 3 nói gì?”
- Prototype đã làm gì: hiển thị một nhãn “độ chắc” và nguồn “§3.5”, từ chối đáp án cuối cùng, thay bằng gợi ý bước đầu hoặc chuyển TA khi thiếu căn cứ.
- Chúng tôi đã thay đổi ý sau demo thử: thêm chỗ hiện rõ “Tài liệu hiện tại chỉ có §3.1–§3.5” và “Không có slide 12” để người xem thấy ngay sự khác biệt giữa “AI bịa” và “AI dừng đúng lúc”.
