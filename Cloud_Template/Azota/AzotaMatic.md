# **AzotaMatic: Bố cục, Quy ước & Quy tắc riêng cho đề thi Azota**

## **I. QUY ƯỚC & RULE RIÊNG NỀN TẢNG AZOTA**

### **1. Định dạng văn bản**

- **Font chữ & Cỡ chữ**: Font `Times New Roman` (hoặc `Aptos`), cỡ chữ `12pt` - `13pt`.

- **Ngắt dòng & Cách dòng**: Đặt thẻ `<br>` cuối mỗi dòng và cách 1 dòng trống giữa các nội dung (câu hỏi, phương án, lời giải) để không bị dính dòng.

### **2. Tiêu đề phần & Đánh số câu**

- **Tiêu đề phần (Heading 1)**: Bắt buộc dùng chữ số La Mã:
  - `# PHẦN I: TRẮC NGHIỆM NHIỀU LỰA CHỌN`
  - `# PHẦN II: TRẮC NGHIỆM ĐÚNG – SAI`
  - `# PHẦN III: TRẮC NGHIỆM TRẢ LỜI NGẮN`

- **Môn Tiếng Anh**: Tên phần bắt buộc thay đổi dựa theo lời dẫn đề bài gốc:
  - `# PART 1: [Lời dẫn đề bài, ví dụ: Read the following advertisement...]`
  - `# PART 2: [Lời dẫn đề bài, ví dụ: Mark the letter A, B, C, or D...]`
  - `# PART 3: [Lời dẫn đề bài, ví dụ: Read the following passage...]`

- **Đánh số câu hỏi (Heading 2)**: Bắt buộc dùng dấu hai chấm `:` sau nhãn câu:
  - `## **Câu [STT]:** [Nội dung câu hỏi không in đậm]`
  - Với môn Tiếng Anh: `## **Question [STT].** [Nội dung câu hỏi không in đậm]`

### **3. Quy tắc nhận diện đáp án từng phần**

- **PHẦN I (Nhiều lựa chọn)**: Có 1 đáp án đúng duy nhất:
  - *Cách 1 (Mặc định)*: Phương án để `**A.**`, ghi `Đáp án: A` trong mục Lời giải.
  - *Cách 2*: Đánh dấu `*<b>A.</b>` trực tiếp trước phương án đúng, không cần dòng `Đáp án: A`.

- **PHẦN II (Đúng – Sai)**: Mỗi câu gồm 4 nhận định a, b, c, d:
  - Nhận định **ĐÚNG**: Đánh dấu tiền tố `*<b>a)</b>`.
  - Nhận định **SAI**: Đánh dấu `**b)**`.

- **PHẦN III (Trả lời ngắn)**:
  - Đáp án ghi tại dòng `Đáp án: [Giá trị]` trong Lời giải.
  - Giới hạn tối đa 4 ký tự số (bao gồm số 0-9, dấu âm `-`, dấu phẩy `,` hoặc chấm `.`).
  - Nếu có nhiều đáp án đúng tương đương: Ngăn cách bằng dấu gạch đứng `|` (Ví dụ: `Đáp án: 12,5 | 12.5`).

### **4. Quy chuẩn công thức & ký hiệu**

- **LaTeX `$..$`**: Chỉ bọc `$..$` khi có công thức toán học, biểu thức tính toán, biến số hoặc ký hiệu khoa học/hóa học (`$x$`, `$v = 5\text{ m/s}$`). Không áp dụng cho văn bản chữ thường.

- **Số thập phân**: Dùng dấu phẩy: `$2{,}5$`.

- **Ký hiệu đặc biệt**: Đơn vị chữ đứng `\text{ kg}`, vectơ `\overrightarrow{AB}`, góc `\widehat{ABC}`.

- **Hoá học**: Dùng `\mathrm{...}` (không dùng `\ce{}`): `$\mathrm{2H_2 + O_2 \xrightarrow{t^\circ} 2H_2O}$`.

### **5. Xử lý câu hỏi, hình ảnh và tư liệu**

- **Tách câu độc lập**: Các câu nhiều ý hoặc dùng chung tư liệu/đồ thị phải được tách thành các câu độc lập (chép lại đoạn thông tin/đồ thị cần thiết vào từng câu).

- **Ảnh câu hỏi**: Chỉ lấy ảnh nội dung trong câu hỏi; thiếu ảnh thì gắn nhãn: `**[CÂU HỎI CÓ HÌNH ẢNH, VUI LÒNG CHÈN HÌNH ẢNH VÀO]**`.

- **Rách/mất chữ**: Điền theo ngữ cảnh và gắn `**[???]**`.

---

## **II. BỐ CỤC MẪU CHUẨN CỦA ĐỀ THI AZOTA**

### **1. Khung tổng thể đề thi hoàn chỉnh**

```markdown
# PHẦN I: TRẮC NGHIỆM NHIỀU LỰA CHỌN
[Nội dung các câu hỏi Phần I]

# PHẦN II: TRẮC NGHIỆM ĐÚNG – SAI
[Nội dung các câu hỏi Phần II]

# PHẦN III: TRẮC NGHIỆM TRẢ LỜI NGẮN
[Nội dung các câu hỏi Phần III]
```

---

### **2. Mẫu Phần I: Trắc nghiệm nhiều lựa chọn**

#### **Cách 1: Ghi đáp án trong Lời giải (Khuyên dùng)**
```markdown
## **Câu 1:** [Nội dung câu hỏi]<br>
[Hình ảnh, tư liệu kèm theo nếu có]<br>
**A.** [Phương án A]<br>
**B.** [Phương án B]<br>
**C.** [Phương án C]<br>
**D.** [Phương án D]<br>
**Lời giải**<br>
Đáp án: A<br>
**Giải thích:**<br>
[Các bước giải và dẫn chứng lý luận]<br>
[Phương án đúng] (A): ĐÚNG. [Lý do]<br>
[Phương án sai] (B): SAI. [Lý do]<br>
[Phương án sai] (C): SAI. [Lý do]<br>
[Phương án sai] (D): SAI. [Lý do]<br>
```

#### **Cách 2: Đánh dấu `*<b>A.</b>` trực tiếp tại phương án**
```markdown
## **Câu 1:** [Nội dung câu hỏi]<br>
*<b>A.</b> [Phương án đúng]<br>
**B.** [Phương án sai 1]<br>
**C.** [Phương án sai 2]<br>
**D.** [Phương án sai 3]<br>
**Lời giải**<br>
**Giải thích:**<br>
[Các bước giải và dẫn chứng lý luận]<br>
```

---

### **3. Mẫu Phần II: Trắc nghiệm Đúng – Sai**

```markdown
## **Câu 1:** [Nội dung lời dẫn câu hỏi]<br>
[Hình ảnh, tư liệu bảng biểu nếu có]<br>
*<b>a)</b> [Nội dung nhận định đúng a]<br>
**b)** [Nội dung nhận định sai b]<br>
*<b>c)</b> [Nội dung nhận định đúng c]<br>
**d)** [Nội dung nhận định sai d]<br>
**Lời giải**<br>
**Giải thích:**<br>
a) ĐÚNG. [Dẫn chứng giải thích ý a]<br>
b) SAI. [Dẫn chứng giải thích ý b]<br>
c) ĐÚNG. [Dẫn chứng giải thích ý c]<br>
d) SAI. [Dẫn chứng giải thích ý d]<br>
```

---

### **4. Mẫu Phần III: Trắc nghiệm trả lời ngắn**

```markdown
## **Câu 1:** [Nội dung bài toán / câu hỏi tính toán]<br>
[Hình ảnh, bảng biểu nếu có]<br>
**Lời giải**<br>
Đáp án: 12,5 | 12.5<br>
**Giải thích:**<br>
[Tóm tắt giả thiết và công thức cần áp dụng]<br>
[Các bước biến đổi chi tiết]<br>
[Kết luận giá trị cần điền]<br>
```

---

### **5. Mẫu các Part môn Tiếng Anh**

#### **Part 1: Đục lỗ (Gap-Filling)**
```markdown
# PART 1: Read the following advertisement and mark the letter A, B, C, or D on your answer sheet to indicate the option that best fits each of the numbered blanks from 1 to [N]

<p align="center"><b>[TIÊU ĐỀ BÀI ĐỌC]</b></p>
[Nội dung văn bản đọc: các chỗ trống bắt buộc reset từ (1), (2), (3)... cho mỗi bài mới, ví dụ: ... (1) ______ ... (2) ______ ...]<br>

## **Question 1.** [Nội dung câu hỏi hoặc dòng chứa chỗ trống (1)]<br>
**A.** [Phương án A]<br>
*<b>B.</b> [Phương án đúng]<br>
**C.** [Phương án C]<br>
**D.** [Phương án D]<br>
**Lời giải**<br>
Đáp án: B<br>
**Giải thích:**<br>
[Kiến thức ngữ pháp / từ vựng và lý do chọn B]<br>
```

#### **Part 2: Sắp xếp đoạn văn (Ordering)**
```markdown
# PART 2: Mark the letter A, B, C, or D to indicate the correct arrangement...

## **Question 2.** [Lời dẫn câu hỏi]<br>
a. [Câu thứ nhất]<br>
b. [Câu thứ hai]<br>
c. [Câu thứ ba]<br>
d. [Câu thứ tư]<br>
e. [Câu thứ năm]<br>
**A.** a - b - c - d - e<br>
*<b>B.</b> b - a - d - c - e<br>
**C.** c - a - b - d - e<br>
**D.** d - c - b - a - e<br>
**Lời giải**<br>
Đáp án: B<br>
**Giải thích:**<br>
- Mở đầu: [Câu mở đoạn]<br>
- Phát triển ý: [Liên kết logic giữa các câu]<br>
- Kết luận: [Câu chốt]<br>
```

#### **Part 3: Đọc hiểu văn bản (Reading Comprehension)**
```markdown
# PART 3: Read the following passage and mark the letter A, B, C, or D...

<p align="center"><b>[TIÊU ĐỀ BÀI ĐỌC HIỂU]</b></p>
[Đoạn 1 bài đọc]<br>
[Đoạn 2 bài đọc]<br>
[Đoạn 3 bài đọc]<br>

## **Question 3.** [Câu hỏi đọc hiểu]<br>
**A.** [Phương án A]<br>
**B.** [Phương án B]<br>
*<b>C.</b> [Phương án đúng C]<br>
**D.** [Phương án D]<br>
**Lời giải**<br>
Đáp án: C<br>
**Giải thích:**<br>
[Dẫn chứng trực tiếp từ đoạn văn trong bài đọc để chứng minh C đúng]<br>
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
