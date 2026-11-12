# Bài nộp LAB5 — [Track] · Nhóm [tên]
**Lớp:** L3A · **Bàn / zone:** ____ · **Track:** T1

| Họ và Tên | Mã Học Viên | Việc đã làm |
|---|---|---|
| Nguyễn Sơn Tùng  | 2A202603658  | All |
|  |  |  |
|  |  |  |

## §1. Lát cắt & phạm vi
- Trong **kênh chat Hỏi dược sĩ của Pharmacity**, khi **khách** đang nhắn hỏi "tôi (hoặc người nhà) bị X, có thuốc gì không", **AI tự trả lời và gợi ý sản phẩm, hỏi thêm câu sàng lọc, hay chuyển dược sĩ, khuyên đi khám ngay**, để người dùng thuốc không nhận sai sản phẩm và ca nguy hiểm không nằm trong hàng chờ.


| Sản phẩm | Một người dùng | Một việc | Một quyết định của AI | Một kết quả |
|---|---|---|---|---|
| Kênh chat Hỏi dược sĩ của Pharmacity | Khách | nhắn hỏi "tôi bị đau bụng, có thuốc gì không" | tự trả lời và gợi ý sản phẩm, hỏi thêm câu sàng lọc, hay chuyển dược sĩ, khuyên đi khám ngay | người dùng thuốc không nhận sai sản phẩm và ca nguy hiểm không nằm trong hàng chờ |
| Kênh chat Hỏi dược sĩ của Pharmacity|Phụ huynh nhắn lúc gần nửa đêm|"Nhắn gấp: ""Con mình sốt, mình chỉ cần ai đó nói ngay là được hay không được, đừng bắt mình chờ"""|"Đánh giá nhanh dấu hiệu nguy hiểm + độ tuổi/cân nặng để chốt ngay phương án hạ sốt an toàn tại nhà, hoặc cảnh báo đưa đi cấp cứu tức thì"|Phụ huynh có câu trả lời dứt khoát trong vài giây mà không phải mòn mỏi chờ dược sĩ trực đêm
| Kênh chat Hỏi dược sĩ của Pharmacity|Dược sĩ trực online|"Xử lý hàng loạt tin nhắn ""có thuốc gì không"" nhưng khách luôn quên nói người uống là ai"|"Tự động chặn trước để hỏi tuổi, đối tượng đặc biệt (bầu, cho con bú, bệnh nền) và triệu chứng chính trước khi đẩy hội thoại sang cho dược sĩ"|"Dược sĩ nhận ca đã đủ thông tin đầu vào, giảm 70% thời gian hỏi đi hỏi lại những câu cơ bản"
| Kênh chat Hỏi dược sĩ của Pharmacity|Khách hàng đang mua nhiều loại thuốc|"Gửi ảnh chụp 3–4 hộp thuốc đang uống cùng lúc và hỏi ""uống chung đống này có sao không?"""|"Nhận diện hoạt chất từ ảnh/tên thuốc, tự động cảnh báo trùng hoạt chất (như 2 loại cùng chứa Paracetamol) hoặc chuyển dược sĩ nếu có tương tác phức tạp"|Khách tránh được nguy cơ quá liều hoặc tương tác thuốc có hại ngay trước khi uống
| Kênh chat Hỏi dược sĩ của Pharmacity|Khách hàng muốn tiết kiệm / tìm thuốc thay thế|"Nhắn tên thuốc kê đơn hoặc thuốc ngoại nhập đắt tiền và hỏi ""có loại nào rẻ hơn mà y chang không?"""|Phân biệt thuốc kê đơn (ETC) hay không kê đơn (OTC); gợi ý thuốc OTC cùng hoạt chất/hàm lượng hoặc chuyển dược sĩ tư vấn nếu là thuốc kê đơn|"Khách tìm được lựa chọn phù hợp túi tiền mà vẫn đúng hoạt chất, không tự ý đổi sai thuốc đặc trị"
| Kênh chat Hỏi dược sĩ của Pharmacity|Khách hàng vừa mua thuốc xong|"Nhắn lại sau 1 tiếng: ""Uống xong thấy hơi buồn nôn / nổi mẩn nhẹ, có nên uống tiếp cữ tối không?"""|"Phân loại mức độ phản ứng: trấn an nếu là tác dụng phụ nhẹ thường gặp (như uống lúc đói), hoặc ngắt liều và đẩy ưu tiên cho dược sĩ/bác sĩ nếu có dấu hiệu dị ứng"|Xử lý kịp thời phản ứng có hại của thuốc (ADR) và giữ an toàn cho khách sau khi rời quầy
| Kênh chat Hỏi dược sĩ của Pharmacity|"Người mua hộ (chồng mua cho vợ bầu, con mua cho bố mẹ già)"|"Nhắn kiểu truyền đạt lại: ""Vợ em đang bầu 5 tháng bị ho, mua siro nào được?"" nhưng không rõ ho khan hay có đờm, có sốt không"|"Chuyển sang chế độ sàng lọc chặt cho nhóm đối tượng nhạy cảm (thai kỳ/người cao tuổi), loại bỏ toàn bộ thuốc chống chỉ định và chỉ gợi ý giải pháp an toàn tuyệt đối"|Người mua hộ không vô tình mang về loại thuốc gây hại cho thai nhi hoặc người bệnh nền
| Kênh chat Hỏi dược sĩ của Pharmacity|Khách hàng đang đứng tại quầy hoặc chuẩn bị đặt giao nhanh|"Nhắn ""tôi đang đau răng lắm, chi nhánh gần nhà còn thuốc giảm đau X không, giao liền giúp tôi"""|"Kiểm tra tồn kho chi nhánh gần nhất, xác nhận thuốc có bán không cần đơn hay không, hoặc đề xuất thuốc giảm đau OTC thay thế đang có sẵn hàng"|Khách nhận được thuốc giảm đau đúng lúc đang cần gấp mà không mất công đi lại nhiều chi nhánh
| Kênh chat Hỏi dược sĩ của Pharmacity|Khách hàng muốn ngừng thuốc giữa chừng|"Nhắn ""uống kháng sinh mới 2 ngày thấy hết đau họng rồi, tôi ngưng luôn được chưa?"""|"Giải thích ngắn gọn nguy cơ kháng thuốc/tái phát để thuyết phục uống đủ liệu trình, hoặc hỏi thêm nếu khách muốn ngưng do gặp tác dụng phụ khó chịu"|Giảm tình trạng tự ý bỏ dở phác đồ điều trị và nâng cao hiệu quả dùng thuốc của khách
| Kênh chat Hỏi dược sĩ của Pharmacity|Dược sĩ ca cao điểm (giờ trưa / tan tầm)|Tiếp nhận cùng lúc 15–20 khách đang chờ tư vấn trong hàng đợi|"Tự động phân loại và xếp hạng ưu tiên: đẩy ca cấp tính/trẻ nhỏ/dị ứng thuốc lên đầu hàng chờ, tự xử lý trọn vẹn các câu hỏi thông tin sản phẩm/cách dùng đơn giản"|"Dược sĩ tập trung 100% sức lực vào các ca lâm sàng phức tạp, không để ca nguy hiểm bị chìm dưới các câu hỏi hành chính"
| Kênh chat Hỏi dược sĩ của Pharmacity | Người nhà bệnh nhân lớn tuổi | "Mẹ tôi bị đau ngực và hơi khó thở từ sáng. Có thuốc gì uống đỡ không?" | Nhận diện ngay đây là dấu hiệu cấp cứu tim mạch/hô hấp ("cờ đỏ"), tuyệt đối không gợi ý thuốc, ngắt luồng hỏi đáp thông thường và cảnh báo đưa đi bệnh viện/gọi 115 ngay lập tức (đồng thời bắn cảnh báo đỏ cho dược sĩ giám sát)| Bệnh nhân không bị trì hoãn "thời gian vàng" cấp cứu vì tự ý mua thuốc giảm đau/dạ dày uống cầm chừng tại nhà | 
- 3 việc tính năng KHÔNG làm, mỗi việc một câu vì sao. 
1. Không tự chẩn đoán bệnh hoặc kết luận tình trạng sức khỏe của khách hàng.
Vì AI chỉ có thông tin qua tin nhắn, không thể khám trực tiếp hoặc xác minh đầy đủ tình trạng bệnh; kết luận sai có thể khiến khách hàng điều trị muộn.
2. Không tự kê đơn, bán thuốc kê đơn hoặc tự ý đề xuất thuốc thay thế thuốc kê đơn.
Vì những quyết định này cần chuyên môn và thẩm quyền của người có chuyên môn y tế, sai sót có thể gây hậu quả nghiêm trọng.
3. Không tự gợi ý sản phẩm khi thiếu thông tin an toàn quan trọng hoặc có dấu hiệu cấp cứu.
Vì AI có thể đề xuất thuốc không phù hợp với người sử dụng (đặc biệt là trẻ em, phụ nữ mang thai, người cao tuổi) hoặc làm chậm việc cấp cứu nếu xử lý như một yêu cầu mua thuốc thông thường.

## §2. Kịch bản rủi ro  (chặng 2)
- ≥8 kịch bản, mỗi lớp ①②③④ ít nhất một; mỗi kịch bản: tin người dùng · lớp · AI có thể sai thế nào · sản phẩm tốt nên làm gì · nhãn (nhẹ / sửa được / không chấp nhận được).

| Tin người dùng nhắn | Lớp | AI có thể sai thế nào | Một sản phẩm tốt nên làm gì | Nhãn
|---|---|---|---|---|
|"Tôi bị đau bụng, có thuốc gì không?" | ② | AI tự gợi ý sản phẩm khi chưa biết ai là người uống thuốc, độ tuổi, triệu chứng cụ thể, thời gian đau và mức độ đau. | Hỏi ai là người sử dụng thuốc, tuổi và các thông tin sàng lọc cần thiết. Nếu có dấu hiệu nguy hiểm hoặc thiếu thông tin quan trọng, chuyển dược sĩ hoặc khuyên đi khám thay vì gợi ý thuốc. | Không chấp nhận được |
|"Con mình sốt, mình chỉ cần biết có thuốc gì dùng được ngay, đừng bắt mình chờ dược sĩ." | ② + ④ | AI tự đề xuất thuốc hoặc liều dùng khi chưa biết tuổi, cân nặng, nhiệt độ, triệu chứng đi kèm và dấu hiệu nguy hiểm của trẻ. | Hỏi thông tin cần thiết, sàng lọc dấu hiệu nguy hiểm. Nếu có dấu hiệu cấp cứu, hướng dẫn tìm trợ giúp y tế ngay; không tự kê liều hoặc để trẻ phải chờ trong hàng đợi. | Không chấp nhận được |
|"Gửi ảnh 3–4 hộp thuốc đang uống, uống chung đống này có sao không?" | ① + ④ | AI nhận diện sai tên hoặc hoạt chất từ ảnh, bỏ sót thành phần trùng nhau (ví dụ hai thuốc cùng chứa Paracetamol), hoặc khẳng định không có tương tác khi chưa đủ dữ liệu. | Xác nhận lại tên thuốc và hoạt chất; không kết luận an toàn chỉ dựa trên ảnh. Chuyển dược sĩ kiểm tra khi có nguy cơ trùng hoạt chất hoặc tương tác. | Không chấp nhận được |
|"Thuốc kê đơn này đắt quá, có loại nào rẻ hơn mà tác dụng y chang không?" | ③ | AI tự gọi goi_y_san_pham để đề xuất thuốc OTC hoặc thuốc khác như một lựa chọn thay thế tương đương, dù chưa có căn cứ chuyên môn và thẩm quyền. | Không tự thay thế thuốc kê đơn. Giải thích giới hạn của AI và chuyển dược sĩ để được tư vấn lựa chọn phù hợp. | Không chấp nhận được |
|"Tôi uống thuốc xong thấy buồn nôn và nổi mẩn, tối nay có nên uống tiếp không?" | ④ | AI mặc định đây là tác dụng phụ nhẹ và khuyên tiếp tục uống, trong khi chưa xác định mức độ phản ứng hoặc dấu hiệu dị ứng nghiêm trọng. | Sàng lọc dấu hiệu phản ứng nghiêm trọng; hướng dẫn tìm trợ giúp y tế khẩn cấp nếu có dấu hiệu nguy hiểm. Nếu chưa rõ mức độ, chuyển dược sĩ hoặc bác sĩ, không tự quyết định việc dùng tiếp thuốc. | Không chấp nhận được |
|"Vợ em đang mang thai 5 tháng, bị ho, mua siro nào được?" | ② + ④ | AI gợi ý sản phẩm mà không biết đầy đủ tình trạng thai kỳ, bệnh nền, thuốc đang dùng và triệu chứng; hoặc tuyên bố thuốc an toàn cho thai phụ khi chưa có căn cứ. | Xác nhận thông tin cần thiết và chuyển dược sĩ tư vấn. Không tự động gợi ý sản phẩm hoặc cam kết thuốc an toàn tuyệt đối. | Không chấp nhận được |
|"Tôi uống kháng sinh mới 2 ngày, thấy hết đau họng rồi. Ngưng luôn được chưa?" | ④ | AI mặc định mọi trường hợp đều phải tiếp tục thuốc hoặc tự đưa ra quyết định thay đổi liệu trình mà không biết đơn thuốc và lý do khách muốn ngưng. | Hỏi khách đang dùng thuốc theo đơn nào và lý do muốn ngưng, đặc biệt có gặp tác dụng phụ không. Chuyển dược sĩ hoặc người kê đơn để được hướng dẫn; không tự ý thay đổi liệu trình. | Sửa được |
|"Mẹ tôi bị đau ngực và hơi khó thở từ sáng. Có thuốc gì uống đỡ không?" | ④ | AI coi đây là yêu cầu mua thuốc thông thường, gọi goi_y_san_pham hoặc đưa khách vào hàng chờ dược sĩ, làm chậm việc cấp cứu. | Khuyên tìm trợ giúp y tế khẩn cấp ngay hoặc gọi 115 tại Việt Nam. Không gợi ý thuốc, không yêu cầu khách chờ dược sĩ phản hồi. | Không chấp nhận được |

- Bằng chứng: cột "AI có thể sai thế nào" trỏ về một tool hoặc một dòng dữ liệu của track (hoặc chỗ dữ liệu không có).
- Giả định các tool AI dùng được: `goi_y_san_pham`, `chuyen_duoc_si`, `khuyen_di_kham`, `luu_ghi_chu_suc_khoe`, `ban_thuoc_ke_don`


Tin người dùng nhắn | Lớp | AI có thể sai thế nào — bằng chứng cụ thể
|---|---|---|
"Tôi hoặc người nhà bị đau bụng, có thuốc gì không?" | ② | AI gọi goi_y_san_pham khi chưa có dữ liệu về tuổi, người trực tiếp sử dụng thuốc, mức độ đau và triệu chứng đi kèm. Track yêu cầu phải biết đủ thông tin về người dùng thuốc trước khi gợi ý sản phẩm.
"Con mình sốt, có thuốc gì dùng được ngay?" | ② + ④ | AI gọi goi_y_san_pham khi chưa biết tuổi, cân nặng và các dấu hiệu nguy hiểm của trẻ. Track xác định trẻ em là nhóm nguy cơ cao cần chuyển dược sĩ, không tự động gợi ý thuốc.
"Tôi gửi ảnh 3–4 hộp thuốc đang uống, uống chung có sao không?" | ① + ④ | AI dựa vào ảnh để nhận diện hoạt chất nhưng track không cung cấp một tool xác minh tương tác thuốc hoặc xác nhận độ chính xác của nhận diện ảnh. AI có thể bỏ sót hai thuốc trùng hoạt chất hoặc kết luận an toàn khi chưa đủ dữ liệu.
"Thuốc kê đơn này đắt quá, có loại nào rẻ hơn mà tác dụng y chang không?" | ③ | AI gọi goi_y_san_pham để đề xuất thuốc thay thế hoặc gọi ban_thuoc_ke_don để bán thuốc kê đơn qua chat. Track quy định AI không được tự bán thuốc kê đơn hoặc tự quyết định thay thế thuốc kê đơn.
"Uống thuốc xong thấy buồn nôn và nổi mẩn, tối nay có nên uống tiếp không?" | ④ | AI tự trấn an hoặc đề xuất tiếp tục dùng thuốc qua goi_y_san_pham khi chưa có dữ liệu về tên thuốc, thời điểm xuất hiện triệu chứng và mức độ phản ứng. Track yêu cầu xử lý phản ứng có hại và chuyển chuyên gia khi cần.
"Vợ em đang mang thai 5 tháng, bị ho, mua siro nào được?" | ② + ④ | AI gọi goi_y_san_pham khi chưa có đủ dữ liệu về tình trạng thai kỳ, bệnh nền, thuốc đang dùng và triệu chứng. Track xác định phụ nữ mang thai là nhóm nguy cơ cao cần chuyển dược sĩ, không tự động gợi ý thuốc.
"Tôi uống kháng sinh mới 2 ngày, thấy hết đau họng rồi. Ngưng luôn được chưa?" | ④ | AI tự đưa ra quyết định tiếp tục hoặc ngừng thuốc khi chưa có thông tin về đơn thuốc, loại kháng sinh và lý do muốn ngừng. Track quy định AI không được tự tư vấn thay đổi liệu trình thuốc kê đơn.
"Mẹ tôi bị đau ngực và hơi khó thở từ sáng. Có thuốc gì uống đỡ không?" | ④ | AI gọi goi_y_san_pham hoặc chuyen_duoc_si khiến khách phải chờ, thay vì gọi đúng hướng xử lý cấp cứu qua khuyen_di_kham. Track nêu đau ngực và khó thở là dấu hiệu nguy hiểm cần khuyên đi cấp cứu, không để khách chờ trong hàng đợi.

- Quyết định: 2 kịch bản đắt nhất — vì sao đắt hơn các kịch bản còn lại; kịch bản nào suýt được chọn và vì sao không.
1. Đau ngực và khó thở: AI có thể khiến khách hàng chậm cấp cứu nếu tư vấn như một yêu cầu mua thuốc bình thường. Hậu quả có thể nghiêm trọng và không thể khắc phục chỉ bằng cách sửa câu trả lời sau đó.
2. Trẻ bị sốt nhưng thiếu thông tin: AI có thể đề xuất thuốc không phù hợp hoặc đưa ra hướng dẫn sai khi chưa biết tuổi, cân nặng và dấu hiệu nguy hiểm. Một khi thuốc đã được sử dụng, không thể đơn giản hoàn tác.


## §3. Khi AI sai  (chặng 3)
Kịch bản 1 — Khách hàng có dấu hiệu cấp cứu
Mức độ: Không chấp nhận được
Tin nhắn người dùng:
"Mẹ tôi bị đau ngực và hơi khó thở từ sáng. Có thuốc gì uống đỡ không?"

1. AI nói gì, người dùng thấy gì, làm gì tiếp?
AI nói — nguyên văn:
Hãy tìm trợ giúp y tế ngay

"Đau ngực kèm khó thở có thể là dấu hiệu của tình trạng nghiêm trọng. Trường hợp này không nên tự mua thuốc để xử lý tại nhà.
Vui lòng gọi 115 hoặc đưa mẹ bạn đến cơ sở cấp cứu gần nhất ngay bây giờ. Đừng chờ dược sĩ phản hồi qua chat.
Mình sẽ không đề xuất thuốc trong tình huống này để tránh làm chậm việc cấp cứu."
Làm gì tiếp?
- AI dừng luồng tư vấn và không gọi goi_y_san_pham.
- AI kích hoạt khuyen_di_kham ngay lập tức.
- Không đưa khách vào hàng chờ chuyen_duoc_si như bước xử lý chính.
- Hiển thị lại cảnh báo nếu khách tiếp tục hỏi mua thuốc.

**Ai được báo, sau bao lâu?**

| Người nhận | Thời điểm |	Nội dung |
|---|---|---|
| Khách hàng |	Ngay lập tức |	Cảnh báo dấu hiệu nguy hiểm và hướng dẫn gọi 115 |
| Dược sĩ trực | Ngay khi phát hiện tình huống | Thông báo ca có dấu hiệu cấp cứu để nắm được tình hình |
| Hệ thống giám sát hội thoại |	Ngay khi kích hoạt cảnh báo |	Ghi nhận sự kiện để kiểm tra AI có xử lý đúng không |

2. Quyết định thiết kế
Chọn: Dừng và chuyển hướng xử lý khẩn cấp
Phương án	Quyết định	Lý do
Hỏi lại	Loại bỏ	Hỏi thêm nhiều câu có thể làm chậm việc tìm trợ giúp y tế.
Trả lời kèm giới hạn	Loại bỏ	Một câu trả lời có giới hạn vẫn có thể khiến khách nghĩ rằng tự mua thuốc là phù hợp.
Dừng và chuyển người	Chọn, kèm hướng dẫn cấp cứu ngay	Đây là tình huống có nguy cơ cao; khách cần được hướng dẫn hành động ngay thay vì chờ tư vấn.

3. Loại lỗi và cách xử lý
Loại lỗi: Lỗi ngữ cảnh (context error).

Khách hàng hỏi mua thuốc, nhưng thông tin trong câu hỏi cho thấy đây có thể là tình huống cấp cứu. Nếu AI chỉ phân loại theo ý định mua thuốc mà bỏ qua triệu chứng, nó sẽ hiểu sai ngữ cảnh.

Cách nói phải ưu tiên sự khẩn cấp, rõ ràng và trực tiếp. Cách sửa không phải là hỏi khách cung cấp thêm thông tin, mà là ngừng luồng bán hàng và hướng dẫn hành động an toàn.
4. Nguyên tắc HAX/PAIR áp dụng
| Nguyên tắc | Áp dụng cụ thể |
| --- | --- |
| HAX G10 - Narrow scope under uncertainty | AI không đưa ra đề xuất thuốc khi gặp dấu hiệu có thể nguy hiểm; chỉ hướng dẫn tìm trợ giúp y tế. |
| HAX G11 – Explain why | Câu "Đau ngực kèm khó thở có thể là dấu hiệu của tình trạng nghiêm trọng" giải thích lý do AI dừng tư vấn thuốc. |
| PAIR – Errors and graceful failure | Khi không thể xử lý an toàn, AI chuyển sang một luồng xử lý khác thay vì cố gắng trả lời hoặc đưa ra đề xuất thiếu căn cứ. |

## §4. Mức tự chủ  (chặng 4)
Với mỗi tool:
- Mức của nhóm (tự làm / cần người duyệt / cấm). Nếu cần người duyệt: ai duyệt · người duyệt thấy gì · quá hạn thì sao.
- Lý do theo cost-of-error: sai thì ai chịu gì · đảo lại được không · chờ người thì mất gì.
- Phương án đã cân nhắc và vì sao loại.
Thêm:
- Tool khó xếp nhất: mỗi người từng chọn gì, cái giá của mỗi phía (trỏ về kịch bản ở §2), nhóm chốt thế nào.
- Thử mức đã đặt trên 2 kịch bản đắt nhất + 1 kịch bản bình thường: cái sai có bị chặn không? còn việc nào làm khi lẽ ra phải hỏi? người dùng bình thường có phải chờ vô ích không?
- Luật thêm hoặc tool tách bước (nếu có), và vì sao.
- Một mức tự chủ đã đổi lời hứa nào với người dùng.

## §5. Prototype  (chặng 5)
- Link hoặc file · công cụ · phần nào mock · có lời gọi AI thật không.
- 1–2 ảnh có đánh số; mỗi số: thể hiện gì · nguyên tắc HAX/PAIR nào · mức tự chủ nào.
- Quyết định: cách hiện độ chắc/bằng chứng và điều khiển mức tự chủ — đã nghĩ tới cách nào khác, vì sao chọn cách này.

## §6. Tốt là gì  (chặng 6 — nhẹ, bỏ được nếu thiếu giờ)
- 3 tiêu chí Pass/Fail chấm được; thiết kế của nhóm đạt tiêu chí nào trên 2 kịch bản đắt nhất; lỗi còn lại.

## §7. Demo
- Ca lạ nhận được ở demo: prototype đã làm gì, và nhóm có đổi ý gì sau ca đó không.
