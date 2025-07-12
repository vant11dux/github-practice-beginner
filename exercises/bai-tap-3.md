# 👤 Bài tập 3: Tạo profile cá nhân

**🎯 Mục tiêu:** Học cách tạo file mới, làm việc với multiple commits

**⏰ Thời gian:** 25-35 phút

**📚 Kiến thức cần:** Hoàn thành bài tập 1 và 2

---

## 🎯 Nhiệm vụ

### Phần A: Chuẩn bị (5 phút)

1. **Tạo branch mới**
   ```bash
   git checkout main
   git pull origin main  # Sync với repo gốc nếu có update
   git checkout -b ten-ban/bai-tap-3
   ```

### Phần B: Tạo profile cá nhân (20 phút)

2. **Tạo file profile của bạn**
   - Tạo file mới: `members/profiles/ten-ban.md` 
   - Thay `ten-ban` bằng username GitHub của bạn

3. **Viết nội dung profile theo template:**

```markdown
# 👋 Xin chào, tôi là [Tên của bạn]!

## 📊 Thông tin cơ bản
- 🎓 **Trường:** [Tên trường]
- 📚 **Khoa:** [Tên khoa/chuyên ngành]  
- 📅 **Năm học:** [Năm thứ mấy]
- 📧 **Email:** [email@example.com]
- 🐙 **GitHub:** [@username](https://github.com/username)

## 🎯 Mục tiêu học tập
- [ ] Học Git/GitHub cơ bản
- [ ] Hoàn thành khóa học [tên khóa học]
- [ ] Tham gia dự án thực tế
- [ ] [Mục tiêu khác của bạn]

## 💻 Kỹ năng đang học
- **Ngôn ngữ lập trình:** [Python/Java/JavaScript/etc]
- **Framework:** [React/Vue/Django/etc] 
- **Tools:** Git, VS Code, [tools khác]
- **Databases:** [MySQL/PostgreSQL/MongoDB/etc]

## 🌟 Dự án đã làm
1. **[Tên project 1]** - [Mô tả ngắn] ([Link GitHub nếu có])
2. **[Tên project 2]** - [Mô tả ngắn] ([Link GitHub nếu có])
3. **Dự án này** - Luyện tập GitHub cơ bản 🎉

## 🎮 Sở thích
- 🎵 Nghe nhạc: [Thể loại yêu thích]
- 📚 Đọc sách: [Thể loại/tác giả yêu thích]  
- ⚽ Thể thao: [Môn thể thao]
- 🎯 Khác: [Sở thích khác]

## 💭 Quote yêu thích
> "[Câu quote/châm ngôn bạn yêu thích]"

## 📈 GitHub Stats
<!-- Các bạn có thể thêm GitHub stats sau khi học xong -->
![GitHub Stats](https://github-readme-stats.vercel.app/api?username=your-username&show_icons=true&theme=radical)

---

**🚀 Cảm ơn bạn đã ghé thăm profile của tôi!**

*Hãy kết nối với tôi qua [email](mailto:your-email) hoặc [GitHub](https://github.com/your-username)!*
```

4. **Điền thông tin thật của bạn**
   - Thay thế tất cả placeholder `[...]` bằng thông tin thực
   - Có thể thêm/bớt section theo ý thích
   - Đảm bảo Markdown syntax đúng

### Phần C: Multiple commits (10 phút)

5. **Commit từng phần một**
   ```bash
   # Commit 1: Tạo file cơ bản
   git add members/profiles/ten-ban.md
   git commit -m "Bài tập 3: Tạo file profile cá nhân"
   
   # Sửa thêm thông tin, rồi commit tiếp
   git add members/profiles/ten-ban.md  
   git commit -m "Bài tập 3: Thêm thông tin kỹ năng và sở thích"
   
   # Có thể có thêm commit thứ 3, 4...
   git commit -m "Bài tập 3: Hoàn thiện profile với GitHub stats"
   ```

6. **Push và tạo PR**
   ```bash
   git push origin ten-ban/bai-tap-3
   ```

---

## ✅ Checklist hoàn thành

- [ ] Đã tạo branch mới từ main
- [ ] Đã tạo file profile với đúng tên format
- [ ] Đã điền đầy đủ thông tin cá nhân
- [ ] Đã sử dụng đúng Markdown syntax
- [ ] Đã có ít nhất 2 commits riêng biệt
- [ ] Đã push và tạo Pull Request
- [ ] Profile trông đẹp và chuyên nghiệp

---

## 🎨 Bonus (Tùy chọn)

Nếu bạn muốn profile đẹp hơn:

1. **Thêm badges:**
```markdown
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat&logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
```

2. **Thêm emoji phù hợp:**
   - 🚀 🎯 💻 📚 🌟 ⚡ 🔥 💡 🎉

3. **Thêm GitHub streak:**
```markdown
![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=your-username&theme=radical)
```

---

## 📚 Kiến thức mới học được

- ✅ Tạo file mới trong Git workflow
- ✅ Làm việc với multiple commits
- ✅ Markdown formatting nâng cao
- ✅ Tổ chức thông tin một cách logic
- ✅ Tạo profile chuyên nghiệp

**➡️ Tiếp theo:** [Bài tập 4 - Merge và Conflict Resolution](./bai-tap-4.md)
