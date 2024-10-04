# **The Complete SQL Bootcamp: Go from Zero to Hero**

## 🔷 Mục lục
- **[Tổng quan SQL](#-tổng-quan-sql)**
- **[Các câu lệnh cơ bản](#-các-câu-lệnh-cơ-bản)**
- **[GROUP BY](#-group-by)**
- **[CREATING DATABASE AND TABLE](#-creating-database-and-table)**

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

- SUB QUERY: là một truy vấn được lồng bên trong một truy vấn khác. Subquery có thể được sử dụng trong nhiều phần của câu lệnh SQL, bao gồm trong phần SELECT, FROM, hoặc WHERE. Subquery có thể trả về một hoặc nhiều giá trị.

  - Syntax:

    ```sql
    SELECT column1, column2, ...  
    FROM table_name  
    WHERE column_name IN (SELECT column_name FROM table_name WHERE condition);
    ```

  - Example

    ```sql
    SELECT employee_id, employee_name  
    FROM employees  
    WHERE department_id IN (SELECT department_id FROM departments WHERE department_name = 'Sales'); 
    ```


## 🔷 GROUP BY

- Aggregation Functions: là các hàm được sử dụng để thực hiện các phép toán tính toán trên tập dữ liệu và trả về một giá trị duy nhất. Chúng thường được sử dụng cùng với câu lệnh GROUP BY để tổng hợp dữ liệu từ nhiều hàng thành một hàng duy nhất. Dưới đây là một số hàm phổ biến.

  - AVG(): sử dụng để tính giá trị trung bình cho một column
    
    - Syntax: 

      ```sql
      SELECT AVG(column_name) FROM table_name;  
      ```

    - Example: 
      
      ```sql
      SELECT AVG(salary) FROM employees;  
      ```

  - AVG(): được sử dụng để đếm số lượng hàng trong một tập dữ liệu
    
    - Syntax: 

      ```sql
      SELECT COUNT(column_name) FROM table_name;  
      ```

    - Example: 
      
      ```sql
      SELECT COUNT(*) FROM employees;  
      ```

  - SUM(): được sử dụng để tính tổng giá trị của một cột số. Nó chỉ hoạt động với các cột có kiểu dữ liệu số
    
    - Syntax: 

      ```sql
      SELECT SUM(column_name) FROM table_name;  
      ```

    - Example: 
      
      ```sql
      SELECT SUM(salary) FROM employees;  
      ```

  - MAX(): được sử dụng để tìm giá trị lớn nhất trong một cột. Nó có thể được sử dụng với các kiểu dữ liệu khác nhau.
    
    - Syntax: 

      ```sql
      SELECT MAX(column_name) FROM table_name;  
      ```

    - Example: 
      
      ```sql
      SELECT MAX(salary) FROM employees;  
      ```

  - MIN(): được sử dụng để tìm giá trị nhỏ nhất trong một cột. Nó cũng có thể được sử dụng với nhiều kiểu dữ liệu.
    
    - Syntax: 

      ```sql
      SELECT MIN(column_name) FROM table_name;  
      ```

    - Example: 
      
      ```sql
      SELECT MIN(salary) FROM employees;  
      ```

- GROUP BY: được sử dụng để nhóm các dữ liệu giống nhau dựa trên một hoặc nhiều cột

  - Syntax: 

      ```sql
      SELECT column1, column2, aggregate_function(column3)  
      FROM table_name  
      WHERE condition  
      GROUP BY column1, column2;  
      ```

  - Example: 
      
    ```sql
    SELECT department, AVG(salary) AS average_salary  
    FROM employees  
    GROUP BY department;  
    ```

- HAVING: được sử dụng để lọc các kết quả từ một câu lệnh GROUP BY. Khác với WHERE, mà áp dụng cho các hàng trước khi chúng được nhóm, HAVING được áp dụng cho các nhóm đã được tạo ra.

  - Syntax:

    ```sql
    SELECT column1, column2
    FROM table1, table2
    WHERE [ conditions ]
    GROUP BY column1, column2
    HAVING [ conditions ]
    ORDER BY column1, column2
    ```

  - Example:

    ```sql
    SELECT department, COUNT(*) AS employee_count  
    FROM employees  
    GROUP BY department  
    HAVING COUNT(*) > 10;  
    ```

## 🔷 JOIN

- AS: được sử dụng để đặt alias (biệt danh) cho các column hoặc table trong các truy vấn. Sử dụng alias giúp mã SQL trở nên dễ đọc hơn và cho phép bạn gán tên dễ hiểu cho dữ liệu mà bạn đang truy vấn, đặc biệt khi làm việc với các hàm tổng hợp hoặc các bảng phức tạp.

  - Syntax:

    ```sql
    SELECT column_name AS alias_name  
    FROM table_name;
    ```

  - Example:

    ```sql
    SELECT first_name AS FirstName, last_name AS LastName, salary  
    FROM employees;
    ```

- INNER: được sử dụng để kết hợp các hàng từ hai hoặc nhiều bảng dựa trên mối quan hệ giữa chúng. JOIN cho phép bạn truy xuất dữ liệu từ nhiều bảng theo cách hợp lý và hiệu quả. Có nhiều loại JOIN, mỗi loại phục vụ cho mục đích khác nhau.

  - INNER JOIN: chỉ trả về các hàng mà có dữ liệu khớp nhau trong cả hai bảng.

    - Syntax:

      ```sql
      SELECT table1.columns1, table2.columns2,...
      FROM table1  
      INNER JOIN table2  
      ON table1.ccolumn = table2.column; 
      ```

  - FULL JOIN (FULL OUTER JOIN): trả về tất cả các hàng từ cả hai bảng, và sẽ khớp các hàng mà có dữ liệu trùng lặp, nếu không có khớp, nó sẽ trả về NULL.

    - Syntax:

      ```sql
      SELECT table1.columns1, table2.columns2,...
      FROM table1  
      FULL OUTER JOIN table2  
      ON table1.column = table2.column; 
      ```

  - LEFT JOIN: trả về tất cả các hàng từ bảng bên trái ngay cả khi không có kết quả nào khớp với bảng bên phải. Nếu không có khớp, nó sẽ trả về NULL từ bảng bên phải.

    - Syntax:

      ```sql
      SELECT table1.columns1, table2.columns2,...
      FROM table1  
      LEFT JOIN table2  
      ON table1.column = table2.column; 
      ```

  - RIGHT JOIN: trả về tất cả các hàng từ bảng bên phải ngay cả khi không có kết quả nào khớp với bảng bên trái. Nếu không có khớp, nó sẽ trả về NULL từ bảng bên trái.

    - Syntax:

      ```sql
      SELECT table1.columns1, table2.columns2,...
      FROM table1  
      RIGHT JOIN table2  
      ON table1.column = table2.column; 
      ```

  - SELF JOIN: được sử dụng để nối một bảng với chính nó

    - Syntax:

      ```sql
      SELECT a.columns1, b.columns2,...
      FROM table1 a, table1 b
      ON a.column = b.column; 
      ```

  - UNION: được sử dụng để kết hợp các kết quả từ hai hoặc nhiều truy vấn SELECT. Điều này cho phép lấy dữ liệu từ nhiều nguồn và hiển thị chúng trong một tập hợp kết quả duy nhất. Để sử dụng UNION, các truy vấn SELECT phải có cùng số cột và kiểu dữ liệu tương ứng. UNION tự động loại bỏ các hàng trùng lặp. Nếu bạn muốn giữ các hàng trùng lặp, bạn có thể sử dụng UNION ALL.

    - Syntax:

      ```sql
      SELECT columns1, columns2,...
      FROM table1
      UNION
      SELECT columns1, columns2,...
      FROM table2;
      ```

## 🔷 CREATING DATABASE AND TABLE

  - Data type: là một phần quan trọng vì nó xác định loại dữ liệu mà một column trong table có thể lưu trữ. Các hệ quản trị cơ sở dữ liệu khác nhau có thể có các kiểu dữ liệu khác nhau, nhưng các kiểu cơ bản thường được chia thành các nhóm như sau:

    - Numeric: dữ liệu kiểu số. Ví dụ INT, FLOAT, DOUBLE,...
    - String: dữ liệu kiểu chuỗi. Ví dụ CHAR, VARCHAR,...
    - DateTime: dùng để lư trữ thông tin về thời gian. Ví dụ DATE, TIME, DATETIME,...
    - BOOLEAN: lưu trữ giá trị true/false
    - BLOB: lưu trữ dữ liệu nhị phân lớn, chẳng hạn như hình ảnh, video,...
    - JSON: lưu trữ dữ liệu định dạng JSON.

  - Primary key: được sử dụng để xác định một tính duy nhất mỗi bản ghi trong một bảng. Nó đảm bảo tính toàn vẹn dữ liệu của bảng. Một bảng có thể chỉ bao gồm một primary key, primary key này có thể bao gồm một hoặc nhiều cột. Primary key không cho phép null hoặc trùng lặp giá trị.

  - Foreign Key: dùng để tạo mối quan hệ giữ 2 bảng, cho phép tham chiếu đến các bản ghi trong một bảng khác. Một bảng có thể có nhiều Foreign Key.