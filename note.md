## 🔄 Luồng hoạt động của Hệ thống Web Application Firewall (WAF)

```mermaid
flowchart TD
    A[Người dùng (Client)] -->|Gửi yêu cầu HTTP/HTTPS| B[WAF]
    B -->|Phân tích gói tin| C{Phù hợp với chính sách?}
    C -->|✅ Hợp lệ| D[Chuyển tiếp yêu cầu đến Web Server]
    C -->|❌ Vi phạm chính sách| E[Ghi log & Chặn yêu cầu]
    D --> F[Web Server xử lý & phản hồi]
    F -->|Trả về phản hồi| B
    B -->|Lọc phản hồi nếu cần (Response Filtering)| G[Trả phản hồi về Client]
    E --> H[Thông báo cảnh báo cho Admin]
