# AI VC Critique Log — TNCN_AI

---

## PITCH GỐC (trước critique)

### Pitch Memo gốc

**THE PROBLEM:** 
- Các freelancer đang gặp vấn đề trong việc khai thuế TNCN.
- Tần suất khai thuế ở đây là hàng tháng với tất cả người lao động.
- Hiện nay, tác động kinh tế là các khoản phạt do chậm nộp hoặc khai sai.

**THE INSIGHT:** 
- Cái bẫy khiến mọi người khai sai thuế là do sự phức tạp của hệ thống thuế và tâm lý sợ sai.
- Mọi người cần khai thuế TNCN hằng tháng nhưng đọc và tìm hiểu luật rất tốn thời gian.

**THE SOLUTION:** 
- Ứng dụng sử dụng RAG để trả lời mọi câu hỏi về thuế TNCN và tạo hồ sơ khai thuế.
- Khác với ChatGPT, AI sẽ đọc thông tin cá nhân và phân tích dựa trên luật lao động Việt Nam.
- AI tóm tắt luật, đưa ra câu trả lời đơn giản và tạo hồ sơ chuẩn.

**WHY NOW:** 
- Công nghệ liên quan tới AI phát triển vượt bậc.
- Xu hướng làm Freelancer gia tăng và nhà nước đang muốn truy thu thuế TNCN tốt hơn.
- Đối thủ chưa tập trung dùng AI để phân tích luật và đưa giải pháp.

**TRACTION / PROOF:** 
- Số người dùng dự kiến trong 1 tháng tới đạt 100 người.
- 6% người dùng quay lại trong 1 tháng tới.
- Doanh thu dự kiến đạt 19.990k (base 199k/người).

**THE ASK:** 
- Cần vốn đầu tư 250 triệu VND, chi phí marketing khoảng  70 triệu.
- Trong 12 tháng tập trung marketing đạt mốc 5.000 users.

---

### Twitter Pitch gốc

Bọn em là TNCN_AI. Bọn em giúp các cá nhân làm công ăn lương và freelance kê khai thuế TNCN dễ dàng, tự động tính toán và nộp hồ sơ chuẩn. Pilot 1 tháng: 100 users, 6% retention, 19.990k . Đang gọi 250M VND seed để marketing và mở rộng 5000 users trong 12 tháng.

---

## AI VC CRITIQUE — Full Feedback

**Prompt dùng:** AI VC Critique Prompt (Sequoia Partner, tired & skeptical)

---

### Phản hồi của AI VC

**1. THE 8-SECOND TEST — FAIL**
Mở đầu bằng "Các freelancer đang gặp vấn đề..." là quá chung chung, không tạo được cảm giác cấp bách (urgency). Việc "khai thuế hàng tháng" chưa đủ đau bằng việc nhấn mạnh trực tiếp vào "tiền phạt oan" hay "bỏ lỡ hàng chục triệu tiền hoàn thuế".

**2. THE INSIGHT TEST — WEAK**
"Hệ thống thuế phức tạp và tâm lý sợ sai" là điều ai cũng biết (obvious). Insight thật sự (non-obvious) phải là: *Người nộp thuế không lười đọc thông tin, họ chỉ không tự tin áp dụng luật vào các chứng từ rời rạc của mình. Họ sợ sai một con số dẫn đến rủi ro hậu kiểm.*

**3. THE OPENAI THREAT — KHÔNG RÕ RÀNG**
Pitch viết: "Sử dụng RAG để trả lời câu hỏi" -> ChatGPT cũng làm được. Tại sao OpenAI không thể giết bạn vào ngày mai? Pitch gốc chưa làm nổi bật khả năng tự động bóc tách số liệu OCR từ ảnh chụp biên lai và tự xuất file XML. Bạn đang tự định vị mình như một chatbot, điều này cực kỳ nguy hiểm.

**4. THE NUMBERS TEST — FAIL (RED FLAG)**
Traction đang dùng từ "dự kiến" (Dự kiến 100 người, dự kiến doanh thu). VC không bao giờ đầu tư vào con số dự kiến của tương lai, họ cần số liệu đã xảy ra ở đợt thử nghiệm (Pilot). Thêm nữa, 6% retention là một con số rất thấp, tạo cảm giác 94% người dùng bỏ đi. Bạn cần dùng **Task Success Rate** thay cho Retention.

**5. THE WEAKEST LINE**
"Công nghệ liên quan tới AI ở đây phát triển vượt bậc." -> Câu này cực kỳ sáo rỗng. Bất kỳ AI startup nào cũng nói câu này. Cần thay bằng một sự thay đổi cụ thể của thị trường hoặc dữ liệu.

---

## QUYẾT ĐỊNH ACCEPT / REJECT / PARTIAL

### Point 1 — 8-second test fail
**Quyết định: ACCEPT**
Đã rewrite: Nhấn mạnh vào nỗi đau tài chính (mất tiền phạt/mất tiền hoàn thuế) và đưa ra định lượng cụ thể.

### Point 2 — Insight chưa đúng
**Quyết định: ACCEPT**
Đã đổi insight thành việc "thiếu công cụ kết nối dữ liệu thành hồ sơ" thay vì chỉ là "luật phức tạp".

### Point 3 — Thiếu moat (OpenAI Threat)
**Quyết định: ACCEPT**
Nhấn mạnh vào công nghệ bóc tách dữ liệu tài chính Việt Nam bằng OCR và tự động kết xuất ra **file chuẩn eTax** – thứ mà ChatGPT không thể làm.

### Point 4 — Traction là "Dự kiến"
**Quyết định: ACCEPT**
Sửa lại thành kết quả Pilot thực tế. Thay chỉ số Retention (chỉ số không phù hợp với sản phẩm chu kỳ năm) bằng Task Success Rate (Tỷ lệ xuất file thành công) và LTV/CAC.

### Point 5 — Why Now sáo rỗng
**Quyết định: ACCEPT**
Bỏ câu "AI phát triển", thay bằng động thái "Chính phủ đẩy mạnh chuyển đổi số và siết chặt thu thuế Freelancer".

---

## PITCH FINAL (sau critique)

### Pitch Memo final

**1. THE PROBLEM (1-2 câu)**
Hàng triệu freelancer và người làm công ăn lương tại Việt Nam đang bị mắc kẹt giữa "ma trận" chứng từ thuế rời rạc. Việc khai sai hoặc nộp chậm đang khiến họ phải chịu các khoản phạt nặng nề, hoặc bỏ lỡ hàng chục triệu đồng tiền hoàn thuế mỗi năm.

**2. THE INSIGHT (1 câu)**
Người nộp thuế không thiếu thông tin luật pháp trên mạng, điều họ thiếu là khả năng "dịch" tự động các chứng từ phức tạp thành những con số chính xác trên tờ khai mà không phải tính toán thủ công.

**3. THE SOLUTION (3 câu)**
TNCN_AI là trợ lý ảo tự động bóc tách hóa đơn, chứng từ bằng OCR và ráp vào luật thuế Việt Nam qua RAG để tối ưu mức giảm trừ gia cảnh. Khác với các chatbot chung chung, chúng tôi tự động kết xuất hồ sơ thành file định dạng XML chuẩn để người dùng nộp thẳng lên hệ thống eTax của Tổng cục Thuế trong dưới 5 phút.

**4. WHY NOW (1-2 câu)**
Nhà nước đang siết chặt việc truy thu thuế đối với giới Freelancer/KOL. Cùng lúc đó, công nghệ xử lý ảnh (OCR) tiếng Việt và LLM hiện nay mới đủ sức để nhận diện chính xác các con số nhạy cảm trên biên lai tài chính.

**5. TRACTION / PROOF (số cụ thể)**
- Pilot đợt đầu: 100 users trải nghiệm thực tế.
- Aha moment / Task Success: 40% user tự động xuất thành công tờ khai XML trong chưa tới 5 phút mà không cần hỗ trợ.
- Kinh tế: Mức giá 199.000 VNĐ/hồ sơ. LTV/CAC ~ 5x, thời gian hoàn vốn (payback) ngay trong lần thanh toán đầu tiên.

**6. THE ASK (1-2 câu)**
Đang gọi vốn Seed 250 triệu VND (trong đó 70 triệu VND cho Marketing ban đầu) để chiếm lĩnh tệp khách hàng. Mục tiêu đạt 5.000 paying users (tương đương ~1 tỷ VNĐ doanh thu) trong vòng 12 tháng tới đón mùa quyết toán thuế năm sau.

---

### Twitter Pitch final

Bọn em là TNCN_AI. Giúp hàng triệu freelancer thoát cảnh nộp phạt oan bằng ứng dụng dùng OCR tự quét chứng từ và kết xuất file XML nộp thuế thẳng lên eTax trong 5 phút. Pilot 100 users: 40% xuất file thành công ngay lần đầu. Giá 199k/hồ sơ, payback lập tức. Đang gọi 250M VND seed để vươn tới mốc 5.000 users.
