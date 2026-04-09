# 📄 REFLECTION REPORT — Nhóm 32 (Phòng E403)
**Dự án:** AI Agent "Copilot" cho khách hàng VinFast
**Người viết:** Nguyễn Thế Anh
**Vai trò:** Tính toán ROI & Xác định Eval Metrics

---

## 1. Vai trò & Đóng góp cụ thể

Trong khuôn khổ dự án xây dựng AI Agent cho VinFast, trọng tâm công việc của tôi nằm ở việc định lượng giá trị hệ thống (Business Value) và thiết lập hàng rào bảo vệ chất lượng (Quality Guardrails). Cụ thể:

* **Xác định Eval Metrics & Threshold:** Xây dựng bộ tiêu chuẩn đánh giá khắt khe để đảm bảo AI Agent không chỉ thông minh mà còn an toàn. Đã thiết lập 3 metrics cốt lõi:
    * *Recall (Safety Triggers) - Tối ưu Recall thay vì Precision:* Đặt ngưỡng ≥ 99% để triệt tiêu False Negatives trong các tình huống nguy hiểm (VD: lỗi phanh), chấp nhận đánh đổi bằng False Positives.
    * *Groundedness Score:* Đặt ngưỡng ≥ 95% để kiểm soát hiện tượng Hallucination, đảm bảo AI bám sát dữ liệu RAG (`data.json`) nội bộ.
    * *Task Completion Rate:* Đặt ngưỡng ≥ 40% để đo lường hiệu năng của Function Calling trong luồng Đặt lịch.
* **Phân tích ROI & Lập Kịch bản Pilot:** Mô hình hóa chi phí và lợi ích kinh tế với 3 kịch bản (Conservative, Realistic, Optimistic). Lập luận chặt chẽ bài toán tối ưu chi phí (sử dụng GPT-4o-mini) so với số giờ CSKH tiết kiệm được, chứng minh Net ROI dương (từ +5M đến +75M VNĐ) để tăng tính thuyết phục khi Pitching. Thiết lập "Kill Criteria" rõ ràng để quản trị rủi ro dự án.



## 2. Reflection Cá nhân (Tự đánh giá)

Dự án này là một lăng kính tuyệt vời để kết nối giữa nghiên cứu học thuật và sản phẩm thực tế. Khi làm việc sâu với các mô hình ngôn ngữ lớn (LLMs), chúng ta dễ bị cuốn vào việc tối ưu hóa cấu trúc kiến trúc, prompt engineering hay giảm thiểu loss function. Tuy nhiên, bài toán Product mang đến một áp lực khác biệt: **Tính khả thi và Trách nhiệm giải trình.**

Việc phụ trách mảng ROI và Eval Metrics buộc tôi phải nhìn AI dưới góc độ kinh doanh. Một mô hình mạnh đến đâu cũng vô nghĩa nếu chi phí vận hành "đốt" sạch lợi nhuận (âm ROI), hoặc nếu nó đưa ra một lời khuyên sai lầm gây nguy hiểm đến tính mạng người lái. Quyết định ưu tiên Recall tuyệt đối cho Safety Trigger và thiết lập "Kill Criteria" dựa trên CSAT/ROI là minh chứng cho tư duy "AI an toàn và sinh lời". 

Khó khăn lớn nhất trong phần việc của tôi là việc lượng hóa các giá trị vô hình (như niềm tin của khách hàng) thành các con số có thể đo lường. Quá trình làm việc cùng team, tranh luận về việc "AI là Automation hay Augmentation", đã giúp tôi nhận ra vai trò thực sự của Copilot: Không phải thay thế hoàn toàn con người, mà là tối ưu hóa luồng công việc để con người xử lý những vấn đề có giá trị cao hơn.