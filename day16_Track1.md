# Day 16 — Dự án AI: Trợ lý Quyết toán Thuế TNCN Thông minh 
*Người thực hiện: Nguyễn Bá Khánh - 2A202600135*

## 1. Idea Reframed

### 1.1. Original Idea
Xây dựng một ứng dụng có khả năng thu thập, tóm tắt các quy định pháp luật và dữ liệu cá nhân liên quan đến thuế thu nhập cá nhân (TNCN). Mục tiêu là tự động hóa việc tạo hồ sơ khai thuế hoàn chỉnh, giúp khách hàng giảm thiểu tối đa việc nhập liệu thủ công mà vẫn đảm bảo hiểu rõ và thực hiện đúng nghĩa vụ thuế.

### 1.2. Reframed as a Product Opportunity
Trong bối cảnh nền kinh tế số, các quy định về thuế tại Việt Nam thường xuyên được cập nhật (thông tư, nghị định mới). Người nộp thuế hiện đang đối mặt với "ma trận" thông tin và thủ tục hành chính rườm rà. 

**Cơ hội sản phẩm:** Áp dụng công nghệ Generative AI và OCR (nhận dạng ký tự quang học) để chuyển hóa các chứng từ rời rạc thành hồ sơ thuế chuẩn hóa theo thời gian thực. Điều này không chỉ giảm 80% thời gian chuẩn bị mà còn loại bỏ hoàn toàn nhu cầu di chuyển vật lý đến cơ quan thuế hoặc ngân hàng thông qua việc tích hợp nộp thuế điện tử.

---

## 2. Customer Segment

* **Segment Name:** Người làm công ăn lương bận rộn.
* **Operation Context:** Nhân viên văn phòng, Freelancer hoặc cá nhân kinh doanh có dòng tiền phức tạp nhưng không có kế toán riêng.
* **Recurring Workflow:** * Hàng tháng/quý: Lưu trữ các chứng từ khấu trừ thuế lẻ.
    * Tháng 3 - Tháng 4 hàng năm: Thời điểm "cao điểm" quyết toán thuế TNCN. Khách hàng phải lục tìm chứng từ, tra cứu mức giảm trừ gia cảnh mới nhất, tính toán số thuế thừa/thiếu.
* **Pain Moment:** * Rơi vào trạng thái "mù mờ" khi đọc các văn bản luật khô khan.
    * Sợ hãi rủi ro pháp lý (bị phạt chậm nộp, tính sai số tiền).
    * Mệt mỏi khi phải xếp hàng tại cơ quan thuế vào những ngày cuối hạn.
* **Why not:** Các giải pháp hiện tại (HTKK của Tổng cục Thuế) quá nặng về kỹ thuật, không có tính năng giải thích hoặc tư vấn. Các công ty dịch vụ kế toán thì chi phí quá cao so với nhu cầu cá nhân.
* **Access Path:** * Các cộng đồng nghề nghiệp (LinkedIn, Group Kế toán, Diễn đàn Freelancer).
    * Hợp tác với các phòng nhân sự (HR) của các công ty để cung cấp như một phúc lợi cho nhân viên.

---

## 3. Need Map

* **Need #1 (Priority):** Sự chính xác tuyệt đối và Giải thích dễ hiểu
* **Statement (JTBD):** Khi chuẩn bị tờ khai TNCN, tôi muốn đảm bảo mọi thông tin (thu nhập, người phụ thuộc, đóng bảo hiểm) đều được khớp nối chính xác với luật hiện hành để tránh rủi ro hậu kiểm, đồng thời tôi cần hiểu tại sao con số đó lại như vậy mà không cần đọc hàng trăm trang thông tư.
* **Current Workaround:** * Tự nghiên cứu trên các trang như Thư viện pháp luật (tốn thời gian, dễ hiểu sai).
    * Nhờ người quen làm kế toán xem hộ (phiền hà, không chủ động).
    * Sử dụng các file Excel tự chế lan truyền trên mạng (rủi ro sai công thức).
* **Pain Signal:** Khách hàng thường xuyên tìm kiếm các từ khóa: "Hướng dẫn quyết toán thuế TNCN 2026", "Cách tính thuế TNCN online", "Mức giảm trừ gia cảnh mới nhất".
* **Evidence / Proxy Evidence:** Các hội nhóm "Cộng đồng quyết toán thuế" trên Facebook bùng nổ tương tác vào tháng 3 với hàng nghìn câu hỏi lặp đi lặp lại về cùng một vấn đề pháp lý.
* **Why underserved:** Phần mềm của chính phủ chỉ tập trung vào việc "thu nhận dữ liệu", không tập trung vào việc "hướng dẫn và tối ưu số thuế" cho người dân.

---

## 4. Strategy Statement

* **For:** Những cá nhân có thu nhập từ lương/thưởng bận rộn, không có chuyên môn về kế toán nhưng muốn thực hiện nghĩa vụ thuế chuẩn xác.
* **Who struggle with:** Việc tiêu tốn hàng giờ đồng hồ để giải mã các quy định thuế phức tạp, lo lắng về sai sót số liệu và ngại các thủ tục hành chính trực tiếp.
* **Our product helps them:** Hoàn tất hồ sơ quyết toán thuế TNCN trong dưới 15 phút với sự hỗ trợ của chuyên gia ảo (AI).
* **Through:** * Công nghệ OCR quét chứng từ tự động.
    * AI Agent được huấn luyện dựa trên kho dữ liệu luật thuế Việt Nam để tư vấn mức giảm trừ tối ưu nhất.
    * Tự động kết xuất file XML/PDF đúng chuẩn để nộp thẳng lên cổng thông tin điện tử.
* **Unlike:** Việc thuê dịch vụ kế toán ngoài (chi phí từ 500k - 2 triệu VNĐ) hoặc tự mày mò phần mềm HTKK phức tạp.
* **Because we can leverage:** Sức mạnh của AI trong việc "dịch" ngôn ngữ pháp lý sang ngôn ngữ bình dân và khả năng xử lý dữ liệu lớn để phát hiện các sai sót logic trước khi nộp hồ sơ.

---

## 5. Moat Hypothesis

**Moat mechanism:** Domain-Specific Feedback Loop (Vòng lặp tri thức chuyên biệt)

Nếu chúng ta triển khai [50.000] lần quyết toán trong [thị trường Việt Nam], các yếu tố sau sẽ được cải thiện vượt trội mà đối thủ ngoại (như ChatGPT thuần túy) không làm được:

* **Thư viện Prompt chuyên sâu:** Các kịch bản xử lý lỗi (ví dụ: lỗi trùng mã số thuế người phụ thuộc, lỗi lệch số lẻ giữa các chứng từ).
* **Cập nhật luật địa phương:** Hệ thống tự động hấp thụ các công văn giải đáp của Tổng cục Thuế theo từng tỉnh thành.
* **Dữ liệu hành vi:** Hiểu rõ các "điểm nghẽn" thường gặp của người dùng Việt để tối ưu UI/UX cho đến khi quy trình chỉ còn 1 nút bấm.

**Tại sao đối thủ khó sao chép:**
Đối thủ cần một đội ngũ vừa giỏi AI vừa am hiểu sâu sắc nghiệp vụ kế toán Việt Nam. Khi chúng ta đã có tệp dữ liệu người dùng lớn, AI của chúng ta sẽ "hiểu" các tình huống thuế thực tế tại Việt Nam chính xác hơn bất kỳ mô hình ngôn ngữ lớn nào khác.

---

## 6. Initial TAM / SAM / SOM view

| Layer | Estimate | Key assumptions | Confidence |
| :--- | :--- | :--- | :--- |
| **TAM** (Thị trường tổng thể) | ~5 triệu người | Số lượng cá nhân có mã số thuế và phát sinh thu nhập chịu thuế tại VN. | Low |
| **SAM** (Thị trường mục tiêu) | ~1 triệu người | Cá nhân làm việc tại các đô thị loại 1, có thói quen dùng app/ngân hàng số và tự quyết toán. | Median |
| **SOM** (Thị trường có thể chiếm lĩnh) | 100.000 người | Người dùng tiếp cận qua chiến dịch HR tại các tập đoàn lớn và kênh Freelancer. | Median |

**Top 3 unknowns requiring further research:**
1.  **Tính pháp lý của chữ ký số:** Người dùng cá nhân có sẵn lòng mua chữ ký số để nộp hồ sơ qua app không hay vẫn phải in ra giấy?
2.  **Giá trị sẵn lòng chi trả (WTP):** 50k là mức giá rẻ, nhưng nếu thu theo % số thuế được hoàn thì khách hàng có thích hơn không?
3.  **API Chính phủ:** Cổng thông tin Thuế điện tử có mở API để đẩy dữ liệu trực tiếp không hay phải qua bước trung gian là file XML.

**Judgment:**
* [x] **Worth pursuing now:** Nhu cầu cực kỳ lớn và chưa có "ông lớn" nào chiếm lĩnh mảng AI cho Thuế cá nhân tại VN.

---

## 7. Positioning Note (2 sentences)

**What we are:**
Chúng tôi là một nền tảng "Trợ lý ảo về Thuế" sử dụng AI để tự động hóa việc lập hồ sơ quyết toán thuế TNCN từ ảnh chụp chứng từ, giúp đảm bảo tính tuân thủ pháp luật tuyệt đối cho người dùng.

**What we are not / not yet:**
Chúng tôi không phải là cơ quan đại diện pháp luật hay tổ chức thay thế Tổng cục Thuế; chúng tôi đóng vai trò là "màng lọc" và "bộ não hỗ trợ" giúp hồ sơ của bạn sạch và đúng trước khi gửi đi. Chúng tôi hiện chưa hỗ trợ các loại thuế phức tạp khác như thuế doanh nghiệp hay thuế chuyển nhượng bất động sản đặc thù.

---

## 8. Self-assessment before Day 17

**Mắt xích yếu nhất:** Market Size & Business Model.

Mặc dù ước tính được số người nộp thuế, nhưng việc chuyển đổi họ từ "tự làm miễn phí nhưng khổ" sang "trả phí để sướng" cần một chiến lược định giá và marketing rất sắc bén. Ngoài ra, rào cản về việc bảo mật dữ liệu tài chính cá nhân cũng là một biến số lớn có thể làm thu hẹp quy mô thị trường thực tế (SOM).
