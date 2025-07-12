# 📖 Glossary - Thuật ngữ Git/GitHub

> **Từ điển các thuật ngữ quan trọng với giải thích bằng tiếng Việt**

## 🔤 A-C

### **Add**
- **Nghĩa:** Thêm file vào staging area
- **Lệnh:** `git add filename`
- **Ví dụ:** "Add file này vào để chuẩn bị commit"

### **Branch** 
- **Nghĩa:** Nhánh - một phiên bản song song của code
- **Lệnh:** `git branch`, `git checkout -b`
- **Ví dụ:** "Tạo branch mới để làm feature login"

### **Clone**
- **Nghĩa:** Sao chép repository từ remote về local
- **Lệnh:** `git clone <url>`
- **Ví dụ:** "Clone repo này về máy để làm việc"

### **Commit**
- **Nghĩa:** Lưu snapshot của thay đổi với message mô tả
- **Lệnh:** `git commit -m "message"`
- **Ví dụ:** "Commit sau khi hoàn thành feature"

### **Conflict**
- **Nghĩa:** Xung đột khi 2 người sửa cùng dòng code
- **Giải quyết:** Edit file để merge changes
- **Ví dụ:** "Có conflict ở file README.md"

## 🔤 F-M

### **Fetch**
- **Nghĩa:** Tải updates từ remote nhưng không merge
- **Lệnh:** `git fetch origin`
- **Khác Pull:** Fetch không tự động merge

### **Fork**
- **Nghĩa:** Tạo bản copy của repository trên GitHub
- **Cách:** Click nút "Fork" trên GitHub
- **Mục đích:** Để contribute hoặc tạo version riêng

### **HEAD**
- **Nghĩa:** Con trỏ tới commit hiện tại đang checkout
- **Ví dụ:** `HEAD~1` = commit trước đó 1 bước

### **Issue**
- **Nghĩa:** Vấn đề, bug, hoặc feature request trên GitHub
- **Cách:** Tạo tại tab Issues của repo
- **Ví dụ:** "Tạo issue để report bug"

### **Merge**
- **Nghĩa:** Gộp changes từ branch này vào branch khác
- **Lệnh:** `git merge branch-name`
- **Kết quả:** Tạo merge commit

## 🔤 O-R

### **Origin**
- **Nghĩa:** Tên mặc định của remote repository
- **Xem:** `git remote -v`
- **Ví dụ:** `origin` trỏ tới GitHub repo

### **Pull**
- **Nghĩa:** Tải và merge changes từ remote
- **Lệnh:** `git pull origin main`
- **Bằng:** `git fetch` + `git merge`

### **Pull Request (PR)**
- **Nghĩa:** Đề xuất merge changes vào main branch
- **Nơi:** Trên GitHub/GitLab
- **Mục đích:** Code review trước khi merge

### **Push**
- **Nghĩa:** Đẩy commits lên remote repository
- **Lệnh:** `git push origin branch-name`
- **Điều kiện:** Cần quyền write access

### **Rebase**
- **Nghĩa:** Áp dụng commits lên base branch mới
- **Lệnh:** `git rebase main`
- **Khác Merge:** Tạo history tuyến tính

### **Remote**
- **Nghĩa:** Repository ở server (GitHub, GitLab...)
- **Lệnh:** `git remote add origin <url>`
- **Ví dụ:** GitHub repo là remote

### **Repository (Repo)**
- **Nghĩa:** Thư mục chứa project và Git history
- **Loại:** Local repo (máy bạn), Remote repo (GitHub)

## 🔤 S-Z

### **Staging Area**
- **Nghĩa:** Khu vực chuẩn bị files cho commit
- **Lệnh:** `git add` để đưa vào staging
- **Xem:** `git status` để check

### **Stash**
- **Nghĩa:** Lưu tạm thời changes chưa commit
- **Lệnh:** `git stash`, `git stash pop`
- **Khi nào:** Cần switch branch mà chưa muốn commit

### **Tag**
- **Nghĩa:** Đánh dấu commit quan trọng (thường là version)
- **Lệnh:** `git tag v1.0.0`
- **Ví dụ:** Tag release versions

### **Upstream**
- **Nghĩa:** Repository gốc (khi bạn fork)
- **Setup:** `git remote add upstream <original-repo-url>`
- **Sync:** `git pull upstream main`

### **Working Directory**
- **Nghĩa:** Thư mục làm việc hiện tại
- **Trạng thái:** Modified, Staged, Committed

## 🎯 Workflow Terms

### **CI/CD**
- **Nghĩa:** Continuous Integration/Continuous Deployment
- **GitHub:** GitHub Actions
- **Mục đích:** Tự động test và deploy

### **Code Review**
- **Nghĩa:** Kiểm tra code trước khi merge
- **Nơi:** Trong Pull Request
- **Ai:** Team members, maintainers

### **Contributor**
- **Nghĩa:** Người đóng góp code cho project
- **Cách:** Fork, code, tạo PR

### **Maintainer**
- **Nghĩa:** Người quản lý repository
- **Quyền:** Merge PRs, manage issues

### **Open Source**
- **Nghĩa:** Mã nguồn mở, ai cũng có thể đóng góp
- **Ví dụ:** Linux, React, Vue.js

## 📊 Status Terms

### **Modified**
- **Nghĩa:** File đã thay đổi nhưng chưa add
- **Status:** Màu đỏ trong `git status`

### **Staged**
- **Nghĩa:** File đã add, sẵn sàng commit
- **Status:** Màu xanh trong `git status`

### **Untracked**
- **Nghĩa:** File mới, Git chưa theo dõi
- **Giải pháp:** `git add` để track

### **Committed**
- **Nghĩa:** Changes đã được lưu vào Git history
- **Vĩnh viễn:** Có thể rollback nhưng đã record

## 🎭 GitHub Specific

### **GitHub Actions**
- **Nghĩa:** CI/CD platform của GitHub
- **File:** `.github/workflows/`

### **GitHub Pages**
- **Nghĩa:** Host static website miễn phí
- **URL:** `username.github.io`

### **Gist**
- **Nghĩa:** Chia sẻ code snippets nhanh
- **URL:** `gist.github.com`

### **Star**
- **Nghĩa:** "Like" một repository
- **Mục đích:** Bookmark, show appreciation

### **Watch**
- **Nghĩa:** Theo dõi notifications của repo
- **Nhận:** Issues, PRs, releases

---

## 📝 Command Quick Reference

| Thuật ngữ | Lệnh | Mô tả |
|-----------|------|-------|
| Add | `git add .` | Thêm tất cả vào staging |
| Commit | `git commit -m "msg"` | Lưu changes |
| Push | `git push origin main` | Đẩy lên remote |
| Pull | `git pull origin main` | Kéo từ remote |
| Branch | `git checkout -b new` | Tạo branch mới |
| Merge | `git merge feature` | Gộp branch |
| Status | `git status` | Xem trạng thái |
| Log | `git log --oneline` | Xem history |

---

**💡 Tip:** Bookmark page này để tra cứu nhanh khi cần!
