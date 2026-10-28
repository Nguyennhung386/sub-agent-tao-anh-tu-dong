---
name: tao-anh-model-theo-mau-flow
description: Tạo ảnh model AI (Lara) giống ảnh mẫu trên Google Flow theo 2 bước, dựng cảnh theo mẫu rồi đưa Lara (mặt và trang phục của cô ấy) vào. Dùng khi nói 'tạo ảnh Lara theo mẫu', 'làm ảnh giống ảnh mẫu trên Flow'.
---

# Tạo ảnh model theo ảnh mẫu trên Google Flow

Mục tiêu: với mỗi ảnh mẫu, tạo một ảnh mới có **cùng dáng, góc máy, bối cảnh và ánh sáng** như ảnh mẫu, còn **khuôn mặt và trang phục là của Lara**.

## Đầu vào

| Thư mục (trên máy Windows của người dùng) | Nội dung |
|---|---|
| `Downloads\LARa Model\ảnh mẫu` | Ảnh mẫu cần bắt chước (khoảng 55 ảnh) |
| `Downloads\LARa Model\Lara` | Ảnh của Lara: mặt và trang phục |
| `Downloads\LARa Model\Flow kết quả` | Nơi lưu ảnh kết quả (tạo mới nếu chưa có) |

Công cụ: Google Flow (https://labs.google/flow), model ảnh Nano Banana, mở trong Chrome đã đăng nhập tài khoản Google của người dùng.

## Quy tắc mặc định

- **Lara mặc đồ của chính cô ấy**, lấy từ ảnh trong thư mục `Lara`. Không lấy trang phục của ảnh mẫu.
- Từ ảnh mẫu chỉ lấy: dáng người, góc máy, bố cục, bối cảnh, ánh sáng, tông màu.
- Mỗi lần dùng **1 ảnh Lara** thấy rõ mặt và trang phục (ưu tiên ảnh nửa người hoặc toàn thân). Chọn ảnh có góc mặt và kiểu khung hình gần ảnh mẫu nhất. Nếu ảnh có trang phục không thấy rõ mặt, thêm 1 ảnh mặt Lara nhìn thẳng.

## Quy trình 2 bước cho mỗi ảnh mẫu

Làm 1 bước một lần thì Flow hay giữ luôn mặt và đồ của người mẫu cũ. Tách thành 2 bước cho kết quả ổn định hơn.

### Bước 1: Dựng cảnh theo ảnh mẫu

1. Tạo ảnh mới trên Flow, thêm **ảnh mẫu** làm ảnh tham chiếu (ingredient).
2. Dán prompt **Bước 1** trong [`prompts.md`](prompts.md), điền phần mô tả cảnh, dáng và ánh sáng.
3. Chọn đúng tỉ lệ khung hình giống ảnh mẫu (dọc 9:16 / 3:4, ngang 16:9...).
4. Tạo ảnh, chọn ảnh giống mẫu nhất về dáng, nền, ánh sáng.

### Bước 2: Đưa Lara vào (mặt + trang phục)

1. Tạo ảnh mới, thêm ảnh tham chiếu: ảnh vừa tạo ở bước 1 và ảnh Lara (thêm ảnh mặt Lara nếu cần).
2. Dán prompt **Bước 2** trong [`prompts.md`](prompts.md). Prompt luôn mở đầu bằng *"GIỮ NGUYÊN 100% khuôn mặt và trang phục..."* của Lara và yêu cầu giữ nguyên dáng, nền, ánh sáng của ảnh bước 1.
3. So sánh với ảnh Lara. Nếu mặt hoặc đồ chưa giống, tạo lại hoặc đổi sang ảnh Lara khác.

## Thử trước, làm hàng loạt sau

1. Làm **1 ảnh thử** trọn 2 bước.
2. Ghép ảnh so sánh (ảnh mẫu, ảnh bước 1, ảnh bước 2, ảnh Lara) gửi người dùng duyệt.
3. Hỏi rõ: mặt và đồ đã đủ giống Lara chưa, có được tải ảnh về máy không.
4. Chỉ khi người dùng đồng ý mới làm các ảnh mẫu còn lại.

## Để ảnh sắc nét

- Dùng ảnh tham chiếu (ảnh mẫu, ảnh Lara) gốc, độ phân giải cao, không mờ, không ảnh chụp màn hình.
- Thêm câu tăng độ nét trong [`prompts.md`](prompts.md) vào cuối prompt Bước 2.
- Khi tải, chọn **mức phân giải cao nhất** mà menu Tải xuống của Flow cho phép (bản phóng to 2K/4K nếu có).
- Nếu ảnh vẫn chưa đủ nét, phóng to thêm bằng công cụ upscale riêng, không chỉnh lại khuôn mặt.

## Tải ảnh về

- Tải bằng **nút Tải xuống (Download) của Flow** để lấy ảnh đầy đủ chất lượng. Không chụp màn hình, không lưu ảnh xem trước.
- Lưu vào `LARa Model\Flow kết quả`, đặt tên theo ảnh mẫu, ví dụ `mau-01_lara.png`.
- Ghi lại ảnh nào lỗi / cần làm lại để báo người dùng khi xong cả bộ.

## Lưu ý

- Không đưa ảnh của Lara hay ảnh mẫu lên kho GitHub công khai.
- Flow có giới hạn lượt tạo ảnh. Nếu hết lượt hoặc bị chặn nội dung, dừng lại và báo người dùng.
