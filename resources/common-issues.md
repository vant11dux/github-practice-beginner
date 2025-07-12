# 🆘 Các lỗi thường gặp và cách giải quyết

> **Troubleshooting guide cho sinh viên mới học Git/GitHub**

## 🔐 Authentication Issues

### 1. Permission denied (publickey)

**Lỗi:**
```bash
git@github.com: Permission denied (publickey)
```

**Nguyên nhân:** Chưa setup SSH key hoặc sai config

**Giải pháp:**

**Option A: Sử dụng HTTPS thay vì SSH**
```bash
# Thay đổi remote URL từ SSH sang HTTPS
git remote set-url origin https://github.com/username/repo-name.git
```

**Option B: Setup SSH Key**
```bash
# 1. Tạo SSH key mới
ssh-keygen -t ed25519 -C "your_email@example.com"

# 2. Copy public key
cat ~/.ssh/id_ed25519.pub

# 3. Paste vào GitHub Settings > SSH Keys
```

### 2. Username/Password không work

**Lỗi:** GitHub từ chối username/password

**Nguyên nhân:** GitHub đã ngừng hỗ trợ password authentication

**Giải pháp:** Sử dụng Personal Access Token
```bash
# 1. Tạo token tại: GitHub Settings > Developer settings > Personal access tokens
# 2. Sử dụng token thay cho password khi Git hỏi
Username: your-username
Password: ghp_your-token-here
```

## 🌿 Branch Issues

### 3. Branch không tồn tại

**Lỗi:**
```bash
error: pathspec 'branch-name' did not match any file(s) known to git
```

**Giải pháp:**
```bash
# Kiểm tra branch có sẵn
git branch -a

# Tạo branch nếu chưa có
git checkout -b branch-name

# Hoặc fetch từ remote
git fetch origin
git checkout -b branch-name origin/branch-name
```

### 4. Không thể switch branch do changes chưa commit

**Lỗi:**
```bash
error: Your local changes would be overwritten by checkout
```

**Giải pháp:**
```bash
# Option 1: Commit changes
git add .
git commit -m "Work in progress"

# Option 2: Stash changes
git stash
git checkout other-branch
git stash pop  # Khi quay lại

# Option 3: Discard changes (CẨNTHẬN!)
git checkout -- .
```

## 📝 Commit Issues

### 5. Commit message editor mở ra và không biết thoát

**Tình huống:** Terminal mở editor lạ (vim/nano) cho commit message

**Giải pháp:**

**Nếu là Vim:**
```bash
# 1. Nhấn 'i' để vào insert mode
# 2. Gõ commit message
# 3. Nhấn Esc
# 4. Gõ ':wq' và Enter để save & quit
```

**Nếu là Nano:**
```bash
# 1. Gõ commit message
# 2. Ctrl + X để exit
# 3. Y để confirm save
# 4. Enter để confirm filename
```

**Hoặc config editor khác:**
```bash
git config --global core.editor "code --wait"  # VS Code
git config --global core.editor "nano"         # Nano
```

### 6. Muốn sửa commit message vừa commit

**Giải pháp:**
```bash
# Chỉ sửa commit cuối cùng (chưa push)
git commit --amend -m "New commit message"

# Nếu đã push, cần force push (NGUY HIỂM với shared branch)
git push --force-with-lease origin branch-name
```

## 🔄 Merge Issues

### 7. Merge conflict

**Lỗi:** Git báo conflict khi merge

**Giải pháp:**
```bash
# 1. Xem files bị conflict
git status

# 2. Mở file, sẽ thấy:
<<<<<<< HEAD
Your changes
=======
Their changes
>>>>>>> branch-name

# 3. Sửa file, xóa markers, giữ content muốn keep
# 4. Mark resolved
git add filename

# 5. Complete merge
git commit
```

### 8. Merge bị stuck

**Giải pháp:**
```bash
# Abort merge và quay lại trạng thái trước
git merge --abort

# Hoặc nếu đang rebase
git rebase --abort
```

## 🌐 Remote Issues

### 9. Remote không sync

**Lỗi:** Local repo không update từ remote

**Giải pháp:**
```bash
# Fetch latest changes
git fetch origin

# Pull specific branch
git pull origin main

# Reset local branch to match remote (CẨNTHẬN!)
git reset --hard origin/main
```

### 10. Push bị reject

**Lỗi:**
```bash
! [rejected] main -> main (fetch first)
```

**Nguyên nhân:** Remote có commits mới mà local chưa có

**Giải pháp:**
```bash
# Pull trước khi push
git pull origin main
git push origin main

# Hoặc rebase để tránh merge commit
git pull --rebase origin main
git push origin main
```

## 📁 File Issues

### 11. File bị xóa nhầm

**Giải pháp:**
```bash
# Restore file từ last commit
git checkout HEAD -- filename

# Hoặc với Git 2.23+
git restore filename

# Restore tất cả files
git checkout HEAD -- .
```

### 12. Gitignore không hoạt động

**Nguyên nhân:** File đã được track trước khi add vào .gitignore

**Giải pháp:**
```bash
# Untrack file nhưng giữ local copy
git rm --cached filename

# Untrack folder
git rm -r --cached foldername/

# Commit thay đổi
git commit -m "Remove tracked files from gitignore"
```

## 🔄 Undo Operations

### 13. Muốn undo last commit

**Giải pháp:**
```bash
# Undo commit nhưng giữ changes
git reset --soft HEAD~1

# Undo commit và xóa changes (CẨNTHẬN!)
git reset --hard HEAD~1

# Undo commit bằng tạo commit mới (an toàn)
git revert HEAD
```

### 14. Nhầm add file không cần thiết

**Giải pháp:**
```bash
# Unstage file cụ thể
git reset HEAD filename

# Unstage all files
git reset HEAD

# Với Git 2.23+
git restore --staged filename
```

## 🚨 Emergency Commands

### 15. Repository hoàn toàn bị mess up

**Giải pháp cuối cùng:**
```bash
# 1. Backup changes quan trọng
cp -r project-folder project-backup

# 2. Clone lại repo mới
rm -rf project-folder
git clone https://github.com/username/repo-name.git

# 3. Copy lại changes từ backup nếu cần
```

## 📋 Prevention Tips

### ✅ Best Practices để tránh lỗi:

1. **Luôn `git status` trước khi làm gì**
2. **Pull trước khi push**
3. **Commit thường xuyên với message rõ ràng**
4. **Không force push trên shared branches**
5. **Backup quan trọng trước khi thử lệnh nguy hiểm**
6. **Đọc error message cẩn thận**
7. **Test trên branch riêng trước khi merge vào main**

### ❌ Tránh những lệnh này khi mới học:
- `git reset --hard` (có thể mất code)
- `git push --force` (có thể phá repo của team)
- `git rebase` trên shared branch
- Xóa `.git` folder

---

## 🔗 Resources thêm

- [Git Official Troubleshooting](https://git-scm.com/docs/git-help)
- [GitHub Community](https://github.community/)
- [Stack Overflow Git Tag](https://stackoverflow.com/questions/tagged/git)

**💡 Tip:** Copy error message và Google search thường cho kết quả tốt!
