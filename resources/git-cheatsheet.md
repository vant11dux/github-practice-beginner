# 📚 Git Cheat Sheet

> **Tham khảo nhanh các lệnh Git thường dùng**

## 🔧 Setup và Config

```bash
# Cấu hình thông tin cá nhân
git config --global user.name "Tên của bạn"
git config --global user.email "email@example.com"

# Kiểm tra config
git config --list
```

## 📂 Repository Operations

```bash
# Clone repository
git clone https://github.com/username/repo-name.git

# Khởi tạo repo mới
git init

# Thêm remote origin
git remote add origin https://github.com/username/repo-name.git

# Kiểm tra remote
git remote -v
```

## 🌿 Branch Operations

```bash
# Liệt kê tất cả branch
git branch -a

# Tạo branch mới
git checkout -b branch-name

# Chuyển branch
git checkout branch-name

# Xóa branch (local)
git branch -d branch-name

# Xóa branch (remote)
git push origin --delete branch-name
```

## 📝 Staging và Commits

```bash
# Kiểm tra status
git status

# Thêm file vào staging
git add filename
git add .                    # Thêm tất cả files
git add *.js                 # Thêm tất cả .js files

# Commit
git commit -m "Commit message"
git commit -am "Add và commit luôn"  # Cho tracked files

# Xem lịch sử commit
git log
git log --oneline           # Gọn hơn
git log --graph             # Hiển thị graph
```

## 🔄 Sync với Remote

```bash
# Push lên remote
git push origin branch-name
git push                    # Push current branch

# Pull từ remote
git pull origin branch-name
git pull                    # Pull current branch

# Fetch (không merge)
git fetch origin
```

## 🔀 Merge và Rebase

```bash
# Merge branch khác vào current branch
git merge other-branch

# Rebase (thận trọng khi dùng)
git rebase main

# Abort merge/rebase nếu có conflict
git merge --abort
git rebase --abort
```

## 🔍 Inspection và Comparison

```bash
# Xem thay đổi chưa stage
git diff

# Xem thay đổi đã stage
git diff --staged

# So sánh giữa branches
git diff branch1..branch2

# Xem thông tin commit cụ thể
git show commit-hash
```

## ↩️ Undo Operations

```bash
# Undo changes chưa stage
git checkout -- filename
git restore filename         # Git 2.23+

# Undo staged changes
git reset HEAD filename
git restore --staged filename # Git 2.23+

# Undo commit (giữ changes)
git reset --soft HEAD~1

# Undo commit (xóa changes)
git reset --hard HEAD~1

# Revert commit (tạo commit mới để undo)
git revert commit-hash
```

## 🏷️ Tags

```bash
# Tạo tag
git tag v1.0.0
git tag -a v1.0.0 -m "Version 1.0.0"

# Push tags
git push origin v1.0.0
git push origin --tags

# Xem tags
git tag
```

## 🔧 Stash (Tạm thời lưu changes)

```bash
# Stash changes
git stash
git stash save "Work in progress"

# Xem stash list
git stash list

# Apply stash
git stash apply
git stash apply stash@{0}

# Drop stash
git stash drop stash@{0}
```

## 🆘 Emergency Commands

```bash
# Nếu repo bị mess up, quay về commit trước
git reset --hard HEAD~1

# Nếu muốn bỏ tất cả changes local
git reset --hard origin/main

# Nếu push nhầm, force push (NGUY HIỂM)
git push --force-with-lease origin branch-name
```

## 📋 Best Practices

### Commit Messages:
```bash
# ✅ Good
git commit -m "Add user authentication feature"
git commit -m "Fix: Resolve login bug for mobile users"
git commit -m "Update: Improve performance of dashboard"

# ❌ Bad  
git commit -m "fix"
git commit -m "update stuff"
git commit -m "asdjklasdjkl"
```

### Branch Naming:
```bash
# ✅ Good
feature/user-authentication
bugfix/login-mobile-issue
hotfix/security-patch
username/feature-name

# ❌ Bad
test
fix
branch1
```

### Workflow:
1. `git pull` trước khi bắt đầu làm việc
2. Tạo branch cho từng feature/bugfix
3. Commit thường xuyên với message rõ ràng
4. Push và tạo Pull Request
5. Review code trước khi merge
6. Xóa branch sau khi merge

---
## 🔍 Inspection và Comparison

```bash
# Xem thay đổi chưa stage
git diff

# Xem thay đổi đã stage
git diff --staged

# So sánh giữa branches
git diff branch1..branch2

# Xem thông tin commit cụ thể
git show commit-hash

# So sánh với commit trước
git diff HEAD~1

# So sánh file cụ thể
git diff filename

# Xem diff với context nhiều hơn
git diff -U10                # 10 dòng context thay vì 3 dòng mặc định
```

### 🎮 Điều khiển trong Git Diff Viewer

```bash
# Navigation (Di chuyển)
q                    # Quit (Thoát)
Space / f            # Next page (Trang tiếp)
b                    # Previous page (Trang trước) 
j / ↓                # Scroll down one line (Xuống 1 dòng)
k / ↑                # Scroll up one line (Lên 1 dòng)
g                    # Go to beginning (Về đầu)
G                    # Go to end (Về cuối)

# Search (Tìm kiếm)
/pattern             # Search forward (Tìm xuống)
?pattern             # Search backward (Tìm lên)
n                    # Next match (Kết quả tiếp)
N                    # Previous match (Kết quả trước)

# Hunk Navigation (Di chuyển giữa các khối thay đổi)
]                    # Next hunk (Khối tiếp)
[                    # Previous hunk (Khối trước)

# View Options (Tùy chọn xem)
h                    # Help (Trợ giúp)
```

### 🎨 Git Diff với màu sắc và format đẹp hơn

```bash
# Bật màu sắc
git config --global color.diff auto

# Sử dụng diff tool bên ngoài
git difftool

# Xem diff theo từng từ thay vì từng dòng
git diff --word-diff

# Xem diff với thống kê
git diff --stat

# Ignore whitespace changes
git diff --ignore-all-space
```
## 🔗 Links hữu ích

- [Git Documentation](https://git-scm.com/docs)
- [GitHub Guides](https://guides.github.com/)
- [Interactive Git Tutorial](https://learngitbranching.js.org/)
- [Git Visualizer](https://git-school.github.io/visualizing-git/)

**💡 Tip:** Bookmark trang này để tham khảo nhanh!
