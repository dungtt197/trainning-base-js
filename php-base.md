# Cơ Bản Về PHP

## Mục Lục

1. [Giới Thiệu PHP](#gioi-thieu-php)
2. [Biến và Kiểu Dữ Liệu](#bien-va-kieu-du-lieu)
3. [Toán Tử](#toan-tu)
4. [Cấu Trúc Điều Khiển](#cau-truc-dieu-khien)
5. [Hàm](#ham)
6. [Mảng](#mang)
7. [Biến Superglobals](#bien-superglobals)
8. [Xử Lý Tệp](#xu-ly-tep)
9. [Session và Cookie](#session-va-cookie)
10. [Lập Trình Hướng Đối Tượng (OOP)](#lap-trinh-huong-doi-tuong-oop)

---

## 1. Giới Thiệu PHP

PHP (Hypertext Preprocessor) là một ngôn ngữ lập trình phía server được thiết kế cho phát triển web. Nó có thể nhúng vào HTML và tương tác với cơ sở dữ liệu.

### Ví dụ:
```php
<?php
  echo "Xin chào, thế giới!";
?>
```

### Bài Tập:
- Cài đặt PHP trên máy của bạn và tạo một script đơn giản để in ra tên của bạn.

---

## 2. Biến và Kiểu Dữ Liệu

Biến trong PHP bắt đầu bằng ký tự `$`. PHP hỗ trợ nhiều kiểu dữ liệu như chuỗi, số nguyên, số thực, boolean và mảng.

### Ví dụ:
```php
<?php
  $ten = "John";
  $tuoi = 25;
  echo "Tôi tên là $ten và tôi $tuoi tuổi.";
?>
```

### Bài Tập:
- Khai báo biến cho tên, tuổi và màu sắc yêu thích của bạn, sau đó in chúng ra.

---

## 3. Toán Tử

PHP hỗ trợ toán tử số học, so sánh, logic, gán và chuỗi.

### Ví dụ:
```php
<?php
  $a = 10;
  $b = 5;
  echo $a + $b; // Kết quả: 15
?>
```

### Bài Tập:
- Viết một script PHP tính tổng, hiệu và tích của hai số.

---

## 4. Cấu Trúc Điều Khiển

Câu lệnh điều kiện (`if`, `else`, `switch`) và vòng lặp (`for`, `while`, `foreach`) giúp kiểm soát luồng thực thi.

### Ví dụ:
```php
<?php
  $x = 10;
  if ($x > 5) {
      echo "X lớn hơn 5";
  }
?>
```

### Bài Tập:
- Viết một script in ra các số từ 1 đến 10 bằng vòng lặp.

---

## 5. Hàm

Hàm giúp tổ chức mã nguồn và có thể tái sử dụng.

### Ví dụ:
```php
<?php
  function chao($ten) {
      return "Xin chào, $ten!";
  }
  echo chao("Alice");
?>
```

### Bài Tập:
- Viết một hàm nhận hai số làm tham số và trả về tổng của chúng.

---

## 6. Mảng

PHP hỗ trợ mảng chỉ mục, mảng kết hợp và mảng đa chiều.

### Ví dụ:
```php
<?php
  $trai_cay = array("Táo", "Chuối", "Cherry");
  echo $trai_cay[1]; // Kết quả: Chuối
?>
```

### Bài Tập:
- Tạo một mảng kết hợp với ba khóa: tên, tuổi và thành phố, sau đó in ra các giá trị.

---

## 7. Biến Superglobals

PHP cung cấp các biến toàn cục như `$_GET`, `$_POST`, `$_SESSION`, `$_COOKIE`, `$_SERVER`.

### Ví dụ:
```php
<?php
  echo $_SERVER['PHP_SELF'];
?>
```

### Bài Tập:
- Tạo một form HTML nhận tên và hiển thị nó bằng `$_POST`.

---

## 8. Xử Lý Tệp

PHP có thể đọc, ghi và xóa tệp.

### Ví dụ:
```php
<?php
  $file = fopen("test.txt", "w");
  fwrite($file, "Xin chào, tập tin!");
  fclose($file);
?>
```

### Bài Tập:
- Viết một script PHP đọc nội dung từ một tệp văn bản và hiển thị nó.

---

## 9. Session và Cookie

Session lưu trữ dữ liệu người dùng trên nhiều trang, còn cookie lưu dữ liệu trên máy người dùng.

### Ví dụ (Session):
```php
<?php
  session_start();
  $_SESSION['user'] = "John Doe";
  echo "Session đã được thiết lập cho người dùng: " . $_SESSION['user'];
?>
```

### Bài Tập:
- Tạo một hệ thống đăng nhập sử dụng session.

---

## 10. Lập Trình Hướng Đối Tượng (OOP)

OOP trong PHP bao gồm lớp, đối tượng, constructor và phương thức.

### Các tính chất của OOP
1. **Tính đóng gói (Encapsulation)** - Bảo vệ dữ liệu bên trong lớp, chỉ cho phép truy cập thông qua các phương thức được định nghĩa.
2. **Tính kế thừa (Inheritance)** - Lớp con có thể kế thừa các thuộc tính và phương thức từ lớp cha.
3. **Tính đa hình (Polymorphism)** - Một phương thức có thể hoạt động khác nhau tùy vào lớp con kế thừa.
4. **Tính trừu tượng (Abstraction)** - Che giấu chi tiết thực hiện của một lớp và chỉ hiển thị những gì cần thiết.

### Ví dụ về OOP:
```php
<?php
class Xe {
    protected $hang;
    
    public function __construct($hang) {
        $this->hang = $hang;
    }
    
    public function getHang() {
        return $this->hang;
    }
}

class Oto extends Xe {
    private $soCho;
    
    public function __construct($hang, $soCho) {
        parent::__construct($hang);
        $this->soCho = $soCho;
    }
    
    public function getThongTin() {
        return "Hãng: " . $this->getHang() . ", Số chỗ: " . $this->soCho;
    }
}

$xe = new Oto("Toyota", 5);
echo $xe->getThongTin();
?>
```

### Abstract Class và Interface

**Abstract Class** là một lớp trừu tượng không thể khởi tạo trực tiếp, chỉ có thể được kế thừa.

```php
<?php
abstract class DongVat {
    abstract public function keu();
}

class Cho extends DongVat {
    public function keu() {
        return "Gâu gâu";
    }
}
$cho = new Cho();
echo $cho->keu();
?>
```

**Interface** định nghĩa các phương thức mà lớp triển khai nó phải có.

```php
<?php
interface HanhDong {
    public function diChuyen();
}

class Meo implements HanhDong {
    public function diChuyen() {
        return "Mèo đi bằng 4 chân";
    }
}
$meo = new Meo();
echo $meo->diChuyen();
?>
```

### Bài Tập:
- Tạo một abstract class `DongVat` với phương thức `keu()`, sau đó tạo lớp `Chim` kế thừa từ `DongVat` và triển khai phương thức `keu()`.
- Viết một interface `HinhHoc` với phương thức `tinhDienTich()`, sau đó tạo lớp `HinhVuong` và `HinhTron` triển khai interface này.

---

Tài liệu này cung cấp hướng dẫn cơ bản về PHP. Hãy thực hành các bài tập để nâng cao kỹ năng của bạn!

