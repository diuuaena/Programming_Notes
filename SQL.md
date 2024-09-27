# **The Complete SQL Bootcamp: Go from Zero to Hero**

## 🔷 Mục lục
- **[Tổng quan SQL](#-tổng-quan-sql)**
- **[Các câu lệnh cơ bản](#-các-câu-lệnh-cơ-bản)**

## 🔷 Tổng quan

### Database

- Database (cơ sở dữ liệu) là một tập hợp các dữ liệu cấu trúc được tổ chức và lưu trữ theo một cách cụ thể để có thể truy cập, cập nhật và quản lý một cách hiệu quả. Database được sử dụng để lưu trữ thông tin, dữ liệu và thông tin quan trọng của một tổ chức hoặc hệ thống.

### SQL

- SQL (Structured Query Language) là ngôn ngữ lập trình dùng để truy vấn, cập nhật, và quản lý cơ sở dữ liệu quan hệ. SQL được sử dụng rộng rãi trong việc tương tác với cơ sở dữ liệu, từ việc truy vấn dữ liệu đến thao tác thêm, sửa, xóa dữ liệu. SQL chủ yếu được sử dụng trong cơ sở dữ liệu quan hệ (RDBMS - Relational Database Management System) như MySQL, PostgreSQL, SQL Server, Oracle, SQLite, và nhiều hệ thống quản lý cơ sở dữ liệu khác.

## 🔷 Các câu lệnh cơ bản

- SELECT: là câu lệnh phổ biến nhất được sử dụng trong SQl, cho phép truy xuất thông tin một hoặc nhiều table trong database, có thể kết hợp với các lệnh khác để thực hiện các câu truy vấn phức tạp hơn.

  - Syntax:

    ```sql
    SELECT column_name1, column_name2,... FROM table_name;
    ```

    hoặc nếu muốn tất cả column trong table có thể sử dụng * để hiển thị tất cả

    ```sql
    SELECT * FROM table_name;
    ```

  - Example:

    ```sql
    SELECT first_name, last_name FROM actor;
    ```

- SELECT DISTINCT: là một câu lệnh trong SQL được sử dụng để truy xuất các bản ghi mà không bị trùng lặp từ một bảng hoặc một tập hợp bảng. Câu lệnh này giúp loại bỏ các giá trị trùng lặp trong kết quả truy vấn, chỉ trả về các giá trị duy nhất.
  - Syntax:

    ```sql
    SELECT DISTINCT column_name1, column_name2,... FROM table_name;
    ```

  - Example:

    ```sql
    SELECT DISTINCT release_year, rental_rate From film;
    ```

- COUNT: sử dụng để đếm số lượng bản ghi trong một tập hợp hoặc số lượng giá trị không NULL trong một cột cụ thể. Đây là một trong những hàm tổng hợp (aggregate function) phổ biến và rất hữu ích khi cần phân tích dữ liệu.

  - Syntax:
    
    ```sql
    SELECT COUNT(column_name) FROM table_name
    WHERE condition;
    ```

  - Example:

    ```sql
    SELECT COUNT(ProductName)
    FROM Products;
    ```

    ```sql
    SELECT COUNT(ProductID)
    FROM Products
    WHERE Price > 20;
    ```

- WHERE: được sử dụng để chỉ định điều kiện cho việc lọc các bản ghi trong câu lệnh truy vấn, thường được sử dụng trong câu lệnh SELECT, UPDATE, và DELETE. Thường sử dụng toán tử để xây dựng các điều kiện.
  - Các toán tử thường được sử dụng:

    ```js
    =:       Bằng
    <>, !=:  Khác
    >:       Lớn hơn
    <:       Nhỏ hơn
    >=:      Lớn hơn hoặc bằng
    <=:      Nhỏ hơn hoặc bằng
    AND:     Bất kỳ điều kiện nào đều phải đúng.
    OR:      Chỉ cần một trong các điều kiện đúng.
    NOT:     Đảo ngược giá trị của điều kiện.
    ```

  - Syntax:

    ```sql
    SELECT column1, column2, ...
    FROM table_name
    WHERE condition;
    ```
    Where không chỉ được sử dụng trong các câu lệnh SELECT mà còn được sử dụng trong các câu lệnh UPDATE, DELETE,...

  - Example:

    ```sql
    SELECT Count(*) From film
    WHERE rating = 'R' OR rating = 'PG-13'
    ```

- ORDER BY: được sử dụng để sắp xếp kết quả trả về từ một câu lệnh truy vấn. Có thể sắp xếp dữ liệu theo một hoặc nhiều column, và có thể sắp xếp theo thứ tự tăng dần (ASC) hoặc giảm dần (DESC). Nếu không chỉ định sắp xếp theo tăng dần hoặc giảm dần thì mặc định sẽ là tăng dần ASC.

  - Syntax:

    ```sql
    SELECT column1, column2, ...
    FROM table_name
    ORDER BY column1, column2, ... ASC|DESC;
    ```

  - Example:

    ```sql
    SELECT * FROM Customers
    ORDER BY Country ASC, CustomerName DESC;
    ```

- LIMIT: được sử dụng để giới hạn số lượng bản ghi được trả về trong kết quả của một câu lệnh truy vấn. Có thể sử dụng LIMIT kết hợp OFFSET để kiểm soát vị trí bắt đầu của bản ghi.

  - Syntax:

    ```sql
    SELECT column1, column2, ... FROM table_name  
    LIMIT number; 
    ```

  - Example:

    ```sql
    SELECT * FROM employees  
    LIMIT 2 OFFSET 2; 
    ``` 

- BETWEEN: được sử dụng để lọc các bản ghi trong một phạm vi cụ thể. Nó xác định một khoảng giá trị mà một ccolumn có thể rơi vào. Cách sử dụng thường thấy của BETWEEN là trong các câu lệnh điều kiện WHERE.

  - Syntax:

    ```sql
    SELECT column1, column2, ... FROM table_name
    WHERE column_name BETWEEN value1 AND value2;
    ```

  - Example:

    ```sql
    SELECT * FROM employees  
    WHERE name BETWEEN 'A' AND 'C'; 
    ```

- IN: được sử dụng để chỉ định một danh sách các giá trị muốn kiểm tra trong câu lệnh truy vấn. Nó cho phép kiểm tra một column có giá trị nằm trong một tập hợp cụ thể, giúp làm cho câu lệnh có cấu trúc hơn và dễ đọc hơn so với việc sử dụng nhiều điều kiện OR.

  - Syntax:

    ```sql
    SELECT column1, column2, ... FROM table_name  
    WHERE column_name IN (value1, value2, value3, ...);  
    ```

  - Example:

    ```sql
    SELECT * FROM employees  
    WHERE department IN ('IT', 'HR');  
    ```

- LIKE và ILKE: được sử dụng để tìm kiếm một mẫu trong các cột thuộc kiểu dữ liệu string. LIKE cso phân biệt chữ hoa chữ thường còn ILIKE thì không

  - %: Đại diện cho bất kỳ chuỗi nào, bao gồm cả chuỗi rỗng. Ví dụ: LIKE 'A%' sẽ khớp với tất cả các chuỗi bắt đầu bằng "A".

  - _: Đại diện cho một ký tự đơn. Ví dụ: LIKE 'A_d' sẽ khớp với các chuỗi như "A1d", "Axd", "Acd", nhưng không khớp với "Abcd" hay "Ad"

  - Syntax: 

    ```sql
    SELECT column1, column2, ...  
    FROM table_name  
    WHERE column_name LIKE hoặc ILIKE pattern;  
    ```

  - Example:

    ```sql
    SELECT * FROM employees  
    WHERE name LIKE 'A%';
    ```