# 🎵 Company Music Player

Web player nghe nhạc của cả công ty theo kiểu **round-robin** (lần lượt từng người).

## ✨ Tính năng

- ✅ **Round-robin mode**: Chạy bài 1 của mọi người → bài 2 của mọi người → ...
- ✅ **Tự động đọc từ Google Sheet**: Không cần hardcode data
- ✅ **Cập nhật real-time**: Sửa Sheet → refresh trang → xong!
- ✅ **Responsive**: Chạy mượt trên mobile + desktop
- ✅ **YouTube embed**: Nghe nhạc trực tiếp không cần mở tab mới
- ✅ **Keyboard shortcuts**: ← → để chuyển bài
- ✅ **100% FREE**: Không cần server, không cần maintain

## 🚀 Quick Start

### 1. Chuẩn bị Google Sheet

Tạo sheet với 4 cột:

| Tên người | Tên bài | Ca sĩ | Link YouTube |
|-----------|---------|-------|--------------|
| HuongLT | 30 For 30 | SZA | https://www.youtube.com/watch?v=... |
| LinhHTK | Roommates | Malcolm Todd | https://www.youtube.com/watch?v=... |

### 2. Publish Sheet thành CSV

1. **File** → **Share** → **Publish to web**
2. Chọn **"Comma-separated values (.csv)"**
3. Copy link

### 3. Cấu hình file HTML

Mở `company-music-player.html`, tìm dòng:

```javascript
const GOOGLE_SHEET_CSV_URL = 'YOUR_GOOGLE_SHEET_CSV_URL_HERE';
```

Thay bằng link CSV của bạn.

### 4. Deploy

Kéo thả file lên:
- **Vercel**: https://vercel.com (khuyên dùng)
- **Netlify**: https://netlify.com
- **GitHub Pages**: Settings → Pages

### 5. Chia sẻ link cho team 🎉

## 📖 Hướng dẫn chi tiết

Xem file [DEPLOY.md](./DEPLOY.md) để biết hướng dẫn từng bước chi tiết.

## 🎮 Cách sử dụng

- **Click vào bài**: Phát bài đó
- **Next/Previous**: Chuyển bài
- **Shuffle**: Xáo trộn playlist
- **← →**: Phím tắt chuyển bài

## 🔄 Cập nhật nhạc

Chỉ cần sửa Google Sheet → Refresh trang web → Xong!

Không cần deploy lại.

## 🎨 Tùy chỉnh

### Đổi màu giao diện

Sửa dòng này trong CSS:

```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

### Thêm tính năng

File HTML là single-file, dễ sửa. Tất cả code ở trong 1 file duy nhất.

## 🏗️ Kiến trúc

```
Google Sheet (CSV)
    ↓
CORS Proxy (allorigins.win)
    ↓
JavaScript fetch & parse
    ↓
Round-robin algorithm
    ↓
YouTube embed player
```

## 🤝 Contributing

Có ý tưởng? Tạo issue hoặc PR!

## 📝 License

MIT - Dùng thoải mái!

---

Made with ❤️ for your company
