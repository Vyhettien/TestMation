# OLMatic: Bố cục, Quy ước & Quy tắc riêng cho đề thi OLM

> **Mô tả**: Tài liệu quy chuẩn về bố cục, cú pháp trình bày và quy tắc nhận diện riêng cho đề thi nạp lên nền tảng OLM.
> **Ngôn ngữ hiển thị**: Tiếng Việt

## 1. QUY ƯỚC & ĐIỀU CẤM NỀN TẢNG OLM

### 1.1 Quy ước bắt buộc
1. **Định dạng văn bản (Word `.docx`)**: Font `Times New Roman` (hoặc `Aptos`), cỡ chữ `13pt`, màu chữ `#000000` (đen thuần — áp dụng 100% kể cả Heading 1/2, không để màu mặc định xanh/xám). Khối mã nguồn (`<code>`) dùng font `Consolas` `11pt` trên nền xám nhẹ.
2. **Bảo toàn nội dung & Câu hỏi chùm (Thẻ OLM)**: Giữ nguyên văn đề và ký hiệu (kể cả từ in đậm / gạch chân trong bài đọc — đó là đề bài, không phải đáp án). Câu hỏi chùm xử lý theo 1 trong 2 chế độ:
   - **Bật**: Dùng thẻ OLM bao bọc cụm câu hỏi (đứng riêng 1 đoạn Normal độc lập, **tuyệt đối không đặt heading `#`**):
     - `**[DIV]**`: Mở nhóm câu dùng chung dữ liệu/bài đọc hiểu mà các câu con có thể đảo ngẫu nhiên.
     - `**[DIV][FIX]**`: BẮT BUỘC cho bài đọc đục lỗ (Gap-filling) hoặc chuỗi câu hỏi phụ thuộc kết quả (cố định thứ tự câu hỏi). Chỗ trống bài đục lỗ BẮT BUỘC reset từ `(1)`, `(2)`, `(3)`... kèm lời dẫn `from 1 to N` cho từng bài mới.
     - `**[ONE]**`: BẮT BUỘC đặt ngay sau câu hỏi cuối cùng của cụm mở bằng `[DIV]` hoặc `[DIV][FIX]` để kết thúc nhóm.
   - **Tắt**: Tách thành các câu độc lập, chép lại dữ kiện chung vào từng câu con.
   - **Môn Tiếng Anh**: Luôn **Bật** ở dạng `# PART [STT]: [Lời dẫn đề bài gốc]`.
3. **Chuyển câu tự luận**: Chuyển toàn bộ câu tự luận sang **Phần 3 (Trả lời ngắn)**.
4. **Tiêu đề phần, Đánh số câu & Nhãn**:
   - **Heading 1 (Tiêu đề phần / Nhóm)**: Bắt buộc dùng chữ số thường (Ả Rập), KHÔNG dùng số La Mã: `# PHẦN 1: TRẮC NGHIỆM NHIỀU LỰA CHỌN`, `# PHẦN 2: TRẮC NGHIỆM ĐÚNG – SAI`, `# PHẦN 3: TRẮC NGHIỆM TRẢ LỜI NGẮN` (hoặc `# PART [STT]: [Lời dẫn đề bài gốc]`).
   - **Heading 2 (Tiêu đề câu)**: Bắt buộc dùng dấu chấm `.` sau nhãn câu (không dùng dấu hai chấm `:`): `## **Câu [STT].** [Nội dung]` · Môn Tiếng Anh: `## **Question [STT].** [Nội dung]`. Phần 2 thêm thẻ `[TF]`: `## **Câu [STT]. [TF]** [Nội dung]`. Có thể đánh số liên tục toàn đề hoặc đặt lại từ `1` theo từng phần / PART (kèm cập nhật `from 1 to N` ở lời dẫn PART Tiếng Anh).
   - **Nhãn & Dấu cách**: Phương án `**<u>A</u>.** ...` hoặc `**B.** ...`. Đúng **1 dấu cách** sau mọi nhãn; **chỉ in đậm nhãn** (và gạch chân duy nhất chữ cái nhãn đáp án đúng), nội dung không in đậm.
5. **Quy tắc nhận diện đáp án từng phần**:
   - **Phần 1 (Nhiều lựa chọn — 1 đáp án đúng)**: Bắt buộc gạch chân chữ cái in hoa của nhãn phương án đúng `**<u>A</u>.**` (trong Word OpenXML là `<w:u w:val="single"/>` chỉ gạch chân chữ cái nhãn, không gạch chân dấu chấm). Tuyệt đối không dùng dấu sao `*` hoặc dòng `Đáp án: A` (OLM không nhận diện được).
   - **Phần 2 (Đúng – Sai — 4 nhận định A, B, C, D)**: Nhận định ĐÚNG gạch chân nhãn `**<u>A</u>.**`, nhận định SAI không gạch chân `**B.**`. Nhãn dùng chữ in hoa `**A.**`, `**B.**`, `**C.**`, `**D.**` (không thêm `#` để OLM tự đảo). Bắt buộc có thẻ `[TF]` ở tiêu đề câu.
   - **Phần 3 (Trả lời ngắn)**: Bắt buộc dùng `**Trả lời:** [[Đáp án 1||Đáp án 2]]`; tối đa **4 ký tự số** (`0–9`, `-`, `,`, `.`); nhiều đáp án tương đương ngăn cách bằng `||` (VD `[[2,5||2.5]]`); số quá lớn/nhỏ thì đổi đơn vị hoặc ghi `$(10^x)$` sau câu hỏi (`OLM-05`).
   - **Thẻ Hướng dẫn giải `[HDG]`**: Bắt buộc mở đầu dòng bằng `**[HDG] Giải thích:**` (bỏ dòng `Lời giải`).
6. **Phân đoạn & Ngắt dòng**: Mỗi thành phần (câu hỏi, thẻ `[DIV]`/`[ONE]`, phương án, nhận định, từng dòng lời giải) nằm trên **1 đoạn (Enter) độc lập**; không dùng thẻ `<br>`, không dùng ngắt dòng mềm (`Shift + Enter`) và không để dòng trống thừa.
7. **Ký hiệu Đúng / Sai trong lời giải**: Dùng Unicode `✔` (`U+2714`) và `✘` (`U+2718`). Trong 4 dòng `✔`/`✘` **chỉ trích nội dung** phương án/nhận định, không lặp nhãn `A.`, `B.` tránh OLM tách nhầm.
8. **Hình ảnh & Khuyết tật dữ liệu**:
   - **Ảnh câu hỏi**: Chỉ lấy ảnh nội dung trong câu hỏi; chèn trực tiếp trong dòng (`inline`), căn giữa, đúng vị trí, giữ nguyên tỷ lệ và không tràn lề A4.
   - **Khuyết tật**: Thiếu ảnh → gắn `**[CÂU HỎI CÓ HÌNH ẢNH, VUI LÒNG CHÈN HÌNH ẢNH VÀO]**`; chữ mờ/rách → điền theo ngữ cảnh kèm `**[???]**`; thiếu đáp án → tự giải và điền trực tiếp; số câu đề nguồn bị lệch / nhảy (VD `Câu 12` → `Câu 14`) → đặt `**[???]**` giữa hai câu.

### 1.2 Điều cấm trên nền tảng OLM
1. **Không sai cấu trúc thẻ `[DIV]`/`[DIV][FIX]`/`[ONE]`** (`OLM-01`): Cấm đặt thẻ heading `#` cho các thẻ chức năng `[DIV]`, `[DIV][FIX]`, `[ONE]`; cấm thiếu thẻ `[ONE]` đóng cụm sau câu hỏi cuối cùng của nhóm; khi Tắt chùm không giữ câu chung dữ kiện chưa tách.
2. **Không gạch chân sai nhãn, không in đậm nội dung & không dùng cú pháp Azota** (`OLM-02`): Cấm gạch chân cả dấu chấm (phải là `**<u>A</u>.**`, không được `**<u>A.</u>**`); chỉ in đậm nhãn, không in đậm nội dung; cấm dùng dấu sao `*` hoặc dòng `Đáp án: A` (OLM không nhận diện được).
3. **Không thiếu thẻ OLM & không sai nhãn phần/câu** (`OLM-03`): Cấm thiếu thẻ `[TF]` ở Phần 2, thiếu `[[...]]` ở Phần 3, thiếu `[HDG]` ở lời giải; cấm dùng số La Mã ở Heading 1 (bắt buộc `# PHẦN 1`, không dùng `PHẦN I`); cấm dùng dấu hai chấm `:` sau nhãn câu (bắt buộc `## **Câu [STT].**`).
4. **Không dùng ký hiệu thay thế sai quy ước** (`OLM-04`): Cấm dùng `X`/`x`, `✓`/`✗`, emoji thay cho `✔` (`U+2714`) và `✘` (`U+2718`); trong 4 dòng `✔`/`✘` không lặp nhãn `A.`, `B.` để tránh OLM tách nhầm.
5. **Không để đáp án Phần 3 vượt quá 4 ký tự số** (`OLM-05`): Đáp án trả lời ngắn giới hạn tối đa 4 ký tự (`0–9`, `-`, `,`, `.`); nếu số quá lớn/nhỏ phải đổi đơn vị hoặc ghi `$(10^x)$` sau câu hỏi.
6. **Không giữ số câu cũ trong bài đục lỗ Tiếng Anh & không dùng `a)`, `b)` trong bài sắp xếp** (`OLM-06`): Chỗ trống bài đục lỗ bắt buộc đặt lại `(1)`, `(2)`... kèm `from 1 to N` cho từng bài; các câu lẻ trong bài sắp xếp dùng `a.`, `b.` hoặc `(a)`, `(b)`.

## 2. MẪU BỐ CỤC CHUẨN ĐỀ THI OLM
*(Mỗi dòng trong khung mẫu tương ứng 1 đoạn độc lập, không dùng `<br>` và không chèn dòng trống thừa. Trong 4 dòng `✔`/`✘` chỉ trích nội dung phương án/nhận định, không lặp nhãn `A.`, `B.`. Nếu dùng chế độ lời giải ngắn gọn, bỏ 4 dòng `✔`/`✘` ở Phần 1–2 và bỏ `**Tóm tắt:**` ở Phần 3.)*

### 2.1 Phần 1: Trắc nghiệm nhiều lựa chọn
```
# PHẦN 1: TRẮC NGHIỆM NHIỀU LỰA CHỌN
## **Câu [STT].** [Nội dung câu hỏi]
[Tư liệu, ảnh, code...]
**<u>A</u>.** [Phương án A đúng]
**B.** [Phương án B]
**C.** [Phương án C]
**D.** [Phương án D]
**[HDG] Giải thích:**
[Các bước làm / dẫn chứng]
**✔** “[Phương án đúng]”: **ĐÚNG.** [Lý do]
**✘** “[Phương án sai 1]”: **SAI.** [Lý do]
**✘** “[Phương án sai 2]”: **SAI.** [Lý do]
**✘** “[Phương án sai 3]”: **SAI.** [Lý do]
```

### 2.2 Phần 2: Trắc nghiệm Đúng – Sai
```
# PHẦN 2: TRẮC NGHIỆM ĐÚNG – SAI
## **Câu [STT]. [TF]** [Nội dung câu dẫn]
[Tư liệu, ảnh, code...]
**<u>A</u>.** [Nhận định A đúng]
**B.** [Nhận định B sai]
**<u>C</u>.** [Nhận định C đúng]
**D.** [Nhận định D sai]
**[HDG] Giải thích:**
[Các bước làm]
**✔** “[Nhận định A]”: **ĐÚNG.** [Lý do]
**✘** “[Nhận định B]”: **SAI.** [Lý do]
**✔** “[Nhận định C]”: **ĐÚNG.** [Lý do]
**✘** “[Nhận định D]”: **SAI.** [Lý do]
```

### 2.3 Phần 3: Trắc nghiệm Trả lời ngắn
```
# PHẦN 3: TRẮC NGHIỆM TRẢ LỜI NGẮN
## **Câu [STT].** [Nội dung câu hỏi] ([đơn vị nếu có])
[Tư liệu, ảnh, code...]
**Trả lời:** [[Đáp án ≤ 4 ký tự||Đáp án tương đương, VD: 2,5||2.5]]
**[HDG] Giải thích:**
**Tóm tắt:**
[Dữ kiện → Cần tìm]
[Công thức & bước giải]
$$[Công thức căn giữa]$$
[Thay số, chốt đáp án, lưu ý cạm bẫy]
```

### 2.4 Câu hỏi chùm / Nhóm (Thẻ `[DIV]` và `[ONE]` — chỉ khi Bật)
*(Thẻ `**[DIV]**` cho nhóm xáo trộn hoặc `**[DIV][FIX]**` cho nhóm cố định thứ tự; đứng riêng 1 đoạn Normal, tuyệt đối không đặt heading `#`; bắt buộc đóng bằng `**[ONE]**` ngay sau câu con cuối cùng.)*
```
**[DIV]**
[Dữ kiện chung: tư liệu, ảnh, bài đọc...]
## **Câu [STT].** [Câu con 1]
[Phương án / Nhận định / Lời giải theo mẫu phần tương ứng]
## **Câu [STT + 1].** [Câu con 2]
[...]
**[ONE]**
```

### 2.5 Tiếng Anh (PART luôn Bật; đánh số `Question` đặt lại `1..N` từng PART hoặc liên tục toàn đề)
*(Tên Part lấy theo lời dẫn đề gốc; nhãn câu `## **Question [STT].**`; đáp án đúng gạch chân chữ cái nhãn `**<u>A</u>.**`.)*

#### 2.5.1 Part đục lỗ (Gap-Filling với `[DIV][FIX]` và `[ONE]`)
*(Chỗ trống mỗi bài **reset** `(1)`, `(2)`..., giữ nguyên `______` không gạch chân, lời dẫn ghi `numbered blanks from 1 to [N]`; câu con trích nguyên câu chứa chỗ trống đã reset — `OLM-06`.)*
```
# PART [STT]: Read the following... numbered blanks from 1 to [N]
**[DIV][FIX]**
<p align="center"><b>[TIÊU ĐỀ BÀI ĐỌC]</b></p>
[Bài đọc với chỗ trống đã reset: ... (1) ______ ... (2) ______ ...]
## **Question [STT].** [Trích nguyên câu chứa chỗ trống (1)]
**<u>A</u>.** [Phương án A đúng]
**B.** [Phương án B]
**C.** [Phương án C]
**D.** [Phương án D]
**[HDG] Giải thích:**
**Dịch:** [Bản dịch tiếng Việt hoàn chỉnh, **in đậm từ điền vào**]
[Dẫn chứng ngữ pháp / ngữ nghĩa]
**✔** “[Phương án đúng]”: **ĐÚNG.** [Lý do]
**✘** “[Phương án sai 1]”: **SAI.** [Lý do]
**✘** “[Phương án sai 2]”: **SAI.** [Lý do]
**✘** “[Phương án sai 3]”: **SAI.** [Lý do]
## **Question [STT + 1].** [Trích nguyên câu chứa chỗ trống (2)]
[...]
**[ONE]**
```

#### 2.5.2 Part sắp xếp (Arrangement — không có bài đọc chung)
*(Các câu lẻ đánh dấu `a.`, `b.`, `c.` hoặc `(a)`, `(b)`, `(c)` — tránh dùng `a)`, `b)`.)*
```
# PART [STT]: Mark the letter A, B, C, or D... correct arrangement of the sentences...
## **Question [STT].** [Đoạn hội thoại / thư / đoạn văn bị xáo trộn]
**<u>A</u>.** [Phương án A đúng]
**B.** [Phương án B]
**C.** [Phương án C]
**D.** [Phương án D]
**[HDG] Giải thích:**
**Dịch:** [Bản dịch tiếng Việt hoàn chỉnh theo thứ tự đúng]
[Dẫn chứng logic nối câu]
**✔** “[Phương án đúng]”: **ĐÚNG.** [Lý do]
**✘** “[Phương án sai 1]”: **SAI.** [Lý do]
**✘** “[Phương án sai 2]”: **SAI.** [Lý do]
**✘** “[Phương án sai 3]”: **SAI.** [Lý do]
```

#### 2.5.3 Part đọc hiểu (Reading Comprehension với `[DIV]` và `[ONE]`)
```
# PART [STT]: Read the following passage and mark the letter A, B, C, or D...
**[DIV]**
<p align="center"><b>[TIÊU ĐỀ BÀI ĐỌC]</b></p>
[Bài đọc — giữ nguyên từ **in đậm**, <u>gạch chân</u>, ký hiệu [I]..[IV] nếu có]
## **Question [STT].** [Nội dung câu hỏi]
**<u>A</u>.** [Phương án A đúng]
**B.** [Phương án B]
**C.** [Phương án C]
**D.** [Phương án D]
**[HDG] Giải thích:**
**Dịch:** [Bản dịch tiếng Việt đoạn văn liên quan]
[Trích dẫn câu chứa thông tin trả lời từ bài đọc]
**✔** “[Phương án đúng]”: **ĐÚNG.** [Lý do]
**✘** “[Phương án sai 1]”: **SAI.** [Lý do]
**✘** “[Phương án sai 2]”: **SAI.** [Lý do]
**✘** “[Phương án sai 3]”: **SAI.** [Lý do]
**[ONE]**
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

### 3.1 Bảng tóm tắt quy ước định dạng OLM
| Thành phần đề thi | Quy ước định dạng | Lưu ý bắt buộc |
| ----- | ----- | ----- |
| `# PHẦN 1`, `2`, `3` / `PART` | **Heading 1** (`Times New Roman` 13pt, đậm, `#000000`) | Bắt buộc số Ả Rập (không dùng số La Mã); Tiếng Anh luôn dùng `PART` |
| `## **Câu [STT].**` / `## **Question [STT].**` | **Heading 2** (`#000000`, chỉ in đậm nhãn) | Dấu chấm `.` sau số câu (không dùng `:`); đánh số liên tục hoặc đặt lại theo phần/PART |
| Thẻ câu hỏi chùm `**[DIV]**`, `**[DIV][FIX]**`, `**[ONE]**` | Đoạn **Normal** (1 đoạn riêng, in đậm) | **Tuyệt đối không đặt heading `#`**; 100% cụm DIV/FIX phải đóng bằng `[ONE]` |
| `## **Câu [STT]. [TF]**` (Phần 2 Đúng–Sai) | **Heading 2** + Thẻ `[TF]` | Bắt buộc có `[TF]`; nhận định dùng chữ in hoa `**A.**`, `**B.**`, `**C.**`, `**D.**` |
| `**<u>A</u>.**` (Phương án / Nhận định đúng) | Gạch chân duy nhất chữ cái nhãn `<w:u w:val="single"/>` | Không gạch chân dấu chấm `.`; đúng 1 dấu cách; không dùng `#`, `*` hay `Đáp án: A` |
| `**Trả lời:** [[Đáp án 1\|\|Đáp án 2]]` (Phần 3) | Đặt trong cặp ngoặc vuông đôi `[[...]]` | Tối đa 4 ký tự số; nhiều đáp án ngăn cách bằng `\|\|` |
| `**[HDG] Giải thích:**` | Mở đầu giải thích bằng thẻ `[HDG]` | Bỏ dòng `Lời giải` |
| Mỗi thành phần câu / lời giải | 1 đoạn (Enter) độc lập | Không dùng `<br>`, ngắt dòng mềm hay dòng trống thừa |
| Bảng số liệu & Khối `<code>` | Bảng chuẩn Word / khối `Consolas` 11pt nền xám nhẹ | Không để sót thẻ HTML hoặc ký hiệu Markdown thô |
| Công thức `$..$`, `$$..$$` | Công thức chuẩn Word (Equation / `Cambria Math`, `#000000`) | Đồng bộ 100% toàn bài; không dùng `\ce{}` |
| Ảnh minh họa | Chèn `inline`, căn giữa | Đúng vị trí câu, giữ tỷ lệ, không `floating` / tràn lề A4 |
| `✔`, `✘`, `**[???]**` | Ký hiệu Unicode trực tiếp, `#000000` | Cấm `X`/`x`, `✓`/`✗`, emoji |

### 3.2 Quy chuẩn & Điều kiện viết công thức LaTeX
- **Điều kiện áp dụng (đồng bộ 100% toàn bài):** Bắt buộc dùng công thức chuẩn cho **mọi** biểu thức, biến số, phân số, lũy thừa, chỉ số, căn thức, tích phân, vectơ, khoảng/đoạn và ký hiệu toán–lý–hóa (`$x$`, `$e^x$`, `$x^\alpha$`, `$v = 5\text{ m/s}$`, `$\mathrm{H_2O}$`) ở **tất cả vị trí** (đề bài, phương án, `Tóm tắt:`, `[HDG] Giải thích:` và **cả 4 dòng `✔`/`✘`**). **Không áp dụng** cho văn bản chữ thường, số đếm/năm/thời gian thông thường (VD `2025`, `50 phút`, `Câu 1`) hoặc môn không có công thức (Ngữ văn, Tiếng Anh...).
- **Dấu bọc theo cách nhập liệu:** Khi biên dịch sang file Word `.docx`, dùng `$..$` (công thức trong dòng) và `$$..$$` (công thức căn giữa dòng riêng).
- **Quy ước ký hiệu chuẩn:** Số thập phân dùng dấu phẩy `$2{,}5$` · đơn vị chữ đứng `\text{ kg}` · vectơ `\overrightarrow{AB}` · góc `\widehat{ABC}` · khoảng `$(-\infty; 2)$`, `$[a; b]$` · hóa học dùng `\mathrm{..}`, không dùng `\ce{}` (`$\mathrm{2H_2 + O_2 \xrightarrow{t^\circ} 2H_2O}$`, phản ứng thuận nghịch `\rightleftharpoons`).

## 4. CHECKLIST KIỂM TRA & LỖI OLM THƯỜNG GẶP

### 4.1 Checklist kiểm tra trước khi nạp OLM
- [ ] Đủ 100% câu hỏi, không nhảy số (câu bị lệch đã gắn `**[???]**`); đánh số nhất quán (liên tục toàn đề hoặc đặt lại `1..N` theo phần / PART kèm `from 1 to N`; bài đục lỗ luôn reset `(1)`, `(2)`...).
- [ ] Câu hỏi chùm nhất quán (Bật: dùng thẻ `**[DIV]**` hoặc `**[DIV][FIX]**` ở kiểu Normal không `#` Heading và 100% cụm đóng bằng `**[ONE]**`; Tắt: đã tách độc lập và chép dữ kiện chung; Tiếng Anh luôn `PART`).
- [ ] Nhãn OLM đúng quy ước (Phần 1 & 2 gạch chân duy nhất chữ cái nhãn `**<u>A</u>.**`, không gạch chân dấu chấm, cấm `*` và `Đáp án: A`; Phần 2 có `[TF]`; Phần 3 có `**Trả lời:** [[...]]` ≤ 4 ký tự; giải thích mở đầu `**[HDG] Giải thích:**`); đúng 1 dấu cách sau mọi nhãn.
- [ ] Văn bản sạch: 100% chữ đen `#000000` (kể cả Heading 1/2), nội dung không in đậm, không có `<br>`, không có ngắt dòng mềm hay dòng trống thừa, không sót ký hiệu Markdown/HTML thô.
- [ ] Công thức đồng bộ 100% toàn bài (đề bài, phương án, `Tóm tắt:`, `[HDG] Giải thích:` và 4 dòng `✔`/`✘`), không sót công thức viết chữ chay (`e^x`, `x^α`, `a/b`, `√`, `∫`) hay lỗi `\ce{}`.
- [ ] Ảnh chèn `inline`, căn giữa, đúng vị trí, giữ nguyên tỷ lệ, không ảnh rác / `floating` / tràn lề A4; ký hiệu `✔`/`✘` đúng Unicode.

### 4.2 Bảng lỗi OLM thường gặp & Cách khắc phục
| Mã | Lỗi thường gặp trên OLM | Cách khắc phục |
| ----- | ----- | ----- |
| **OLM-01** | Sai cấu trúc thẻ `[DIV]`/`[FIX]`/`[ONE]` hoặc sai chế độ chùm | Đặt `**[DIV]**`, `**[DIV][FIX]**` và `**[ONE]**` ở kiểu Normal (không heading `#`), 100% cụm mở đóng bằng `**[ONE]**`; khi Tắt chùm: tách độc lập + chép dữ kiện chung |
| **OLM-02** | Gạch chân sai nhãn, in đậm nội dung hoặc dùng cú pháp Azota | Chỉ in đậm nhãn; chỉ gạch chân chữ cái đầu nhãn qua `<w:u w:val="single"/>` (`**<u>A</u>.**`), không gạch chân dấu chấm; cấm `*` hoặc `Đáp án: A` |
| **OLM-03** | Thiếu thẻ OLM hoặc sai nhãn phần/câu | Gắn đủ `[TF]` (Phần 2), `[[...]]` (Phần 3), `[HDG]` (Giải thích); Heading 1 dùng số Ả Rập (`# PHẦN 1`); nhãn câu dùng dấu chấm `.` (`## **Câu [STT].**`) |
| **OLM-04** | Dùng `X`/`x`, `✓`/`✗`, emoji thay cho `✔`/`✘` | Đổi sang `✔` (`U+2714`), `✘` (`U+2718`) và không lặp nhãn `A.`, `B.` trong 4 dòng phân tích |
| **OLM-05** | Đáp án Phần 3 > 4 ký tự số | Đổi đơn vị hoặc ghi `$(10^x)$` sau câu hỏi |
| **OLM-06** | Chỗ trống bài đục lỗ không reset hoặc bài sắp xếp dùng `a)`, `b)` | Reset `(1)`, `(2)`... kèm `from 1 to N` cho từng bài; bài sắp xếp dùng `a.`, `b.` hoặc `(a)`, `(b)` |
