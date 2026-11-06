# Đạo hàm = độ dốc tại một điểm: README

Cập nhật lần cuối: 05/11/2026 · Người giữ README: Tuấn · File hiện hành: `derivative_screens_1-3.html` (chi tiết ở mục 5)

---

## 0. Quy tắc cho AI khi sửa file (đọc trước khi làm gì)

1. Đọc README này và file HTML hiện hành TRƯỚC khi sửa. Nếu README nói một đằng, file làm một nẻo, báo chỗ lệch cho tác giả trước. Không tự đoán, không giả định "chắc đã sửa rồi".
2. Sau khi sửa, cập nhật README bằng **sửa cục bộ** (không viết lại cả file), và chỉ các mục sau:
   - **Mục 2:** trạng thái của màn vừa sửa (chưa build / đã build / đã kiểm bằng gì).
   - **Mục 3:** thêm một dòng nếu trong lượt này tác giả chốt điều mới hoặc bỏ một phương án. Chỉ ghi `[chốt]` khi chính tác giả nói; ý của AI ghi `[đề xuất]`.
   - **Mục 5:** tên file/phiên bản, lỗi đã biết, cái chưa kiểm.
3. KHÔNG đụng: mục 1, mục 4 (nhật ký thử nghiệm là của tác giả; AI không được bịa quan sát), và cột "học sinh nói được" ở mục 2 (tác giả duyệt).
4. Ghi "đã kiểm bằng gì" (ảnh chụp / assert Playwright / SymPy) và "chưa kiểm". Không ghi "đã xong" cho thứ chưa kiểm.
5. Cuối lượt, liệt kê các dòng README đã đổi.
6. Không ghi tên hay dữ liệu cá nhân của học sinh vào README hay log.

---

## 1. Mục tiêu và nguyên tắc

**Vấn đề:** học sinh lớp 11–12 tính đạo hàm như cái máy nhưng không hiểu công thức đo cái gì.

**Đích sau 5 màn:** đạo hàm tại một điểm = độ thay đổi độ cao tức thời tại điểm đó (gọi là độ dốc); công thức đo nó là f′(x₀) = lim_{h→0} [f(x₀+h) − f(x₀)] / h. Ví dụ đóng vòng: (x²)′ = lim (2x+h) = 2x chính là công thức học sinh dùng hằng ngày.

**Mô hình thay cho lời giảng trừu tượng của thầy cô.** Vì vậy:
- Xây lời dẫn logic trước, rồi xây màn tương ứng sau. Lời dẫn là sản phẩm chính, hình chỉ phục vụ lời dẫn.
- Mỗi màn: 1 câu hỏi → 1 hành động → 1 câu chốt → 1 câu dẫn. Câu chốt chỉ hiện sau hành động.
- Cụ thể trước, khái quát sau. Lần đầu phải đặc biệt cụ thể, rồi tua nhanh vài lần, rồi mới dùng chữ.
- Không hiện số mà học sinh chưa có cách tính ở màn trước.
- Hands-on chỉ đặt sau khi học sinh đã nắm trực giác và công thức; tách riêng, làm nổi bật; chỉ dùng loại tự chấm được (điền số, trắc nghiệm có đáp án nhiễu đúng vào hiểu lầm điển hình).
- Màn nào không có hands-on thì giữ nhẹ.

**Thuật ngữ cố định**
- **điểm** = giá trị x ("điểm 15" nghĩa là x = 15)
- **bước** = đơn vị trên trục x · **cao thêm** · **độ dốc**
- **bước thử** (từ M2) · **quy về 1 bước**
- **cát tuyến** (đường nối A–B, M3) · **tiếp tuyến / hệ số góc tiếp tuyến** (chỉ từ M4)
- Cấm ở M1–M3: "con số", "độ dốc thật", "tiếp tuyến".
- Dấu phẩy thập phân (0,20); số nguyên không có phần thập phân.

---

## 2. Khung 5 màn

Chuỗi câu hỏi nối các màn: M1 đo "độ nghiêng" bằng số thế nào? → M2 đường thẳng đo được rồi, núi cong thì sao? → M3 bước đủ ngắn, nhưng cần cách chọn điểm, cách đo, cách viết "càng sát càng tốt" → M4 công thức đây, tự tay tính được không? → M5 (x²)′ = 2x chính là phép đo này.

### M1 — Chỗ nào leo mệt nhất?
| Thành phần | Mục đích |
|---|---|
| Title + gợi ý | Gắn "dốc" với cảm giác mệt khi leo; cho học sinh một việc làm ngay: chạm để đoán. |
| Mô hình | Chạm một điểm → mảnh núi dưới chân duỗi thẳng ra ngay trên núi, kèm đường của chỗ dốc nhất (x = 180). Cho thấy mỗi chỗ có một độ nghiêng riêng, và độ nghiêng ấy là một đường thẳng. Không có số, không có "1 bước". |
| Câu setup | Đặt cách hiểu chung về độ dốc để từ trực quan quay về định nghĩa toán học. |
| Dẫn tiếp | Tạo nhu cầu đo bằng số; mở sang việc xem đã có công thức nào cho độ dốc. |

Lời dẫn nguyên văn (của tác giả):
- Title: *Chỗ nào leo mệt nhất*
- Gợi ý: *Càng dốc càng mệt, bạn đoán xem chỗ nào dốc nhất?*
- Setup: *Độ dốc tại một chỗ trên núi cho biết mỗi bước tiếp theo về phía trước mệt thế nào; hay nói cách khác, mỗi bước đi tiếp thì độ cao thêm (hoặc giảm) bao nhiêu, nếu mặt núi cứ nghiêng y như chỗ bạn đang đứng.*
- Dẫn tiếp: *Làm sao chúng ta đo được số đo của "độ nghiêng chỗ bạn đang đứng"? Hãy xem chúng ta có công thức nào để tính độ dốc trước.*

**Học sinh nói được:** độ dốc tại một chỗ là mỗi bước đi tiếp thì cao thêm (hoặc giảm) bao nhiêu, nếu mặt núi giữ nguyên độ nghiêng ở chỗ đó.
**Trạng thái:** file hiện hành còn thiết kế CŨ (khung "Con đường tưởng tượng", chip, nút đánh dấu). Prompt P3 sửa theo thiết kế trên; chưa xác nhận đã chạy.

### M2 — Đo độ dốc của một đường thẳng, f(x) = 3x + 5
| Thành phần | Mục đích |
|---|---|
| Gợi ý | Đưa về ca đơn giản nhất. Chốt từ vựng: x = vị trí, f(x) = độ cao, "điểm 0" nghĩa là x = 0. ↩ M1: vì sao đo đường thẳng là hợp lý. |
| Beat 1: bước thử đúng 1 bước từ điểm 0 (học sinh tự bấm từng mảnh) | Định nghĩa độ dốc bằng hành động, rồi công thức mới ra: [f(1) − f(0)] / [1 − 0] = 3. Lần đầu cụ thể nhất. |
| Beat 2: tua nhanh 1→2, 2→3 | Ở đâu cũng ra 3. |
| Beat 3: đi 4 bước; nửa bước; 0,1 bước | Vì sao có "÷ (b − a)". Gieo "bước nhỏ thì cao thêm ít, chia cho cỡ bước để quy về 1 bước". ↪ M3 dùng đúng thao tác này. |
| Khái quát a, b | Ký hiệu đến sau số: [f(b) − f(a)] / [b − a]. |
| Hands-on "Tới lượt bạn" | Điền số cho điểm 3 → 6, rồi trắc nghiệm hiểu lầm ("độ dốc = độ cao", "độ dốc = cao thêm cả đoạn"). |
| Dẫn tiếp | Nối M1: muốn đo độ dốc tại điểm A trên núi, ta bước thử như vừa làm? Bước dài hay ngắn? |

**Học sinh nói được:** chia cao thêm cho số bước để quy về 1 bước; nửa bước cao thêm 1,5 m thì 1 bước là 3 m.
**Trạng thái:** file hiện hành còn bản CŨ (đường độ dốc 0,20, kéo A/B, bảng đo). Prompt P2 viết lại; chưa xác nhận đã chạy.

### M3 — Trên núi, nên chọn hai điểm nào?
| Thành phần | Mục đích |
|---|---|
| Lời dẫn | Nêu rõ mục tiêu: đo độ dốc tại điểm A (x = 240), cách làm là bước thử như M2. ↩ M2 |
| Bước dài (h = 120) | Đi trên đường cong, không phải đường thẳng; A, B cao bằng nhau nên ra 0. Vì sao bước phải ngắn. |
| Bước ngắn dần + bảng 3 cột (cách nhau h · cao thêm · quy về 1 bước) | Đoạn núi gần thẳng; cột "quy về 1 bước" ổn định dần. ↩ M2 (nửa bước × 2). |
| Hiệu ứng kéo giãn | Đoạn nhỏ giãn thành 1 bước = nhân hệ số = đường thẳng ở M1. Hợp thức hoá điều M1 mới chỉ cho thấy. |
| Chốt + dẫn tiếp | Đo độ dốc tại A = bước thử rất ngắn rồi quy về 1 bước. Còn thiếu cách chọn điểm, cách đo, cách viết "càng sát càng tốt". |

**Học sinh nói được:** bước phải ngắn, vì bước dài là đi trên đường cong, không phải đường thẳng.
**Trạng thái:** bản đã build (port từ bản GPT, có bảng 7 hàng); tác giả duyệt lời diễn giải, chưa nhận xét về hình. CẦN sửa theo logic mới (bước thử, bước dài/ngắn, bảng 3 cột, hiệu ứng kéo giãn); chưa có prompt.
Hands-on: không có (màn này đã nặng ba ý).

### M4 — Từ bảng số đến công thức
| Thành phần | Mục đích |
|---|---|
| Mô hình | Ba thứ còn thiếu ở M3 thành ba nhãn: **chọn điểm** (A = x₀, B = x₀ + h) · **đo** ((f(x₀+h) − f(x₀))/h) · **viết** (lim h→0). Cột bảng cũ đổi nhãn thành h và biểu thức. |
| Chip "sao không lấy h = 0?" | Đối mặt chỗ học sinh thắc mắc nhất: 0/0. Chỉ cần thấy, chưa giải thích vội (giải thích ở M5). |
| Chốt | Đạo hàm = độ dốc = độ thay đổi độ cao tức thời. Giới thiệu "tiếp tuyến": cát tuyến khi B → A thành tiếp tuyến; f′(x₀) là hệ số góc. ↩ M1: đường thẳng duỗi ra ở M1 chính là tiếp tuyến. Thêm cách viết của SGK (x → x₀). |
| Hands-on | Điền chỗ trống để ráp công thức. |

**Học sinh nói được:** vì sao không lấy h = 0 ngay (hai điểm trùng nhau, 0/0).
**Trạng thái:** chưa build, chưa có prompt.

### M5 — Tự tay tính với y = x²
| Thành phần | Mục đích |
|---|---|
| Số trước | x₀ = 3: h = 1; 0,1; 0,01 → 7; 6,1; 6,01 (dần về 6). Mỗi dòng là "6 + h". ↩ bảng ở M3. |
| Đại số | Khai triển, rút h, rồi mới cho h → 0. **Đây là chỗ lấp khoảng trống chính của cả bài:** bước đại số tồn tại để loại h khỏi mẫu, nhờ đó thay h = 0 mà không còn 0/0. Trả lời nốt câu hỏi ở M4. |
| Công thức | x₀ cụ thể → x₀ bất kì → 2x₀. (x²)′ = 2x là kết quả của phép đo, không phải luật để nhớ. |
| Ba chỗ đặc biệt | x₀ = −2, 0, 2 → −4, 0, 4. Đóng vòng với M1: đường duỗi ra giờ có số; dấu âm/dương dạy ở đây. |
| Hands-on | Tính (3,1² − 9)/0,1 = ?; rồi dự đoán độ dốc tại x₀ = 5. |

**Học sinh nói được:** vì sao phải rút h trước rồi mới cho h → 0.
**Trạng thái:** chưa build, chưa có prompt.

---

## 3. Nhật ký quyết định

`[chốt]` = tác giả nói rõ · `[đề xuất]` = Claude đề xuất, tác giả chưa phản hồi cụ thể.
Ngày "phiên trước" = các phiên làm việc trước 05/11/2026.

| # | Ngày | Quyết định | Lý do | Đã bỏ | Trạng thái |
|---|---|---|---|---|---|
| 1 | phiên trước | Định nghĩa: độ dốc tại một chỗ = mỗi bước đi tiếp thì cao thêm/giảm bao nhiêu, nếu mặt núi giữ nguyên độ nghiêng như chỗ đang đứng | Từ trực quan quay về định nghĩa toán học | — | chốt |
| 2 | phiên trước | Bỏ "đường vàng" (đường tham chiếu) | Học sinh hỏi "đường vàng là cái gì?" | Đường vàng | chốt |
| 3 | phiên trước | Motion tự chạy, không slider; điều hướng tự do giữa màn | Đơn giản, tránh học sinh phải nghĩ giao diện | Slider | chốt |
| 4 | 05/11/2026 | Xây lời dẫn logic trước, màn sau | Mô hình thay lời giảng; hình phục vụ lời dẫn | Dựng hình trước | chốt |
| 5 | 05/11/2026 | M1: chạm → mảnh núi duỗi thẳng ngay trên núi; chỉ hai đường (điểm chọn + chỗ dốc nhất); không số, không "1 bước", không chip/nút phụ | Bản "con đường tưởng tượng" của GPT: định nghĩa vòng tròn, hiện số chưa có cách tính, lộ đáp án ngay, tỉ lệ hình mâu thuẫn (núi trông ~30° mà đường ~6°) | Khung "Con đường tưởng tượng", chip, nút "Đánh dấu dự đoán" | chốt |
| 6 | 05/11/2026 | M1 hiện luôn chỗ dốc nhất; M5 chuyển từ "khám phá" sang "kiểm chứng bằng số" | Hệ quả của quyết định 5 | Khám phá chỗ dốc nhất ở M5 | chốt (hệ quả) |
| 7 | 05/11/2026 | "Điểm" luôn nghĩa là x | Tránh mơ hồ "tại điểm 15" | — | chốt |
| 8 | 05/11/2026 | Cụ thể → khái quát; lần đầu cụ thể nhất; tua nhanh các lần sau; hiện cả các phân số của lần tua | Học sinh cần hiểu công thức đến từ hành động | Đưa ký hiệu trước | chốt |
| 9 | 05/11/2026 | M2 dùng f(x) = 3x + 5, bước thử từ điểm 0 | Số nguyên sạch; f(0) = 5, f(1) = 8 | Đường độ dốc 0,20, kéo A/B, bảng đo | chốt (hàm) · đề xuất (các beat chi tiết) |
| 10 | 05/11/2026 | M2 thêm "đổi cỡ bước" (4 bước, nửa bước, 0,1 bước) | Nếu chỉ bước 1 thì mẫu luôn = 1; M3 sẽ gây sốc "bước tí mà tăng nhiều mét". Gieo "quy về 1 bước" | — | đề xuất |
| 11 | 05/11/2026 | Hands-on: sau trực giác + công thức; chỉ tự chấm được; mỗi màn ≤ 1 chỗ; M3 không có | Tự luận cần người chấm; tránh quá tải | Câu trả lời tự do | chốt (nguyên tắc) · đề xuất (chi tiết) |
| 12 | 05/11/2026 | M3: kéo dài đoạn nhỏ = nhân hệ số = đường thẳng ở M1 (một hiệu ứng); bảng 3 cột; hàng cuối h = 0,1 | h = 0,0001 chỉ cho 0,0000147 m, quá nhỏ để hiện; cần cột "quy về 1 bước" | Hiện bước 0,0001 | đề xuất |
| 13 | 05/11/2026 | M4 dùng ký hiệu x₀ như sách; ba nhãn chọn điểm / đo / viết; giới thiệu "tiếp tuyến" ở M4 | Tác giả nói sách dùng x₀; nối đạo hàm với hệ số góc tiếp tuyến | — | chốt (x₀) · đề xuất (còn lại) |
| 14 | 05/11/2026 | M5: x² (số cụ thể → đại số → 2x₀); 5 màn, không nén xuống 4 | Nếu thiếu x², khoảng trống "tính như máy" không lấp được | Bỏ x² hoặc để app tính hộ | đề xuất |
| 15 | 05/11/2026 | Một hằng VEXAG = 2,5 cho hình núi (M1, M3); M2 dùng đồ thị toán thường | Tránh mâu thuẫn tỉ lệ; f(x) = 3x + 5 quá dốc cho tỉ lệ núi | — | đề xuất (đã được áp dụng ở bản build) |
| 16 | 05/11/2026 | Dùng một README duy nhất làm nhật ký; thử nghiệm bằng quan sát và hỏi miệng 5 câu "học sinh nói được" trước | Cỡ mẫu nhỏ; log sự kiện không đo được hiểu | Dựng log phức tạp ngay | đề xuất |

---

## 4. Nhật ký thử nghiệm

*(Chưa có thử nghiệm với học sinh. Do tác giả điền; AI không điền.)*

| Ngày | Bản file | Ai (mã), bao nhiêu em | Câu hỏi | Quan sát (chậm/rối ở đâu) | Sửa gì sau đó |
|---|---|---|---|---|---|

**Cách thử đề xuất:** 3–5 em, ngồi cạnh, hỏi miệng 5 câu "học sinh nói được" (mục 2) khi các em xong màn tương ứng. Ghi chỗ các em chậm hoặc rối. Không ghi tên: dùng mã do tác giả tự gán. Xin phụ huynh đồng ý nếu các em dưới 18 tuổi. Kế hoạch lớn hơn (kiểm tra trước/sau/trì hoãn, nhóm đối chứng, chấm mù) để sau vòng thử định tính này.

---

## 5. Ghi chú build

**File**
- `derivative_screens_1-3.html`: bản hiện hành (Cowork build từ prompt P1). Một file HTML, vanilla JS + SVG, không thư viện, không gọi mạng.
- `derivative_v1_1.html`: bản nền cũ (3 chặng). Chỉ lấy bảng màu dark và hàm núi. KHÔNG lấy logic các màn cũ.
- `mountain-first-three-v2.html`: bản tham chiếu do GPT dựng (app nằm trong `data-srcdoc` của iframe, đã HTML-escape). Nguồn gốc của M3 hiện tại. M1 của file này đã bị bác.

**Prompt đã dùng / đã viết**
| Prompt | Nội dung | Trạng thái |
|---|---|---|
| P1 | Build S1–S3 thành 1 file | Đã chạy → `derivative_screens_1-3.html` |
| P2 | Viết lại createS2 (f(x) = 3x + 5; beat 1–4; hands-on; sửa 1 câu chú thích ở S3) | Đã viết; chưa xác nhận đã chạy |
| P3 | Sửa createS1 (duỗi thẳng độ nghiêng trực tiếp trên núi; xoá khung "con đường", chip, nút đánh dấu) | Đã viết; chưa xác nhận đã chạy |
| P4 | M3 (bước dài/ngắn, bảng 3 cột, hiệu ứng kéo giãn) | Chưa viết |
| P5 | M4 và M5 | Chưa viết |

P2 và P3 sửa hai hàm khác nhau nên chạy thứ tự nào cũng được. Nếu P3 chạy trước thì dòng QA của P2 "S1 vẫn như cũ" đổi thành "S1 theo prompt P3".

**Kiến trúc file:** mảng `screens[]` (mỗi màn có `mount` / `unmount` / `redraw`), `state` theo màn, helper dùng chung (`node`, `line`, `path`, `makeAnimator`, `renderHint`, `F`, `fmt`), `EVENTS` + `log()`, `window.__app`. Palette dark: `--bg #0b1220`, teal (núi), amber (người đi), violet (cát tuyến/ước lượng), `--up`, `--down`, `--flat`.

**Quy ước QA:** Playwright, viewport 390×844 và 1100×800, tự xem ảnh chụp trước khi báo xong; các id ổn định để test; báo rõ cái đã kiểm và cái chưa.

**Lỗi / rủi ro đã biết**
- M1 và M2 trong file hiện hành còn thiết kế cũ (chờ P3, P2).
- Chú thích bảng ở M3 còn chữ "0,20" (P2 sửa).
- M3 chưa theo logic mới.
- Tiếp xúc tại x = 180 (điểm uốn) cắt qua đường núi. Phải giữ đường ngắn để khỏi rối.
- `EVENTS` có nhưng chưa có nút xuất log.

**Chưa kiểm**
- Bản build sau P2, P3.
- Hiệu ứng "duỗi thẳng" ở M1 nhìn có tự nhiên không (nếu giả thì bỏ pha duỗi, cho đường hiện thẳng ra từ chấm).
- Hiệu ứng M3 hoạt động tốt trên điện thoại.
- Mọi điều về mức độ hiểu của học sinh thật.
- Tần suất trong đề thi, thời gian mỗi màn, cỡ mẫu cần cho kiểm chứng lớn.

---

## 6. Số liệu đã verify (SymPy)

- Núi: h(x) = 40·exp(−(x−300)² / (2·120²)), x ∈ [0, 600] bước; h tính bằng mét.
- Độ dốc h′(x) = −h(x)·(x−300) / 120². h′(70) = 0,1018 · h′(180) = 0,2022 (lớn nhất) · h′(240) = 0,1471 · h′(300) = 0 · h′(420) = −0,2022.
- Ước lượng tại A = 240, B = 240 + h; (cao thêm = ước lượng × h).

| h | cao thêm (m) | quy về 1 bước (m/bước) |
|---|---|---|
| 120 | 0,0000 | 0,0000 |
| 60 | 4,7001 | 0,0783 |
| 20 | 2,5385 | 0,1269 |
| 10 | 1,3743 | 0,1374 |
| 5 | 0,7119 | 0,1424 |
| 1 | 0,1462 | 0,1461 |
| 0,1 | 0,0147 | 0,1470 |

- h = 120 cho 0 vì A (240) và B (360) cao bằng nhau (đối xứng quanh 300).
- Với h = 0,0001 cao thêm chỉ khoảng 0,0000147 m (không phải 0,00147): vì vậy không hiện bước này ra cho học sinh.
- f(x) = 3x + 5: f(0) = 5; f(1) = 8; f(2) = 11; f(3) = 14; f(5) = 20; f(2,1) = 11,3; f(2,5) = 12,5; f(6) = 23.
- x², x₀ = 3: [(3+h)² − 9] / h = 6 + h → h = 1: 7; h = 0,1: 6,1; h = 0,01: 6,01. Tổng quát: [(x₀+h)² − x₀²] / h = 2x₀ + h.

---

## 7. Việc còn mở

1. Chạy P3 (M1) và P2 (M2); tác giả báo chỗ chậm/rối nhất.
2. Viết P4 (M3) và P5 (M4–M5).
3. Đối chiếu SGK: gửi 1–2 trang định nghĩa đạo hàm để chốt ký hiệu (h / Δx / x → x₀) và cách sách nói về "hệ số góc tiếp tuyến". Chưa có trang sách nào.
4. Thêm nút ẩn xuất log (`EVENTS`) trước khi thử với học sinh.
5. Điền cột "học sinh nói được" cuối cùng và duyệt lại (tác giả).
6. Chuyển lời dẫn nguyên văn của M2–M5 vào một phụ lục khi chốt (hiện nằm trong các prompt trong chat).


## 8. CẬP NHẬT README (bắt buộc, sau khi sửa file)
Đọc README.md đính kèm trước khi sửa. Nếu README và file HTML lệch nhau, báo chỗ lệch trước, đừng đoán.
Sau khi sửa xong, cập nhật README bằng sửa cục bộ (không viết lại cả file), chỉ ở:
 - Mục 2: trạng thái của màn vừa sửa
 - Mục 3: một dòng nếu tôi vừa chốt điều mới hoặc bỏ một phương án trong lượt này (chỉ ghi [chốt] khi chính tôi nói; ý của bạn ghi [đề xuất])
 - Mục 5: tên file/phiên bản, lỗi đã biết, cái chưa kiểm
KHÔNG đụng mục 1, mục 4, cột "học sinh nói được". Ghi rõ "đã kiểm bằng gì" và "chưa kiểm". Cuối cùng liệt kê các dòng README đã đổi.
