# Laravel Cơ Bản - Hướng Dẫn Thực Hành

## Mục Lục
1. [Giới thiệu Laravel](#1)
2. [Cấu trúc thư mục trong Laravel](#2)
3. [Routing trong Laravel](#3)
4. [Controller và Middleware](#4)
5. [Model và Eloquent ORM](#5)
6. [Blade Template](#6)
7. [Form và Validation](#7)
8. [Migration và Seeder](#8)
9. [Authentication và Authorization](#9)
10. [API với Laravel](#10)
10. [Project cuối khóa](#11)

---

## <a id="1"></a> 1. Giới thiệu Laravel
Laravel là một PHP framework mạnh mẽ giúp phát triển ứng dụng web nhanh chóng với cú pháp dễ hiểu và nhiều tính năng hỗ trợ.

### Cài đặt Laravel
```bash
composer create-project --prefer-dist laravel/laravel my_project
```

### Chạy ứng dụng Laravel
```bash
php artisan serve
```

### Kiến trúc MVC trong Laravel
Laravel tuân theo mô hình **MVC (Model-View-Controller)** giúp phân tách rõ ràng giữa dữ liệu, giao diện và logic xử lý.
- **Model**: Quản lý dữ liệu, tương tác với database.
- **View**: Giao diện người dùng.
- **Controller**: Xử lý yêu cầu và điều phối dữ liệu.

**Bài tập:**
- Cài đặt Laravel và khởi chạy một ứng dụng mới.
- Tìm hiểu file `.env` và cấu hình kết nối database.

---

## <a id="2"></a>  2. Cấu trúc thư mục trong Laravel
Laravel có cấu trúc thư mục rõ ràng:
- `app/` - Chứa model, controller, middleware.
- `routes/` - Chứa định tuyến (`web.php`, `api.php`).
- `resources/views/` - Chứa Blade templates.
- `database/` - Chứa migration, seeder.
- `config/` - Chứa cấu hình hệ thống.

**Bài tập:**
- Tạo một file `routes/test.php` và thử thêm một route đơn giản.
- Phân tích cấu trúc thư mục `app/Http` và vai trò của từng file.

---

## <a id="33"></a>  3. Routing trong Laravel
Routing giúp điều hướng yêu cầu HTTP đến đúng controller hoặc xử lý logic.

### Định nghĩa route đơn giản
```php
Route::get('/hello', function () {
    return 'Xin chào Laravel!';
});
```

### Route với tham số
```php
Route::get('/user/{id}', function ($id) {
    return 'User ID: ' . $id;
});
```

### Route với middleware
```php
Route::middleware(['auth'])->group(function () {
    Route::get('/dashboard', function () {
        return view('dashboard');
    });
});
```

**Bài tập:**
- Tạo một route với tham số và kiểm tra kết quả.
- Thêm middleware vào một route cụ thể.

---

## <a id="44"></a>  4. Controller và Middleware
Controller giúp tổ chức logic xử lý, Middleware giúp kiểm soát request.

### Tạo Controller
```bash
php artisan make:controller TestController
```

```php
class TestController extends Controller {
    public function index() {
        return "Hello from Controller!";
    }
}
```

### Middleware
```bash
php artisan make:middleware CheckAge
```

```php
public function handle($request, Closure $next) {
    if ($request->age < 18) {
        return redirect('home');
    }
    return $next($request);
}
```

**Bài tập:**
- Tạo một Controller với method trả về danh sách user.
- Viết middleware kiểm tra tuổi người dùng trước khi truy cập trang.

---

## <a id="5"></a>  5. Model và Eloquent ORM
Eloquent giúp thao tác với database dễ dàng.

### Tạo Model
```bash
php artisan make:model Product
```

### Quan hệ giữa các Model
```php
class Category extends Model {
    public function products() {
        return $this->hasMany(Product::class);
    }
}
```

**Bài tập:**
- Tạo Model `Category` và thêm phương thức quan hệ với `Product`.
- Viết query lấy danh sách sản phẩm thuộc danh mục cụ thể.

---

## <a id="6"></a>  6. Blade Template
Blade giúp render giao diện linh hoạt.

### Cấu trúc Blade
```blade
@extends('layouts.app')
@section('content')
    <h1>Chào mừng!</h1>
@endsection
```

### Component trong Blade
```blade
<x-alert type="success" message="Thành công!" />
```

**Bài tập:**
- Tạo một file Blade để hiển thị danh sách sản phẩm.
- Sử dụng Blade component để tái sử dụng giao diện.

---

## <a id="7"></a>  7. Form và Validation
Laravel hỗ trợ validate dữ liệu form dễ dàng.

```php
$request->validate([
    'name' => 'required|min:3',
]);
```

**Bài tập:**
- Tạo form nhập sản phẩm với validation.
- Viết validation rule tùy chỉnh.

---

## <a id="88"></a>  8. Migration và Seeder
Migration giúp tạo bảng, Seeder giúp nhập dữ liệu mẫu.

### Tạo migration
```bash
php artisan make:migration create_products_table
```

**Bài tập:**
- Tạo migration cho bảng `categories`.
- Viết seeder nhập dữ liệu mẫu.

---

## <a id="9"></a>  9. Authentication và Authorization
Laravel cung cấp hệ thống đăng nhập sẵn có.

```bash
composer require laravel/ui
php artisan ui bootstrap --auth
```

**Bài tập:**
- Cài đặt authentication và tạo user login.
- Phân quyền người dùng theo role.

---

## <a id="10"></a>  10. API với Laravel
Laravel hỗ trợ xây dựng API nhanh chóng.

```php
Route::get('/products', [ProductController::class, 'index']);
```

**Bài tập:**
- Xây dựng API CRUD cho sản phẩm.
- Thêm authentication cho API với Passport hoặc Sanctum.

---

## <a id="11"></a> 11. Dự án Cuối Khóa: Xây Dựng Hệ Thống Quản Lý Sản Phẩm
Dự án này sẽ giúp bạn áp dụng kiến thức vào thực tế.

### Tính Năng
- Quản lý danh mục sản phẩm.
- CRUD sản phẩm.
- Xử lý hình ảnh sản phẩm.
- Hệ thống đăng nhập, phân quyền Admin/User.
- API cho danh sách sản phẩm.

### Hướng Dẫn
1. **Tạo project Laravel**:
    ```bash
    composer create-project --prefer-dist laravel/laravel ProductManagement
    ```
2. **Tạo model, migration, controller**:
    ```bash
    php artisan make:model Product -mcr
    ```
3. **Thiết kế database**
    ```php
    Schema::create('products', function (Blueprint $table) {
        $table->id();
        $table->string('name');
        $table->decimal('price', 8, 2);
        $table->string('image');
        $table->timestamps();
    });
    ```
4. **Tạo API**:
    ```php
    Route::apiResource('products', ProductController::class);
    ```
5. **Tạo Blade template danh sách sản phẩm**
    ```blade
    @foreach($products as $product)
        <div>{{ $product->name }} - {{ $product->price }} VND</div>
    @endforeach
    ```
6. **Thêm authentication**:
    ```bash
    composer require laravel/ui
    php artisan ui bootstrap --auth
    ```

**Bài tập:**
- Hoàn thành CRUD danh mục sản phẩm.
- Viết API lấy danh sách sản phẩm theo danh mục.
- Thêm middleware bắt buộc đăng nhập khi thêm/sửa/xóa sản phẩm.
