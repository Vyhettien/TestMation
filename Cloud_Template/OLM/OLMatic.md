# **OLMatic: Bố cục, Quy ước & Quy tắc riêng cho đề thi OLM**

## **I. QUY ƯỚC & RULE RIÊNG NỀN TẢNG OLM**

### **1. Định dạng văn bản**

- **Font chữ & Cỡ chữ**: Font `Times New Roman` (hoặc `Aptos`), cỡ chữ `12pt` - `13pt`.

- **Ngắt dòng & Cách dòng**: Đặt thẻ `<br>` cuối mỗi dòng và cách 1 dòng trống giữa các nội dung (câu hỏi, phương án, lời giải) để không bị dính dòng.

### **2. Tiêu đề phần & Đánh số câu**

- **Tiêu đề phần (Heading 1)**: Bắt buộc dùng chữ số thường (Ả Rập), không dùng số La Mã:
  - `# PHẦN 1: TRẮC NGHIỆM NHIỀU LỰA CHỌN`
  - `# PHẦN 2: TRẮC NGHIỆM ĐÚNG – SAI`
  - `# PHẦN 3: TRẮC NGHIỆM TRẢ LỜI NGẮN`

- **Môn Tiếng Anh**: Tên phần bắt buộc thay đổi dựa theo lời dẫn đề bài gốc:
  - `# PART 1: [Lời dẫn đề bài, ví dụ: Read the following...]`
  - `# PART 2: [Lời dẫn đề bài, ví dụ: Mark the letter A, B, C, or D...]`
  - `# PART 3: [Lời dẫn đề bài, ví dụ: Read the following passage...]`

- **Đánh số câu hỏi (Heading 2)**: Bắt buộc dùng dấu chấm `.` sau nhãn câu (không dùng dấu hai chấm `:`):
  - `## **Câu [STT].** [Nội dung câu hỏi không in đậm]`
  - Với môn Tiếng Anh: `## **Question [STT].** [Nội dung câu hỏi không in đậm]`

### **3. Hệ thống thẻ nhận diện (Tags OLM)**

- **Gạch chân phương án đúng**: Bắt buộc dùng cú pháp `**<u>A</u>.**` (chỉ gạch chân chữ cái nhãn, không gạch chân dấu chấm).
  - *Lưu ý*: Tuyệt đối không dùng dấu sao `*` hoặc dòng `Đáp án: A` (OLM không nhận diện được).

- **Phần 2 (Đúng – Sai)**: Bắt buộc thêm thẻ `[TF]` đặt ngay sau câu hỏi:
  - Cú pháp: `## **Câu [STT].** [TF] [Lời dẫn câu hỏi]`
  - Nhận định ĐÚNG: Gạch chân nhãn `**<u>A</u>.**`.
  - Nhận định SAI: Không gạch chân `**B.**`.

- **Phần 3 (Trả lời ngắn)**: Bắt buộc đặt trong cặp ngoặc vuông đôi `[[...]]`:
  - Cú pháp: `**Trả lời:** [[Đáp án 1||Đáp án 2]]`
  - Giới hạn tối đa 4 ký tự số. Nhiều đáp án tương đương ngăn cách bằng dấu `||` (hoặc `|`).

- **Thẻ Hướng dẫn giải `[HDG]`**: Bắt buộc mở đầu dòng bằng `**[HDG] Giải thích:**` (bỏ dòng 'Lời giải').

- **Quy tắc gom nhóm câu chùm và thẻ đóng `[ONE]`**:
  - Thẻ `**[DIV]**`: Mở nhóm câu dùng chung dữ liệu/bài đọc hiểu mà các câu hỏi có thể đảo vị trí độc lập. Đứng riêng một dòng, có dòng trống cách ly và không đặt heading.
  - Thẻ `**[DIV][FIX]**`: Mở nhóm câu đục lỗ hoặc câu phụ thuộc kết quả (cố định thứ tự câu hỏi). Đứng riêng một dòng, có dòng trống cách ly và không đặt heading. Với bài đục lỗ, số thứ tự chỗ trống cần điền bên trong đoạn văn BẮT BUỘC reset từ `(1)`, `(2)`, `(3)`... cho mỗi bài mới.
  - Thẻ `**[ONE]**`: **Sau tag [DIV] (hoặc [DIV][FIX]) BẮT BUỘC PHẢI CÓ tag [ONE] để kết thúc cụm**, đặt ngay sau câu hỏi cuối cùng của cụm (đứng riêng một dòng, cách dòng ra, không đặt heading) để giải phóng nhóm và đưa hệ thống trở lại dạng câu đơn độc lập.

### **4. Quy chuẩn công thức & ký hiệu**

- **LaTeX `$..$`**: Chỉ bọc `$..$` khi có công thức toán học, biểu thức tính toán, biến số hoặc ký hiệu khoa học/hóa học (`$x$`, `$v = 5\text{ m/s}$`).

- **Số thập phân**: Dùng dấu phẩy: `$2{,}5$`.

- **Ký hiệu đặc biệt**: Đơn vị chữ đứng `\text{ kg}`, vectơ `\overrightarrow{AB}`, góc `\widehat{ABC}`.

- **Hoá học**: Dùng `\mathrm{...}`: `$\mathrm{2H_2 + O_2 \xrightarrow{t^\circ} 2H_2O}$`.

---

## **II. BỐ CỤC MẪU CHUẨN CỦA ĐỀ THI OLM**

### **1. Khung tổng thể đề thi hoàn chỉnh**

```markdown
# PHẦN 1: TRẮC NGHIỆM NHIỀU LỰA CHỌN
[Nội dung các câu hỏi Phần 1]

# PHẦN 2: TRẮC NGHIỆM ĐÚNG – SAI
[Nội dung các câu hỏi Phần 2]

# PHẦN 3: TRẮC NGHIỆM TRẢ LỜI NGẮN
[Nội dung các câu hỏi Phần 3]
```

---

### **2. Mẫu Phần 1: Trắc nghiệm nhiều lựa chọn**

```markdown
## **Câu 1.** [Nội dung câu hỏi]<br>
[Hình ảnh, bảng biểu nếu có]<br>
**<u>A</u>.** [Phương án đúng - gạch chân nhãn A]<br>
**B.** [Phương án sai 1]<br>
**C.** [Phương án sai 2]<br>
**D.** [Phương án sai 3]<br>
**[HDG] Giải thích:**<br>
[Các bước giải và dẫn chứng lý luận]<br>
[Phương án đúng] (A): ĐÚNG. [Lý do]<br>
[Phương án sai] (B): SAI. [Lý do]<br>
[Phương án sai] (C): SAI. [Lý do]<br>
[Phương án sai] (D): SAI. [Lý do]<br>
```

---

### **3. Mẫu Phần 2: Trắc nghiệm Đúng – Sai (Thẻ `[TF]`)**

```markdown
## **Câu 1.** [TF] [Nội dung lời dẫn câu hỏi]<br>
[Hình ảnh, bảng biểu nếu có]<br>
**<u>A</u>.** [Nhận định đúng - gạch chân nhãn A]<br>
**B.** [Nhận định sai - không gạch chân]<br>
**<u>C</u>.** [Nhận định đúng - gạch chân nhãn C]<br>
**D.** [Nhận định sai - không gạch chân]<br>
**[HDG] Giải thích:**<br>
A: ĐÚNG. [Dẫn chứng giải thích ý A]<br>
B: SAI. [Dẫn chứng giải thích ý B]<br>
C: ĐÚNG. [Dẫn chứng giải thích ý C]<br>
D: SAI. [Dẫn chứng giải thích ý D]<br>
```

---

### **4. Mẫu Phần 3: Trắc nghiệm trả lời ngắn (Cú pháp `[[...]]`)**

```markdown
## **Câu 1.** [Nội dung bài toán / câu hỏi tính toán]<br>
[Hình ảnh, bảng biểu nếu có]<br>
**Trả lời:** [[12,5||12.5]]<br>
**[HDG] Giải thích:**<br>
[Tóm tắt giả thiết và công thức cần áp dụng]<br>
[Các bước biến đổi chi tiết]<br>
[Kết luận giá trị cần điền]<br>
```

---

### **5. Mẫu câu chùm và các Part Tiếng Anh (Cụm thẻ `[DIV]`, `[DIV][FIX]` và đóng `[ONE]`)**

#### **Cụm câu chùm bài đọc hiểu (Dùng `[DIV]` và đóng `[ONE]`)**
```markdown
**[DIV]**

<p align="center"><b>[TIÊU ĐỀ BÀI ĐỌC]</b></p>
[Nội dung bài đọc dùng chung cho các câu hỏi bên dưới]<br>

## **Câu 1.** [Nội dung câu hỏi đọc hiểu 1]<br>
**<u>A</u>.** [Phương án đúng]<br>
**B.** [Phương án sai 1]<br>
**C.** [Phương án sai 2]<br>
**D.** [Phương án sai 3]<br>
**[HDG] Giải thích:**<br>
[Giải thích chi tiết]<br>

## **Câu 2.** [Nội dung câu hỏi đọc hiểu 2]<br>
**A.** [Phương án sai 1]<br>
**<u>B</u>.** [Phương án đúng]<br>
**C.** [Phương án sai 2]<br>
**D.** [Phương án sai 3]<br>
**[HDG] Giải thích:**<br>
[Giải thích chi tiết]<br>

**[ONE]**
```

#### **Cụm bài đục lỗ / phụ thuộc thứ tự (Dùng `[DIV][FIX]` và đóng `[ONE]`)**
```markdown
**[DIV][FIX]**

<p align="center"><b>[TIÊU ĐỀ BÀI ĐỤC LỖ]</b></p>
[Nội dung đoạn văn có các vị trí cần điền từ: bắt buộc reset từ (1), (2), (3)... cho mỗi bài mới]<br>

## **Câu 3.** [Trích đoạn chứa chỗ trống (1)]<br>
**<u>A</u>.** [Phương án đúng]<br>
**B.** [Phương án sai]<br>
**C.** [Phương án sai]<br>
**D.** [Phương án sai]<br>
**[HDG] Giải thích:**<br>
[Giải thích ngữ pháp / từ vựng]<br>

## **Câu 4.** [Trích đoạn chứa chỗ trống (2)]<br>
**A.** [Phương án sai]<br>
**<u>B</u>.** [Phương án đúng]<br>
**C.** [Phương án sai]<br>
**D.** [Phương án sai]<br>
**[HDG] Giải thích:**<br>
[Giải thích ngữ pháp / từ vựng]<br>

**[ONE]**
```

---

### **6. Mẫu định dạng tư liệu đính kèm**

#### **Tư liệu văn bản**
```markdown
<p align="center"><b>[TIÊU ĐỀ TƯ LIỆU]</b></p>
[Nội dung đoạn trích tư liệu - mỗi đoạn một dòng]<br>
<p align="right"><i>(Nguồn: [Tên nguồn tài liệu])</i></p>
```

#### **Tư liệu bảng số liệu**
```markdown
<p align="center"><b>[TÊN BẢNG SỐ LIỆU]</b></p>
<p align="right"><i>(Đơn vị: [Đơn vị tính])</i></p>

| **[Cột 1]** | **[Cột 2]** | **[Cột 3]** |
| :---: | :---: | :---: |
| **[Hàng 1]** | [Số liệu] | [Số liệu] |
| **[Hàng 2]** | [Số liệu] | [Số liệu] |

<p align="right"><i>(Nguồn: [Tên nguồn tài liệu])</i></p>
```

#### **Tư liệu khối mã (Code)**
```markdown
<code>
[Nội dung đoạn code, mỗi lệnh một dòng]
</code>
```
