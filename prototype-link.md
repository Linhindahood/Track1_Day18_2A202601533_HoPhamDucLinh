# Prototype Link — A/B/C (bản chung của nhóm)

**Nhóm:** JCungdc-1 · **Case:** AI Support Radar (VLearn) · **Day:** 18

---

## Link chính

Cả ba option nằm trong **một file HTML tĩnh duy nhất**, chuyển qua lại bằng tab ở đầu trang. Người test bắt đầu từ tab **0. Bối cảnh**.

| | |
|---|---|
| **Link prototype (A/B/C)** | `VLearn-Micro-Prototypes.html` |
| **File nguồn** | `VLearn-Micro-Prototypes.html` |
| **Dạng** | HTML tĩnh, dữ liệu fake toàn bộ, **không gọi API, không backend** |

---

## Bản đồ tab

| Tab | Nội dung | Owner |
|---|---|---|
| **0. Bối cảnh** | Lớp D302 · ~150 học viên · 1 giảng viên · 3–4 Lab Coach · Slide 14/32 | chung |
| **A** | Consent-First Support Queue — góc nhìn Lab Coach + lời mời consent phía học viên | Đức Linh |
| **B** | Nút ẩn danh + AI gom chủ đề — góc nhìn học viên + màn Top 3 của giảng viên | Vương Hưng |
| **C** | Slide Copilot theo ngữ cảnh — khung chat cạnh slide + đường "Gọi Lab Coach" | Hoàng Việt |

Quay lại tab **0. Bối cảnh** bất cứ lúc nào sẽ **reset mọi thao tác** — dùng giữa hai người test.

---

## Cách chạy phiên test

1. Mở link, để ở tab **0. Bối cảnh**, đọc to phần bối cảnh cho người test.
2. Chuyển sang option đầu tiên **theo đúng thứ tự đã phân** (chống order bias):

   | Người facilitate | Thứ tự |
   |---|---|
   | Đức Linh | **A → B → C** |
   | Vương Hưng | B → C → A |
   | Hoàng Việt | C → A → B |

3. Với mỗi option: để người test tự khám phá, **không giải thích tính năng**. Sự bối rối của họ chính là dữ liệu.
4. Sau khi xem đủ ba option, hỏi đúng 4 câu ở phần dưới.
5. Reset về tab 0 trước người test tiếp theo.

## Bốn câu hỏi dùng chung — không đổi, không thêm

1. "Trong buổi học thật, bạn sẽ dùng cái nào? Kể cho mình nghe bạn dùng nó lúc nào."
2. "Vì sao bạn **không** dùng hai cái kia?"
3. "Cái nào khiến bạn thấy khó chịu hoặc không thoải mái? Chỗ nào cụ thể?"
4. "Nếu ngày mai cái này biến mất, bạn có nhớ nó không?"

## Không được làm

- Không hỏi "bạn có thích không" hay "cái này hay không".
- Không giải thích hệ thống dựa vào tín hiệu gì (Option A), không nói trước là AI sẽ hỏi ngược (Option C).
- Không hỏi câu giả định tương lai ("nếu có tính năng X thì bạn thấy sao").
- Không test với người trong nhóm.