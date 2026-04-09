
## Research Notes (Ghi chú Nghiên cứu)

Để đưa ra được các con số và kiến trúc đánh giá trên, tôi đã tiến hành nghiên cứu sâu vào các khía cạnh sau:

* **Đánh giá hệ thống RAG (RAG Evaluation):** Việc đo lường Groundedness không thể chỉ dựa vào cảm quan. Đã nghiên cứu các phương pháp tiếp cận như RAGAS (Retrieval Augmented Generation Assessment) để đánh giá mức độ trung thành của câu trả lời sinh ra từ Context. Điều này đặc biệt quan trọng để xử lý bài toán Semantic Gap giữa truy vấn tiếng Việt và Data tiếng Anh.
* **Đánh đổi giữa Precision và Recall trong Safety-Critical Systems:** Tìm hiểu các case study về triển khai AI trong ngành ô tô. Phân tích toán học cho thấy chi phí khắc phục hậu quả (Cost of Failure) khi AI nhận diện trượt một cảnh báo lỗi nghiêm trọng cao hơn gấp nhiều lần chi phí điều hướng nhầm khách hàng sang tư vấn viên con người. Quyết định "Optimize Recall" được đưa ra dựa trên cơ sở này.
* **Token Economics & LLM Routing:** Nghiên cứu cấu trúc chi phí của OpenAI API. Lựa chọn GPT-4o-mini cho các tác vụ routing và intent mapping đơn giản để giữ chi phí ở mức ~$0.01/chat, đảm bảo tính khả thi (Feasibility) của mô hình ROI.
