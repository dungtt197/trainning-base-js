# JavaScript Cơ Bản

## Mục Lục
- [Session 1: Giới thiệu JavaScript & Biến, Kiểu Dữ Liệu](#session-1)
- [Session 2: Toán Tử và Câu Lệnh Điều Kiện](#session-2)
- [Session 3: Vòng Lặp](#session-3)
- [Session 4: Hàm (Function)](#session-4)
- [Session 5: Mảng và Object](#session-5)
- [Session 6: DOM và Sự Kiện](#session-6)
- [Session 7: Bất Đồng Bộ (Async & Promise)](#session-7)

---

## <a id="session-1"></a> Session 1: Giới thiệu JavaScript & Biến, Kiểu Dữ Liệu
### 1.1. Giới thiệu JavaScript
- JavaScript là ngôn ngữ lập trình phổ biến trên web.
- Được sử dụng để tạo hiệu ứng động, xử lý dữ liệu và giao tiếp với server.
- Có thể chạy trên trình duyệt hoặc môi trường Node.js.

### 1.2. Khai báo biến
JavaScript có ba cách khai báo biến:
```js
var a = 10;
let b = 20;
const c = 30;
console.log(a, b, c);
```

### 1.3. Kiểu dữ liệu cơ bản
- **Primitive types**: Number, String, Boolean, Null, Undefined, Symbol, BigInt.
- **Reference types**: Object, Array, Function.

```js
let num = 42; // Number
let str = "Hello"; // String
let bool = true; // Boolean
let arr = [1, 2, 3]; // Array (Object)
let obj = { name: "Alice", age: 25 }; // Object
let func = function() { return "Hello"; }; // Function
```

### 1.4. Bài tập thực hành
Viết một chương trình khai báo biến `name`, `age`, `isStudent` và in ra màn hình:
```plaintext
Tên: [name], Tuổi: [age], Là sinh viên: [isStudent]
```

[🔝 Quay lại đầu trang](#mục-lục)

---

## <a id="session-2"></a> Session 2: Toán Tử và Câu Lệnh Điều Kiện
### 2.1. Toán tử trong JavaScript
```js
let x = 10, y = 5;
console.log(x + y, x - y, x * y, x / y);
console.log(x > y, x === 10, y !== 5);
console.log(true && false, true || false, !true);
```

### 2.2. Câu lệnh điều kiện (if-else, switch)
```js
let age = 18;
if (age >= 18) {
    console.log("Bạn đã đủ tuổi.");
} else {
    console.log("Bạn chưa đủ tuổi.");
}
```

### 2.3. Bài tập thực hành
Viết chương trình nhập vào tuổi, nếu >= 18 in "Đủ tuổi bầu cử", ngược lại in "Chưa đủ tuổi bầu cử".

[🔝 Quay lại đầu trang](#mục-lục)

---

## <a id="session-3"></a> Session 3: Vòng Lặp
```js
for (let i = 1; i <= 5; i++) {
    console.log("Lần lặp thứ", i);
}
```

### 3.1. Bài tập thực hành
Viết chương trình in ra bảng cửu chương 2.

[🔝 Quay lại đầu trang](#mục-lục)

---

## <a id="session-4"></a> Session 4: Hàm (Function)
```js
function sayHello(name) {
    return "Hello, " + name;
}
console.log(sayHello("John"));
```

### 4.1. Bài tập thực hành
Viết hàm `calculateArea(radius)` tính diện tích hình tròn.

[🔝 Quay lại đầu trang](#mục-lục)

---

## <a id="session-5"></a> Session 5: Mảng và Object
```js
let numbers = [1, 2, 3, 4, 5];
numbers.push(6);
numbers.pop();
```

### 5.1. Bài tập thực hành
Viết một object chứa thông tin của bạn và in ra màn hình.

[🔝 Quay lại đầu trang](#mục-lục)

---

## <a id="session-6"></a> Session 6: DOM và Sự Kiện
```js
document.getElementById("btn").addEventListener("click", function() {
    alert("Bạn vừa nhấn nút!");
});
```

### 6.1. Bài tập thực hành
Tạo một nút `<button>` khi click sẽ thay đổi nội dung của `<p>` bên cạnh.

[🔝 Quay lại đầu trang](#mục-lục)

---

## <a id="session-7"></a> Session 7: Bất Đồng Bộ (Async & Promise)
```js
async function getData() {
    let result = await new Promise(resolve => setTimeout(() => resolve("Dữ liệu đã tải xong"), 2000));
    console.log(result);
}
getData();
```

### 7.1. Bài tập thực hành
Viết một hàm trả về `Promise` sau 3 giây, khi hoàn thành sẽ log "Hoàn thành!".

[🔝 Quay lại đầu trang](#mục-lục)
