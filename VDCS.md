[Vận dụng chuyên sâu] Thiết kế giải pháp Prompting ứng dụng thực tế cho Kỹ thuật Prompting Nâng cao (Logic & Chuỗi)
BƯỚC 1: XÁC ĐỊNH ĐẦU VÀO & ĐẦU RA
Bài toán: Tự động hóa việc xử lý khiếu nại đổi trả hàng của cửa hàng (xử lý tin nhắn khách, kiểm tra lỗi và đưa ra câu trả lời).
Input (Đầu vào):
Tin nhắn phàn nàn của khách.
Dữ liệu đơn hàng từ hệ thống.
Chính sách đổi trả của cửa hàng (trong 7 ngày, còn nguyên tem).
Output (Đầu ra): Kết quả kiểm tra đơn, trạng thái xử lý ([Đồng ý] / [Từ chối] / [Cần hỏi thêm]) và tin nhắn trả lời khách hàng.
BƯỚC 2: MẪU PROMPT & KẾT QUẢ
Phần 1: Kiểm tra thông tin (Lọc lỗi dữ liệu)
Markdown
# Yêu cầu: Đọc tin nhắn khách và dữ liệu đơn hàng.
- Nếu khách thiếu mã đơn hàng hoặc sai thông tin, đánh dấu lỗi và yêu cầu khách gửi lại.
- Nếu đủ thông tin, chuyển sang bước xét duyệt tiếp theo.
Phần 2: Đưa ra quyết định và trả lời
Markdown
# Yêu cầu: Dựa vào thông tin đã lọc để xét theo chính sách (đổi trả trong 7 ngày).
- Nếu không đủ điều kiện: Từ chối khéo léo và giải thích lý do.
- Nếu hợp lệ: Soạn tin nhắn xin lỗi và hướng dẫn khách các bước tiếp theo.
Ví dụ chạy thực tế (Khi khách nhắn thiếu mã đơn):
Khách nhắn: "Shop ơi hàng bị lỗi, hoàn tiền ngay cho tôi!" (Quên không gửi mã đơn).

AI trả lời:

TRẠNG THÁI: [Cần bổ sung thông tin]
TIN NHẮN TRẢ LỜI: Chào bạn, shop rất xin lỗi vì sự cố này. Bạn vui lòng cung cấp giúp shop Mã đơn hàng để bên mình kiểm tra và hỗ trợ hoàn tiền ngay cho bạn nhé!
