# 🔄 Bài tập 4: Merge và Conflict Resolution

**🎯 Mục tiêu:** Học cách merge branch và giải quyết conflict cơ bản

**⏰ Thời gian:** 30-40 phút

**📚 Kiến thức cần:** Hoàn thành bài tập 1, 2, 3

---

## 📖 Background

Trong thực tế, nhiều người cùng làm việc trên một repo. Điều này có thể dẫn đến **conflict** khi 2 người sửa cùng một phần của file. Bài tập này sẽ simulate tình huống đó và học cách giải quyết.

---

## 🎯 Nhiệm vụ

### Phần A: Tạo conflict có chủ ý (15 phút)

1. **Quay về main branch**
   ```bash
   git checkout main
   git pull origin main
   ```

2. **Tạo branch "team-member"** (giả lập teammate)
   ```bash
   git checkout -b team-member/update-readme
   ```

3. **Sửa file README.md** (phần đầu tiên)
   - Mở `README.md`
   - Tìm dòng có "Repo luyện tập GitHub dành cho sinh viên mới bắt đầu"
   - Thay đổi thành: "Repo luyện tập GitHub cho sinh viên HUST"
   - Thêm dòng mới: "🔥 Updated by team member"

4. **Commit thay đổi của "teammate"**
   ```bash
   git add README.md
   git commit -m "Team member: Cập nhật mô tả repo"
   ```

5. **Quay về main và tạo branch của bạn**
   ```bash
   git checkout main
   git checkout -b ten-ban/bai-tap-4
   ```

6. **Sửa cùng phần trong README.md** (tạo conflict)
   - Mở `README.md`
   - Tìm dòng "Repo luyện tập GitHub dành cho sinh viên mới bắt đầu"  
   - Thay đổi thành: "Repo luyện tập Git & GitHub cho sinh viên Việt Nam"
   - Thêm dòng mới: "✨ Updated by [tên bạn]"

7. **Commit thay đổi của bạn**
   ```bash
   git add README.md  
   git commit -m "Bài tập 4: Cập nhật mô tả và thêm thông tin"
   ```

### Phần B: Merge và giải quyết conflict (20 phút)

8. **Merge branch team-member vào branch của bạn**
   ```bash
   git merge team-member/update-readme
   ```
   
   ➡️ **Bùm!** 💥 Bạn sẽ thấy conflict message!

9. **Kiểm tra status**
   ```bash
   git status
   ```
   
   Bạn sẽ thấy: `both modified: README.md`

10. **Mở file README.md và xem conflict**
    Sẽ có dạng như này:
    ```
    <<<<<<< HEAD
    > **Repo luyện tập Git & GitHub cho sinh viên Việt Nam**
    ✨ Updated by [tên bạn]
    =======
    > **Repo luyện tập GitHub cho sinh viên HUST**
    🔥 Updated by team member  
    >>>>>>> team-member/update-readme
    ```

11. **Giải quyết conflict bằng cách chọn cách merge phù hợp**
    
    **Option 1:** Giữ cả hai (recommended)
    ```markdown
    > **Repo luyện tập Git & GitHub cho sinh viên HUST và Việt Nam**
    
    ✨ Updated by [tên bạn]
    🔥 Updated by team member
    ```
    
    **Option 2:** Tạo version hoàn toàn mới
    ```markdown
    > **Repo luyện tập GitHub - Collaborative Learning cho sinh viên**
    
    🤝 Được cập nhật bởi team: [tên bạn] & team member
    ```

12. **Xóa các conflict markers**
    - Xóa `<<<<<<< HEAD`
    - Xóa `=======` 
    - Xóa `>>>>>>> team-member/update-readme`
    - Giữ lại content đã merge

13. **Commit resolution**
    ```bash
    git add README.md
    git commit -m "Bài tập 4: Giải quyết conflict khi merge team-member branch"
    ```

### Phần C: Push và tạo PR (5 phút)

14. **Push lên GitHub**
    ```bash
    git push origin ten-ban/bai-tap-4
    ```

15. **Tạo Pull Request**
    - Title: `[Tên bạn] - Hoàn thành bài tập 4: Merge & Conflict Resolution`
    - Mô tả: Giải thích cách bạn giải quyết conflict

---

## ✅ Checklist hoàn thành

- [ ] Đã tạo branch team-member và sửa README.md
- [ ] Đã tạo branch cá nhân và sửa cùng phần README.md
- [ ] Đã thực hiện merge gây ra conflict
- [ ] Đã hiểu được conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)
- [ ] Đã giải quyết conflict một cách hợp lý
- [ ] Đã xóa sạch tất cả conflict markers
- [ ] Đã commit resolution với message rõ ràng
- [ ] Đã push và tạo Pull Request

---

## 🔍 Kiến thức về Conflict Resolution

### Các loại conflict phổ biến:

1. **Content Conflict** (như bài tập này)
   - 2 người sửa cùng dòng
   - Giải pháp: Merge manually

2. **File rename conflict**
   - Người A đổi tên file, người B sửa nội dung
   - Giải pháp: Rename + apply changes

3. **Delete/Modify conflict**
   - Người A xóa file, người B sửa file
   - Giải pháp: Quyết định keep hay delete

### Best practices:

- ✅ **Đọc kỹ cả hai phiên bản** trước khi quyết định
- ✅ **Communicate với teammate** khi không chắc chắn
- ✅ **Test code** sau khi resolve conflict
- ✅ **Commit message rõ ràng** về resolution
- ❌ **Không tự ý xóa code** của người khác

---

## 🆘 Troubleshooting

### Nếu merge bị stuck:
```bash
git merge --abort  # Hủy merge và quay lại trạng thái trước
```

### Nếu muốn xem diff:
```bash
git diff HEAD~1  # Xem thay đổi so với commit trước
```

### Nếu commit nhầm:
```bash
git reset --soft HEAD~1  # Undo commit nhưng giữ changes
```

---

## 🎉 Kết thúc

Chúc mừng! Bạn đã hoàn thành tất cả 4 bài tập cơ bản. Bạn đã học được:

- ✅ **Fork & Clone** repository
- ✅ **Branch management** và workflow
- ✅ **Commit** với message có ý nghĩa
- ✅ **Push & Pull Request** workflow
- ✅ **Markdown** formatting
- ✅ **Merge** và **Conflict Resolution**

**🚀 Bây giờ bạn đã sẵn sàng tham gia các dự án thực tế!**

---

**➡️ Bonus:** [Bài tập nâng cao - Rebase và Squash](./bai-tap-bonus.md) (tùy chọn)
