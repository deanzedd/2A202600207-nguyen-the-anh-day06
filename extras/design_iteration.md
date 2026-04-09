
## Design Iteration (Quá trình lặp lại thiết kế)

Sản phẩm không đi theo một đường thẳng mà đã trải qua các vòng lặp thiết kế quan trọng để xử lý các rủi ro phát sinh:

* **Iteration 1: Q&A Bot thuần túy -> Agentic Workflow.** Ban đầu, hệ thống chỉ dự kiến trả lời câu hỏi RAG. Tuy nhiên, khi áp dụng metric *Task Completion*, nhận thấy việc chỉ cung cấp thông tin không giải quyết triệt để "pain point" của khách. Thiết kế được nâng cấp thêm Native Function Calling để thực thi Action (đặt lịch).
* **Iteration 2: Từ "Trả lời mọi thứ" sang "Biết khi nào nên im lặng".** Khi đánh giá các Failure Modes (đặc biệt là Jailbreak và lỗi an toàn), hệ thống ban đầu quá "cố gắng" dự đoán lỗi xe. Sau khi review lại ngưỡng Recall 99%, thiết kế đã thay đổi: Bổ sung cơ chế **Safety Fallback** (Hàm `escalate_to_human`), ép AI từ chối chẩn đoán các lỗi mập mờ và hiển thị UI Cảnh báo ĐỎ.
* **Iteration 3: Tối ưu User Correction.** Nhận thấy người dùng có thể nhập sai thông tin đặt lịch, thay vì bắt user điền lại form từ đầu, luồng hội thoại được thiết kế lại để lưu Session State. Điều này giúp LLM tự cập nhật Context (VD: sửa giờ, sửa tên xe) một cách mượt mà, trực tiếp cải thiện *Task Completion Rate*.
## 3. Design Iteration (Quá trình lặp lại thiết kế)

Sản phẩm không đi theo một đường thẳng mà đã trải qua các vòng lặp thiết kế quan trọng để xử lý các rủi ro phát sinh:

* **Iteration 1: Q&A Bot thuần túy -> Agentic Workflow.** Ban đầu, hệ thống chỉ dự kiến trả lời câu hỏi RAG. Tuy nhiên, khi áp dụng metric *Task Completion*, nhận thấy việc chỉ cung cấp thông tin không giải quyết triệt để "pain point" của khách. Thiết kế được nâng cấp thêm Native Function Calling để thực thi Action (đặt lịch).
* **Iteration 2: Từ "Trả lời mọi thứ" sang "Biết khi nào nên im lặng".** Khi đánh giá các Failure Modes (đặc biệt là Jailbreak và lỗi an toàn), hệ thống ban đầu quá "cố gắng" dự đoán lỗi xe. Sau khi review lại ngưỡng Recall 99%, thiết kế đã thay đổi: Bổ sung cơ chế **Safety Fallback** (Hàm `escalate_to_human`), ép AI từ chối chẩn đoán các lỗi mập mờ và hiển thị UI Cảnh báo ĐỎ.
* **Iteration 3: Tối ưu User Correction.** Nhận thấy người dùng có thể nhập sai thông tin đặt lịch, thay vì bắt user điền lại form từ đầu, luồng hội thoại được thiết kế lại để lưu Session State. Điều này giúp LLM tự cập nhật Context (VD: sửa giờ, sửa tên xe) một cách mượt mà, trực tiếp cải thiện *Task Completion Rate*.