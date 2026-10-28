---
name: tao-anh-model-theo-mau-flow
description: Tạo ảnh model AI (Lara) giống ảnh mẫu trên Google Flow theo 2 bước, dựng cảnh theo mẫu rồi thay mặt thành Lara. Dùng khi nói 'tạo ảnh Lara theo mẫu', 'làm ảnh giống ảnh mẫu trên Flow'.
---

# Tạo ảnh model theo ảnh mẫu trên Google Flow

Mục tiêu: với mỗi ảnh mẫu, tạo một ảnh mới có **cùng dáng, bối cảnh, trang phục và ánh sáng** như ảnh mẫu, nhưng **khuôn mặt là Lara**.

## Đầu vào

| Thư mục (trên máy Windows của người dùng) | Nội dung |
|---|---|
| `Downloads\LARa Model\ảnh mẫu` | Ảnh mẫu cần bắt chước (khoảng 55 ảnh) |
| `Downloads\LARa Model\Lara` | Ảnh khuôn mặt / chân dung của Lara |
| `Downloads\LARa Model\Flow kết quả` | Nơi lưu ảnh kết quả (tạo mới nếu chưa có) |

Công cụ: Google Flow (https://labs.google/flow), model ảnh Nano Banana, mở trong Chrome đã đăng nhập tài khoản Google của người dùng.

## Quy tắc mặc định

- **Trang phục lấy theo ảnh mẫu.** Chỉ thay khuôn mặt thành Lara. Nếu người dùng muốn Lara giữ đồ của chính cô ấy thì phải được nói rõ.
- Giữ nguyên dáng người, góc máy, bố cục, nền, ánh sáng, màu sắc của ảnh mẫu.
- Mỗi lần chỉ dùng **1 ảnh mặt Lara rõ nét, nhìn thẳng** làm tham chiếu khuôn mặt. Chọn ảnh Lara có góc mặt gần với ảnh mẫu nhất nếu có.

## Quy trình 2 bước cho mỗi ảnh mẫu

Làm 1 bước một lần thì Flow hay giữ luôn mặt người mẫu cũ. Tách thành 2 bước cho kết quả ổn định hơn.

### Bước 1: Dựng cảnh theo ảnh mẫu

1. Tạo ảnh mới trên Flow, thêm **ảnh mẫu** làm ảnh tham chiếu (ingredient).
2. Dán prompt **Bước 1** trong [`prompts.md`](prompts.md), điền phần mô tả cảnh.
3. Chọn đúng tỉ lệ khung hình giống ảnh mẫu (dọc 9:16 / 3:4, ngang 16:9...).
4. Tạo ảnh, chọn ảnh giống mẫu nhất về dáng, nền, đồ, ánh sáng.

### Bước 2: Thay mặt thành Lara

1. Tạo ảnh mới, thêm **2 ảnh tham chiếu**: ảnh vừa tạo ở bước 1 và 1 ảnh mặt Lara.
2. Dán prompt **Bước 2** trong [`prompts.md`](prompts.md). Prompt luôn mở đầu bằng *"GIỮ NGUYÊN 100% khuôn mặt..."* của Lara và yêu cầu giữ nguyên mọi thứ khác của ảnh bước 1.
3. So sánh với ảnh mặt Lara. Nếu mặt chưa giống, tạo lại hoặc đổi sang ảnh mặt Lara khác góc hơn.

## Thử trước, làm hàng loạt sau

1. Làm **1 ảnh thử** trọn 2 bước.
2. Ghép ảnh so sánh (ảnh mẫu, ảnh bước 1, ảnh bước 2, ảnh mặt Lara) gửi người dùng duyệt.
3. Hỏi rõ: mặt đã đủ giống Lara chưa, trang phục theo mẫu hay theo Lara, có được tải ảnh về máy không.
4. Chỉ khi người dùng đồng ý mới làm các ảnh mẫu còn lại.

## Tải ảnh về

- Tải bằng **nút Tải xuống (Download) của Flow** để lấy ảnh đầy đủ chất lượng. Không chụp màn hình, không lưu ảnh xem trước.
- Lưu vào `LARa Model\Flow kết quả`, đặt tên theo ảnh mẫu, ví dụ `mau-01_lara.png`.
- Ghi lại ảnh nào lỗi / cần làm lại để báo người dùng khi xong cả bộ.

## Lưu ý

- Không đưa ảnh của Lara hay ảnh mẫu lên kho GitHub công khai.
- Flow có giới hạn lượt tạo ảnh. Nếu hết lượt hoặc bị chặn nội dung, dừng lại và báo người dùng.
