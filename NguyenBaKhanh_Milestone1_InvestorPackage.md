# 📄 Milestone 1: Investor Package — TNCN_AI
> **Project:** TNCN_AI 
> **Họ và tên và mã sinh viên :** Nguyễn Bá Khánh (2A202600135)




## COVER & TWITTER PITCH

### TNCN_AI: Tự động hóa quyết toán thuế cho Freelancer

**Twitter Pitch:**
Ứng dụng tên là **TNCN_AI** Giúp hàng triệu freelancer thoát cảnh nộp phạt oan bằng ứng dụng dùng OCR tự quét chứng từ và kết xuất file XML nộp thuế thẳng lên eTax trong 5 phút. Pilot 100 users: 40% xuất file thành công ngay lần đầu. Giá 159.000 VNĐ / tài khoản . Đang gọi 250.000.000 VNĐ seed để vươn tới mốc 5.000 users.



## PITCH MEMO, MARKET OPPORTUNITY & PRD

### 1. The Problem
Hàng triệu freelancer và người làm công ăn lương tại Việt Nam đang bị mắc kẹt giữa "ma trận" chứng từ thuế rời rạc. Việc khai sai hoặc nộp chậm đang khiến họ phải chịu các khoản phạt nặng nề, hoặc bỏ lỡ hàng chục triệu đồng tiền hoàn thuế mỗi năm.

### 2. The Insight
Người nộp thuế không thiếu thông tin luật pháp trên mạng, điều họ thiếu là khả năng "dịch" tự động các chứng từ phức tạp thành những con số chính xác trên tờ khai mà không phải tính toán thủ công.

### 3. The Solution
TNCN_AI là trợ lý ảo tự động bóc tách hóa đơn, chứng từ bằng OCR và ráp vào luật thuế Việt Nam qua RAG để tối ưu mức giảm trừ gia cảnh. Khác với các chatbot chung chung, chúng tôi tự động kết xuất hồ sơ thành file định dạng XML chuẩn để người dùng nộp thẳng lên hệ thống eTax của Tổng cục Thuế trong dưới 5 phút.

### 4. Why Now
Nhà nước đang siết chặt việc truy thu thuế đối với giới Freelancer/KOL. Cùng lúc đó, công nghệ xử lý ảnh (OCR) tiếng Việt và LLM hiện nay mới đủ sức để nhận diện chính xác các con số nhạy cảm trên biên lai tài chính.

### 5. Market Opportunity (TAM/SAM/SOM)
*   **TAM (Thị trường tổng thể):** ~1,000,000 người (Cá nhân có mã số thuế và thu nhập chịu thuế tại VN).
*   **SAM (Thị trường mục tiêu):** ~500,000 người (Nhân viên đô thị, freelancer quen dùng app/ngân hàng số).
*   **SOM (Thị trường có thể chiếm lĩnh):** 100,000 người (Tiếp cận qua HR và cộng đồng Freelancer).

### 6. PRD & Product Workflow
**Core Workflow (3 bước):**
1. **Intelligent Scanning:** Upload CCCD và biên lai khấu trừ. OCR tự nhận diện con số và mã số thuế.
2. **Legal Reasoning:** AI đối chiếu luật để tối ưu hóa mức giảm trừ gia cảnh.
3. **One-Click Compliance:** Trích xuất file XML chuẩn để nộp trực tiếp eTax.

**Riskiest Assumption:** Người dùng e ngại việc tải lên các thông tin nhạy cảm.
**Mitigation (Fallback UX):** Xử lý lỗi thông minh nếu ảnh mờ, yêu cầu người dùng tự xác nhận thông tin bị tô đỏ trước khi đi tiếp.



## FINANCIAL MODEL & UNIT ECONOMICS

### 1. Traction / Proof (Pilot Results)
*   **Scale:** Đã triển khai thử nghiệm (Pilot) với 100 users trải nghiệm thực tế.
*   **Aha Moment / Task Success:** 40% user tự động xuất thành công tờ khai XML trong chưa tới 5 phút mà không cần hỗ trợ.

### 2. Unit Economics
*   **Giá bán (Pricing):** 159.000 VNĐ / hồ sơ.
*   **LTV/CAC:** ~ 5x.
*   **Thời gian hoàn vốn (Payback):** Lập tức (Ngay trong lần thanh toán đầu tiên).
*   **Mục tiêu (12 tháng tới):** 5.000 paying users, tương đương ~1 tỷ VNĐ doanh thu.

### 3. The Ask
**Đang gọi vốn Seed: 250.000.000 VND**
*   **Chi phí Marketing:** 70 triệu VND để chạy quảng cáo và chiếm lĩnh khách hàng.
*   **Chi phí Vận hành & Sản phẩm:** 180 triệu VND (Server, API AI, pháp lý và update luật).



## ROADMAP & OKRs

### 1. Roadmap (Now / Next / Later)
*   **NOW:** Code giao diện cơ bản; 10 users dùng AI để tóm tắt luật thuế TNCN. Sử dụng LLM đọc tài liệu mẫu.
*   **NEXT:** Thêm dữ liệu để tạo hồ sơ và tăng tính chính xác; Cập nhật bộ luật mới. Thêm chatbot hỗ trợ tư vấn hồ sơ.
*   **LATER:** Xử lý các case đặc biệt/lỗi phát sinh. Tối ưu hóa mô hình LLM và xây dựng Chatbot tổng thể chuyên sâu về pháp luật thuế.

### 2. OKRs (Mục tiêu 1 Quý)
**Objective:** Trở thành AI số 1 hỗ trợ khách hàng khai thuế nhanh chóng, giảm tải hoàn toàn công việc thủ công.
*   **KR1 (Leading):** Đạt 100 người sử dụng ứng dụng > 3 giờ/tuần.
*   **KR2 (Lagging):** Doanh thu đạt mức 159.000.000 VND (1000 users x 159k), tốc độ tăng trưởng > 50% so với quý trước.
*   **KR3 (Quality):** Tỷ lệ người dùng duy trì (Retention rate) đạt 3%/tháng.



## DEPENDENCY MAP & CRITICAL PATH

### 1. Dependency Map & Risk Mitigation

| Lớp | Đối tác/Dịch vụ | Rủi ro | Chiến lược giảm thiểu rủi ro (Mitigation) |
| :--- | :--- | :--- | :--- |
| **Tier 1 — Critical** | OpenAI/Gemini API | Khóa tài khoản, tăng giá 5x, rate limit | **Multi-vendor:** Dự phòng OpenAI + Gemini |
| | Cloud (AWS, Google) | Tăng giá 10x, ban account | **Multi-region:** Triển khai hạ tầng phân tán |
| **Tier 2 — Important** | Apple/Google Play | Xóa ứng dụng khỏi Store | **Web app fallback:** Tuân thủ policy từ Day-1, chuẩn bị sẵn môi trường backup |
| | API từ bên thứ 3 | Thay đổi kiến trúc API | **Abstract layer:** Tích hợp linh hoạt với nhiều vendor dự phòng |
| **Tier 3 — Watch** | Extension Stores | Đổi policy duyệt extension | **Direct download:** Cung cấp file tải trực tiếp |
| | Data sources | Cấm scraping, chặn API | **Partnerships:** Đàm phán hợp đồng B2B chính thức |

### 2. Critical Path

1. **Data Pipeline:** Xây dựng luồng dữ liệu nền tảng ổn định và tự động hóa.
2. **Legal Compliance (Tuân thủ pháp lý):** Tích hợp chặt chẽ các ràng buộc luật định vào thiết kế và trải nghiệm người dùng (*Yêu cầu đầu vào từ: UI/UX Design*).
3. **Model Fine-tune:** Tinh chỉnh mô hình AI bám sát định hướng truyền thông và nhu cầu khách hàng (*Yêu cầu đầu vào từ: Marketing Site*).
4. **API Integration:** Thực hiện kết nối hệ thống thông suốt qua tài liệu kỹ thuật chuẩn hóa (*Yêu cầu đầu vào từ: Docs*).
5. **Launch:** Kích hoạt hệ thống theo dõi và đo lường để đánh giá hiệu suất khi go-live (*Yêu cầu đầu vào từ: Analytics*).


## PHỤ LỤC

` Đã được push lên link github hết tổng hợp của các ngày ` 

