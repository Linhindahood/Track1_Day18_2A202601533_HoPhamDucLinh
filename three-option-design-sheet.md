# Three Option Design Sheet

**Nhóm:** JCungdc-1 · **Case:** AI Support Radar (VLearn) · **Day:** 18

---

## 0. Bối cảnh chung — dùng cho cả A, B, C

Buổi lab **Deep Learning Cơ Bản**, phòng **D302** · ~**150 học viên** · **1 giảng viên** · **3–4 Lab Coach** · đang chiếu **Slide 14 / 32 — Backpropagation: phép chuyển vị (Transpose)**.

Người test được đặt vào vai **học viên đang ngồi trong buổi này và đang vướng ở Slide 14**. Cả ba prototype dùng đúng một nội dung học và một thời điểm, để chênh lệch feedback đến từ *cơ chế*, không phải từ *bối cảnh*.

### Trục phân biệt ba option

```
AI TỰ SUY LUẬN  →  HỌC VIÊN TỰ PHÁT TÍN HIỆU  →  HỌC VIÊN TỰ GIẢI QUYẾT
     (A)                      (B)                          (C)
```

Nếu ba option chỉ khác giao diện, feedback khi test sẽ vô giá trị — đây là tiêu chí nhóm dùng để kiểm tra trước khi build.

---

## Option A — Consent-First Support Queue

**Owner:** Hồ Phạm Đức Linh · **Parking Lot #3** · **Người can thiệp:** Lab Coach, ngay trong giờ

### Cơ chế
Hệ thống đọc **thao tác của học viên trên máy** (dừng lâu ở một slide, đổi đáp án nhiều lần, quay lại slide cũ, hỏi AI chat lặp một khái niệm) → suy ra tín hiệu "có thể đang bí" → xếp thành **hàng đợi ưu tiên** cho Lab Coach. Trước khi coach được gọi, học viên **nhận lời mời và tự chọn**: *"Có, nhờ coach ghé qua"* / *"Không, mình ổn"* / *"Xem hệ thống đang thấy gì về mình"*.

Không đọc camera, không đọc màn hình cá nhân. Hàng đợi hiển thị **mã ẩn danh + vị trí chỗ ngồi**, không hiện tên.

### Màn hình trong prototype
1. **Support Queue** (góc nhìn Lab Coach) — 3 thẻ ưu tiên, mỗi thẻ có tín hiệu chính + **nhãn độ tin cậy**; dải thống kê *đang chờ / đã hỗ trợ / tự đánh dấu "Tôi ổn"*; nhấn mạnh **xếp theo thứ tự ưu tiên, không xếp theo thời gian chờ**.
2. **Modal chi tiết HV-2841** — dòng thời gian 3 tín hiệu thô đã tạo ra gợi ý, nội dung nghi vấn (Slide 14), khối **"Hệ thống không biết"**, và nút *"Bỏ qua — tôi đã quan sát thấy bạn này ổn"* / *"Tín hiệu sai"*.
3. **Lời mời phía học viên** — consent-first, ba lựa chọn, không có đường lờ đi.
4. **"Xem hệ thống đang thấy gì về mình"** — liệt kê tín hiệu đã ghi nhận, kèm câu thừa nhận *"Hệ thống không phân biệt được bạn đang bí hay đang làm việc riêng. Đây là suy đoán, không phải kết luận"* và dấu hiệu ngược lại (đã nộp đúng task 1). Có nút **"Tắt theo dõi buổi này"**.

### Chi tiết thiết kế cố ý
- Thẻ **độ tin cậy thấp** (*"Không thao tác 9 phút — có thể đang bí, cũng có thể đang làm việc khác"*) trông khác hẳn và **chờ lâu nhất nhưng xếp cuối** — mâu thuẫn này là để test xem coach có tin thứ tự ưu tiên không.
- Toàn bộ ngôn ngữ tránh từ phán xét: không "yếu", "kém", "at risk".

### Giả định rủi ro nhất
Tín hiệu hành vi có phân biệt được **"đang bí"** với **"đang làm việc riêng"** không? Và Lab Coach — người tự tin vào quan sát của chính mình — có làm theo thứ tự hệ thống đề xuất không?

### Điểm yếu đã biết trước khi test
HV#1 phản ứng tiêu cực với việc bị ghi nhận hành vi (*"vô nghĩa, không thể xảy ra được"*, không muốn biết hệ thống ghi gì). HV#2 gần như **vô hình** với telemetry: không dùng slide, không ghi chú, không nhắn hỏi.

---

## Option B — Nút ẩn danh + AI gom chủ đề

**Owner:** Vương Hưng · **Parking Lot #1 + #5** · **Người can thiệp:** Giảng viên, 5 phút cuối buổi

### Cơ chế
Dưới slide đang chiếu có một nút: **"Chỗ này khó hiểu — gửi ẩn danh"**. Một chạm là xong — không form, không đăng nhập. Lượt bấm chỉ mang theo **slide + thời điểm**. AI gom các lượt bấm (và phần mô tả tùy chọn) thành **Top 3 chủ đề nóng** cho giảng viên, kèm **ngưỡng ẩn danh**: chủ đề dưới 5 lượt bấm không hiển thị.

### Màn hình trong prototype
1. **Góc nhìn học viên** — slide + nút gửi ẩn danh; micro-copy nói rõ *"giảng viên chỉ thấy con số, không thấy tên"* và *"kết quả đến ở 5 phút cuối buổi, không phải ngay bây giờ"*.
2. **Sau khi bấm** — xác nhận đã gửi; ô tùy chọn nói rõ hơn chỗ vướng, có sẵn cả lựa chọn *"Mình không biết diễn đạt thế nào"*; nút **"Rút lại lượt bấm"**; trạng thái chờ *"Thắc mắc của bạn nằm trong nhóm 31 người"*.
3. **Góc nhìn giảng viên** — Top 3 chủ đề (Transpose · Chain rule · Khởi tạo trọng số) kèm slide, khung giờ, số lượt bấm, và ghi chú *"AI gom từ 4 cách diễn đạt khác nhau"*; nút **Giảng lại / Bỏ qua / Tách chủ đề**.
4. **Trạng thái "không bấm cũng được"** — hệ thống không ghi nhận việc bỏ qua, không nhắc lại, không tính chuyên cần.

### Giả định rủi ro nhất
Gỡ được nỗi ngại rồi thì học viên **có thật sự bấm** không? Hay nỗi ngại nằm ở chỗ khác — sợ bị nhìn thấy đang thao tác?

### Điểm yếu đã biết trước khi test
Chỉ bắt được chỗ học viên **biết** là mình chưa hiểu. Phản hồi đến muộn — người cần gỡ ngay tại slide 14 phải chờ đến cuối buổi.

---

## Option C — Slide Copilot theo ngữ cảnh (Socratic)

**Owner:** Hoàng Việt · **Parking Lot #4** · **Người can thiệp:** không ai — AI trả lời tại chỗ

### Cơ chế
Khung chat cạnh slide, **đã đồng bộ ngữ cảnh Slide 14**. AI chỉ đọc nội dung slide đang chiếu — không đọc bài làm của học viên. Sau khi trả lời, AI **hỏi ngược lại** một câu kiểm tra nhanh thay vì chỉ đưa đáp án. Nếu học viên chọn *"Tôi chọn đáp án này — nhưng không chắc lắm"*, hiện đường thoát **"Gọi Lab Coach"**.

### Màn hình trong prototype
1. **Slide + khung Copilot** — lời chào gắn với đúng slide, một lượt hỏi–đáp về phép Transpose.
2. **Kiểm tra nhanh (Socratic)** — hai đáp án về lệch kích thước ma trận, kèm nút "không chắc lắm".
3. **Gọi Lab Coach** — xác nhận *"đã gọi Coach — vị trí #2 trong hàng đợi"*, tức C có đường nối ngược về A.
4. Cảnh báo cố định: *"AI có thể trả lời không chính xác. Hãy kiểm chứng nếu không chắc chắn."*

### Giả định rủi ro nhất
HV#2 đã tự tra ra trong *"mấy phút"*. Làm nhanh hơn và đúng ngữ cảnh hơn có đủ tạo giá trị để đổi hành vi không?

### Điểm yếu đã biết trước khi test
Bỏ hẳn vai trò Lab Coach — mâu thuẫn với mô hình vận hành hiện tại (3–4 coach đã có mặt tại lớp). AI có thể sai. Người ngại vẫn có thể không gõ câu hỏi.

---

## Bảng so sánh nhanh

| | A | B | C |
|---|---|---|---|
| Ai phát tín hiệu | Hệ thống | Học viên (1 chạm) | Học viên (tự hỏi) |
| Ai can thiệp | Lab Coach | Giảng viên | Không ai |
| Thời điểm giá trị đến | Trong vài phút | 5 phút cuối buổi | Tức thì |
| Mức riêng tư | Thấp nhất (có telemetry) | Cao nhất (ẩn danh hoàn toàn) | Trung bình (nội dung câu hỏi) |
| Chi phí triển khai | Cao | Thấp | Trung bình |
| Bắt được người *không biết mình bí* | ✅ | ❌ | ❌ |
| Bắt được người *ngại lên tiếng* | ✅ | ✅ | ✅ |
| Bắt được *"không biết cái để hỏi"* | ❌ | ❌ | ❌ |

## Ràng buộc thiết kế chung (rút từ phỏng vấn Day 17)

1. **Ẩn danh và không gắn mác** — không tên, không xếp hạng, không từ "yếu/kém/at risk".
2. **Không ai khác nhìn thấy được** — học viên không thấy ai đã bấm, và ngược lại.
3. **Luôn thừa nhận khi hệ thống đang đoán** — có nhãn độ tin cậy và khối "Hệ thống không biết".
4. **Luôn có đường từ chối** — "Không, mình ổn", "Không bấm cũng được", "Tắt theo dõi buổi này".