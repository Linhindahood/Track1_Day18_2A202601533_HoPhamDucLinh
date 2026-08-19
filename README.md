# Track 1 — Day 18 · Three Solution Options & Micro-Prototypes

## 1. Thông tin cá nhân và nhóm

| | |
|---|---|
| **Họ và tên** | Hồ Phạm Đức Linh |
| **MHV** | 2A202601533 |
| **Tên nhóm** | JCungdc-1 |
| **Case study** | **AI Support Radar** (VLearn) — tiếp nối đúng case đã làm ở Day 17 |
| **Track / Day** | Track 1 · Day 18 |

### Thành viên nhóm

| Thành viên | MHV | Option sở hữu chính |
|---|---|---|
| Hồ Phạm Đức Linh | 2A202601533 | **Option A** — Consent-First Support Queue |
| Vương Hưng | 01789 | **Option B** — Nút ẩn danh + AI gom chủ đề |
| Hoàng Việt | 01543 | **Option C** — Slide Copilot theo ngữ cảnh |

### Bối cảnh lớp học (dùng chung cho cả A/B/C)

Buổi lab *Deep Learning Cơ Bản*, phòng D302 — khoảng **150 học viên**, **1 giảng viên**, **3–4 Lab Coach**. Hai kênh hỗ trợ đã tồn tại sẵn: Lab Coach xuống tận bàn ngay trong giờ, và giảng viên giảng lại ở cuối buổi.

---

## 2. Hypothesis Problem (bản nhóm dùng trong Day 18)

> Học viên biết mình không hiểu ngay tại lớp, nhưng **ngại giơ tay hỏi trước đám đông** và **sợ làm mất thời gian của cả lớp** — nên các bạn im lặng rồi tự xoay xở. Cùng lúc đó, mỗi **Lab Coach phải để mắt tới khoảng 40 bạn** nên không biết nên đến bàn nào trước. Kết quả: chỗ chưa hiểu bị bỏ qua, còn Lab Coach thì đi hỗ trợ gần như ngẫu nhiên.

### Đây là bản v2 — đã sửa so với Day 17

| Bằng chứng từ phỏng vấn Day 17 | Giả định v1 bị đập | Nhóm xử lý |
|---|---|---|
| Lab Coach: *"gần như không bị nhầm"*, dành ~90% thời gian đi quanh lớp quan sát | "Lab Coach mù thông tin, không biết đến bàn nào" | Bỏ pain "coach không phát hiện được" |
| ~40 học viên / 1 coach | Nút thắt là *phát hiện* | Đổi thành **thứ tự ưu tiên & năng lực xử lý** |
| Lab Coach báo tình hình lớp về **bên vận hành**, không báo giảng viên | Quy trình "Giảng viên duyệt → điều phối Coach" | Hạ giảng viên xuống actor phụ; Lab Coach thành actor chính của Option A |
| HV#1: *"vô nghĩa, không thể xảy ra được"*; không muốn biết hệ thống ghi nhận gì | Học viên chấp nhận bị theo dõi hành vi | Thêm ràng buộc **ẩn danh + xin đồng ý (consent-first)** |
| HV#2 (QT): tự tra ra trong *"mấy phút"* | Pain đủ lớn để đổi hành vi | Alternative hiện tại đã "đủ tốt" → mọi option phải cạnh tranh với nó |
| HV#2: *"sợ mất thời gian chung của giảng viên"* | Pain là phát hiện | Pain thật = **ngại + sợ mất thời gian của lớp** |

**Điều gì khiến nhóm bác bỏ hypothesis này:** nếu người test cho rằng tự tra AI/Google là đủ và không muốn bất kỳ hình thức can thiệp nào, hoặc nếu Lab Coach nói thứ tự ưu tiên do hệ thống đề xuất không đáng tin bằng quan sát của họ.

---

## 3. Three Solution Options

Ba option được tách theo đúng **một trục: ai phát tín hiệu** — để mỗi option kiểm chứng một giả định rủi ro khác nhau, thay vì là ba phiên bản giao diện của cùng một ý tưởng.

| | **A — Consent-First Support Queue** | **B — Nút ẩn danh + AI gom chủ đề** | **C — Slide Copilot theo ngữ cảnh** |
|---|---|---|---|
| Ai phát tín hiệu | Hệ thống suy luận từ thao tác | Học viên — một chạm, ẩn danh | Học viên tự hỏi, tự gỡ |
| Ai can thiệp | **Lab Coach** xuống tận bàn trong giờ | **Giảng viên** giảng lại cuối buổi | Không ai — AI trả lời tại chỗ |
| Parking Lot | #3 | #1 + #5 | #4 |
| Owner | Đức Linh | Vương Hưng | Hoàng Việt |
| Được gì | Bắt được nhóm im lặng và **không tự biết mình đang bí** — nhóm mà B và C bỏ sót | Gỡ nỗi ngại mà **không giám sát ai**; rẻ và khả thi nhất | Trả lời **tức thì đúng slide** — cạnh tranh trực diện với thói quen tự tra vài phút |
| Đánh đổi | Suy đoán có thể sai; chạm ngưỡng riêng tư nên phải xin đồng ý trước khi gọi coach | Chỉ bắt được chỗ học viên **biết** là mình chưa hiểu; phản hồi đến muộn ở 5 phút cuối buổi | Bỏ hẳn vai trò Lab Coach; AI có thể sai; người ngại vẫn không gõ câu hỏi |
| Giả định rủi ro nhất | Tín hiệu hành vi có phân biệt được "đang bí" vs "đang làm việc riêng"? | Gỡ nỗi ngại rồi thì học viên có **thật sự bấm** không? | Nhanh hơn & đúng ngữ cảnh hơn có đủ để đổi hành vi không? |

**Điểm mù chung của cả ba:** học viên **không biết là mình không biết** — *"có những câu hỏi mình biết cái để hỏi, còn một số khác thì không"* (HV#2). Không option nào hiện xử lý được lớp lỗ hổng này.

Chi tiết: [`three-option-design-sheet.md`](./three-option-design-sheet.md) · Link prototype: [`prototype-link.md`](./prototype-link.md)

### Kết quả test A/B/C (3 phiên, 3 người ngoài nhóm)

| Người test | Vai trò | Chọn |
|---|---|---|
| Nguyễn Mạnh Tú | Lab Coach · D303 | Không chọn đơn lẻ — ưu tiên **C → A** gộp thành một luồng |
| Tạ Thị Nga | Học viên · D303 | **C** (nếu chỉ so A với B thì chọn B) |
| Đoàn Văn Tuyền | Học viên · D304 | **C** |

**Next Change:** gộp **C → A** thành một luồng nối tiếp — Copilot là điểm chạm đầu tiên, chỉ khi Copilot không gỡ được mới sinh request tới Lab Coach/giảng viên, và request đó mang theo **nội dung học viên đã trao đổi với AI** thay vì chỉ một cảnh báo hành vi. Nhóm **dừng** dùng telemetry im lặng làm nguồn tín hiệu chính của Support Queue.

Đầy đủ: [`group-feedback-synthesis.md`](./group-feedback-synthesis.md)

---

## 4. Đóng góp của tôi trong nhóm

| Hạng mục | Việc cụ thể tôi đã làm |
|---|---|
| **Option sở hữu** | Option A — Consent-First Support Queue. Thiết kế toàn bộ luồng: Support Queue xếp theo thứ tự ưu tiên → modal "vì sao học viên này ở đầu hàng đợi" → lời mời consent phía học viên → màn "xem hệ thống đang thấy gì về mình". |
| **Shared context / content** | Viết bản **bối cảnh chung dùng cho cả A/B/C** (lớp D302, 150 học viên, 1 giảng viên, 3–4 Lab Coach, đang chiếu Slide 14/32 — Backpropagation) để ba prototype đứng trên cùng một tình huống, tránh việc người test so sánh nhầm giữa ba bối cảnh khác nhau. |
| **Sửa Hypothesis Problem** | Phát hiện bản Day 17 mâu thuẫn với chính dữ liệu phỏng vấn (coach nói họ *phát hiện được*), đề xuất và chốt bản v2 với nhóm. |
| **Practice Note** | Viết note từ cuộc phỏng vấn **Học viên #2 (QT)** — bao gồm phần chỉ ra 4 điểm dữ liệu phản bác chính Option A do tôi sở hữu. |
| **Human–AI decisions** | Xem [`ai-support-log.md`](./ai-support-log.md) — ghi rõ chỗ nào tôi nhận đề xuất của AI, chỗ nào tôi bác và tự sửa. |
| **Facilitation** | Facilitate phiên test theo thứ tự **A → B → C** với **Tạ Thị Nga** (học viên, D303) — người ngoài nhóm. |
| **Observation** | Ghi observation phiên do tôi facilitate: [`prototype-feedback-note.md`](./prototype-feedback-note.md) |
| **Tổng hợp feedback** | Chủ trì gộp 3 feedback thành **một** Next Change: [`group-feedback-synthesis.md`](./group-feedback-synthesis.md) |
| **Tài liệu nhóm** | Viết bản phân công Day 18, design brief Option A, và deck 3 slide trình bày nhóm/pain point/trade-off. |

---

## 5. Cấu trúc repo

```
Track1_Day18_2A202601533_HoPhamDucLinh/
├── README.md                        # file này
├── three-option-design-sheet.md     # mô tả chi tiết A/B/C
├── prototype-link.md                # link A/B/C chung của nhóm
├── prototype-feedback-note.md       # phiên do chính tôi facilitate
├── group-feedback-synthesis.md      # gộp 3 feedback → 1 Next Change
└── ai-support-log.md                # nhật ký dùng AI
└── VLearn-Micro-Prototypes.html     # file demo 3 solution options
```