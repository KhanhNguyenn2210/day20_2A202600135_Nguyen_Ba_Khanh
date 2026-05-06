## Now/Next/Later 

**Now**
Vấn đề: 10 người dùng đang dùng AI để đọc các tóm tắt về luật thuế TNCN 
Đang code: Đã code được giao diện đầu tiên cho ứng dụng, sử dụng mô hình LLM để đọc các tài liệu mẫu ( đang ít tài liệu )
**Next**
Vấn đề:Cần thêm dữ liệu để tạo hồ sơ và đảm bảo tính chính xác , các bộ luật update thêm nhiều để đảm bảo độ sâu và chính xác, thêm chatbot vào để hỗ trợ người dùng 

Đang code: Đang tìm kiếm các tài liệu pháp lý và các bộ luật liên quan và sử dụng thêm các mô hình LLM để backup trong trường hợp thiếu tài nguyên , các mô hình LLM đã khá tốt trong việc tóm tắt và hiểu luật.Thêm chatbot nhỏ trong việc xử lý hồ sơ
 
**Later**
Vấn đề: Xử lý các trường hợp đặc biệt và các lỗi phát sinh 
Đang code: Tiếp tục tối ưu hóa mô hình LLM và xử lý các trường hợp đặc biệt và các lỗi phát sinh trong tương lai mà khách hàng phản hồi, thêm chatbot tổng thể hơn để có thể trả lời các câu hỏi liên quan đến pháp luật và các vấn đề phát sinh


## OKR 
- Objective : Trở thành AI có thể hỗ trợ khách hàng trong việc khai thuế rất cần thiết trong cuộc sống và giúp giảm tải công việc cho con người.

- KR1( leading ): 100 người sử dụng app > 3 giờ / tuần
- KR2( lagging ): Doanh thu được 1000 x 159.000 VND , tăng nhanh hơn 50% so với quý trước. 
- KR3 ( Quality ): Số người ở lại 3%/tháng 

## Dependecy Map: 
| Lớp | Ai? | Họ có thể làm gì? | Mitigation (Giảm thiểu rủi ro) |
| :--- | :--- | :--- | :--- |
| **Tier 1 — Critical** | OpenAI/Gemini API | Khóa account, tăng giá 5x, rate limit | Multi-vendor (OpenAI + Gemini fallback) |
| | Cloud (AWS, Google ) |  tăng giá 10x, ban account | Multi-region deployment |
| **Tier 2 — Important** | Apple/Google Play |  ban app | Web app fallback, comply policy day-1, có backup môi trường cho app  |
| | API từ bên thứ 3|  đổi API | Abstract layer, có backup vendor |
| **Tier 3 — Watch** | Browser extension stores | Đổi policy | Direct download fallback |
| | Data sources | Cấm scraping, đóng API | Negotiate B2B contract |
 

## Critical path


1. **Data Pipeline:** Xây dựng luồng dữ liệu nền tảng ổn định và tự động hóa.
2. **Legal Compliance (Tuân thủ pháp lý):** Tích hợp chặt chẽ các ràng buộc luật định vào thiết kế và trải nghiệm người dùng (*Yêu cầu đầu vào từ: UI/UX Design*).
3. **Model Fine-tune:** Tinh chỉnh mô hình AI bám sát định hướng truyền thông và nhu cầu khách hàng (*Yêu cầu đầu vào từ: Marketing Site*).
4. **API Integration:** Thực hiện kết nối hệ thống thông suốt qua tài liệu kỹ thuật chuẩn hóa (*Yêu cầu đầu vào từ: Docs*).
5. **Launch:** Kích hoạt hệ thống theo dõi và đo lường để đánh giá hiệu suất khi go-live (*Yêu cầu đầu vào từ: Analytics*).
  