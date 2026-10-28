# Sub-agent tạo ảnh tự động

Bộ hướng dẫn (skill) để Claude tự lên **Google Flow** tạo ảnh cho model AI **Lara** giống y ảnh mẫu: cùng dáng, góc máy, bối cảnh, ánh sáng, còn khuôn mặt và trang phục là của Lara.

Kho này không chứa code chạy được, mà là **skill + prompt** để Claude làm theo bằng trình duyệt. Kho không chứa ảnh nào (kho công khai).

## Cách hoạt động: 2 bước cho mỗi ảnh

```
Ảnh mẫu ──► Bước 1: dựng lại cảnh theo mẫu ──► Ảnh cảnh
                                                  │
Ảnh Lara (mặt+đồ) ─────────────────────────────────┤
                                                  ▼
                                   Bước 2: đưa Lara vào ──► Ảnh kết quả
```

1. **Bước 1, dựng cảnh:** đưa ảnh mẫu vào Flow làm tham chiếu, tạo lại ảnh giữ nguyên dáng, góc máy, nền và ánh sáng.
2. **Bước 2, đưa Lara vào:** đưa ảnh bước 1 + ảnh Lara vào Flow, dùng prompt bắt đầu bằng *"GIỮ NGUYÊN 100% khuôn mặt và trang phục..."* để thay mặt và đồ thành của Lara, giữ dáng, nền, ánh sáng.

Làm gộp 1 bước thì Flow hay giữ luôn mặt và đồ của người mẫu cũ, nên tách 2 bước cho giống Lara hơn.

## Cấu trúc kho

```
skills/tao-anh-model-theo-mau-flow/
├── SKILL.md     # Quy trình đầy đủ cho Claude
└── prompts.md   # Mẫu prompt Bước 1, Bước 2 và cách sửa lỗi
```

## Chuẩn bị trên máy

| Thư mục | Nội dung |
|---|---|
| `Downloads\LARa Model\ảnh mẫu` | Ảnh mẫu cần bắt chước |
| `Downloads\LARa Model\Lara` | Ảnh Lara: mặt và trang phục |
| `Downloads\LARa Model\Flow kết quả` | Ảnh kết quả tải từ Flow về |

Cần thêm: Chrome đã đăng nhập tài khoản Google dùng Flow và bật tiện ích Claude in Chrome.

## Cách dùng

1. Thêm skill trong `skills/tao-anh-model-theo-mau-flow/` vào Claude.
2. Nói với Claude: *"Tạo ảnh Lara theo ảnh mẫu trên Flow"*.
3. Claude làm thử 1 ảnh và gửi ảnh so sánh để bạn duyệt.
4. Bạn đồng ý thì Claude làm hết các ảnh còn lại và tải bản đầy đủ chất lượng (nút Tải xuống của Flow) về `Flow kết quả`.

## Mặc định

- Lara mặc đồ của chính cô ấy; từ ảnh mẫu chỉ lấy dáng, góc máy, bối cảnh, ánh sáng.
- Luôn thử 1 ảnh, chờ duyệt rồi mới chạy cả bộ.
