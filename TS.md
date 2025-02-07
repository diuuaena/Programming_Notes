# **Typescript**

## 🔷 MỤC LỤC

- **[Typescript là gì](#-typescript-là-gì)**
- **[Các kiểu dữ liệu trong typescript](#-các-kiểu-dữ-liệu-trong-typescript)**

## 🔷 Typescript là gì

### Typescript (TS)

- **Typescript** là một ngôn ngữ lập trình kiểu tĩnh, là siêu tập hợp cú pháp nghiêm ngặt của **Javascript (JS)**. Ngôn ngữ này được phát triển và duy trì bởi Microsoft. **Typescript** được tạo ra để giải quyết những thách thức trong việc xây dựng các ứng dụng JS quy mô lớn và thêm các **class**, **interface** và các tính năng khác vào ngôn ngữ

- Một số ưu điểm nổi bật của **Typescript**

    + **Kiểu dữ liệu** TS có chú thích kiểu dữ liệu tuỳ chọn trong khi JS là kiểu dữ liệu động. Với TS, có thể chỉ định kiểu dữ liệu của biến, tham số và giá trị trả về, có thể giúp phát hiện lỗi liên quan đế kiểu dữ liệu tại thời điểm biên dịch

    + **Cú pháp** TS mở rộng cú pháp JS với các tính năng như **Interface**, **Class** và **Namespaces**. Điều này cung cấp cấu trúc mạnh mẽ và có tổ chức hơn trong các dự án quy mô lớn

    + **Công cụ** TS hỗ trợ công cụ tốt hơn, chẳng hạn như tích hợp trình soạn thảo, kiểm tra kiểu dữ liệu và tái cấu trúc mã tốt hơn

    + **Khả năng tương thích** TS có thể biên dịch thành bất kì phiên bản nào của mã JS

- Bên cạnh đó, **Typescript** vẫn còn tồn tại một số nhược điểm như sau

    + **Thời gian biên dịch** Việc biên dịch TS mất nhiều thời gian hơn so với việc biên dịch JS bởi vì cần có thêm bước biên dịch để chuyển đổi TS sang JS để trình duyệt thực thi

    + **Tích hợp và cấu hình bổ sung** Để sử dụng TS cần phải cấu hình trình biên dịch và có thể tích hợp các công cụ đóng gói và xây dựng khác như Webpack, Rollup, hoăc Parcel. Điều này có thể tăng thêm độ phức tạp cho quá trình thiết lập dự án

    + **Một số lỗi ngầm khi biên dịch qua Javascript** Việc biên dịch từ TS sang JS đôi khi có thể che giấu các lỗi hoặc hành vi không mong muốn, đặc biệt là nếu tính nghiêm ngặt của kiểm tra kiểu dữ liệu không được cấu hình đúng cách

## 🔷 Các kiểu dữ liệu trong Typescript

### Static Types (kiểu dữ liệu tĩnh)

- **Static Types** là kiểu dữ liệu của biến được biết tại thời điểm biên dịch thay vì tại thời điểm chạy. Một khi biến được khai báo là có kiểu nhất định, nó không được gán lại thành một kiểu khác sau đó. Điều này có thể ngăn ngừa nhiều lỗi phổ biến có thể xảy ra trong ngôn ngữ với Dynamic Types (kiểu dữ liệu động) đó là kiểu của một biến có thể thay đổi trong quá trình thực thi chương trình

- Có 3 kiểu **dữ liệu nguyên thuỷ** trong TS đó là:

    + **number** Bao gồm tất cả các số, không có sự phân biệt giữa số nguyên và số thực

    + **string** Bao gồm tất cả các giá trị văn bản

    + **boolean** Chỉ có duy nhất 2 giá trị `true` và `false`, không có giá trị `truthy` hoặc `falsy`

- Cách khai báo

    ```ts
    // Init [name] with data type [string]
    const name: string = 'Phong'
    ```

