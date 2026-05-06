# Day 17 Submission
**Student:** [Nguyen Ba Khanh]
**Date:** [2026-04-25]
**Product idea:** [Ứng dụng AI hỗ trợ quyết toán thuế TNCN ]

---

## 1. MVP Boundary Sheet

**Riskiest Assumption:**
> [Người dùng sẵn sàng chia sẻ chứng từ cực kỳ nhạy cảm (CCCD, sao kê thu nhập, biên lai thuế) cho một ứng dụng bên thứ 3 hoàn toàn mới (chưa có uy tín trên thị trường) để đổi lấy sự tiện lợi.]

**In-Scope** (tối đa 3):
- Tính năng nhận diện văn bản (OCR) chuyên sâu cho tài liệu tài chính — tự động trích xuất chính xác các con số từ ảnh chụp CCCD, chứng từ khấu trừ thuế TNCN, hóa đơn.
- Tính năng "Contextual AI" (AI theo ngữ cảnh) — giải thích các thuật ngữ thuế, hướng dẫn các khoản giảm trừ gia cảnh hiển thị trực tiếp trên giao diện tờ khai khi người dùng gặp khó khăn (RAG trên tệp dữ liệu luật thuế đã được kiểm duyệt).
- Tính năng tự động tính toán và tối ưu: Đối chiếu các nguồn thu nhập và gợi ý cách phân bổ người phụ thuộc để tối ưu số thuế phải nộp/được hoàn.

**Out-of-Scope:**
- Truy xuất thông tin thu nhập trực tiếp từ hệ thống của Tổng cục Thuế (lý do: API chưa mở cho bên thứ 3 và rào cản pháp lý rất lớn).
- Tự động nộp tờ khai thay người dùng (lý do: Rủi ro pháp lý cao, người dùng sẽ tự tải file XML về nộp trên eTax).

**Non-Goals:**
- Chatbot hỏi đáp luật pháp mở (Open-ended Legal Chatbot) — Lý do: Dễ sinh ra ảo giác (hallucination) dẫn đến tư vấn sai luật, gây hậu quả nghiêm trọng.
- Tính năng kết nối trực tiếp với nhân viên tư vấn thuế (Live Agent) — Lý do: Quá tốn kém chi phí vận hành, không phù hợp cho mô hình MVP.

---

## 2. PRD Skeleton

### Problem Statement
> [Những người làm công ăn lương có nhiều nguồn thu nhập và freelancer đang gặp khó khăn trong việc hiểu luật thuế và tự quyết toán thuế, nhưng không có ngân sách (hoặc không đáng) để thuê dịch vụ kế toán ngoài, dẫn tới việc khai thuế sai, nộp phạt trễ hạn hoặc mất đi quyền lợi được hoàn thuế.]

### Target User
> [Người làm công ăn lương bận rộn (25-40 tuổi) có thêm thu nhập bên ngoài, và freelancer có dòng tiền phức tạp nhưng không có kế toán riêng, rành công nghệ nhưng mù mờ về luật kế toán.]

### User Stories
**Story 1:**
> As a [nhân viên văn phòng có thu nhập từ 2-3 công ty], I want [một phần mềm có thể tự động đọc chứng từ và điền sẵn các trường thông tin tờ khai], so that [tôi có thể hoàn thành việc quyết toán thuế trong 15 phút mà không sợ tính toán sai sót].

**Story 2:**
> As a [freelancer có thu nhập biến động], I want [hệ thống gợi ý cách tính toán mức giảm trừ gia cảnh (bản thân, con cái, cha mẹ) tối ưu nhất], so that [tôi có thể nhận lại được số tiền thuế đã bị khấu trừ một cách hợp pháp tối đa].

### AI-Specific
**Model Selection:**
- Model: [Gemini 2.5 Pro]
- Lý do chọn: [Có khả năng xử lý OCR tiếng Việt trên hình ảnh rất xuất sắc, context window lớn để đọc hiểu các quy định thuế dài, khả năng lý luận (reasoning) tốt.]
- Trade-offs chấp nhận: [Chi phí API ($1.25 / 1 triệu tokens) cao hơn các model nhỏ, nhưng bắt buộc phải dùng để đảm bảo độ chính xác khi xử lý số liệu tài chính.]
- Trade-offs không chấp nhận: [Không chấp nhận model sinh ra ảo giác (hallucination) đối với các con số tính toán. Các phép tính phải được thực thi bằng code deterministic, AI chỉ trích xuất (OCR) và giải thích văn bản.]

**Data Requirements:**
- Nguồn: [Cổng thông tin điện tử Chính phủ, Tổng cục Thuế (Các thông tư, nghị định hiện hành về Thuế TNCN).]
- Owner: [Đội ngũ phát triển (tự cập nhật và xây dựng Vector Database).]
- Update frequency: [Theo năm hoặc ngay khi có thông tư/nghị định mới ban hành.]

**Fallback UX:**
- Chiến lược: [Xử lý lỗi khi AI OCR nhận diện ảnh mờ hoặc không tự tin (< 85%).]
- Trigger: [Người dùng upload ảnh chứng từ bị lóa sáng, nhòe hoặc mất góc.]
- Hành động: [Hệ thống sẽ highlight màu đỏ hoặc vàng tại các ô dữ liệu AI không chắc chắn (ví dụ: Mã số thuế, Số tiền) và để trống.]
- User options: [Bắt buộc người dùng phải kiểm tra lại và tự nhập tay các ô bị bôi đỏ trước khi cho phép bấm nút "Tiếp tục".]

### Success Metrics
- Primary metric: [Task Success Rate (Tỷ lệ hoàn thành xuất file tờ khai)].
- Ngưỡng thành công: [> 40% người dùng sau khi tải lên chứng từ đầu tiên có thể đi đến bước cuối cùng là xuất được file XML.]
- Timeframe đo lường: [Trong vòng 2 tháng mùa quyết toán thuế (Tháng 3 - Tháng 4).]

### Dependencies & Constraints
- Thời gian: [4 tuần (phải ra mắt kịp trước tháng 3 để đón sóng quyết toán thuế).]
- Tài chính: [Ngân sách rất hẹp (10 triệu VNĐ) chủ yếu dành cho phí Server và API AI, không đủ chạy Marketing lớn.]

---

## 3. Hypothesis Table

### Hypothesis 1 (cho tính năng In-Scope #1 - OCR)
> "Chúng tôi tin rằng [tính năng OCR quét chứng từ tự động] sẽ giúp [người dùng bận rộn] đạt được [việc điền tờ khai quyết toán thuế chính xác trong dưới 15 phút].
> Chúng tôi sẽ biết mình đúng khi thấy [Tỷ lệ hoàn thành xuất tờ khai] đạt [40%] trong [tháng ra mắt đầu tiên]."
- Riskiest assumption: [Người dùng sẵn sàng chia sẻ chứng từ nhạy cảm (CCCD, sao kê) với một ứng dụng noname mới ra mắt.]
- Cách test cheapest: [Tạo một Landing Page giới thiệu "Giải pháp AI làm hồ sơ thuế trong 5 phút". Yêu cầu người dùng để lại Email kèm cam kết bảo mật. Đo lường tỷ lệ Conversion Rate (Số email / Số lượng truy cập) từ quảng cáo FB Ads.]

### Hypothesis 2 (cho tính năng In-Scope #2 - Contextual AI)
> "Chúng tôi tin rằng [tính năng AI giải thích thuật ngữ thuế tại chỗ] sẽ giúp [người dùng] đạt được [sự tự tin khi kiểm tra và chốt các khoản thu nhập/giảm trừ].
> Chúng tôi sẽ biết mình đúng khi thấy [Tỷ lệ bỏ cuộc (Drop-off rate) ở màn hình kiểm tra số liệu] giảm xuống [dưới 20%]."
- Riskiest assumption: [Người dùng có thể quá tin tưởng AI, nếu AI giải thích sai luật dẫn đến người dùng khai sai, họ sẽ đổ lỗi cho ứng dụng.]
- Cách test cheapest: [Dùng phương pháp Wizard of Oz: Làm một giao diện chat giả, đằng sau là người thật (chuyên gia kế toán) trả lời để xem thực tế người dùng thường hỏi những câu hỏi khó lường nào.]

---

## 4. PMF Scorecard
**Aha Moment:**
> [Mô tả hành vi cụ thể — không phải cảm giác]
> Người dùng upload thành công 3 tờ biên lai khấu trừ thuế và ngay lập tức thấy ứng dụng hiện lên thông báo: "Bạn đủ điều kiện được hoàn 5.200.000 VNĐ", kèm theo tờ khai đã được điền sẵn 100% dữ liệu chính xác.

**Actionable Metric:**
> [Tên metric + cách đo]
> Tỷ lệ xuất file thành công và Tỷ lệ giới thiệu (Referral Rate). (Lưu ý: Không dùng số lượng hồ sơ >3 hồ sơ/tháng vì cá nhân chỉ quyết toán 1 năm 1 lần).

**PMF Method:**
-  [Sean Ellis Test]
-  Ngưỡng thành công: [ > 40% người dùng trả lời "Rất thất vọng" (Very disappointed) nếu không còn được sử dụng sản phẩm vào mùa quyết toán năm sau.]

**Vanity Metrics tôi sẽ không dùng:**
- Số lượt tải ứng dụng / Lượt truy cập web (Không phản ánh việc người dùng có tạo ra giá trị hay không).
- Tổng số lượng tin nhắn hỏi đáp với AI (Hỏi càng nhiều chứng tỏ ứng dụng thiết kế UX càng rắc rối).
- Số tài khoản đăng ký mới.

---

## 5. AI Critique Log

**Điểm AI chỉ ra (so với Version A ban đầu):**
1. **[Logic] Mâu thuẫn giữa In-Scope và Non-Goal về Chatbot luật:** Bản A In-scope có "trả lời câu hỏi thông qua AI", nhưng Non-goal lại là "không làm chatbot".
   - **Action: Accept** — Lý do: Cần thu hẹp scope lại thành "Contextual AI" (AI giải thích theo ngữ cảnh ngay tại tooltip) thay vì làm một chatbot mở trò chuyện tự do để tránh rủi ro pháp lý.
2. **[Metric] Actionable metric không thực tế:** Bản A đưa ra metric "quay lại sử dụng sau 1 tháng và hoàn thành > 3 hồ sơ/tháng".
   - **Action: Accept** — Lý do: Quyết toán thuế cá nhân là hành vi theo mùa (1 năm 1 lần), người dùng cá nhân không có nhu cầu làm 3 hồ sơ trong 1 tháng. Đã đổi thành "Task Success Rate" (Tỷ lệ xuất file thành công).
3. **[UX] Fallback UX sai định nghĩa:** Bản A nhầm Fallback UX thành tính năng "cập nhật luật mới".
   - **Action: Accept** — Lý do: Fallback UX là thiết kế phòng hờ khi AI thất bại (vd: OCR mờ, AI không đọc được số). Đã sửa lại thành cảnh báo highlight đỏ yêu cầu người dùng nhập tay.
4. **[Hypothesis Test] Cách test rủi ro bảo mật chưa chuẩn:** Chạy quảng cáo tính năng không giúp xác định người dùng có dám upload ảnh thật hay không.
   - **Action: Partial** — Lý do: Chạy quảng cáo là đúng, nhưng Cần test bằng Landing Page + Form Email kèm các cảnh báo bảo mật (Disclaimer) để xem họ có thực sự cam kết (skin in the game) bước đầu không.

**Thay đổi lớn nhất giữa Version A và Version B:**
> [Điều chỉnh lại tính thực tế của sản phẩm và các chỉ số đo lường (Metrics). Version B đã loại bỏ các Metrics vô lý (3 hồ sơ/tháng) và thay bằng Task Success Rate phù hợp với sản phẩm chu kỳ năm. Đồng thời, thiết kế lại "Fallback UX" chuẩn xác để xử lý trường hợp AI đọc sai chứng từ, và thu hẹp tính năng AI từ "chatbot luật" thành "AI giải thích ngữ cảnh" để giảm thiểu rủi ro pháp lý.]

---

## 6. Self-assessment

**Mắt xích nào trong [MVP Boundary -> PRD -> Hypothesis -> PMF] bạn đang yếu nhất?**
> [Trả lời thật]
- Khả năng xử lý các văn bản luật pháp nhà nước bằng AI mà không vi phạm luật bảo mật thông tin và quy định tư vấn luật pháp

Open questions bạn muốn giải đáp tiếp:
1. Làm thế nào để thiết lập các giới hạn (guardrails) kỹ thuật giúp AI chỉ cung cấp thông tin luật thuần túy (dạng trích dẫn văn bản) mà không vô tình đưa ra lời khuyên pháp lý (legal advice) cụ thể cho từng cá nhân, nhằm tránh vi phạm quy định về tư vấn luật?
2. Cần áp dụng những biện pháp kỹ thuật nào (như ẩn danh hóa dữ liệu tại client-side) hoặc các chính sách bảo mật nào để chứng minh với người dùng rằng thông tin từ CCCD và biên lai thuế của họ không bị lưu trữ hay sử dụng để huấn luyện mô hình?