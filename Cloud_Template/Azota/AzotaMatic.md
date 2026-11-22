# AzotaMatic: Bố cục, Quy ước & Quy tắc riêng cho đề thi Azota

> **Mô tả**: Tài liệu quy chuẩn về bố cục, cú pháp trình bày và quy tắc nhận diện riêng cho đề thi nạp lên nền tảng Azota.
> **Ngôn ngữ hiển thị**: Tiếng Việt

## 1. QUY ƯỚC & ĐIỀU CẤM NỀN TẢNG AZOTA

### 1.1 Quy ước bắt buộc
1. **Định dạng văn bản (Word `.docx`)**: Font `Times New Roman` (hoặc `Aptos`), cỡ chữ `13pt`, màu chữ `#000000` (đen thuần — áp dụng 100% kể cả Heading 1/2, không để màu mặc định xanh/xám). Khối mã nguồn (`<code>`) dùng font `Consolas` `11pt` trên nền xám nhẹ.
2. **Bảo toàn nội dung & Câu hỏi chùm**: Giữ nguyên văn đề và ký hiệu (kể cả từ in đậm / gạch chân trong bài đọc). Câu hỏi chùm xử lý theo 1 trong 2 chế độ:
   - **Bật**: Dùng tiêu đề nhóm `# Câu hỏi chùm [STT].` hoặc `# Nhóm [STT].` (Heading 1), **tên nhóm không trùng** trong cùng một đề, dữ kiện chung đặt 1 lần ngay dưới tên nhóm.
   - **Tắt**: Tách thành các câu độc lập, chép lại dữ kiện chung vào từng câu con.
   - **Môn Tiếng Anh**: Luôn **Bật** ở dạng `# PART [STT]: [Lời dẫn đề gốc]`.
3. **Chuyển câu tự luận**: Chuyển toàn bộ câu tự luận sang **Phần III (Trả lời ngắn)**.
4. **Tiêu đề phần, Đánh số câu & Nhãn**:
   - **Heading 1 (Tiêu đề phần / Nhóm)**: Bắt buộc dùng chữ số La Mã: `# PHẦN I: TRẮC NGHIỆM NHIỀU LỰA CHỌN`, `# PHẦN II: TRẮC NGHIỆM ĐÚNG – SAI`, `# PHẦN III: TRẮC NGHIỆM TRẢ LỜI NGẮN` (hoặc `# Câu hỏi chùm [STT].`, `# Nhóm [STT].`, `# PART [STT]: ...`).
   - **Heading 2 (Tiêu đề câu)**: `## **Câu [STT]:** [Nội dung]` · Môn Tiếng Anh: `## **Question [STT].** [Nội dung]`. Có thể đánh số liên tục toàn đề hoặc đặt lại từ `1` theo từng phần / PART (kèm cập nhật `from 1 to N` ở lời dẫn PART Tiếng Anh).
   - **Nhãn & Dấu cách**: Phương án `**A.** ...` hoặc `*<b>A.</b> ...`; nhận định `**a)** ...` hoặc `*<b>a)</b> ...`. Đúng **1 dấu cách** sau mọi nhãn; **chỉ in đậm nhãn**, nội dung không in đậm (`Đáp án: A` giữ chữ thường).
5. **Quy tắc nhận diện đáp án từng phần**:
   - **Phần I (Nhiều lựa chọn — 1 đáp án đúng)**: *Cách 1 (Mặc định)* để phương án `**A.**`, ghi `Đáp án: A` (chữ thường) trong `**Lời giải**`; *Cách 2* đánh dấu `*<b>A.</b>` trực tiếp tại phương án đúng, bỏ dòng `Đáp án: A`.
   - **Phần II (Đúng – Sai — 4 nhận định a, b, c, d)**: Nhận định ĐÚNG dùng `*<b>a)</b>`, nhận định SAI dùng `**b)**`.
   - **Phần III (Trả lời ngắn)**: Ghi `Đáp án: [Giá trị]` trong `**Lời giải**`; tối đa **4 ký tự** (`0–9`, `-`, `,`, `.`); nhiều đáp án tương đương ngăn cách bằng `|` (VD `2,5 | 2.5`); số quá lớn/nhỏ thì đổi đơn vị hoặc ghi `$(10^x)$` sau câu hỏi (`AZO-04`).
6. **Phân đoạn & Ngắt dòng**: Mỗi thành phần (câu hỏi, phương án, nhận định, từng dòng lời giải) nằm trên **1 đoạn (Enter) độc lập**; không dùng thẻ `<br>`, không dùng ngắt dòng mềm (`Shift + Enter`) và không để dòng trống thừa.
7. **Ký hiệu Đúng / Sai trong lời giải**: Dùng Unicode `✔` (`U+2714`) và `✘` (`U+2718`). Trong 4 dòng `✔`/`✘` **chỉ trích nội dung** phương án/nhận định, không lặp nhãn `A.`, `a)` tránh Azota tách nhầm.
8. **Hình ảnh & Khuyết tật dữ liệu**:
   - **Ảnh câu hỏi**: Chỉ lấy ảnh nội dung trong câu hỏi; chèn trực tiếp trong dòng (`inline`), căn giữa, đúng vị trí, giữ nguyên tỷ lệ và không tràn lề A4.
   - **Khuyết tật**: Thiếu ảnh → gắn `**[CÂU HỎI CÓ HÌNH ẢNH, VUI LÒNG CHÈN HÌNH ẢNH VÀO]**`; chữ mờ/rách → điền theo ngữ cảnh kèm `**[???]**`; thiếu đáp án → tự giải và điền trực tiếp; số câu đề nguồn bị lệch / nhảy (VD `Câu 12` → `Câu 14`) → đặt `**[???]**` giữa hai câu.

### 1.2 Điều cấm trên nền tảng Azota
1. **Không sai chế độ câu hỏi chùm** (`AZO-01`): Khi Tắt chùm không giữ câu chung dữ kiện chưa tách; khi Bật phải dùng đúng `# Câu hỏi chùm [STT].` / `# Nhóm [STT].` (riêng Tiếng Anh luôn dùng `PART`).
2. **Không trộn Cách 1 & Cách 2, không in đậm nội dung và không xóa dấu `*`** (`AZO-02`): Cấm vừa đánh dấu `*<b>A.</b>` vừa ghi `Đáp án: A` trong cùng một câu; chỉ in đậm nhãn và bắt buộc **giữ nguyên ký tự `*` thật** trước nhãn đúng `*A.`, `*a)` trong file Word để Azota nhận diện đáp án.
3. **Không dùng ký hiệu thay thế sai quy ước** (`AZO-03`): Cấm dùng `X`/`x`, `✓`/`✗`, emoji thay cho `✔` (`U+2714`) và `✘` (`U+2718`); trong 4 dòng `✔`/`✘` không lặp nhãn `A.`, `a)` để tránh Azota tách nhầm.
4. **Không để đáp án Phần III vượt quá 4 ký tự** (`AZO-04`): Đáp án trả lời ngắn giới hạn tối đa 4 ký tự (`0–9`, `-`, `,`, `.`); nếu số quá lớn/nhỏ phải đổi đơn vị hoặc ghi `$(10^x)$` sau câu hỏi.
5. **Không giữ số câu cũ trong bài đục lỗ Tiếng Anh & không dùng `a)`, `b)` trong bài sắp xếp** (`AZO-05`): Chỗ trống bài đục lỗ bắt buộc đặt lại `(1)`, `(2)`... kèm `from 1 to N` cho từng bài; các câu lẻ trong bài sắp xếp dùng `a.`, `b.` hoặc `(a)`, `(b)` để tránh Azota nhận nhầm sang Đúng–Sai.
6. **Không đặt trùng tên nhóm** (`AZO-06`): Tên nhóm (`Câu hỏi chùm [STT].`, `Nhóm [STT].`) phải duy nhất, tăng dần trong cùng một đề.

## 2. MẪU BỐ CỤC CHUẨN ĐỀ THI AZOTA
*(Mỗi dòng trong khung mẫu tương ứng 1 đoạn độc lập, không chèn dòng trống thừa. Trong 4 dòng `✔`/`✘` chỉ trích nội dung phương án/nhận định, không lặp nhãn `A.`, `a)`. Nếu dùng chế độ lời giải ngắn gọn, bỏ 4 dòng `✔`/`✘` ở Phần I–II và bỏ `**Tóm tắt:**` ở Phần III.)*

### 2.1 Phần I: Trắc nghiệm nhiều lựa chọn (Cách 1 mặc định)
```
# PHẦN I: TRẮC NGHIỆM NHIỀU LỰA CHỌN
## **Câu [STT]:** [Nội dung câu hỏi]
[Tư liệu, ảnh, code...]
**A.** [Phương án A]
**B.** [Phương án B]
**C.** [Phương án C]
**D.** [Phương án D]
**Lời giải**
Đáp án: A
**Giải thích:**
[Các bước làm / dẫn chứng]
**✔** “[Phương án đúng]”: **ĐÚNG.** [Lý do]
**✘** “[Phương án sai 1]”: **SAI.** [Lý do]
**✘** “[Phương án sai 2]”: **SAI.** [Lý do]
**✘** “[Phương án sai 3]”: **SAI.** [Lý do]
```

*Cách 2: đổi phương án đúng thành `*<b>A.</b> ...` và bỏ dòng `Đáp án: A`.*

### 2.2 Phần II: Trắc nghiệm Đúng – Sai
```
# PHẦN II: TRẮC NGHIỆM ĐÚNG – SAI
## **Câu [STT]:** [Nội dung câu dẫn]
[Tư liệu, ảnh, code...]
*<b>a)</b> [Nhận định đúng]
**b)** [Nhận định sai]
*<b>c)</b> [Nhận định đúng]
**d)** [Nhận định sai]
**Lời giải**
**Giải thích:**
[Các bước làm]
**✔** “[Nhận định a]”: **ĐÚNG.** [Lý do]
**✘** “[Nhận định b]”: **SAI.** [Lý do]
**✔** “[Nhận định c]”: **ĐÚNG.** [Lý do]
**✘** “[Nhận định d]”: **SAI.** [Lý do]
```

### 2.3 Phần III: Trắc nghiệm Trả lời ngắn
```
# PHẦN III: TRẮC NGHIỆM TRẢ LỜI NGẮN
## **Câu [STT]:** [Nội dung câu hỏi] ([đơn vị nếu có])
[Tư liệu, ảnh, code...]
**Lời giải**
Đáp án: [≤ 4 ký tự] | [Đáp án tương đương, VD: 2,5 | 2.5]
**Tóm tắt:**
[Dữ kiện → Cần tìm]
**Giải thích:**
[Công thức & bước giải]
$$[Công thức căn giữa]$$
[Thay số, chốt đáp án, lưu ý cạm bẫy]
```

### 2.4 Câu hỏi chùm / Nhóm (chỉ khi Bật)
*(Tên nhóm là Heading 1, dùng `# Câu hỏi chùm [STT].` hoặc `# Nhóm [STT].`, không trùng trong 1 đề; dữ kiện chung đặt 1 lần dưới tên nhóm.)*
```
# Câu hỏi chùm [STT].
[Dữ kiện chung: tư liệu, ảnh, bài đọc...]
## **Câu [STT]:** [Câu con 1]
[Phương án / Nhận định / Lời giải theo mẫu phần tương ứng]
## **Câu [STT + 1]:** [Câu con 2]
[...]
```

### 2.5 Tiếng Anh (PART luôn Bật; đánh số `Question` đặt lại `1..N` từng PART hoặc liên tục toàn đề)
*(Tên Part lấy theo lời dẫn đề gốc; nhãn câu `## **Question [STT].**`. Mẫu dưới đây theo Cách 1 — nếu dùng Cách 2 đổi phương án đúng thành `*<b>A.</b>` và bỏ dòng `Đáp án: A`.)*

#### 2.5.1 Part đục lỗ (Gap-Filling)
*(Chỗ trống mỗi bài **reset** `(1)`, `(2)`..., giữ nguyên `______` không gạch chân, lời dẫn ghi `numbered blanks from 1 to [N]`; câu con trích nguyên câu chứa chỗ trống đã reset — `AZO-05`.)*
```
# PART [STT]: Read the following... numbered blanks from 1 to [N]
<p align="center"><b>[TIÊU ĐỀ BÀI ĐỌC]</b></p>
[Bài đọc với chỗ trống đã reset: ... (1) ______ ... (2) ______ ...]
## **Question [STT].** [Trích nguyên câu chứa chỗ trống (1)]
**A.** [Phương án A]
**B.** [Phương án B]
**C.** [Phương án C]
**D.** [Phương án D]
**Lời giải**
Đáp án: A
**Giải thích:**
**Dịch:** [Bản dịch tiếng Việt hoàn chỉnh, **in đậm từ điền vào**]
[Dẫn chứng ngữ pháp / ngữ nghĩa]
**✔** “[Phương án đúng]”: **ĐÚNG.** [Lý do]
**✘** “[Phương án sai 1]”: **SAI.** [Lý do]
**✘** “[Phương án sai 2]”: **SAI.** [Lý do]
**✘** “[Phương án sai 3]”: **SAI.** [Lý do]
```

#### 2.5.2 Part sắp xếp (Arrangement — không có bài đọc chung)
*(Các câu lẻ đánh dấu `a.`, `b.`, `c.` hoặc `(a)`, `(b)`, `(c)` — tránh dùng `a)`, `b)` dễ bị Azota nhận nhầm sang Đúng–Sai.)*
```
# PART [STT]: Mark the letter A, B, C, or D... correct arrangement of the sentences...
## **Question [STT].** [Đoạn hội thoại / thư / đoạn văn bị xáo trộn]
**A.** [Phương án A]
**B.** [Phương án B]
**C.** [Phương án C]
**D.** [Phương án D]
**Lời giải**
Đáp án: A
**Giải thích:**
**Dịch:** [Bản dịch tiếng Việt hoàn chỉnh theo thứ tự đúng]
[Dẫn chứng logic nối câu]
**✔** “[Phương án đúng]”: **ĐÚNG.** [Lý do]
**✘** “[Phương án sai 1]”: **SAI.** [Lý do]
**✘** “[Phương án sai 2]”: **SAI.** [Lý do]
**✘** “[Phương án sai 3]”: **SAI.** [Lý do]
```

#### 2.5.3 Part đọc hiểu (Reading Comprehension)
```
# PART [STT]: Read the following passage and mark the letter A, B, C, or D...
<p align="center"><b>[TIÊU ĐỀ BÀI ĐỌC]</b></p>
[Bài đọc — giữ nguyên từ **in đậm**, <u>gạch chân</u>, ký hiệu [I]..[IV] nếu có]
## **Question [STT].** [Nội dung câu hỏi]
**A.** [Phương án A]
**B.** [Phương án B]
**C.** [Phương án C]
**D.** [Phương án D]
**Lời giải**
Đáp án: A
**Giải thích:**
**Dịch:** [Bản dịch tiếng Việt đoạn văn liên quan]
[Trích dẫn câu chứa thông tin trả lời từ bài đọc]
**✔** “[Phương án đúng]”: **ĐÚNG.** [Lý do]
**✘** “[Phương án sai 1]”: **SAI.** [Lý do]
**✘** “[Phương án sai 2]”: **SAI.** [Lý do]
**✘** “[Phương án sai 3]”: **SAI.** [Lý do]
```

### 2.6 Tư liệu (văn bản · bảng · code)
#### 2.6.1 Tư liệu văn bản
```
<p align="center"><b>[TÊN TƯ LIỆU]</b></p>
[Nội dung — mỗi đoạn 1 dòng]
<p align="right"><i>(Nguồn: [Tên nguồn])</i></p>
```

#### 2.6.2 Bảng số liệu
```
<p align="center"><b>[TÊN BẢNG]</b></p>
<p align="right"><i>(Đơn vị: ...)</i></p>
| **[Cột 1]** | **[Cột 2]** |
| :---: | :---: |
| **[Hàng 1]** | [Dữ liệu] |
<p align="right"><i>(Nguồn: [Tên nguồn])</i></p>
```

#### 2.6.3 Khối Code
```
<code>
[Dòng code 1 — không viết gộp dòng]
[Dòng code 2]
</code>
```

## 3. QUY CHUẨN CÔNG THỨC & BẢNG TÓM TẮT QUY ƯỚC

### 3.1 Bảng tóm tắt quy ước định dạng Azota
| Thành phần đề thi | Quy ước định dạng | Lưu ý bắt buộc |
| ----- | ----- | ----- |
| `# PHẦN` / `PART` / `Câu hỏi chùm [STT].` / `Nhóm [STT].` | **Heading 1** (`Times New Roman` 13pt, đậm, `#000000`) | Tên nhóm không trùng; Tiếng Anh luôn dùng `PART` |
| `## **Câu [STT]:**` / `## **Question [STT].**` | **Heading 2** (`#000000`, chỉ in đậm nhãn) | Đúng 1 dấu cách sau nhãn; đánh số liên tục hoặc đặt lại theo phần/PART |
| `*<b>A.</b>`, `*<b>a)</b>` (Cách 2 / Đúng–Sai) | **Giữ nguyên dấu `*`** + in đậm nhãn | Đúng 1 dấu cách sau nhãn; tuyệt đối không xóa `*` |
| `Đáp án: A` / `Đáp án: [giá trị]` (Cách 1 / Phần III) | Văn bản thường (không in đậm) | Phần III ≤ 4 ký tự; nhiều đáp án ngăn cách bằng `\|` |
| Mỗi thành phần câu / lời giải | 1 đoạn (Enter) độc lập | Không dùng `<br>`, ngắt dòng mềm hay dòng trống thừa |
| Bảng số liệu & Khối `<code>` | Bảng chuẩn Word / khối `Consolas` 11pt nền xám nhẹ | Không để sót thẻ HTML hoặc ký hiệu Markdown thô |
| Công thức `$..$`, `$$..$$` | Công thức chuẩn Word (Equation / `Cambria Math`, `#000000`) | Đồng bộ 100% toàn bài; không dùng `\ce{}` |
| Ảnh minh họa | Chèn `inline`, căn giữa | Đúng vị trí câu, giữ tỷ lệ, không `floating` / tràn lề A4 |
| `✔`, `✘`, `**[???]**` | Ký hiệu Unicode trực tiếp, `#000000` | Cấm `X`/`x`, `✓`/`✗`, emoji |

### 3.2 Quy chuẩn & Điều kiện viết công thức LaTeX
- **Điều kiện áp dụng (đồng bộ 100% toàn bài):** Bắt buộc dùng công thức chuẩn cho **mọi** biểu thức, biến số, phân số, lũy thừa, chỉ số, căn thức, tích phân, vectơ, khoảng/đoạn và ký hiệu toán–lý–hóa (`$x$`, `$e^x$`, `$x^\alpha$`, `$v = 5\text{ m/s}$`, `$\mathrm{H_2O}$`) ở **tất cả vị trí** (đề bài, phương án, `Tóm tắt:`, `Giải thích:` và **cả 4 dòng `✔`/`✘`**). **Không áp dụng** cho văn bản chữ thường, số đếm/năm/thời gian thông thường (VD `2025`, `50 phút`, `Câu 1`) hoặc môn không có công thức (Ngữ văn, Tiếng Anh...).
- **Dấu bọc theo cách nhập liệu:** Khi biên dịch sang file Word `.docx`, dùng `$..$` (công thức trong dòng) và `$$..$$` (công thức căn giữa dòng riêng). Nếu dán trực tiếp vào trình **Tự soạn Đề thi** trên web Azota, bọc toàn bộ công thức bằng `$$..$$` (trình soạn web không nhận diện `$..$` đơn).
- **Quy ước ký hiệu chuẩn:** Số thập phân dùng dấu phẩy `$2{,}5$` · đơn vị chữ đứng `\text{ kg}` · vectơ `\overrightarrow{AB}` · góc `\widehat{ABC}` · khoảng `$(-\infty; 2)$`, `$[a; b]$` · hóa học dùng `\mathrm{..}`, không dùng `\ce{}` (`$\mathrm{2H_2 + O_2 \xrightarrow{t^\circ} 2H_2O}$`, phản ứng thuận nghịch `\rightleftharpoons`).

## 4. CHECKLIST KIỂM TRA & LỖI AZOTA THƯỜNG GẶP

### 4.1 Checklist kiểm tra trước khi nạp Azota
- [ ] Đủ 100% câu hỏi, không nhảy số (câu bị lệch đã gắn `**[???]**`); đánh số nhất quán (liên tục toàn đề hoặc đặt lại `1..N` theo phần / PART kèm `from 1 to N`; bài đục lỗ luôn reset `(1)`, `(2)`...).
- [ ] Câu hỏi chùm nhất quán (Bật: `Câu hỏi chùm [STT].` / `Nhóm [STT].` không trùng tên; Tắt: đã tách độc lập và chép dữ kiện chung; Tiếng Anh luôn `PART`).
- [ ] Nhãn Azota đúng quy ước (`Đáp án: A` chữ thường hoặc `*A.` giữ nguyên dấu `*` + nhãn đậm, không trộn Cách 1 & 2; `*a)` giữ nguyên dấu `*` + nhãn đậm; Phần III ≤ 4 ký tự); đúng 1 dấu cách sau mọi nhãn.
- [ ] Văn bản sạch: 100% chữ đen `#000000` (kể cả Heading 1/2), nội dung không in đậm, không có `<br>`, không có ngắt dòng mềm hay dòng trống thừa, không sót ký hiệu Markdown/HTML thô.
- [ ] Công thức đồng bộ 100% toàn bài (đề bài, phương án, `Tóm tắt:`, `Giải thích:` và 4 dòng `✔`/`✘`), không sót công thức viết chữ chay (`e^x`, `x^α`, `a/b`, `√`, `∫`) hay lỗi `\ce{}`.
- [ ] Ảnh chèn `inline`, căn giữa, đúng vị trí, giữ nguyên tỷ lệ, không ảnh rác / `floating` / tràn lề A4; ký hiệu `✔`/`✘` đúng Unicode.

### 4.2 Bảng lỗi Azota thường gặp & Cách khắc phục
| Mã | Lỗi thường gặp trên Azota | Cách khắc phục |
| ----- | ----- | ----- |
| **AZO-01** | Sai chế độ câu hỏi chùm | Tắt: tách độc lập + chép dữ kiện chung; Bật: giữ `Câu hỏi chùm [STT].`/`Nhóm [STT].`/`PART [STT]` (Tiếng Anh luôn `PART`) |
| **AZO-02** | In đậm nội dung, xóa mất dấu `*`, hoặc trộn Cách 1 & 2 | Chỉ in đậm nhãn; giữ nguyên ký tự `*` trước `*A.`, `*a)`; không trộn `*A.` với `Đáp án: A` trong cùng câu |
| **AZO-03** | Dùng `X`/`x`, `✓`/`✗`, emoji thay cho `✔`/`✘` | Đổi sang `✔` (`U+2714`), `✘` (`U+2718`) và không lặp nhãn `A.`, `a)` trong 4 dòng phân tích |
| **AZO-04** | Đáp án Phần III > 4 ký tự | Đổi đơn vị hoặc ghi `$(10^x)$` sau câu hỏi |
| **AZO-05** | Chỗ trống bài đục lỗ không reset hoặc bài sắp xếp dùng `a)`, `b)` | Reset `(1)`, `(2)`... kèm `from 1 to N` cho từng bài; bài sắp xếp dùng `a.`, `b.` hoặc `(a)`, `(b)` |
| **AZO-06** | Trùng tên nhóm | Đặt tên nhóm duy nhất, tăng dần trong cùng đề |
