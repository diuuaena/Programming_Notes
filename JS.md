# **Learning JS**

## 🔷 Mục lục
- **[Tổng quan về Javascript](#-tổng-quan-về-javascript)**
- **[Kiểu dữ liệu trong Javascript](#-kiểu-dữ-liệu-trong-javascript)**
- **[Biến, build-in, toán tử](#-biến-build-in-toán-tử)**
- **[Vòng lặp trong Javascript](#-vòng-lặp-trong-javascript)


## 🔷 Tổng quan về Javascript
  - Javascript là một ngôn ngữ lập trình kiểu động bởi vì nó không yêu cầu khai báo kiểu dữ liệu cụ thể cho biến mà sẽ cho phép người dùng thay đổi kiểu dữ liệu trong quá trình thực thi. Nó được phát triển bởi Brendan Eich tại Netscape vào năm 1995. Tên ban đầu của nó là Mocha sau đó được đổi thành LiveScript và cuối cùng là JavaScript.
  - Một số ưu điểm của Javascript:

    - JavaScript là ngôn ngữ thông dịch nên không cần compiler
    - JavaScript cho phép tạo ra các trang web tương tác thông qua các thao tác DOM, quản lý sự kiện, và AJAX, từ đó cải thiện trải nghiệm người dùng.
    - Với sự ra đời của Node.js, JavaScript không chỉ giới hạn trên trình duyệt mà còn có thể chạy các ứng dụng server-side, giúp phát triển full-stack bằng một ngôn ngữ duy nhất.
    - JavaScript có một cộng đồng lớn mạnh và cung cấp nhiều thư viện, framework hỗ trợ như React, Angular, và Vue.js, màng lưới mạnh mẽ cho phát triển ứng dụng.

  - Nhược điểm của Javascript:

    - Javascrip thường chậm hơn các ngôn ngữ lập trình khác như C++ hoặc Java do bản chất thông dịch của nó, nghĩa là mã được thực thi theo từng dòng thay vì được biên dịch thành mã máy trước khi thực thi.
    - Có thể gây ra rủi ro bảo mất nếu không được triển khai đúng.
    - Việc gỡ lỗi JavaScript có thể phức tạp hơn do tính năng không đồng bộ và xử lý sự kiện.



## 🔷 Kiểu dữ liệu trong Javascript

### Primitive Data: là các kiểu dữ liệu cơ bản nhất trong javascript. Chúng được lưu trữ trong ngăn xếp (stack) và không thể thay đổi giá trị hoặc thuộc tính, mặc dù có thể thay đổi biến tham chiếu đến giá trị đó. Có các kiểu dữ liệu nguyên thuỷ như sau:

  - Number: Nó không phân biệt kiểu nguyên hay không nguyên, dùng được cho cả integer và float
    ```js
    let age = 25;  
    let price = 99.99;  
    ```

  - String: là dạng dữ liệu kiểu chuỗi, gồm một hoặc nhiều ký tự.
    ```js
    let name = "John Doe";  
    let greeting = 'Hello, World!';  
    ```

  - Boolean: Chỉ có 2 value là true. Có các giá trị false, 0, NaN, '', null, undefined khi chuyển qua boolean sẽ là false và được gọi là Falsy. Ngoài những giá trị trên thì tất cả các giá trị khác khi qua boolean sẽ là true và được gọi là Truthy.
    ```js
    let isAvailable = true;  
    let isComplete = false;  
    ```

  - Undefined: Chỉ mới khai báo mà chưa gán giá trị.
    ```js
    let x;  
    console.log(x); // undefined  
    ```

  - Null: Ý nghĩa của nó là không có ý nghĩa gì, giá trị rỗng hoặc không xác định.
    ```js
    let emptyValue = null;  
    console.log(emptyValue); // null
    ```

  - Symbol: Được sử dụng để tạo ra các giá trị duy nhất và bất biến. Đây là kiểu dữ liệu mới được giới thiệu trong ES6.
    ```js
    let uniqueKey = Symbol('key');  
    ```

### Complex Data: kiểu dữ liệu này có thể lưu trữ và quản lí nhiều giá trị và thuộc tính

  - Object: là tập hợp của các **key** và **value** với key gọi là thuộc tính còn value là giá trị tương ứng của thuộc tính. Các cặp key và value ngăn cách với nhau bằng dấu ```,```. Có thể sử dụng ```. hoặc []``` để tuy cập vào thuộc tính của object. Toán tử ```.``` chỉ dùng được trong trường hợp tên thuộc tính không có kí tự đặc biệt (ngoại trừ kí tự _ và $). Khi key chứa dấu cách, hoặc các ký tự đặc biệt khác thì bắt buộc phải sử dụng toán tử ```[]```.
    ```js
    let person = {  
      firstName: "John",  
      lastName: "Doe",  
      age: 30,  
      greet: function() {  
        console.log("Hello!");  
      }  
    };
    ```
  - Array: là một đối tượng có thứ tự (ordered list) lưu trữ một tập hợp dữ liệu, được quản lý bởi chỉ số (index), bắt đầu từ 0.
    ```js
    let fruits = ["apple", "banana", "cherry"];
    ```

  - Function: cũng được xem là một object trong JavaScript, có thể được gán cho một biến, truyền vào hàm khác như tham số hoặc trả về từ một hàm
    ```js
    function add(a, b) {  
      return a + b;  
    }  
      
    let sum = add(5, 10);
    ```

## 🔷 Biến, build-in, toán tử

- Biến: là các đại diện cho giá trị mà có thể thay đổi trong quá trình thực thi chương trình. Bạn có thể sử dụng biến để lưu trữ dữ liệu, như số, chuỗi, đối tượng, mảng, và nhiều loại khác. JS cung cấp 3 cách khai báo biến: var, let const

  - var: Biến khai báo với var có phạm vi trong hàm (function scope) hoặc toàn cục (global scope) nếu không nằm trong function.

  - let: Biến khai báo với let có phạm vi khối (block scope), nghĩa là nó chỉ tồn tại trong khối mã nơi nó được khai báo.

  - const: Tương tự như let, const cũng có phạm vi khối. Được sử dụng để khai báo một hằng số. Không thể gán lại giá trị cho biến được khai báo bởi const

- Build-in: là những hàm đã được xây dựng sẵn. Có thể lấy ra để sử dụng mà không cần tự viết lại. Ví dụ: alert, console, confirm,...

- Toán tử: 

  - Toán tử số học (Arithmetic): được sử dụng để thực hiện các phép toán. Một vài toán tử số học thường hay sử dụng:

    - Toán tử cộng (+): Dùng để cộng 2 số lại với nhau 
      ```js
      let a = 5;  
      let b = 10;  
      let sum = a + b; // sum = 15  
      console.log(sum); // 15  
      ```

    - Toán tử trừ (-): Dùng để trừ 1 số cho 1 số khác
      ```js
      let a = 10;  
      let b = 4;  
      let difference  = a - b; // difference  = 6
      console.log(difference ); // 6 
      ```

    - Toán tử nhân (*): Dùng để nhân 2 số với nhau
      ```js
      let a = 7;  
      let b = 3;  
      let product = a * b; // product = 21  
      console.log(product); // 21 
      ```

    - Toán tử chia (/): Dùng để chia 1 số cho 1 số khác
      ```js
      let a = 20;  
      let b = 4;  
      let quotient = a / b; // quotient = 5  
      console.log(quotient); // 5  
      ```

    - Toán tử chia lấy dư (&): Dùng để chia lấy phần dư của phép chia
      ```js
      let a = 10;  
      let b = 3;  
      let remainder = a % b; // remainder = 1  
      console.log(remainder); // 1  
      ```

    - Toán tử luỹ thừa (**): Dùng để tính luỹ thừa của 1 số
      ```js
      let a = 2;  
      let b = 3;  
      let power = a ** b; // power = 8 (2^3)  
      console.log(power); // 8   
      ```

    - Toán tử gia tăng (++): Dùng để tăng giá trị lên 1. Nếu là tiền tố (++a) thì sẽ tăng giá trị lên 1 và trả về giá trị sau khi tăng. Nếu là hậu tố (a++) thì sẽ tăng giá trị lên 1 và trả về giá trị trước khi tăng
      ```js
      let a = 5;  
      console.log(++a); // 6 (gia tăng trước)  
      console.log(a++); // 6 (gia tăng sau, a trở thành 7 sau đó)  
      console.log(a);   // 7  
      ```

    - Toán tử giảm (++): Dùng để giảm giá trị xuống 1. Nếu là tiền tố (--a) thì sẽ giảm giá trị xuống 1 và trả về giá trị sau khi giảm. Nếu là hậu tố (a--) thì sẽ giảm giá trị xuống 1 và trả về giá trị trước khi giảm
      ```js
      let a = 5;  
      console.log(--a); // 4 (giảm trước)  
      console.log(a--); // 4 (giảm sau, a trở thành 3 sau đó)  
      console.log(a);   // 3  
      ```

  - Toán tử gán (Assignment):  sử dụng để gán giá trị cho biến. Toán tử này cho phép bạn thiết lập hoặc cập nhật giá trị của biến một cách đơn giản và dễ dàng. Một số toán tử thường được sử dụng:

    - Toán tử gán =: dùng để gán giá trị cho biến
      ```js
      let a = 5; // Gán giá trị 5 cho biến a  
      let b = 10; // Gán giá trị 10 cho biến b  
        
      console.log(a); // 5  
      console.log(b); // 10  
      ```

    - Toán tử gán cộng (+=): cộng giá trị bên phải với gái trị biến bên trái rồi sau đó gán giá trị đó cho biến bên trái.
      ```js
      let a = 10;  
      a += 5; // Tương đương với a = a + 5  
      console.log(a); // 15  
      ```
    - Toán tử gán trừ (-=): giá trị của biến bên trái trừ đi giá trị bên phải rồi gán giá trị cho biến bên trái
      ```js
      let a = 10;  
      a -= 5; // Tương đương với a = a - 5  
      console.log(a); // 5  
      ```
    - Còn một vài toán tử gán khác như *=, /=, %=, **= cũng tương tự như trên.

  - Toán tử so sánh (Comparision): được sử dụng để so sánh hai giá trị và trả về một giá trị boolean dựa trên kết quả so sánh. Khi so sánh các toán hạng khác kiểu dữ liệu, js sẽ chuyển đổi các toán hạng sang dạng số để so sánh. Khi trong biểu thức có nhiều toán tử so sánh thì thứ tự sẽ được thực hiện từ trái sang phải. Các toán tử so sánh thường được sử dụng là `>, <, >=, <=, ==, !=, ===, !===`. Có thể tham khảo thêm [tại đây.](https://kungfutech.edu.vn/bai-viet/javascript/so-sanh-trong-javascript)

  - Toán tử logic (Logical): là toán tử kết nối hai hay nhiều biểu thức, dùng để kiểm tra mối quan hệ logic giữa các biểu thức. Kết quả cuối cùng phụ thuộc vào giá trị của từng biểu thức và loại toán tử logic.

    - Toán tử OR (||): sẽ tìm và trả về giá trị truthy đầu tiên. Nếu không có giá trị truthy nào thì kết quả sẽ là giá trị của toán hạng cuối cùng. Thứ tự thực hiện sẽ từ trái sang phải.
      ```js
      console.log(1 || 0); // 1 (giá trị truthy đầu tiên là 1)
      console.log(null || 2); // 2 (giá trị truthy đầu tiên là 2)
      console.log("" || undefined || 0 || 10); // 10 (giá trị truthy đầu tiên là 10)
      console.log(null || 100 || 5 || undefined); // 100 (giá trị truthy đầu tiên là 100)
      console.log("" || 0 || null); // null (không có giá trị truthy, trả về giá trị cuối cùng)
      ```

    - Toán tử AND (&&): tìm và trả về giá trị falsy đầu tiên. Nếu không có giá trị falsy nào thì kết quả sẽ là giá trị của toán hạng cuối cùng. Thứ tự thực hiện sẽ từ trái sang phải.
      ```js
      console.log(1 && 0); // 0 (giá trị falsy đầu tiên là 0)
      console.log(null && 2); // null (giá trị falsy đầu tiên là null)
      console.log(10 && "" && undefined && 0); // "" (giá trị falsy đầu tiên là "")
      console.log("n" && undefined && 10); // undefined (giá trị falsy đầu tiên là undefined)
      console.log(10 && "a"); // "a" (không có giá trị falsy, trả về giá trị cuối cùng)
      ```

    - Toán tử NOT (!): trả về giá trị true nếu toán hạng là false và trả về false nếu toán hạng là true. Nếu sử dụng hai toán tử !! thì nó sẽ có tác dụng convert kiểu dữ liệu về boolean.
      ```js
      console.log(!!"hello"); // true
      console.log(!!null); // false
      ```

## 🔷 Vòng lặp trong Javascript

  - Vòng lặp for:  
