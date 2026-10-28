# Mẫu prompt cho Google Flow

Thay phần trong `[ngoặc vuông]` bằng mô tả của từng ảnh mẫu. Viết tiếng Việt hoặc tiếng Anh đều được, Flow hiểu cả hai.

---

## Bước 1: Dựng cảnh theo ảnh mẫu

**Ảnh tham chiếu:** ảnh mẫu.

```
Tái tạo chính xác bức ảnh tham chiếu: cùng dáng người, cùng góc máy, cùng bố cục khung hình,
cùng bối cảnh, cùng trang phục, cùng ánh sáng và tông màu.

Cảnh: [ví dụ: cô gái ngồi xổm trên vỉa hè phố đêm, đèn neon phía sau, mặt đường ướt phản chiếu ánh đèn]
Trang phục: [ví dụ: áo khoác da màu đỏ, quần jean đen, bốt cao cổ]
Dáng: [ví dụ: ngồi xổm, hai tay đặt trên gối, nghiêng đầu nhìn vào máy]
Ánh sáng: [ví dụ: ánh đèn đường vàng ấm từ bên trái, viền sáng neon xanh phía sau]

Ảnh chụp thật, chân thực như ảnh máy ảnh, da có kết cấu tự nhiên, độ nét cao, không chữ, không logo.
```

---

## Bước 2: Thay mặt thành Lara

**Ảnh tham chiếu:** (1) ảnh tạo ở bước 1, (2) 1 ảnh mặt Lara rõ nét.

```
GIỮ NGUYÊN 100% khuôn mặt của cô gái trong ảnh tham chiếu thứ hai (Lara): đúng dáng mặt,
mắt, mũi, môi, lông mày, làn da, kiểu tóc và màu tóc. Khuôn mặt phải nhận ra ngay là Lara.

Giữ nguyên mọi thứ khác của ảnh tham chiếu thứ nhất: dáng người, tư thế tay chân, góc máy,
bố cục, bối cảnh, trang phục, phụ kiện, ánh sáng, tông màu và tỉ lệ khung hình.
Chỉ thay khuôn mặt (và tóc) thành Lara, hướng mặt và biểu cảm theo ảnh thứ nhất.

Ánh sáng trên mặt khớp với ánh sáng của cảnh. Ảnh chụp thật, chân thực, độ nét cao,
không chữ, không logo.
```

---

## Khi kết quả chưa đạt

| Vấn đề | Thêm vào prompt |
|---|---|
| Mặt vẫn giống người mẫu cũ | `Không dùng khuôn mặt của ảnh thứ nhất. Khuôn mặt phải lấy hoàn toàn từ ảnh thứ hai.` |
| Đồ hoặc nền bị đổi | `Không thay đổi trang phục, không thay đổi nền. Chỉ đổi khuôn mặt.` |
| Dáng bị lệch | `Giữ đúng tư thế như ảnh thứ nhất, không xoay người, không đổi vị trí tay.` |
| Ảnh trông giả, da nhựa | `Da có lỗ chân lông và kết cấu tự nhiên, ảnh như chụp bằng máy ảnh thật.` |
