# 📋 Tóm tắt kiểm tra bài tập

## ✅ Đã sửa các vấn đề:

### 1. **Workflow chồng lấn giữa các bài tập**
- **Trước:** Bài tập 2 yêu cầu làm từ branch bài tập 1
- **Sau:** Mỗi bài tập đều tạo branch mới từ main, workflow độc lập

### 2. **Tên repo không nhất quán**
- **Trước:** SETUP.md và README.md có tên repo khác nhau
- **Sau:** Thống nhất sử dụng `github-practice-beginner-pva`

### 3. **Thiếu thư mục profiles**
- **Thêm:** `/members/profiles/` với file `.gitkeep`

### 4. **File sample-document.md được thiết kế lại**
- **Có các lỗi cố ý để sinh viên sửa:**
  - Header thiếu space: `##Giới thiệu` 
  - Mix bullet points: `*` và `-`
  - Link typo: `htps://` thay vì `https://`
  - Code block thiếu language
  - Image syntax sai: `!(alt)[url]`
  - Table format thiếu separators
  - Header thiếu space: `###Code` và `####Kết`
  - Numbered list thiếu số: `2 Làm tutorial`

### 5. **Cập nhật checklist bài tập 2**
- Thêm chi tiết cụ thể về các lỗi cần sửa

## 🎯 Workflow rõ ràng cho từng bài tập:

**Bài tập 1:** Fork → Clone → Branch → Edit members.txt → Commit → Push → PR
**Bài tập 2:** Tạo branch mới → Sửa lỗi markdown → Commit → Push → PR  
**Bài tập 3:** Tạo branch mới → Tạo profile → Multiple commits → Push → PR
**Bài tập 4:** Simulate conflict → Merge → Resolve → Commit → Push → PR

## ✅ Kết luận:
- ❌ **Không còn chồng lấn nhiệm vụ** giữa các bài tập
- ✅ **Workflow nhất quán** và độc lập cho mỗi bài tập  
- ✅ **Tên repo thống nhất** trong tất cả file
- ✅ **Có đủ lỗi thực tế** trong sample-document.md để luyện tập
- ✅ **Cấu trúc thư mục hoàn chỉnh**
