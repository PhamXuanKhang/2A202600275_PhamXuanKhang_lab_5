# UX Exercise - MoMo Moni AI

## Sản phẩm: MoMo - Trợ lý Moni AI (phân loại chi tiêu)

## As-is -> To-be

**As-is:**
- Chưa có cơ chế ghi nhớ ngữ cảnh (memory), nên mỗi lần mở lại ứng dụng gần như bắt đầu từ đầu.
- Chất lượng phản hồi chưa ổn định: nhiều trường hợp trả lời thiếu chắc chắn hoặc xử lý chưa tốt.

**To-be:**
- Lưu được ngữ cảnh người dùng để phân loại nhanh hơn, giảm thao tác lặp lại.
- Hiển thị mức độ tự tin (confidence) của AI; khi confidence thấp thì không tự động gắn nhãn.

---

## 4 luồng trải nghiệm chính

- **AI đúng**
- **AI không chắc**
- **AI sai**
- **Người dùng mất niềm tin**

---

### 1. AI đúng
- Khi hệ thống nhận diện đúng giao dịch và confidence vượt ngưỡng, hệ thống tự động gắn danh mục.
- UI hiển thị tag + biểu tượng danh mục, không yêu cầu người dùng xác nhận thêm.
- Mục tiêu UX: thao tác nhanh, ít gián đoạn.

### 2. AI không chắc
- Khi confidence dưới ngưỡng, hệ thống không auto-tag mà hỏi người dùng: *"Bạn có muốn phân loại giao dịch này không?"*
- Nếu người dùng đồng ý, hệ thống hỏi thêm thông tin để làm rõ ngữ cảnh (ví dụ: mục đích chuyển tiền, loại hàng hóa/dịch vụ).
- Mục tiêu UX: tránh gắn nhãn sai và tăng độ chính xác qua dữ liệu bổ sung.

### 3. AI sai
- Hệ thống gắn nhãn sai, người dùng phải sửa lại danh mục.
- Luồng hiện tại còn dài: mở chi tiết giao dịch -> chỉnh danh mục -> lưu (khoảng 3 bước).
- Vấn đề UX: chưa minh bạch việc AI có học từ lần sửa này hay không.

### 4. Người dùng mất niềm tin
- Sau nhiều lần sai, người dùng ngừng dùng auto-tag và chuyển sang nhập thủ công.
- Vấn đề UX: chưa có tùy chọn rõ ràng để tắt auto-tag, giảm mức tự động hóa, hoặc chuyển sang chế độ an toàn (fallback mode).

---

## Luồng yếu nhất: Luồng 3 + 4

- Khi AI sai, luồng khôi phục (recovery flow) còn nhiều bước và tốn thời gian.
- Thiếu vòng phản hồi rõ ràng: người dùng sửa nhưng không biết hệ thống đã học hay chưa.
- Chưa có cơ chế thoát an toàn cho người dùng mất niềm tin (ví dụ: chế độ "chỉ gợi ý, không tự gắn nhãn").

---

## Khoảng cách giữa marketing và trải nghiệm thực tế

- **Marketing:** "Moni giúp quản lý chi tiêu thông minh".
- **Thực tế:** auto-tag chỉ đạt khoảng 70% với giao dịch phổ biến; các trường hợp biên (chuyển khoản cá nhân, mua sắm online, giao dịch đa mục đích) dễ bị gắn sai hoặc bỏ sót.
- **Khoảng cách lớn nhất:** thông điệp truyền thông chưa mô tả rõ cách hệ thống xử lý khi AI không chắc hoặc dự đoán sai, dẫn đến kỳ vọng người dùng quá cao.

---

## Sketch luồng trải nghiệm

- **As-is:** Giao dịch mới -> AI auto-tag -> người dùng xem kết quả -> nếu sai thì tự vào sửa thủ công.
- **To-be:** Giao dịch mới -> AI đánh giá confidence ->
	- Nếu cao: auto-tag và hiển thị kết quả ngay.
	- Nếu thấp: hỏi xác nhận phân loại.
	- Nếu người dùng sửa: hệ thống ghi nhận chỉnh sửa, phản hồi rõ *"Đã ghi nhận để cải thiện cho lần sau"*.

