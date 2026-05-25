# 🚀 Hướng dẫn Deploy Company Music Player

## 📋 Flow hoàn chỉnh (3 bước)

```
Google Sheet (mọi người điền) 
    ↓ 
Publish as CSV public
    ↓ 
Web app đọc CSV tự động
    ↓ 
Deploy lên Vercel/Netlify/GitHub Pages (FREE)
    ↓ 
Ném link cho cả công ty dùng 🎉
```

**Hoàn toàn FREE, không cần server, không cần maintain!**

---

## 🎯 Bước 1: Chuẩn bị Google Sheet

### 1.1. Tạo Google Sheet với cấu trúc:

| Tên người | Tên bài | Ca sĩ | Link YouTube |
|-----------|---------|-------|--------------|
| HuongLT | 30 For 30 | SZA | https://www.youtube.com/watch?v=... |
| LinhHTK | Roommates | Malcolm Todd | https://www.youtube.com/watch?v=... |
| NhuLTQ | Gội đầu | Thắng | https://www.youtube.com/watch?v=... |

**Lưu ý:**
- Cột 1: Tên người (viết tắt hoặc tên đầy đủ)
- Cột 2: Tên bài hát
- Cột 3: Ca sĩ
- Cột 4: Link YouTube đầy đủ

### 1.2. Publish Google Sheet thành CSV

1. Mở Google Sheet
2. **File** → **Share** → **Publish to web**
3. Chọn tab **"Link"**
4. Dropdown đầu tiên: chọn sheet cần publish
5. Dropdown thứ hai: chọn **"Comma-separated values (.csv)"**
6. Click **"Publish"**
7. Copy link (dạng: `https://docs.google.com/spreadsheets/d/1ABC.../export?format=csv`)

---

## 🎯 Bước 2: Cấu hình file HTML

### 2.1. Mở file `company-music-player.html`

### 2.2. Tìm dòng này (ở đầu thẻ `<script>`):
```javascript
const GOOGLE_SHEET_CSV_URL = 'YOUR_GOOGLE_SHEET_CSV_URL_HERE';
```

### 2.3. Thay bằng link CSV vừa copy:
```javascript
const GOOGLE_SHEET_CSV_URL = 'https://docs.google.com/spreadsheets/d/1ABC.../export?format=csv';
```

### 2.4. Save file

---

## 🎯 Bước 3: Deploy lên hosting (chọn 1 trong 3)

### ✅ Option 1: Vercel (Khuyên dùng - Nhanh nhất)

1. Vào https://vercel.com
2. Đăng ký bằng GitHub (miễn phí)
3. Click **"Add New Project"**
4. Kéo thả file `company-music-player.html` vào
5. Đợi 30 giây → Lấy link → **XONG!**

**Link sẽ có dạng:** `https://your-app.vercel.app`

---

### ✅ Option 2: Netlify

1. Vào https://netlify.com (đăng ký miễn phí)
2. **Đổi tên file** từ `company-music-player.html` → `index.html`
3. Kéo thả file vào Netlify Drop
4. Đợi 20 giây → **XONG!**

**Link sẽ có dạng:** `https://your-app.netlify.app`

---

### ✅ Option 3: GitHub Pages

#### 3.1. Tạo repo GitHub
```bash
git init
git add company-music-player.html
git commit -m "Add music player"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/company-music.git
git push -u origin main
```

#### 3.2. Bật GitHub Pages
1. Vào repo → **Settings** → **Pages**
2. Source: chọn `main` branch
3. Save → Đợi 1 phút

#### 3.3. Truy cập
**Link:** `https://YOUR_USERNAME.github.io/company-music/company-music-player.html`

---

## 🔄 Cập nhật danh sách nhạc

### Cách 1: Thêm bài mới vào Google Sheet (Khuyên dùng)
1. Mở Google Sheet
2. Thêm dòng mới với format: `Tên người | Tên bài | Ca sĩ | Link YouTube`
3. Save → **Web tự động cập nhật** (refresh trang web)

**Không cần deploy lại!** 🎉

### Cách 2: Sửa trực tiếp file HTML
- Chỉ dùng khi muốn thay đổi giao diện hoặc logic
- Sau khi sửa phải deploy lại

---

## 🎨 Tùy chỉnh giao diện

### Đổi màu gradient nền
Tìm dòng này trong CSS:
```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

**Màu đẹp gợi ý:**
- Xanh dương tím: `#667eea 0%, #764ba2 100%` (mặc định)
- Xanh lá: `#11998e 0%, #38ef7d 100%`
- Cam đỏ: `#f46b45 0%, #eea849 100%`
- Hồng: `#ff6a88 0%, #ff99ac 100%`

---

## ❓ Troubleshooting

### ❌ Lỗi: "Không thể tải Google Sheet"
**Nguyên nhân:** Link CSV chưa đúng hoặc chưa publish

**Giải pháp:**
1. Kiểm tra lại link CSV có dạng: `https://docs.google.com/spreadsheets/d/.../export?format=csv`
2. Đảm bảo đã click **"Publish"** trong Google Sheet
3. Thử truy cập link CSV trực tiếp trên trình duyệt → phải thấy data dạng CSV

### ❌ Video YouTube không chạy
**Nguyên nhân:** 
- Link YouTube không đúng format
- Video bị chặn embed

**Giải pháp:**
- Dùng link đầy đủ: `https://www.youtube.com/watch?v=VIDEO_ID`
- Thử video khác

### ❌ Không hiển thị bài hát
**Nguyên nhân:** Format CSV sai

**Giải pháp:**
- Đảm bảo Google Sheet có đúng 4 cột
- Không có dòng trống
- Dòng đầu tiên có thể là header (sẽ tự động bỏ qua)

---

## 🎉 Xong rồi!

Giờ cả công ty có thể:
- ✅ Nghe nhạc theo kiểu **round-robin** (lần lượt từng người)
- ✅ Thêm bài mới chỉ cần sửa Google Sheet
- ✅ Không cần maintain server
- ✅ Hoàn toàn FREE

**Link deploy của bạn:** _________________ (điền sau khi deploy)

---

Made with ❤️ for your company
