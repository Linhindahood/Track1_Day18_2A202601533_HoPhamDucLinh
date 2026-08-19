# AI Support Log — Day 18

**Người viết:** Hồ Phạm Đức Linh (2A202601533) · **Nhóm:** JCungdc-1
**Công cụ:** Claude (chat) — dùng cho phân tích, viết tài liệu và dựng prototype tĩnh.

---

## 1. AI đã giúp gì

### 1.1. Phát hiện mâu thuẫn giữa hypothesis Day 17 và chính dữ liệu phỏng vấn
Đây là đóng góp có giá trị nhất. Khi tôi đưa file brainstorm Day 17 (kèm 3 bản phỏng vấn) và bảo "giúp tôi lên kế hoạch Day 18", AI không làm ngay mà chỉ ra rằng **hypothesis cũ mâu thuẫn với lời của chính người được phỏng vấn**:

- Bản Day 17 viết *"Lab Coach lúng túng không biết đến bàn nào"*, trong khi coach nói *"gần như không bị nhầm"* và dành ~90% thời gian đi quanh lớp quan sát.
- Bản Day 17 mô tả quy trình *"Giảng viên duyệt → điều phối Coach"*, trong khi coach nói thông tin lớp được báo về **bên vận hành**, không báo giảng viên.

Tôi tự đọc lại bản phỏng vấn và xác nhận cả hai điểm là đúng, rồi mới chốt sửa hypothesis sang bản v2.

### 1.2. Tách ba option theo một trục thay vì ba biến thể giao diện
Ý tưởng ban đầu của tôi có nguy cơ tạo ra ba phiên bản của cùng một Support Queue. AI đề xuất tách theo trục **"ai phát tín hiệu"** (hệ thống → học viên bấm → học viên tự gỡ), và đề xuất Option C là bản *làm ngược* — bỏ hẳn Support Queue. Tôi nhận đề xuất này.

### 1.3. Chỉ ra rằng luồng làm việc tôi tự nghĩ ra bị thiếu bước
Tôi định dừng ở "mỗi người làm 1 prototype". AI chỉ ra đề bài còn hai bước nữa: **test chéo đủ A/B/C** và **gộp 3 feedback thành một thay đổi** — đúng phần được chấm.

### 1.4. Soạn thảo
Bản phân công Day 18, design brief Option A gửi Claude Design, practice note từ phỏng vấn HV#2, deck 3 slide, và bộ tài liệu nộp này.

---

## 2. AI sai hoặc hời hợt ở đâu

### 2.1. Dựng sai mô hình vận hành của lớp — lỗi nghiêm trọng nhất
AI đọc câu *"mình coach cho khoảng 150 học viên"* trong bản phỏng vấn rồi suy ra tỉ lệ **1 Lab Coach / 150 học viên**, và viết con số này vào cả hypothesis lẫn slide. Thực tế lớp có **1 giảng viên và 3–4 Lab Coach**, mỗi coach bao quát khoảng 40 bạn. Câu trong phỏng vấn là góc nhìn cá nhân của một coach về quy mô lớp, không phải tỉ lệ nhân sự.

**Tôi tự sửa:** chỉ ra bối cảnh thật, đổi chỉ số thành `~40 / coach`, và tách rõ hai kênh can thiệp — **Lab Coach xuống tận bàn trong giờ** (Option A) và **giảng viên giảng lại cuối buổi** (Option B).

### 2.2. Dùng ngôn ngữ hàn lâm cho phần cần dễ hiểu nhất
AI viết pain point là *"chi phí xã hội của việc hỏi công khai quá cao"*. Đây là cách nói của sách, không phải cách người nghe hiểu ngay.

**Tôi tự sửa:** yêu cầu viết lại thành **"học viên ngại giơ tay hỏi trước đám đông"** và **"sợ làm mất thời gian của cả lớp"** — đúng chữ mà chính học viên đã nói.

### 2.3. Tự gán vai trò cho thành viên khi thiếu dữ liệu
AI tự phân practice note và option cho từng thành viên mà không hỏi, dẫn đến gán sai — tôi mới là người phỏng vấn HV#2 và làm Option A.

**Tôi tự sửa:** báo lại phân công đúng, AI cập nhật tài liệu.

### 2.4. Có xu hướng lấp đầy khung thay vì để trống
Ở bước đầu AI đề nghị "sinh ra 3 practice notes" — tức là **bịa dữ liệu phỏng vấn**. Sau đó chính AI cảnh báo lại rằng nhóm đã có 3 cuộc phỏng vấn thật và không được bịa. Đây là rủi ro lớn nhất khi dùng AI cho môn này: nó viết trôi chảy kể cả khi không có dữ liệu.

**Tôi tự đặt luật:** mọi phần feedback và observation trong repo này để **`[ĐIỀN]`** cho đến khi có phiên test thật. Không dòng nào được viết trước.

### 2.5. Suýt tổng hợp feedback khi feedback chưa tồn tại
Khi dựng bộ tài liệu nộp, AI có thể viết trọn phần "kết quả test" chỉ từ khung có sẵn. Tôi bắt để trống toàn bộ bằng ô `[ĐIỀN]` cho tới khi có ba phiên thật, rồi mới đưa nguyên văn báo cáo của ba tester vào để tổng hợp.

**Kết quả của việc chờ:** dữ liệu thật đi ngược dự đoán của nhóm. Không ai chọn Option A — kể cả chính Lab Coach. Nếu để AI viết trước, phần tổng hợp gần như chắc chắn đã nghiêng về A, vì đó là option nhóm đầu tư nhiều nhất.

---

## 3. Human–AI decisions — tôi giữ quyền quyết định ở đâu

| Quyết định | Ai quyết | Ghi chú |
|---|---|---|
| Sửa hypothesis sang bản v2 | **Tôi**, sau khi AI chỉ ra mâu thuẫn | Tôi tự đọc lại bản phỏng vấn để xác minh |
| Trục phân biệt ba option | AI đề xuất, **tôi chốt** | |
| Bối cảnh lớp (150 / 1 GV / 3–4 coach) | **Tôi** — AI đã dựng sai | |
| Cách diễn đạt pain point | **Tôi** — bác cách nói hàn lâm của AI | |
| Option A theo hướng consent-first | **Tôi**, dựa trên phản ứng của HV#1 | |
| Phân công thành viên | **Tôi** | AI gán sai lúc đầu |
| Nội dung feedback và observation | **Tôi** — ghi từ ba phiên test thật | AI chỉ dựng khung và soi mẫu chung sau khi có dữ liệu |
| Next Change và Still Unproven | **Tôi + nhóm** | AI đề xuất cách gộp C→A dựa trên ba báo cáo; tôi đối chiếu lại từng câu của tester trước khi chốt |

---

## 4. Điều tôi rút ra khi dùng AI cho case này

1. **AI mạnh ở việc soi mâu thuẫn trong tài liệu của chính mình** — nó bắt được hai chỗ hypothesis Day 17 tự đá nhau mà nhóm đã đọc qua nhiều lần vẫn không thấy.
2. **AI yếu ở bối cảnh vận hành thực tế** — mọi con số về nhân sự, quy trình, cách lớp chạy đều phải do người trong cuộc xác nhận. Nó suy ra từ một câu trong transcript và nói ra với giọng rất chắc chắn.
3. **Nguy hiểm nhất là lúc AI viết trôi chảy về thứ nó không có dữ liệu.** Cách chặn hiệu quả nhất là bắt nó để trống, chứ không phải bảo nó "viết cẩn thận hơn".
4. **Đưa dữ liệu thô cho AI tốt hơn đưa bản tóm tắt.** Khi tôi đưa nguyên transcript phỏng vấn thay vì bản đã tóm tắt ở README, chất lượng phân tích khác hẳn — vì các chi tiết như *"báo tới bên vận hành"* chỉ tồn tại trong bản thô.

5. **Chờ dữ liệu thật là quyết định đúng đắn nhất trong Day 18.** Ba tester đều không chọn Option A — option nhóm đầu tư nhiều nhất và cũng là option AI mô tả trôi chảy nhất. Nếu viết phần tổng hợp trước khi test, cả nhóm sẽ đã bảo vệ một kết luận sai bằng những câu chữ rất thuyết phục.