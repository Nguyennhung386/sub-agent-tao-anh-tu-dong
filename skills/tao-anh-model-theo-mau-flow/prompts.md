# Mẫu prompt cho Google Flow

Thay phần trong `[ngoặc vuông]` bằng mô tả của từng ảnh mẫu. Viết tiếng Việt hoặc tiếng Anh đều được, Flow hiểu cả hai.

---

## Bước 1: Dựng cảnh theo ảnh mẫu

**Ảnh tham chiếu:** ảnh mẫu.

```
Tái tạo chính xác bức ảnh tham chiếu: cùng dáng người, cùng góc máy, cùng bố cục khung hình,
cùng bối cảnh, cùng ánh sáng và tông màu.

Cảnh: [ví dụ: cô gái ngồi xổm trên vỉa hè phố đêm, đèn neon phía sau, mặt đường ướt phản chiếu ánh đèn]
Dáng: [ví dụ: ngồi xổm, hai tay đặt trên gối, nghiêng đầu nhìn vào máy]
Ánh sáng: [ví dụ: ánh đèn đường vàng ấm từ bên trái, viền sáng neon xanh phía sau]

Ảnh chụp thật, chân thực như ảnh máy ảnh, da có kết cấu tự nhiên, độ nét cao, không chữ, không logo.
```

---

## Bước 2: Đưa Lara vào (mặt + trang phục)

**Ảnh tham chiếu:** (1) ảnh tạo ở bước 1, (2) ảnh Lara thấy rõ mặt và trang phục
(thêm (3) ảnh mặt Lara nhìn thẳng nếu ảnh (2) không rõ mặt).

```
GIỮ NGUYÊN 100% khuôn mặt và trang phục của cô gái trong ảnh tham chiếu thứ hai (Lara):
đúng dáng mặt, mắt, mũi, môi, lông mày, làn da, kiểu tóc, màu tóc; đúng kiểu đồ, màu sắc,
chất liệu, họa tiết và phụ kiện. Nhìn vào phải nhận ra ngay là Lara trong bộ đồ của cô ấy.

Giữ nguyên từ ảnh tham chiếu thứ nhất: dáng người, tư thế tay chân, góc máy, bố cục,
bối cảnh, ánh sáng, tông màu và tỉ lệ khung hình. Hướng mặt và biểu cảm theo ảnh thứ nhất.
Không dùng khuôn mặt và trang phục của người trong ảnh thứ nhất.

Ánh sáng trên người khớp với ánh sáng của cảnh. Ảnh chụp thật, chân thực, độ nét cao,
không chữ, không logo.
```

---

## Khi kết quả chưa đạt

| Vấn đề | Thêm vào prompt |
|---|---|
| Mặt vẫn giống người mẫu cũ | `Khuôn mặt phải lấy hoàn toàn từ ảnh thứ hai, không giữ nét mặt của ảnh thứ nhất.` |
| Vẫn mặc đồ của ảnh mẫu | `Thay toàn bộ trang phục bằng bộ đồ trong ảnh thứ hai, không giữ lại món đồ nào của ảnh thứ nhất.` |
| Nền bị đổi | `Không thay đổi nền và bối cảnh của ảnh thứ nhất.` |
| Dáng bị lệch | `Giữ đúng tư thế như ảnh thứ nhất, không xoay người, không đổi vị trí tay.` |
| Ảnh trông giả, da nhựa | `Da có lỗ chân lông và kết cấu tự nhiên, ảnh như chụp bằng máy ảnh thật.` |
