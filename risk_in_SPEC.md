# Phân tích rủi ro AI trong tuyển dụng

| # | Vấn đề AI có thể sai | User Story Path thiếu | Giải pháp |
|---|---|---|---|
| 1 | **Bias hệ thống** — Học theo pattern lịch sử → tự động hạ điểm CV nữ hoặc trường tỉnh dù năng lực tương đương | Không có bước audit hay debiasing sau mỗi batch tuyển dụng | Blind screening (ẩn tên, giới tính, trường); audit định kỳ; làm sạch training data trước |
| 2 | **Loại nhầm người giỏi** — Career changer có kỹ năng thực chiến nhưng title cũ không match keyword → bị loại oan | Không có cơ chế nhận diện transferable skills | Dùng semantic matching thay keyword; thêm trường "kỹ năng chuyển ngành"; chọn top 30 thay vì top 20, HR review buffer 10 |
| 3 | **Không có human review** — 480 người bị loại mà không ai kiểm tra → mất ứng viên tốt, rủi ro pháp lý | Không định nghĩa ai chịu trách nhiệm approve trước khi gửi reject | AI chỉ shortlist, HR phải approve; AI phải giải thích lý do xếp hạng; lưu audit log mọi quyết định |
| 4 | **Thiếu định nghĩa "phù hợp"** — AI tự suy diễn tiêu chí → kết quả không nhất quán giữa các lần chạy | Không có rubric chấm điểm được hiring manager xác nhận | Xây rubric rõ (kỹ năng bắt buộc 40%, kinh nghiệm 30%, kỹ năng phụ 20%, bằng cấp 10%); hiring manager ký duyệt trước khi chạy AI |