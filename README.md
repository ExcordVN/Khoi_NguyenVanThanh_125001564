# Vị Việt

Website giới thiệu món ăn Việt Nam, viết hoàn toàn bằng HTML5 và CSS3. Không có JavaScript, TypeScript, framework hay bước build.

## Cách mở

- Nhấp đúp `index.html` để mở trực tiếp trong trình duyệt, hoặc
- Dùng tiện ích Live Server trong VS Code: chuột phải `index.html` rồi chọn "Open with Live Server".

Cần kết nối mạng để tải ảnh món ăn (Unsplash) và phông chữ (Google Fonts). Nếu ảnh không tải được, trang dùng ảnh dự phòng trong `assets/images/`.

## Cấu trúc

```
index.html
style.css
README.md
prompt_log.md
assets/
  logo.svg
  favicon.svg
  README.md
  images/
    food-placeholder.svg
    restaurant-placeholder.svg
```

## Giới hạn của bản HTML + CSS

- Ô tìm kiếm chỉ để minh họa (bị vô hiệu hóa), không lọc được món ăn.
- Mục quán ăn là dữ liệu mẫu tĩnh; không có định vị, không tính khoảng cách, không lấy dữ liệu thật.
- Mục "Hôm nay ăn gì?" là các gợi ý cố định, không tạo gợi ý động theo lựa chọn.
- Menu trên điện thoại dùng checkbox CSS; điều hướng dùng liên kết neo (`#id`).
