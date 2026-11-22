# OLMation

> **Description**: Complete, standardized automated exam generation system for OLM on Cloud AI.
> **Output Language**: Vietnamese

## PREREQUISITES
> [!CAUTION]
> Requires 1 of 2 environments: **(1) Sandbox/Python** (recommended; OpenXML `.docx`, OMML `<m:oMath>`, underline `<w:u>`, `.zip`) · **(2) Google Docs/Drive** (split long exams `_[1]`, `_[2]`... then merge; Google Docs only).
> Missing both → halt, no plain text: `[LỖI: HỆ THỐNG KHÔNG THỂ SỬ DỤNG ĐƯỢC do thiếu Sandbox/Python hoặc Google Docs/Drive. Vui lòng đổi sang môi trường hỗ trợ.]`

## USER SETTINGS
*(Check `[x]` or edit parameters below before sending to AI)*

- **File Naming (`.docx`)**: `[Môn học]_[Giai đoạn]_[Lớp]_[Nền tảng].docx`
  *(Example: `VatLi_CuoiKy2_11_OLM.docx` or `TiengAnh_GiuaKy1_12_OLM.docx`)*

- **Multi-Exam Documents**:
  - [x] **Split into multiple files**: Export 1 separate `.docx` per sub-exam (`..._[MãĐề].docx`; bundle multiple files into `.zip`)
  - [ ] **Merge into one file**: Combine all sub-exams into 1 `.docx` (clearly separated between exams)

- **MCQ & True–False Answer Marking (Part 1 & Part 2)**:
  - Mandatory: underline only the capital letter of the correct option label `**<u>A</u>.**` (`<w:u w:val="single"/>`, never underline the period — OLM standard)

- **Question Numbering**:
  - [x] **Continuous across exam** (Câu 1, Câu 2... Câu N)
  - [ ] **Reset from Câu 1 per section** (Part 1, 2, 3 / update `from 1 to N` in English PART prompt)

- **Clustered / Group / Part Questions**:
  - [x] **On**: Auto-insert `**[DIV]**` (reading / shuffleable cluster) or `**[DIV][FIX]**` (gap-fill / fixed order), close cluster with `**[ONE]**`
  - [ ] **Off**: Split standalone, copy shared data into each sub-question *(English always On with `PART [STT]` + `[DIV]`/`[DIV][FIX]` and `[ONE]`)*

- **Explanation Detail Level**:
  - [ ] **Concise**: Start with `**[HDG] Giải thích:**`, core rationale only; omit 4 `✔`/`✘` lines and `**Tóm tắt:**`
  - [x] **Detailed**: Start with `**[HDG] Giải thích:**` + full rationale + `✔`/`✘` option analysis (4 `✔`/`✘` lines in Part 1–2, `**Tóm tắt:**` in Part 3)

- **Word (`.docx`) Formatting**:
  - Font: `Times New Roman` (or `Aptos`) · Size: `13pt` · Color: `#000000` (pure black)

## EXECUTION GUIDE
1. Send `OLMation_EN.md` to Cloud AI.
2. Send exam + `P1` (summary report only; if interrupted send `P1.2`) → `P2` (build exam + OLM tags + keys; if overflow send `P2.2`).
3. Send `P3` (add detailed explanations + auto-QA and receive download link; if overflow send `P3.2`).
4. *(Optional)* Send `QA` for independent quality audit, 100% elimination of raw syntax (#, ##, <b>, <u>, <i>...) or standardizing an existing Word file.

## 1. AUTHORING RULES & PROHIBITIONS
### 1.1 Mandatory Rules
1. **Preserve**: Keep original wording and notation (incl. bold/underlined words in passages — those belong to the prompt, not answer keys). Handle groups per Settings: On → wrap with `**[DIV]**` or `**[DIV][FIX]**` and close with `**[ONE]**`; Off → split standalone, copy shared data into each sub-question.
2. **Essay questions** → convert all to Part 3 (Short Answer).
3. **Labels, OLM Tags & Headings**: `# PHẦN [STT]: ...` (Arabic numerals `1`, `2`, `3`), English `# PART [STT]: [Original prompt]` (Heading 1); `## **Câu [STT].** ...` (period after number, not `:`), True–False `## **Câu [STT]. [TF]** ...`, English `## **Question [STT].** ...` (Heading 2); cluster tags `**[DIV]**`, `**[DIV][FIX]**`, `**[ONE]**` on their own standalone **Normal** line (never `#` Heading); options / statements `**<u>A</u>.** ...` (underline capital letter only, not the period) or `**B.** ...` (omit `#` prefix so OLM auto-shuffles); Short Answer `**Trả lời:** [[Đáp án 1||Đáp án 2]]` (≤ 4 numeric chars); explanations start with `**[HDG] Giải thích:**` (omit `Lời giải`). Exactly 1 space after label; **bold label only**, unbolded content.
4. **Paragraphs**: Each element (question, `[DIV]`/`[ONE]` tag, option, statement, solution line) = 1 source line = 1 `<w:p>`; no `<br>`, no empty paragraphs.
5. **Symbols**: True `✔` (`U+2714`), False `✘` (`U+2718`).
6. **Defects** (`DAT-01..06`): missing image → `**[CÂU HỎI CÓ HÌNH ẢNH, VUI LÒNG CHÈN HÌNH ẢNH VÀO]**`; blurry text → infer from context + `**[???]**`; missing key → AI solves; skipped/misaligned source numbering (e.g. `Câu 12` → `Câu 14` or `Câu 43` → `Câu 45`) → place `**[???]**` between both items (applies to both numbering modes).
7. **Token overflow control**: Explain current item only, no equivalent questions (`TOK-02`); `P1` never prints raw exam (`TOK-05`); `P1`–`P2` forbid `**[HDG] Giải thích:**`, `**Tóm tắt:**`, or 4 `✔`/`✘` lines (`P2` keys only: underline `**<u>A</u>.**` in Part 1–2 and `**Trả lời:** [[...]]` in Part 3) (`TOK-04`); on overflow call `.[n]` from `.2` (`P2.2`, `P3.2`...) to continue & merge (`TOK-03`).
8. **Publishing**: Sandbox → `.docx` (or `.zip` when split); Google Docs → split then merge (`PKG-01`).
9. **Images**: Question-content images only; insert inline, centered, exact position, keep aspect ratio (`DAT-05`).

### 1.2 PROHIBITIONS
1. **Extra `python-docx` XML**: 0 `<w:spacing>` (never set `space_before`/`space_after`), 0 extra `<w:sz>` on normal text runs (`<code>` uses dedicated `Consolas` 11pt paragraph style), 0 `<w:br/>`; no empty paragraphs (`add_paragraph("")`, `<w:p/>`) (`FMT-03`).
2. **`<br>` tags**: Forbidden everywhere.
3. **Wrong timing / bloat**: No equivalent questions; no `**[HDG] Giải thích:**`, `**Tóm tắt:**`, or 4 `✔`/`✘` lines in `P1`–`P2`; no full raw exam output in `P1`.
4. **Bold, underline & color**: Never bold body content; never underline the period after the option letter (`<u>A.</u>` is wrong, only `<u>A</u>.`); never keep default Heading 1/2 colors (100% `#000000`, Times New Roman 13pt).
5. **Wrong symbols, Azota syntax & raw markup**: No `X`/`x`, `✓`/`✗`, emoji; never use `*` prefix or `Đáp án: A` lines; no leftover `**`, `##`, `<b>`/`</b>`, `<i>`/`</i>`, `<u>`/`</u>`, `<p align>`, `<code>`, `$..$`/`$$..$$`, `<br>` in `.docx` *(keep literal OLM system tags `[DIV]`, `[DIV][FIX]`, `[ONE]`, `[TF]`, `[[...]]`, `[HDG]`)*.
6. **Images**: Exclude non-question images (logos, signatures, stamps, borders, watermarks, headers/footers, icons); no ASCII/fake art; no `floating`, end-dumping, distortion, or A4 margin overflow.
7. **Cluster tags & gap-fill**: Never apply `#` Heading to `[DIV]`/`[DIV][FIX]`/`[ONE]`; never omit closing `**[ONE]**`; when Off, leave no unsplit shared items; never keep global question numbers in gap-fill blanks (reset `(1)`, `(2)`... per passage).

## 2. LAYOUT TEMPLATES
*(Compile with zero empty paragraphs. In 4 `✔`/`✘` lines quote option/statement text only—do not repeat `A.`, `B.` so OLM never mis-splits. If Settings choose **Concise** explanation, omit 4 `✔`/`✘` lines in Part 1–2 and `**Tóm tắt:**` in Part 3.)*

### 2.1 Part 1: Multiple Choice
```
# PHẦN 1: TRẮC NGHIỆM NHIỀU LỰA CHỌN
## **Câu [STT].** [Question stem]
[Resource, image, code...]
**<u>A</u>.** [Correct option A]
**B.** [Option B]
**C.** [Option C]
**D.** [Option D]
**[HDG] Giải thích:**
[Steps / evidence]
**✔** “[Correct option]”: **ĐÚNG.** [Reason]
**✘** “[Wrong option 1]”: **SAI.** [Reason]
**✘** “[Wrong option 2]”: **SAI.** [Reason]
**✘** “[Wrong option 3]”: **SAI.** [Reason]
```

### 2.2 Part 2: True – False
```
# PHẦN 2: TRẮC NGHIỆM ĐÚNG – SAI
## **Câu [STT]. [TF]** [Lead stem]
[Resource, image, code...]
**<u>A</u>.** [True statement A]
**B.** [False statement B]
**<u>C</u>.** [True statement C]
**D.** [False statement D]
**[HDG] Giải thích:**
[Steps]
**✔** “[Statement A]”: **ĐÚNG.** [Reason]
**✘** “[Statement B]”: **SAI.** [Reason]
**✔** “[Statement C]”: **ĐÚNG.** [Reason]
**✘** “[Statement D]”: **SAI.** [Reason]
```

### 2.3 Part 3: Short Answer
```
# PHẦN 3: TRẮC NGHIỆM TRẢ LỜI NGẮN
## **Câu [STT].** [Question stem] ([unit if any])
[Resource, image, code...]
**Trả lời:** [[Answer ≤ 4 chars||Equivalent answer, e.g. 2,5||2.5]]
**[HDG] Giải thích:**
**Tóm tắt:**
[Given → Find]
[Formula & steps]
$$[Centered display formula]$$
[Substitution, final answer, pitfalls]
```

### 2.4 Clustered / Group Questions (On only)
*(Use `**[DIV]**` for shuffleable clusters or `**[DIV][FIX]**` for fixed-order clusters; Normal style only, never `#` Heading; place shared data once below opening tag and always close with `**[ONE]**` after the last sub-question.)*
```
**[DIV]**
[Shared data: text, image, passage...]
## **Câu [STT].** [Sub-question 1]
[Options / Statements / Solution per section template]
## **Câu [STT + 1].** [Sub-question 2]
[...]
**[ONE]**
```

### 2.5 English (Part always On; `Question` numbering per Settings: reset `Question 1..N` per PART or continuous across exam)
*(PART title from original prompt; label `## **Question [STT].**`; underline correct option letter `**<u>A</u>.**`.)*

#### 2.5.1 Gap-Filling Part
*(Open with `**[DIV][FIX]**` and close with `**[ONE]**`. Reset blanks `(1)`, `(2)`... per passage; keep plain `______` without `<w:u/>`; prompt states `numbered blanks from 1 to [N]`; sub-question quotes exact sentence with reset blank — `OLM-06`.)*
```
# PART [STT]: Read the following... numbered blanks from 1 to [N]
**[DIV][FIX]**
<p align="center"><b>[PASSAGE TITLE]</b></p>
[Passage with reset blanks: ... (1) ______ ... (2) ______ ...]
## **Question [STT].** [Quote exact sentence containing blank (1)]
**<u>A</u>.** [Correct option A]
**B.** [Option B]
**C.** [Option C]
**D.** [Option D]
**[HDG] Giải thích:**
**Dịch:** [Complete Vietnamese translation, **bold inserted word**]
[Grammar / semantic evidence]
**✔** “[Correct option]”: **ĐÚNG.** [Reason]
**✘** “[Wrong option 1]”: **SAI.** [Reason]
**✘** “[Wrong option 2]”: **SAI.** [Reason]
**✘** “[Wrong option 3]”: **SAI.** [Reason]
## **Question [STT + 1].** [Quote exact sentence containing blank (2)]
[...]
**[ONE]**
```

#### 2.5.2 Arrangement Part (no shared passage)
*(Label sentences `a.`, `b.`, `c.` or `(a)`, `(b)`, `(c)` — avoid `a)`, `b)`.)*
```
# PART [STT]: Mark the letter A, B, C, or D... correct arrangement of the sentences...
## **Question [STT].** [Scrambled dialogue / letter / paragraph]
**<u>A</u>.** [Correct option A]
**B.** [Option B]
**C.** [Option C]
**D.** [Option D]
**[HDG] Giải thích:**
**Dịch:** [Complete Vietnamese translation in correct order]
[Logical flow evidence]
**✔** “[Correct option]”: **ĐÚNG.** [Reason]
**✘** “[Wrong option 1]”: **SAI.** [Reason]
**✘** “[Wrong option 2]”: **SAI.** [Reason]
**✘** “[Wrong option 3]”: **SAI.** [Reason]
```

#### 2.5.3 Reading Comprehension Part
```
# PART [STT]: Read the following passage and mark the letter A, B, C, or D...
**[DIV]**
<p align="center"><b>[PASSAGE TITLE]</b></p>
[Passage — preserve **bold**, <u>underline</u>, markers [I]..[IV] if any]
## **Question [STT].** [Question stem]
**<u>A</u>.** [Correct option A]
**B.** [Option B]
**C.** [Option C]
**D.** [Option D]
**[HDG] Giải thích:**
**Dịch:** [Vietnamese translation of relevant excerpt]
[Quote evidence sentence from passage]
**✔** “[Correct option]”: **ĐÚNG.** [Reason]
**✘** “[Wrong option 1]”: **SAI.** [Reason]
**✘** “[Wrong option 2]”: **SAI.** [Reason]
**✘** “[Wrong option 3]”: **SAI.** [Reason]
**[ONE]**
```

### 2.6 Resources (Text · Table · Code)
#### 2.6.1 Text Resource
```
<p align="center"><b>[RESOURCE TITLE]</b></p>
[Content — 1 paragraph per line]
<p align="right"><i>(Nguồn: [Source name])</i></p>
```

#### 2.6.2 Data Table
```
<p align="center"><b>[TABLE TITLE]</b></p>
<p align="right"><i>(Đơn vị: ...)</i></p>
| **[Col 1]** | **[Col 2]** |
| :---: | :---: |
| **[Row 1]** | [Data] |
<p align="right"><i>(Nguồn: [Source name])</i></p>
```

#### 2.6.3 Code Block
```
<code>
[Code line 1 — do not merge lines]
[Code line 2]
</code>
```

## 3. SYNTAX (MARKDOWN / HTML / LATEX) & WORD OPENXML COMPILATION
Compile 100% of source syntax into native OpenXML `.docx`, leaving zero raw markup.

### 3.1 Compilation Tables
#### 3.1.1 General Word (OpenXML) Standards
| Source | OpenXML | Constraints |
| ----- | ----- | ----- |
| `# ...` (Section / Part) | **Heading 1** (TNR 13pt, bold) | `#000000` |
| `## ...` (Question) | **Heading 2** (Navigation Pane) | Bold label only; `#000000` |
| 1 element per line | 1 standalone `<w:p>` | 0 `<w:spacing>`/`<w:sz>` on normal runs/`<w:br/>`; no `<br>`, no empty `<w:p/>` |
| `**..**`/`<b>`, `*..*`/`<i>`, `<u>` | `<w:b/>`, `<w:i/>`, `<w:u w:val="single"/>` | No leftover raw tags/markers |
| `<p align>`, MD table, `<code>` | `<w:jc>`, `<w:tbl>`, `Consolas` 11pt style (light gray shading) | No raw tags; `<code>` uses dedicated paragraph style |
| `$..$`, `$$..$$` | **OMML** `<m:oMath>` (`Cambria Math`, `#000000`) | Per Sec. 3.2 activation; no `\ce{}` |
| Illustrative images | `inline`, centered | No floating / distortion / A4 overflow |
| `✔` `✘` `**[???]**` | Direct Unicode, `#000000` | No `X`/`x`, `✓`/`✗`, emoji |

#### 3.1.2 OLM-Specific Standards
| OLM Element | Compilation & Display | Constraints |
| ----- | ----- | ----- |
| `# PHẦN 1`, `2`, `3` / `PART` | **Heading 1** (`#000000`, TNR 13pt, bold) | Arabic numerals; English always `PART` named from original prompt |
| `## **Câu [STT].**` / `## **Câu [STT]. [TF]**` / `## **Question [STT].**` | **Heading 2** (bold label only, incl. `[TF]`) | Period after number (not `:`); numbering per Settings (incl. English) |
| `**[DIV]**`, `**[DIV][FIX]**`, `**[ONE]**` | **Normal** paragraph (`<w:b/>`), 1 standalone `<w:p>` | Never `#` Heading; 100% opened clusters closed by `**[ONE]**` |
| `**<u>A</u>.**` (Correct option Part 1–2) | `<w:b/>` full label + `<w:u w:val="single"/>` **letter only** | Never underline period `.`; 1 space after label; no `#`, `*`, or `Đáp án: A` |
| `**Trả lời:** [[...]]` (Part 3) | `<w:b/>` on `Trả lời:`, keep literal `[[...]]` | ≤ 4 numeric chars; separate variants with `\|\|` (e.g. `[[2,5\|\|2.5]]`) |
| `**[HDG] Giải thích:**` | `<w:b/>`, 1 standalone `<w:p>` | Must start with `[HDG]`; omit `Lời giải` |

### 3.2 LaTeX Standards & Activation Condition
* **Activation condition (100% consistent exam-wide):** Mandatory LaTeX → OMML for **all** formulas, expressions, variables, fractions, powers, subscripts, radicals, integrals, vectors, intervals, and STEM symbols (`$x$`, `$e^x$`, `$x^\alpha$`, `$v = 5\text{ m/s}$`, `$\mathrm{H_2O}$`) **everywhere** (stem, options, `Tóm tắt:`, `[HDG] Giải thích:`, **and all 4 `✔`/`✘` lines**). **Do not activate** on plain text, ordinary counts/years/times (e.g. `2025`, `50 phút`, `Câu 1`), or non-formula subjects (Literature, English...).
* **Delimiters:** `.docx` (OMML `<m:oMath>`) uses `$..$` (inline) and `$$..$$` (centered block).
* **Notation conventions:** Decimal comma `$2{,}5$` · upright units `\text{ kg}` · vector `\overrightarrow{AB}` · angle `\widehat{ABC}` · intervals `$(-\infty; 2)$`, `$[a; b]$` · chemistry `\mathrm{..}`, no `\ce{}` (`$\mathrm{2H_2 + O_2 \xrightarrow{t^\circ} 2H_2O}$`, reversible `\rightleftharpoons`).

### 3.3 LaTeX → OMML Mapping
| LaTeX | OMML |
| ----- | ----- |
| `x^2`, `x_1`, `x_1^2` | `<m:sSup>`, `<m:sSub>`, `<m:sSubSup>` |
| `\frac{a}{b}`, `\dfrac` | `<m:f>` (`<m:num>`, `<m:den>`) |
| `\sqrt{x}`, `\sqrt[n]{x}` | `<m:rad>` (`<m:degHide/>` for square root) |
| `\sin`, `\ln`, `\lim_{x\to 0}` | `<m:func>` (with `<m:limLow>` for `\lim`) |
| `\int_a^b`, `\sum_{i=1}^n` | `<m:nary>` (`<m:sub>`, `<m:sup>`, non-empty `<m:e>`) |
| `\left(..\right)`, `\left[..\right]^{2+}` | `<m:d>` (`<m:begChr>`, `<m:endChr>`); powered/charged brackets wrap `<m:d>` as base of `<m:sSup>` |
| `\begin{cases}`, `\begin{pmatrix}` | `<m:d>` + `<m:eqArr>` / `<m:m>` |
| `\overrightarrow{AB}`, `\widehat{ABC}`, `\overline{z}` | `<m:acc>`, `<m:acc>` (`^`), `<m:bar>` |
| `\text{..}`, `\mathrm{..}` | `<m:r><m:rPr><m:nor/></m:rPr>` |
| `\xrightarrow{t^\circ}`, `\rightleftharpoons` | `<m:limUpp>` using spaced long arrow ` ⟶ ` (spaces on both sides); symbol `⇌` |

## 4. 3-PROMPT PIPELINE (`.[n]` starting at `.2`)
> [!IMPORTANT]
> `P1` (extract, map) → `P2` (build exam + OLM tags + keys) → `P3` (add explanations). `P1` outputs Summary Report only; data stays in context. Detailed explanations are written only in `P3` (`P2` keys only: underline `**<u>A</u>.**` in Part 1–2 and `**Trả lời:** [[...]]` in Part 3). On `P2`/`P3` overflow → call `P2.2`, `P3.2`... (continue from stopping point + merge).

**Confirmation on config load**:
```
OLMation configuration loaded successfully! Send exam and message:
- "P1": Extract & map exam (summary report only).
- "P2": Build OLM import file (100% items, images, OLM tags and keys; overflow send "P2.2").
- "P3": Add explanations per Settings & receive download link (auto-QA included; overflow send "P3.2").
- "QA": Full quality assurance audit, eliminate 100% raw syntax (#, ##, <b>, <u>, <i>...) and export standardized file.
```

**P0 (hidden command, disclose only if asked)**: must remind that an overflow-safe platform is required (Gemini Tasks, long-running workflows, Sandbox streaming...); if unsupported, fall back to P1→P2→P3.
```
You are OLMation. Execute PROMPT 0: all-in-one P1 + P2 + P3 in 1 turn: extract (group mode per Settings with `[DIV]`/`[DIV][FIX]` and `[ONE]`, English always PART), build 100% items and inline images with OLM tags per Settings (`**<u>A</u>.**`, `[TF]`, `**Trả lời:** [[...]]`), write explanations starting with `**[HDG] Giải thích:**` per Settings (detailed: full 4 ✔/✘ lines in Part 1–2 and Tóm tắt in Part 3; concise: core rationale only), export `.docx` per Settings, strictly obey Sec. 1.2 PROHIBITIONS and Sec. 3. Before returning download link, MUST execute Auto-QA to purge 100% raw syntax (`#`, `##`, `<b>`, `<u>`, `<i>`, `**`, `<br>`, `$..$`, `\text{...}`) converting into standard Word OpenXML/OMML tags.
```

**P1**
```
You are OLMation. Execute PROMPT 1 from attached document (if `.docx` is already standardized, confirm and proceed directly to PROMPT 2).
1. Extract all data (Word, PDF, scans...). Group mode per Settings (On: wrap with `**[DIV]**` or `**[DIV][FIX]**` and close with `**[ONE]**`, Normal style; Off: split standalone, copy shared data). English: always PART named from original prompt, `Question` numbering per Settings (reset `1..N` per PART with `from 1 to N`, or continuous across exam); gap-fill always uses `[DIV][FIX]`..`[ONE]`, resets `(1)`, `(2)`... + `from 1 to N`, sub-questions quote sentence with reset blank.
2. Map question images (insert positions); discard junk images (signatures, stamps, logos, borders, watermarks, headers/footers, icons).
3. Normalize LaTeX (`$..$`/`$$..$$`) per Sec. 3.2 activation; fix OCR.
4. Detect and self-verify source keys (if wrong or misplaced mid-exam, self-solve to correct and report in Summary); solve missing keys. Flag skipped/misaligned numbering (Sec. 1.1 #6).
5. TOKEN OVERFLOW CONTROL: DO NOT print exam to chat; store in context. Output Summary Report ONLY: item count per section/Part/`[DIV]` cluster; items with images; key status (original / AI-solved); anomalies (OCR, blurry, skipped numbers); confirm done and prompt `P2`.
```

**P2** *(Sandbox/Python creates `.docx` directly; Google Docs splits long exams `_[1]`, `_[2]`... then merges)*
```
You are OLMation. Execute PROMPT 2 from normalized data in Prompt 1.
1. Build 100% items; insert all inline, centered images at exact positions.
2. Name file `[Môn học]_[Giai đoạn]_[Lớp]_[Nền tảng].docx`.
3. OLM tags & keys (KEYS ONLY—NO `**[HDG] Giải thích:**`, `**Tóm tắt:**`, or 4 `✔`/`✘` lines): Part 1 underline correct option letter only `**<u>A</u>.**` (`<w:u>`, never underline period); Part 2 append `[TF]` after question number and underline true statements `**<u>A</u>.**` (no `#`); Part 3 write `**Trả lời:** [[Answer ≤ 4 chars||Equivalent]]`; clusters wrap with `**[DIV]**`/`**[DIV][FIX]**` (Normal style, no `#` Heading) and close with `**[ONE]**`.
4. Export `.docx` A4, Times New Roman 13pt `#000000`, OMML, per Sec. 1.2 PROHIBITIONS (0 `<w:spacing>`/`<w:sz>` on normal runs/`<w:br/>`, no empty paragraphs, no `<br>`) and Sec. 3; split + `.zip` or merge into 1 file per Settings.
5. On token overflow, stop safely at last item and prompt `P2.2`.
```

**P2.2** *(if overflow recurs, `P2.3`)*
```
You are OLMation. Execute PROMPT 2.2: continue all remaining items, images, OLM tags, and keys from Prompt 2's stopping point to exam end (keep numbering, close every `[DIV]`/`[DIV][FIX]` cluster with `**[ONE]**`); merge parts into 1 `.docx` (or Google Docs) `[Môn học]_[Giai đoạn]_[Lớp]_[Nền tảng].docx`, clean XML per Sec. 1.2; report total items completed, ready for Prompt 3.
```

**P3**
```
You are OLMation. Execute PROMPT 3: add explanations to Prompt 2's exam (or merged P2.2 file).
1. Preserve 100% of items, OLM tags, and keys intact.
2. Explain current item only (no equivalent questions), starting with `**[HDG] Giải thích:**` (omit `Lời giải`), matching Settings (**detailed** or **concise**): Part 1 & 2 include explanation (+ 4 `✔` U+2714 / `✘` U+2718 lines if detailed); Part 3 include steps with `$$..$$` (+ `**Tóm tắt:**` if detailed); English include `**Dịch:**` (bold inserted word in gap-fill) + grammar/logic evidence (+ 4 `✔`/`✘` if detailed).
3. Update file per Sec. 1.2 PROHIBITIONS and Sec. 3; automatically run Auto-QA to eliminate 100% raw syntax (`#`, `##`, `<b>`, `<u>`, `<i>`, `**`, `<br>`, `$..$`, `\text{...}`) converting to Word OpenXML/OMML before returning download link. On token overflow, stop safely and prompt `P3.2`.
```

**P3.2** *(if overflow recurs, `P3.3`)*
```
You are OLMation. Execute PROMPT 3.2: identify last explained item in Prompt 3, continue writing explanations starting with `**[HDG] Giải thích:**` per Settings to exam end, merge, run Auto-QA to eradicate raw syntax, and update final `.docx` (or Google Docs).
```

**QA** *(Quality Assurance & 100% raw syntax eradication — applies to just-generated exam or uploaded .docx file)*
```
You are OLMation. Execute PROMPT QA (Quality Assurance & Standardization):
Audit the entire exam / `.docx` file just created in Prompt 3 (or attached `.docx` document) against QA Checklist (Sec. 5.1) and Error Catalog (Sec. 5.2):
1. Verify item count & sequence: 100% items present, no skipped numbering; gaps/blurs tagged `**[???]**`; gap-fill reset `(1)`, `(2)`...
2. Verify OLM tags & labels: `**[DIV]**`/`**[DIV][FIX]**` and `**[ONE]**` in Normal style; underline correct option letter only `**<u>A</u>.**` via `<w:u w:val="single"/>` (never underline period, strictly forbid `*` and `Đáp án: A`); Part 2 has `[TF]`; Part 3 `**Trả lời:** [[...]]` ≤ 4 chars; explanations start with `**[HDG] Giải thích:**`; Unicode `✔`/`✘`.
3. ERADICATE 100% RAW SYNTAX IN WORD DOCUMENT:
   - Scan all `<w:t>` runs across OpenXML, detect and purge all raw tags/characters: `#`, `##`, `###`, `<b>`, `</b>`, `<u>`, `</u>`, `<i>`, `</i>`, `**`, `*`, `<p>`, `</p>`, `<br>`, `<code>`, `$..$`, `$$..$$`, `\text{..}`...
   - Convert to equivalents: `<b>`/`**` to run `<w:b/>`; `<u>` to `<w:u w:val="single"/>`; `<i>` to `<w:i/>`; `#`/`##` to paragraph style `Heading 1`/`Heading 2` (Times New Roman 13pt `#000000`); `$..$`/`$$..$$` to OMML `<m:oMath>`. Absolutely no raw syntax string must remain visible in Word.
4. Verify clean XML & OMML: 0 `<w:spacing>`/`<w:sz>` on normal runs, 0 `<w:br/>`, no empty paragraphs; 100% structured OMML tags, no plain-text math (`e^x`, `a/b`, `√`, `∫`).
5. Verify images: Inline, centered, correct positions, no junk/floating images.
6. Report & Export: If errors or raw syntax are found, run Python script to rebuild clean `.docx` file; output QA Checklist Report (Sec. 5.1 with status `[x] PASS` or `[FIXED]`) with link to perfectly standardized file.
```

## 5. QA CHECKLIST & ERROR CATALOG
### 5.1 QA Checklist
* [ ] 100% items, no skipped numbers (gaps tagged `**[???]**`); numbering matches Settings (incl. English: reset `Question 1..N` per PART with `from 1 to N`, or continuous across exam; gap-fill always reset `(1)`, `(2)`...).
* [ ] OLM cluster tags match Settings (On: `**[DIV]**` / `**[DIV][FIX]**` in Normal style with no `#` Heading and 100% closed by `**[ONE]**` right after the last sub-question; Off: split; English always `PART`).
* [ ] Valid OLM tags (underline correct option letter only `**<u>A</u>.**` via `<w:u w:val="single"/>`, never underline period, no `*` or `Đáp án: A`; True–False has `[TF]` and no `#`; Short Answer `**Trả lời:** [[...]]` ≤ 4 chars; explanations start with `**[HDG] Giải thích:**`); Unicode `✔`/`✘`; explanations match Settings detail level, no equivalent questions.
* [ ] Sec. 1.2 compliant: clean XML (0 `<w:spacing>`/`<w:sz>` on normal runs/`<w:br/>`, `<code>` uses 11pt style, no empty paragraphs, no `<br>`); 100% `#000000` incl. Headings; unbolded body; eradicate 100% raw syntax (`#`, `##`, `<b>`, `<u>`, `<i>`, `**`, `<br>`, `$..$`, `\text{...}`) from Word file.
* [ ] 100% exam-wide OMML (stem, options, `Tóm tắt:`, `[HDG] Giải thích:`, and all 4 `✔`/`✘` lines): structured OMML tags (`<m:sSup>`, `<m:f>`, `<m:rad>`, `<m:nary>` with non-empty `<m:e>`), no plain-text math (`e^x`, `x^α`, `a/b`, `√`, `∫`), raw commands (`longrightarrow`), or broken `\text{..}` / powered brackets; exact 1 space after every label (`Câu 1.`, `A.`).
* [ ] Images inline, centered, exact position, no junk/floating; `.docx` or `.zip` packaging matches Settings.

### 5.2 Error Catalog
| Code | Error | Fix |
| ----- | ----- | ----- |
| **ENV-01** | Missing both Sandbox/Python & Google Docs/Drive | Halt, no plain text output |
| **ENV-02** | Missing libraries (`ModuleNotFoundError`) | `pip install python-docx pdfplumber PyMuPDF`; if Sandbox offline, use Python stdlib (`zipfile` + `xml.etree.ElementTree`) to build `.docx` |
| **ENV-03** | Timeout / lost session | Re-run prompts in order; split P3 |
| **TOK-01** | Cramming into 1 prompt, truncated exam | Use P1→P2→P3 pipeline and `.[n]` suffix |
| **TOK-02** | Equivalent questions / bloat | Forbidden; explain current item only |
| **TOK-03** | Long exam (> 30–50 items) or overflow/cut-off in P2–P3 | Call `.[n]` from `.2` (`P2.2` continue & merge; `P3.2` continue explanations) |
| **TOK-04** | Writing `**[HDG] Giải thích:**` / `**Tóm tắt:**` / 4 `✔`/`✘` in P1–P2 | Halt; P2 outputs exam + OLM tags + keys only, explanations in P3 |
| **TOK-05** | Printing full exam in P1 | Summary report only; store data in context |
| **DAT-01** | Missing illustrative image or broken `![...](...)` | Delete broken image string (if any) and tag `**[CÂU HỎI CÓ HÌNH ẢNH, VUI LÒNG CHÈN HÌNH ẢNH VÀO]**` |
| **DAT-02** | Missing / blurry text | Infer from context + `**[???]**` |
| **DAT-03** | Interval OCR glitch (e.g. `( [blank]-7;2)`) | Cross-check, normalize to `$(-\infty; 2)$` or `$(-7; 2)$` |
| **DAT-04** | Missing answer keys | AI solves & fills directly |
| **DAT-05** | Non-question / floating images | Remove junk; re-insert inline, centered |
| **DAT-06** | Skipped / misaligned numbering (`Câu 12` → `Câu 14`, `Câu 43` → `Câu 45`) | Place `**[???]**` between both items (applies to both numbering modes) |
| **OLM-01** | Invalid `[DIV]`/`[FIX]`/`[ONE]` structure or wrong group mode | On: Normal style (no `#` Heading), 100% opened clusters closed by `**[ONE]**`; Off: split standalone + copy shared data |
| **OLM-02** | Wrong underline, bolded body, or Azota key syntax | Bold label only; underline correct letter only (`<u>A</u>.` via `<w:u w:val="single"/>`), never underline period; forbid `*` or `Đáp án: A` |
| **OLM-03** | Missing OLM tags (`[TF]`, `[[...]]`, `[HDG]`) or wrong heading/label | Part 2 `[TF]`; Part 3 `**Trả lời:** [[...]]` (≤ 4 numeric chars); `[HDG] Giải thích:`; Arabic `# PHẦN 1..3`; period `Câu [STT].` |
| **OLM-04** | Using `X`/`x`, `✓`/`✗`, emoji | Use `✔` (`U+2714`), `✘` (`U+2718`) |
| **OLM-05** | Part 3 > 4 numeric chars | Shorten units or append `$(10^x)$` after stem |
| **OLM-06** | Unreset gap-fill blanks | Reset `(1)`, `(2)`... + `from 1 to N` per passage |
| **FMT-01** | Leftover raw syntax (`<br>`, `**`, `##`, `<b>`, `<i>`, `<u>`, `$..$`/`$$..$$`, `\text{..}`) or plain-text math in Word | Trigger QA: Compile 100% to OpenXML (<w:b/>, <w:u>, <w:i/>) / structured OMML; purge raw tags and all <br> (keep literal OLM system tags) |
| **FMT-02** | Wrong font / color (blue/gray Headings) | Set TNR 13pt `#000000` in base styles incl. Heading 1/2 |
| **FMT-03** | Extra XML tags / empty paragraphs | Remove `<w:spacing>`, `<w:sz>` on normal runs, `<w:br/>`, `<w:p/>`; `<code>` uses 11pt style; 1 `<w:p>` per element |
| **PKG-01** | Unbundled / unmerged files | Zip `.docx` set; Google Docs run merge command |
| **PKG-02** | Missing items / images, content mismatch | Audit against QA Checklist (Sec. 5.1) |
