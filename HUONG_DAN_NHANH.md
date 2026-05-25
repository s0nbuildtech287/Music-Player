# ⚡ HƯỚNG DẪN NHANH - 5 PHÚT LÀ XONG!

## Bước 1: Tạo Google Sheet (2 phút)

### 1.1. Tạo sheet mới với 4 cột:

```
Tên người | Tên bài | Ca sĩ | Link YouTube
```

**Ví dụ:**
```
HuongLT | 30 For 30 | SZA | https://www.youtube.com/watch?v=abc123
LinhHTK | Roommates | Malcolm Todd | https://www.youtube.com/watch?v=xyz789
```

### 1.2. Publish thành CSV:

1. **File** → **Share** → **Publish to web**
2. Chọn **"Comma-separated values (.csv)"**
3. Click **"Publish"**
4. **Copy link** (dạng: `https://docs.google.com/spreadsheets/d/.../export?format=csv`)

---

## Bước 2: Cấu hình file HTML (30 giây)

### 2.1. Mở file `company-music-player.html`

### 2.2. Tìm dòng 93 (hoặc Ctrl+F tìm "YOUR_GOOGLE_SHEET"):

```javascript
const GOOGLE_SHEET_CSV_URL = 'YOUR_GOOGLE_SHEET_CSV_URL_HERE';
```

### 2.3. Thay bằng link CSV vừa copy:

```javascript
const GOOGLE_SHEET_CSV_URL = 'https://docs.google.com/spreadsheets/d/1ABC.../export?format=csv';
```

### 2.4. **Save file** (Ctrl+S)

---

## Bước 3: Deploy lên Vercel (2 phút)

### 3.1. Vào https://vercel.com

### 3.2. Đăng ký bằng GitHub (miễn phí)

### 3.3. Click **"Add New Project"**

### 3.4. Kéo thả file `company-music-player.html` vào

### 3.5. Đợi 30 giây → **XONG!**

**Link của bạn:** `https://your-app.vercel.app`

---

## 🎉 Xong rồi!

Giờ chia sẻ link cho cả công ty:

```
🎵 Company Music Player
Link: https://your-app.vercel.app

Nghe nhạc của cả team theo kiểu round-robin!
```

---

## 🔄 Muốn thêm bài mới?

1. Mở Google Sheet
2. Thêm dòng mới
3. Save
4. Refresh trang web → **Xong!**

**Không cần deploy lại!**

---

## ❓ Gặp lỗi?

### Lỗi: "Không thể tải Google Sheet"

**Giải pháp:**
1. Kiểm tra link CSV có đúng không
2. Đảm bảo đã click **"Publish"** trong Google Sheet
3. Thử truy cập link CSV trực tiếp → phải thấy data

### Video không chạy?

**Giải pháp:**
- Dùng link YouTube đầy đủ: `https://www.youtube.com/watch?v=VIDEO_ID`
- Một số video bị chặn embed → thử video khác

---

## 📞 Cần hỗ trợ?

Xem file **DEPLOY.md** để biết hướng dẫn chi tiết hơn!

---

**Chúc bạn thành công! 🚀**
