# Track1_Day17

Thông tin cá nhân
- Họ và tên: Đặng Thái Nam Sơn
- MSSV: 2A202601413

Thông tin nhóm
Thành viên 

**Đề bài đã chọn**

Case C — AI Support Radar
Sau mỗi phiên học, hệ thống phân tích các tín hiệu như di chuyển giữa slide, dừng lâu hoặc xem lại, highlight và ghi chú, đánh dấu “Chưa hiểu”, thay đổi câu trả lời, và nội dung trao đổi với AI Chat.

AI tạo một Support Queue cho giảng viên, gồm:

Những học viên có thể cần hỗ trợ.
Phần nội dung mà họ có thể đang gặp khó khăn.
Các tín hiệu dẫn đến nhận định đó.
Một hành động hỗ trợ được đề xuất.
Giảng viên xem lại và quyết định có liên hệ với học viên hay không.

| Thành phần | Solution đã mô tả |
| Trigger | Kết thúc một phiên học |
| Input | Slide navigation, notes, answers và AI Chat |
| AI action | Suy đoán nhu cầu hỗ trợ và xếp mức ưu tiên |
| Output Support | Queue cho giảng viên |
| Human control | Giảng viên quyết định có can thiệp hay không |

**Người phù hợp để phỏng vấn:** ưu tiên hai learners và một coach/instructor. Nếu không có coach/instructor trong giờ lab, nhóm có thể phỏng vấn ba learners nhưng phải ghi rõ: “Vòng này chỉ có learner-side evidence; instructor-side job chưa được kiểm chứng.”