# Dự Án Tổng Hợp Cuối Khóa

## Mục Tiêu
Xây dựng một ứng dụng web hoàn chỉnh sử dụng các kiến thức đã học từ ba khóa học: JavaScript, PHP, và Laravel.

## Yêu Cầu
1. **Frontend**:
    - Sử dụng HTML, CSS và JavaScript để xây dựng giao diện người dùng.
    - Sử dụng DOM để thay đổi nội dung trang web khi người dùng tương tác.
    - Sử dụng AJAX để gửi và nhận dữ liệu từ server mà không cần tải lại trang.

2. **Backend**:
    - Sử dụng PHP và Laravel để xây dựng API và xử lý logic phía server.
    - Sử dụng Eloquent ORM để tương tác với cơ sở dữ liệu.
    - Sử dụng session hoặc cookie để quản lý thông tin người dùng.

## Tính Năng
- **Quản lý người dùng**:
    - Đăng ký, đăng nhập, và đăng xuất.
    - Quản lý thông tin cá nhân.
- **Quản lý sản phẩm**:
    - Thêm, sửa, xóa và xem danh sách sản phẩm.
    - Tìm kiếm và lọc sản phẩm.
- **Giỏ hàng**:
    - Thêm sản phẩm vào giỏ hàng.
    - Xem và cập nhật giỏ hàng.
    - Thanh toán đơn hàng.

## Hướng Dẫn
1. **Tạo project Laravel**:
    ```bash
    composer create-project --prefer-dist laravel/laravel FinalProject
    ```

2. **Thiết kế database**:
    - Tạo các bảng `users`, `products`, `orders`, `order_items`.

3. **Tạo model, migration, controller**:
    ```bash
    php artisan make:model User -mcr
    php artisan make:model Product -mcr
    php artisan make:model Order -mcr
    php artisan make:model OrderItem -mcr
    ```

4. **Xây dựng API**:
    - Tạo các route và controller cho API quản lý người dùng, sản phẩm, và đơn hàng.

5. **Xây dựng giao diện người dùng**:
    - Sử dụng HTML, CSS và JavaScript để tạo các trang đăng ký, đăng nhập, danh sách sản phẩm, giỏ hàng, và thanh toán.

6. **Tích hợp AJAX**:
    - Sử dụng AJAX để gửi và nhận dữ liệu từ server mà không cần tải lại trang.

## Bài Tập
- Hoàn thành các tính năng quản lý người dùng.
- Xây dựng API CRUD cho sản phẩm.
- Tạo giao diện giỏ hàng và tích hợp AJAX để thêm sản phẩm vào giỏ hàng.
- Hoàn thành quy trình thanh toán đơn hàng.

## Tài Liệu Tham Khảo
- [Laravel Documentation](https://laravel.com/docs)
- [MDN Web Docs](https://developer.mozilla.org/)
- [W3Schools](https://www.w3schools.com/)

Chúc bạn thành công với dự án cuối khóa!
