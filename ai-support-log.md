# AI SUPPORT LOG — NHẬT KÝ SỬ DỤNG TRỢ LÝ AI

> **Khóa học / Track**: Track 1 - AI Product Management / Product Metrics  
> **Họ và tên học viên**: Nguyễn Thị Minh Khánh  
> **Mã học viên**: 2A202602546  
> **Dự án**: StudyMate AI - Trợ lý AI Luyện đề & Ôn thi Thông minh  

---

## 1. AI ĐÃ GIÚP TÔI Ở ĐÂU?

* **Phản biện & Kiểm tra JTBD (Core Job to be Done):**  
  AI đóng vai *sinh viên đại học khó tính và bận rộn* để phản biện các giả định ban đầu, giúp làm sắc nét Job-to-be-Done thực tế: Sinh viên không cần một chatbot để trò chuyện dài dòng, mà cần một công cụ giải quyết bài toán thi cử cấp bách — biến slide bài giảng 60 trang thành bộ câu hỏi test nhanh trong 5 phút để biết ngay mình đang hổng kiến thức ở đâu.

* **Brainstorming rủi ro của sản phẩm AI & Counter-metrics:**  
  AI gợi ý các kịch bản lỗi đặc thù của mô hình GenAI trong giáo dục (ảo giác kiến thức, đáp án sai lệch, câu hỏi mơ hồ), từ đó giúp tôi xây dựng Counter-metric sắc bén AI Error / Hallucination Report Rate (với trần kiểm soát $\le 2\%$) để bảo vệ uy tín học thuật của sản phẩm.

* **Chuẩn hóa Naming Convention & Tracking Spec:**  
  AI hỗ trợ gợi ý quy chuẩn đặt tên Event dạng object_action (user_signed_up, document_uploaded, quiz_completed, quiz_shared...) và cung cấp cú pháp mẫu cho 2 tiêu chí nghiệm thu (Acceptance Criteria) chống bắn event sớm và chống trùng lặp do reload.

* **Hỗ trợ trực quan hóa:**  
  AI hỗ trợ viết mã nguồn sơ đồ Mermaid cho Product Loop và render công thức toán học LaTeX cho các chỉ số Metric.

---

## 2. AI SAI, HỜI HỢT HOẶC ĐỀ XUẤT METRIC SAI NATURE Ở ĐÂU?

* **Đề xuất Core Action hời hợt & rơi vào bẫy System Output:**  
  Ban đầu, AI đề xuất chọn document_uploaded (hành vi đầu vào) hoặc quiz_generated (System Output của AI) làm Core Action. Tôi nhận ra đây là lỗi kinh điển vì AI tạo đề thành công không có nghĩa là sinh viên đã học và hiểu kiến thức. Ngoài ra, AI gợi ý đếm số lượt nộp bài thuần túy mà không có ngưỡng chất lượng (Quality Threshold), điều này rất dễ bị game hoặc phản ánh sinh viên làm bừa.

* **Ép Cadence sai bản chất tự nhiên (Bẫy Daily DAU & D7 Retention):**  
  AI có xu hướng áp đặt mô hình của app học ngoại ngữ giải trí (như Duolingo) và đề xuất đo lường DAU và D1 / D7 Retention. Điều này hoàn toàn sai lệch với Natural Cadence của sinh viên đại học (học theo tín chỉ 2-3 buổi/tuần và thi cử định kỳ). Nếu ép Daily sẽ thúc đẩy đội ngũ phát triển tính năng ép dùng độc hại.

* **Thiết kế vòng lặp dựa dẫm vào Push Notification & Streak:**  
  AI từng đề xuất cơ chế giữ chân bằng cách gửi push notification liên tục và tạo chuỗi streak điểm thưởng ảo. Đây là biểu hiện của một Product Loop giả tạo vì nó không xuất phát từ giá trị tự nhiên của sản phẩm.

---

## 3. TÔI ĐÃ TỰ SỬA HOẶC QUYẾT ĐỊNH LẠI ĐIỀU GÌ?

* **Tự quyết định Core Action có Quality Threshold (Score $\ge 70\%$):**  
  Tôi quyết định chọn hành vi quiz_completed với điều kiện bắt buộc score >= 70% (hoặc xem hết 100% giải thích câu sai) mới được xem là *Qualified Core Action*. Quyết định này giúp North Star Metric phản ánh đúng giá trị học tập thực chất.

* **Tự xác lập chuẩn Weekly Cadence (7 ngày) & Weekly Cohorts:**  
  Tôi tự quyết định chọn nhịp đo Weekly cho StudyMate AI dựa trên phân tích lịch học đại học thực tế tại Việt Nam, thiết lập hệ thống Weekly Rolling Windows (W1..W12) khớp với thời lượng 1 học kỳ (12–15 tuần).

* **Tự thiết kế Stored Value (Sổ tay lỗi sai) làm động lực giữ chân không cần Notification:**  
  Tôi tự kiến tạo cơ chế lưu trữ câu sai vào *Sổ tay lỗi sai* (Saved State / Investment) để biến dữ liệu học tập thành lý do quay lại tự nhiên cho sinh viên. Đồng thời, tôi thiết kế thêm *Collaborative Loop* (chia sẻ đề cho nhóm bạn học cùng lớp) để tận dụng sức mạnh của học nhóm (Peer Learning).

* **Tự viết 100% Rationale, Metric Hypothesis & Hợp đồng Retention 6 thành phần:**  
  Tôi trực tiếp chịu trách nhiệm lập luận, bảo vệ toàn bộ tính logic từ Core Action $\rightarrow$ Cadence $\rightarrow$ Metric System $\rightarrow$ Retention $\rightarrow$ Product Loop $\rightarrow$ Minimum Tracking Spec.

---

### TỰ ĐÁNH GIÁ TUÂN THỦ NGUYÊN TẮC SỬ DỤNG AI
- [x] Không để AI chọn thay Core Action hoặc viết thay kết luận Cadence.
- [x] Không bịa đặt số liệu benchmark hay retention không có cơ sở.
- [x] Tự viết và chịu trách nhiệm 100% về phần Rationale và Reflection.
- [x] Đã phản biện và loại bỏ các đề xuất sai nature của AI.
