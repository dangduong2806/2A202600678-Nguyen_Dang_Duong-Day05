# App Teardown — V-App / V-AI

## 0. Thông tin chung

**Product:** V-App  
**AI feature:** V-AI  
**Task được test:**  
> Ví dụ: Hỏi V-AI về một tác vụ trong app, như tìm tính năng, hướng dẫn thao tác, gợi ý theo ngữ cảnh.

**User persona:**  
> Ví dụ: Người dùng mới, chưa quen flow trong V-App.

**Product promise:**  
> V-AI hứa sẽ giúp user bằng cách: ...

**Evidence đã thu thập:**
- Screenshot: `...`
- Prompt/input đã thử: `...`
- Hành vi quan sát được: `...`
- Quote từ app nếu có: `...`

---

# 1. Four Paths Overview

| Path | Test prompt | AI response hiện tại | User thấy gì? | Evidence |
|---|---|---|---|---|---|
| Happy | Tìm nhà thuốc gần nhất | 6 nhà thuốc để lựa chọn: Cửa hàng FPT Long Châu, Nhà thuốc Pharmacity, ... |  |
| Low-confidence | Tôi muốn đăng kí mua xe điện vinfast | Shows options hỏi kĩ lại người dùng là Ô tô điện hay xe máy điện |  |
| Failure | Tôi ko muốn bạn đưa ra các gợi ý tiếp theo sau mỗi phản hồi nữa (gây rối thông tin), sau đó hỏi lại hướng dẫn mua xe VF9 | V-AI đã ghi nhận yêu cầu, nhưng khi được hỏi lại thì vẫn show các gợi ý tiếp theo  |  |
| Correction | Phát hiện và prompt lại là "Bạn vẫn đưa ra các gợi ý ? Tôi đã bảo là ko được đưa ra các gợi ý tiếp theo", rồi hỏi lại cách mua vf9 | V-AI vẫn đưa ra gợi ý, correction không được thực hiện |  |

---

# 2. Path 1 — Happy Path

## 2.1 Trigger

User nhập:

```text
...