# JavaScript Cơ Bản

## 1. Giới thiệu về JavaScript
JavaScript là một ngôn ngữ lập trình phổ biến, chủ yếu được sử dụng để phát triển web. Nó giúp tạo ra các trang web động và tương tác. JavaScript có thể chạy trên trình duyệt hoặc trên máy chủ với Node.js.

### Bài tập thực hành
1. Viết một đoạn script JavaScript để hiển thị thông báo "Chào mừng đến với JavaScript!" trên trình duyệt.
2. Tạo một file `.js` riêng biệt và liên kết với file HTML.



## 2. Biến và Kiểu dữ liệu trong JavaScript

### 2.1. Biến trong JavaScript
Biến là một vùng nhớ dùng để lưu trữ giá trị và có thể thay đổi trong quá trình thực thi chương trình.

#### Khai báo biến
Trong JavaScript, có 3 cách để khai báo biến:
1. **`var`**: Phạm vi **function scope**, có thể khai báo lại và gán lại.
2. **`let`**: Phạm vi **block scope**, không thể khai báo lại nhưng có thể gán lại.
3. **`const`**: Phạm vi **block scope**, không thể khai báo lại và không thể gán lại giá trị mới.

Ví dụ:
```js
var x = 10; // Khai báo biến bằng var
let y = 20; // Khai báo biến bằng let
const z = 30; // Khai báo biến bằng const
```

#### So sánh `var`, `let` và `const`
| Thuộc tính  | `var` | `let` | `const` |
|-------------|------|------|--------|
| Phạm vi (Scope) | Function Scope | Block Scope | Block Scope |
| Có thể khai báo lại | ✔ | ❌ | ❌ |
| Có thể gán lại | ✔ | ✔ | ❌ |
| Có hoisting | ✔ | ✔ (không khởi tạo) | ✔ (không khởi tạo) |

Ví dụ minh họa phạm vi của `var`, `let` và `const`:
```js
function testScope() {
    if (true) {
        var a = "Tôi là var";
        let b = "Tôi là let";
        const c = "Tôi là const";
    }
    console.log(a); // Hoạt động (vì var có phạm vi function)
    console.log(b); // Lỗi (vì let có phạm vi block)
    console.log(c); // Lỗi (vì const có phạm vi block)
}
testScope();
```

---

### 2.2. Kiểu dữ liệu trong JavaScript
JavaScript có hai nhóm kiểu dữ liệu chính:
1. **Kiểu dữ liệu nguyên thủy (Primitive)**
2. **Kiểu dữ liệu tham chiếu (Reference)**

#### 1. Kiểu dữ liệu nguyên thủy (Primitive)
Đây là các kiểu dữ liệu đơn giản, lưu trữ giá trị trực tiếp trong bộ nhớ.
- **Number**: Chứa cả số nguyên và số thực.
  ```js
  let num1 = 10;
  let num2 = 3.14;
  ```
- **String**: Chứa chuỗi ký tự.
  ```js
  let str = "Hello, world!";
  ```
- **Boolean**: Chứa giá trị `true` hoặc `false`.
  ```js
  let isJSFun = true;
  ```
- **Undefined**: Một biến được khai báo nhưng chưa có giá trị.
  ```js
  let notDefined;
  console.log(notDefined); // undefined
  ```
- **Null**: Một giá trị rỗng có chủ đích.
  ```js
  let emptyValue = null;
  ```
- **Symbol** (ES6): Tạo giá trị duy nhất.
  ```js
  let uniqueKey = Symbol("id");
  ```

#### 2. Kiểu dữ liệu tham chiếu (Reference)
Kiểu dữ liệu tham chiếu lưu trữ địa chỉ của đối tượng trong bộ nhớ.
- **Array**: Mảng chứa nhiều giá trị.
  ```js
  let numbers = [1, 2, 3, 4, 5];
  ```
- **Object**: Đối tượng chứa cặp key-value.
  ```js
  let person = {
      name: "Alice",
      age: 25
  };
  ```
- **Function**: Một hàm cũng là một kiểu dữ liệu trong JavaScript.
  ```js
  function greet() {
      console.log("Hello!");
  }
  ```

---

### 2.3. Ép kiểu trong JavaScript
JavaScript là ngôn ngữ **dynamically typed**, nghĩa là kiểu dữ liệu có thể thay đổi trong quá trình thực thi.

#### Ép kiểu tự động (Type Coercion)
```js
console.log("5" + 5); // "55" (ép kiểu sang chuỗi)
console.log("5" - 3); // 2 (ép kiểu sang số)
```

#### Ép kiểu tường minh (Explicit Conversion)
Dùng các hàm:
- `Number()`, `String()`, `Boolean()`
```js
let str = "123";
let num = Number(str); // Chuyển thành số
console.log(num); // 123
```

---

### Bài tập thực hành
1. Khai báo một biến chứa tên của bạn và hiển thị nó ra console.
2. Tạo một mảng chứa danh sách 5 số và tính tổng các số trong mảng.
3. Viết chương trình kiểm tra kiểu dữ liệu của một biến bằng `typeof`.

---


## 3. Toán tử trong JavaScript

Toán tử là các ký hiệu đặc biệt giúp chúng ta thực hiện các phép tính hoặc thao tác trên các giá trị. JavaScript cung cấp nhiều loại toán tử khác nhau.

---

### 3.1. Toán tử số học (Arithmetic Operators)
Dùng để thực hiện các phép toán trên số.

| Toán tử | Ý nghĩa | Ví dụ | Kết quả |
|---------|--------|-------|---------|
| `+` | Cộng | `5 + 3` | `8` |
| `-` | Trừ | `5 - 3` | `2` |
| `*` | Nhân | `5 * 3` | `15` |
| `/` | Chia | `10 / 2` | `5` |
| `%` | Chia lấy dư | `10 % 3` | `1` |
| `**` | Lũy thừa | `2 ** 3` | `8` |

Ví dụ:
```js
let a = 10, b = 3;
console.log(a + b); // 13
console.log(a - b); // 7
console.log(a * b); // 30
console.log(a / b); // 3.33
console.log(a % b); // 1
console.log(2 ** 3); // 8
```

---

### 3.2. Toán tử gán (Assignment Operators)
Dùng để gán giá trị cho biến.

| Toán tử | Ý nghĩa | Ví dụ |
|---------|--------|-------|
| `=` | Gán | `x = 10` |
| `+=` | Cộng và gán | `x += 5` (tương đương `x = x + 5`) |
| `-=` | Trừ và gán | `x -= 3` (tương đương `x = x - 3`) |
| `*=` | Nhân và gán | `x *= 2` (tương đương `x = x * 2`) |
| `/=` | Chia và gán | `x /= 4` (tương đương `x = x / 4`) |
| `%=` | Chia lấy dư và gán | `x %= 2` (tương đương `x = x % 2`) |

Ví dụ:
```js
let x = 10;
x += 5; // x = x + 5 (x = 15)
x *= 2; // x = x * 2 (x = 30)
console.log(x); // 30
```

---

### 3.3. Toán tử so sánh (Comparison Operators)
Dùng để so sánh hai giá trị, trả về `true` hoặc `false`.

| Toán tử | Ý nghĩa | Ví dụ | Kết quả |
|---------|--------|-------|---------|
| `==` | So sánh bằng (không xét kiểu) | `5 == "5"` | `true` |
| `===` | So sánh bằng (có xét kiểu) | `5 === "5"` | `false` |
| `!=` | So sánh khác (không xét kiểu) | `5 != "5"` | `false` |
| `!==` | So sánh khác (có xét kiểu) | `5 !== "5"` | `true` |
| `>` | Lớn hơn | `5 > 3` | `true` |
| `<` | Nhỏ hơn | `5 < 3` | `false` |
| `>=` | Lớn hơn hoặc bằng | `5 >= 5` | `true` |
| `<=` | Nhỏ hơn hoặc bằng | `3 <= 5` | `true` |

Ví dụ:
```js
console.log(10 == "10");  // true (so sánh giá trị, không xét kiểu)
console.log(10 === "10"); // false (so sánh cả kiểu dữ liệu)
console.log(10 != "10");  // false
console.log(10 !== "10"); // true
console.log(5 > 3);       // true
```

---

### 3.4. Toán tử logic (Logical Operators)
Dùng để kết hợp nhiều điều kiện.

| Toán tử | Ý nghĩa | Ví dụ | Kết quả |
|---------|--------|-------|---------|
| `&&` | Và | `true && false` | `false` |
| `||` | Hoặc | `true || false` | `true` |
| `!` | Phủ định | `!true` | `false` |

Ví dụ:
```js
let age = 25;
let isAdult = age > 18 && age < 65; // true
let canVote = age >= 18 || age < 65; // true
let notAdult = !isAdult; // false

console.log(isAdult);  // true
console.log(canVote);  // true
console.log(notAdult); // false
```

---

### 3.5. Toán tử tăng/giảm (Increment/Decrement Operators)
Dùng để tăng hoặc giảm giá trị của biến.

| Toán tử | Ý nghĩa | Ví dụ |
|---------|--------|-------|
| `++` | Tăng 1 đơn vị | `x++` hoặc `++x` |
| `--` | Giảm 1 đơn vị | `x--` hoặc `--x` |

Ví dụ:
```js
let num = 10;
console.log(num++); // 10 (hậu tố: trả về giá trị trước khi tăng)
console.log(num);   // 11

let num2 = 10;
console.log(++num2); // 11 (tiền tố: tăng rồi mới trả về giá trị)
```

---

### 3.6. Toán tử ba ngôi (Ternary Operator)
Toán tử ba ngôi (`? :`) giúp viết câu lệnh `if-else` ngắn gọn.

Cú pháp:
```js
condition ? expression1 : expression2;
```

Ví dụ:
```js
let age = 20;
let message = age >= 18 ? "Bạn đủ tuổi" : "Bạn chưa đủ tuổi";
console.log(message);
```

---

##  Bài tập thực hành
1. Viết chương trình yêu cầu người dùng nhập hai số và kiểm tra xem số nào lớn hơn.
2. Viết chương trình kiểm tra một số có chia hết cho 5 hay không.
3. Viết chương trình kiểm tra người dùng có đủ tuổi uống rượu (từ 18 tuổi trở lên) bằng toán tử ba ngôi.
4. Viết chương trình tính tiền lương nhân viên dựa trên số giờ làm (lương cơ bản là 50.000 VNĐ/giờ, nếu làm trên 40 giờ thì giờ thêm sẽ nhân đôi).
5. Viết chương trình kiểm tra một số có phải là số chẵn hay không bằng toán tử `&&` và `||`.

---


# 4. Cấu trúc điều kiện và vòng lặp trong JavaScript

## 4.1. Cấu trúc điều kiện (Conditional Statements)
Cấu trúc điều kiện cho phép kiểm tra một điều kiện và thực thi các đoạn code tương ứng.

### 4.1.1. `if`, `else if`, `else`
Cú pháp:
```js
if (điều_kiện) {
    // Code được thực thi nếu điều kiện đúng
} else if (điều_kiện_khác) {
    // Code nếu điều kiện thứ nhất sai nhưng điều kiện này đúng
} else {
    // Code được thực thi nếu tất cả điều kiện trên sai
}
```
Ví dụ:
```js
let age = 20;

if (age < 18) {
    console.log("Bạn chưa đủ tuổi.");
} else if (age >= 18 && age < 60) {
    console.log("Bạn là người trưởng thành.");
} else {
    console.log("Bạn là người cao tuổi.");
}
```

---

### 4.1.2. `switch case`
Dùng để kiểm tra nhiều trường hợp của một biến hoặc giá trị.

Cú pháp:
```js
switch (biểu_thức) {
    case giá_trị_1:
        // Code được thực thi nếu biểu_thức === giá_trị_1
        break;
    case giá_trị_2:
        // Code được thực thi nếu biểu_thức === giá_trị_2
        break;
    default:
        // Code thực thi nếu không có case nào khớp
}
```
Ví dụ:
```js
let day = 3;

switch (day) {
    case 1:
        console.log("Hôm nay là Thứ Hai.");
        break;
    case 2:
        console.log("Hôm nay là Thứ Ba.");
        break;
    case 3:
        console.log("Hôm nay là Thứ Tư.");
        break;
    default:
        console.log("Không xác định.");
}
```

🔹 **Lưu ý:** Nếu không có `break`, tất cả các `case` sau nó sẽ được thực thi.

---

### 4.1.3. Toán tử ba ngôi (`?:`)
Cú pháp:
```js
điều_kiện ? giá_trị_nếu_đúng : giá_trị_nếu_sai;
```
Ví dụ:
```js
let age = 18;
let message = age >= 18 ? "Bạn đủ tuổi" : "Bạn chưa đủ tuổi";
console.log(message);
```

---

## 4.2. Cấu trúc vòng lặp (Loops)
Vòng lặp giúp lặp đi lặp lại một đoạn code theo điều kiện nhất định.

### 4.2.1. Vòng lặp `for`
Dùng khi biết trước số lần lặp.

Cú pháp:
```js
for (khởi_tạo; điều_kiện; bước_nhảy) {
    // Code thực thi trong vòng lặp
}
```
Ví dụ:
```js
for (let i = 1; i <= 5; i++) {
    console.log("Lần lặp thứ:", i);
}
```

---

### 4.2.2. Vòng lặp `while`
Dùng khi không biết trước số lần lặp, chỉ dừng khi điều kiện sai.

Cú pháp:
```js
while (điều_kiện) {
    // Code thực thi nếu điều kiện còn đúng
}
```
Ví dụ:
```js
let i = 1;
while (i <= 5) {
    console.log("Lần lặp thứ:", i);
    i++;
}
```

---

### 4.2.3. Vòng lặp `do while`
Dùng khi muốn thực hiện ít nhất một lần trước khi kiểm tra điều kiện.

Cú pháp:
```js
do {
    // Code thực thi
} while (điều_kiện);
```
Ví dụ:
```js
let i = 1;
do {
    console.log("Lần lặp thứ:", i);
    i++;
} while (i <= 5);
```

---

### 4.2.4. `forEach()` (Duyệt mảng)
Dùng để lặp qua từng phần tử của mảng.

Cú pháp:
```js
mảng.forEach(function(phần_tử, chỉ_số, mảng) {
    // Code thực thi
});
```
Ví dụ:
```js
let numbers = [1, 2, 3, 4, 5];
numbers.forEach(function(num, index) {
    console.log(`Phần tử ${index}: ${num}`);
});
```

---

### 4.2.5. `map()` (Tạo mảng mới từ mảng cũ)
Khác với `forEach()`, `map()` trả về một mảng mới.

Ví dụ:
```js
let numbers = [1, 2, 3, 4, 5];
let doubled = numbers.map(num => num * 2);
console.log(doubled); // [2, 4, 6, 8, 10]
```

---

### 4.2.6. `break` và `continue`
- `break`: Dừng vòng lặp ngay lập tức.
- `continue`: Bỏ qua lần lặp hiện tại và chuyển sang lần tiếp theo.

Ví dụ:
```js
for (let i = 1; i <= 10; i++) {
    if (i === 5) break; // Dừng vòng lặp khi i = 5
    console.log(i);
}

for (let i = 1; i <= 10; i++) {
    if (i % 2 === 0) continue; // Bỏ qua số chẵn
    console.log(i);
}
```

---

## 🎯 Bài tập thực hành
1. Viết chương trình yêu cầu người dùng nhập một số và kiểm tra số đó có lớn hơn 10 không.
2. Viết chương trình nhập một số từ người dùng và hiển thị tên ngày trong tuần bằng `switch case`.
3. Viết chương trình in ra tất cả các số từ 1 đến 100, nhưng bỏ qua các số chia hết cho 3 bằng `continue`.
4. Viết chương trình tính tổng của tất cả các số từ 1 đến 50 bằng `for` và `while`.
5. Viết chương trình nhập vào một số nguyên và kiểm tra xem số đó có phải là số nguyên tố hay không.


---

# 6. DOM (Document Object Model) và Sự kiện (Events) trong JavaScript

## 6.1. DOM là gì?
**DOM (Document Object Model)** là mô hình cây thể hiện cấu trúc của một trang HTML. Nó cho phép JavaScript truy cập và thay đổi nội dung, cấu trúc, cũng như kiểu dáng của trang web.  

📌 Mỗi phần tử HTML trên trang web được xem như một **node (nút)** trong cây DOM.

Ví dụ:
```html
<!DOCTYPE html>
<html>
<head>
    <title>DOM Example</title>
</head>
<body>
    <h1 id="title">Xin chào!</h1>
    <p class="description">Đây là đoạn văn bản.</p>
    <button onclick="changeText()">Bấm vào tôi</button>

    <script>
        function changeText() {
            document.getElementById("title").innerText = "Chào mừng bạn đến với DOM!";
        }
    </script>
</body>
</html>
```
➡️ Khi người dùng bấm vào nút, tiêu đề sẽ thay đổi nội dung.

---

## 6.2. Các phương thức thao tác với DOM
### 6.2.1. Chọn phần tử HTML
Để thao tác với các phần tử trên trang web, ta có thể sử dụng một trong các phương thức sau:

| Phương thức | Mô tả | Ví dụ |
|------------|-------|-------|
| `document.getElementById(id)` | Chọn phần tử theo `id` | `document.getElementById("title")` |
| `document.getElementsByClassName(class)` | Chọn tất cả phần tử có class | `document.getElementsByClassName("description")` |
| `document.getElementsByTagName(tag)` | Chọn tất cả phần tử có tag HTML | `document.getElementsByTagName("p")` |
| `document.querySelector(selector)` | Chọn phần tử đầu tiên theo CSS selector | `document.querySelector(".description")` |
| `document.querySelectorAll(selector)` | Chọn tất cả phần tử theo CSS selector | `document.querySelectorAll("p")` |

Ví dụ:
```js
let title = document.getElementById("title");
let paragraphs = document.getElementsByTagName("p");
console.log(title.innerText); // In ra nội dung của tiêu đề
console.log(paragraphs.length); // In ra số lượng thẻ <p>
```

---

### 6.2.2. Thay đổi nội dung HTML
| Phương thức | Mô tả | Ví dụ |
|------------|-------|-------|
| `.innerHTML` | Thay đổi nội dung HTML bên trong phần tử | `element.innerHTML = "<b>Hello</b>";` |
| `.innerText` | Thay đổi nội dung dạng văn bản (không chứa HTML) | `element.innerText = "Hello";` |
| `.textContent` | Giống `innerText`, nhưng hiển thị cả nội dung ẩn | `element.textContent = "Hello";` |

Ví dụ:
```js
document.getElementById("title").innerText = "DOM rất thú vị!";
```

---

### 6.2.3. Thay đổi CSS bằng JavaScript
Có thể thay đổi CSS của phần tử thông qua `.style`:
```js
document.getElementById("title").style.color = "red";
document.getElementById("title").style.fontSize = "24px";
```
Hoặc thêm/lớp CSS bằng `classList`:
```js
document.getElementById("title").classList.add("highlight");
document.getElementById("title").classList.remove("highlight");
document.getElementById("title").classList.toggle("highlight"); // Thêm nếu chưa có, xóa nếu đã có
```

---

## 6.3. Xử lý sự kiện (Events)
### 6.3.1. Các loại sự kiện phổ biến
| Sự kiện | Mô tả |
|---------|------|
| `click` | Khi người dùng nhấp chuột vào phần tử |
| `mouseover` | Khi di chuột vào phần tử |
| `mouseout` | Khi di chuột ra khỏi phần tử |
| `keydown` | Khi nhấn phím bất kỳ |
| `keyup` | Khi thả phím ra |
| `change` | Khi giá trị của input thay đổi |
| `submit` | Khi form được gửi đi |

---

### 6.3.2. Cách gán sự kiện trong JavaScript
Có 3 cách để gán sự kiện:

#### Cách 1: Trực tiếp trong HTML
```html
<button onclick="sayHello()">Bấm vào tôi</button>
<script>
    function sayHello() {
        alert("Xin chào!");
    }
</script>
```

#### Cách 2: Gán trong JavaScript
```html
<button id="myButton">Bấm vào tôi</button>
<script>
    document.getElementById("myButton").onclick = function() {
        alert("Xin chào!");
    };
</script>
```

#### Cách 3: Sử dụng `addEventListener`
```html
<button id="myButton">Bấm vào tôi</button>
<script>
    document.getElementById("myButton").addEventListener("click", function() {
        alert("Xin chào!");
    });
</script>
```
🚀 **Ưu điểm của `addEventListener`**: Cho phép gán nhiều sự kiện vào cùng một phần tử.

---

### 6.3.3. Lấy thông tin từ sự kiện
Khi một sự kiện xảy ra, ta có thể lấy thông tin về sự kiện đó bằng đối tượng `event`:
```js
document.getElementById("myButton").addEventListener("click", function(event) {
    console.log("Tọa độ X:", event.clientX);
    console.log("Tọa độ Y:", event.clientY);
});
```

---

### 6.3.4. Ngăn chặn hành vi mặc định
Một số sự kiện có hành vi mặc định (ví dụ: `submit` trong form sẽ tải lại trang). Để ngăn chặn điều đó, ta dùng `preventDefault()`:
```html
<form id="myForm">
    <input type="text" id="name">
    <button type="submit">Gửi</button>
</form>
<script>
    document.getElementById("myForm").addEventListener("submit", function(event) {
        event.preventDefault();
        alert("Form đã được xử lý mà không tải lại trang.");
    });
</script>
```

---

## 🎯 Bài tập thực hành
1. **Viết một trang web đơn giản** với một tiêu đề `<h1>` và một nút `<button>`. Khi bấm nút, tiêu đề sẽ thay đổi nội dung.
2. **Tạo một ô nhập liệu** và hiển thị nội dung ô nhập trong một thẻ `<p>` khi người dùng nhập vào.
3. **Tạo một form** có ô nhập tên và nút gửi. Khi nhấn gửi, hiển thị tên trong một thẻ `<h2>` mà không tải lại trang.
4. **Viết chương trình đổi màu nền** trang web mỗi lần nhấn nút.
5. **Tạo một danh sách động**: Khi nhập vào ô input và nhấn "Thêm", mục nhập sẽ được thêm vào danh sách `<ul>`.

---

## 7. Hàm trong JavaScript
Hàm giúp tái sử dụng mã nguồn.
### 1. Định nghĩa hàm
Có thể khai báo bằng `function` hoặc `arrow function` (ES6).
```js
function greet(name) {
    return "Hello " + name;
}
console.log(greet("Alice"));

const greetArrow = (name) => "Hello " + name;
console.log(greetArrow("Bob"));
```
### 2. Hàm có tham số mặc định
```js
function multiply(a, b = 1) {
    return a * b;
}
console.log(multiply(5)); // 5
console.log(multiply(5, 2)); // 10
```
### 3. Hàm ẩn danh
```js
let add = function(a, b) {
    return a + b;
};
console.log(add(3, 4));
```
### Bài tập thực hành
1. Viết một hàm nhận vào một số và trả về bình phương của số đó.
2. Viết một hàm kiểm tra xem một chuỗi có chứa chữ cái 'a' không.

---

##8. Lập trình hướng đối tượng
### 1. Giới Thiệu OOP trong JavaScript
Lập trình hướng đối tượng (OOP) là một mô hình lập trình dựa trên khái niệm "đối tượng", giúp tổ chức mã nguồn dễ quản lý hơn. JavaScript hỗ trợ OOP thông qua cả prototype-based và class-based.

### 2. Các Khái Niệm Cơ Bản
#### 2.1. Object (Đối Tượng)
Một đối tượng trong JavaScript là một tập hợp các cặp key-value (thuộc tính và phương thức).
```js
let person = {
    name: "John",
    age: 30,
    greet: function() {
        console.log("Hello, my name is " + this.name);
    }
};
person.greet();
```

#### 2.2. Constructor Function (Hàm Tạo)
Hàm tạo dùng để tạo nhiều đối tượng có cùng cấu trúc.
```js
function Person(name, age) {
    this.name = name;
    this.age = age;
    this.greet = function() {
        console.log("Hello, my name is " + this.name);
    };
}
let person1 = new Person("Alice", 25);
let person2 = new Person("Bob", 28);
person1.greet();
person2.greet();
```

#### 2.3. Prototype
Prototype giúp chia sẻ phương thức giữa các đối tượng để tối ưu bộ nhớ.
```js
function Car(brand, model) {
    this.brand = brand;
    this.model = model;
}
Car.prototype.getDetails = function() {
    return `${this.brand} - ${this.model}`;
};
let car1 = new Car("Toyota", "Camry");
console.log(car1.getDetails());
```

#### 2.4. Class (Lớp) - ES6
ES6 giới thiệu cú pháp `class`, giúp viết OOP trong JavaScript dễ đọc hơn.
```js
class Animal {
    constructor(name, sound) {
        this.name = name;
        this.sound = sound;
    }
    makeSound() {
        console.log(`${this.name} says ${this.sound}`);
    }
}
let dog = new Animal("Dog", "Woof");
dog.makeSound();
```

### 3. Các Nguyên Tắc OOP trong JavaScript
#### 3.1. Encapsulation (Đóng gói)
Giữ dữ liệu an toàn bằng cách sử dụng `private` fields (`#`).
```js
class BankAccount {
    #balance;
    constructor(owner, balance) {
        this.owner = owner;
        this.#balance = balance;
    }
    getBalance() {
        return this.#balance;
    }
}
let account = new BankAccount("John", 1000);
console.log(account.getBalance()); // 1000
```

#### 3.2. Inheritance (Kế thừa)
Cho phép một class con kế thừa từ class cha.
```js
class Animal {
    constructor(name) {
        this.name = name;
    }
    speak() {
        console.log(`${this.name} makes a noise.`);
    }
}
class Dog extends Animal {
    speak() {
        console.log(`${this.name} barks.`);
    }
}
let myDog = new Dog("Rex");
myDog.speak();
```

#### 3.3. Polymorphism (Đa hình)
Ghi đè phương thức của class cha trong class con.
```js
class Shape {
    getArea() {
        return 0;
    }
}
class Circle extends Shape {
    constructor(radius) {
        super();
        this.radius = radius;
    }
    getArea() {
        return Math.PI * this.radius * this.radius;
    }
}
let circle = new Circle(5);
console.log(circle.getArea());
```

#### 3.4. Abstraction (Trừu tượng hóa)
Ẩn chi tiết triển khai và chỉ hiển thị những gì cần thiết.
```js
class Vehicle {
    constructor(type) {
        this.type = type;
        if (this.constructor === Vehicle) {
            throw new Error("Cannot instantiate abstract class");
        }
    }
    move() {
        throw new Error("Method 'move()' must be implemented.");
    }
}
class Car extends Vehicle {
    move() {
        console.log("Car is moving");
    }
}
let myCar = new Car("Sedan");
myCar.move();
```

### 4. Bài Tập Thực Hành
#### Bài 1: Tạo Class `Student`
Viết class `Student` với thuộc tính `name`, `age` và phương thức `introduce()` in ra tên và tuổi.
```js
class Student {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
    introduce() {
        console.log(`My name is ${this.name} and I am ${this.age} years old.`);
    }
}
let student = new Student("Alice", 22);
student.introduce();
```

#### Bài 2: Kế thừa class `Person`
Viết class `Teacher` kế thừa từ `Person`, thêm thuộc tính `subject` và phương thức `teach()`.
```js
class Person {
    constructor(name) {
        this.name = name;
    }
}
class Teacher extends Person {
    constructor(name, subject) {
        super(name);
        this.subject = subject;
    }
    teach() {
        console.log(`${this.name} teaches ${this.subject}`);
    }
}
let teacher = new Teacher("Mr. Smith", "Math");
teacher.teach();
```

#### Bài 3: Tạo Class `BankAccount`
Viết class `BankAccount` với private property `balance`, phương thức `deposit(amount)` và `withdraw(amount)`.
```js
class BankAccount {
    #balance;
    constructor(owner, balance) {
        this.owner = owner;
        this.#balance = balance;
    }
    deposit(amount) {
        this.#balance += amount;
        console.log(`Deposited ${amount}, new balance: ${this.#balance}`);
    }
    withdraw(amount) {
        if (amount > this.#balance) {
            console.log("Insufficient funds");
        } else {
            this.#balance -= amount;
            console.log(`Withdrawn ${amount}, new balance: ${this.#balance}`);
        }
    }
}
let account = new BankAccount("Alice", 500);
account.deposit(200);
account.withdraw(100);
```

## 9. Bài tập tổng hợp
Viết một chương trình quản lý danh sách sinh viên với các chức năng sau:
1. Thêm sinh viên (Tên, Tuổi, Lớp).
2. Hiển thị danh sách sinh viên.
3. Tìm kiếm sinh viên theo tên.
4. Xóa sinh viên khỏi danh sách.

---
