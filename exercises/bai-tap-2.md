# 🔧 Bài tập 2: Sửa lỗi Markdown

**🎯 Mục tiêu:** Học cách edit file, commit và hiểu về diff

**⏰ Thời gian:** 20-30 phút

**📚 Kiến thức cần:** Hoàn thành bài tập 1

---

## 📖 Background

File `sample-document.md` trong thư mục này có một số lỗi Markdown syntax. Nhiệm vụ của bạn là tìm và sửa tất cả các lỗi này.

---

## 🎯 Nhiệm vụ

### Phần A: Chuẩn bị (5 phút)

1. **Đảm bảo bạn đang ở main branch và sync với remote**
   ```bash
   git checkout main
   git pull origin main
   ```

2. **Tạo branch mới cho bài tập 2**
   ```bash
   git checkout -b ten-ban/bai-tap-2
   ```

### Phần B: Tìm và sửa lỗi (15 phút)

3. **Mở file có lỗi**
   - Mở file `exercises/sample-document.md`
   - Đọc kỹ nội dung và tìm lỗi Markdown

4. **Các lỗi cần sửa** (Gợi ý):
   - ❌ Header sai syntax (thiếu space)
   - ❌ Link bị hỏng (sai URL)
   - ❌ List formatting không đúng (mix bullets)
   - ❌ Code block thiếu syntax highlighting
   - ❌ Image link sai format
   - ❌ Table formatting lỗi
   - ❌ Numbered list bị thiếu số

5. **Sửa từng lỗi một cách cẩn thận**
   - Đọc thêm về [Markdown syntax](https://www.markdownguide.org/basic-syntax/) nếu cần
   - Test bằng cách preview trong VS Code hoặc editor khác

### Phần C: Commit và push (10 phút)

6. **Kiểm tra thay đổi**
   ```bash
   git diff
   git status
   ```

7. **Commit từng loại sửa lỗi**
   ```bash
   git add exercises/sample-document.md
   git commit -m "Bài tập 2: Sửa lỗi syntax header và list formatting"
   ```

8. **Push lên GitHub**
   ```bash
   git push origin ten-ban/bai-tap-2
   ```

9. **Tạo Pull Request mới**
   - Title: `[Tên bạn] - Hoàn thành bài tập 2`
   - Mô tả: Liệt kê các lỗi đã sửa

---

## ✅ Checklist hoàn thành

- [ ] Đã tạo branch mới cho bài tập 2
- [ ] Đã tìm ra tất cả lỗi Markdown trong sample-document.md
- [ ] Đã sửa header syntax (thêm space sau #)
- [ ] Đã sửa link formatting (sửa URL lỗi)
- [ ] Đã sửa list formatting (consistent bullets)
- [ ] Đã sửa code block syntax (thêm language)
- [ ] Đã sửa image link (đúng format ![](url))
- [ ] Đã sửa table formatting (đúng columns)
- [ ] Đã sửa numbered list (thêm số thiếu)
- [ ] Đã commit với message rõ ràng
- [ ] Đã push và tạo Pull Request

---

## 🔍 Hints

<details>
<summary>💡 Click để xem gợi ý (chỉ xem khi thực sự cần)</summary>

### Các lỗi thường gặp trong Markdown:

1. **Header:** 
   - ❌ `###Header without space`
   - ✅ `### Header with space`

2. **Links:**
   - ❌ `[text](broken link)`
   - ✅ `[text](https://valid-link.com)`

3. **Lists:**
   - ❌ Mix giữa `-` và `*` không nhất quán
   - ✅ Sử dụng consistent bullet points

4. **Code blocks:**
   - ❌ ``` without language
   - ✅ ```javascript với language

5. **Images:**
   - ❌ `!(alt text)[src]`
   - ✅ `![alt text](src)`

</details>

---

## 📚 Kiến thức mới học được

Sau bài tập này, bạn sẽ hiểu:
- ✅ Cách tạo branch từ branch khác
- ✅ Cách sử dụng `git diff` để xem thay đổi
- ✅ Markdown syntax cơ bản
- ✅ Cách commit thay đổi có ý nghĩa
- ✅ Workflow làm việc với multiple branches

**➡️ Tiếp theo:** [Bài tập 3 - Tạo profile cá nhân](./bai-tap-3.md)
