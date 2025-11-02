# learn-nuxt3-tutorial
Learn use nuxt v3

## Hướng dẫn chạy project

Các bước nhanh:
1. Cài dependencies
```bash
npm install
```
2. Chạy development server
```bash
npm run dev
```

## Sử dụng Fake Store API

Dự án tham khảo Fake Store API để lấy dữ liệu mẫu. Tham khảo docs đầy đủ tại: https://fakestoreapi.com/docs

Ví dụ gọi API trong Nuxt 3 (setup / composable) với useFetch:
```js
// Lấy danh sách sản phẩm
const { data: products, error } = await useFetch('https://fakestoreapi.com/products')

// Lấy chi tiết sản phẩm theo id
const { data: product, error: err } = await useFetch('https://fakestoreapi.com/products/1')
```

Hoặc dùng global $fetch:
```js
const products = await $fetch('https://fakestoreapi.com/products')
```

## Ghi chú
- Fake Store API là public demo API, xem https://fakestoreapi.com/docs để biết các endpoint khác (carts, users, categories).
- Nếu cần thay base URL, cấu hình trong runtime config (.env / nuxt.config).
