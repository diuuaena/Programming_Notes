# **Typescript**

## 🔷 MỤC LỤC

- **[Typescript là gì](#typescript)**
- **[Các kiểu dữ liệu trong typescript](#static-types-kiểu-dữ-liệu-tĩnh)**
- **[Classes](#classes)**
- **[Interface](#interface)**
- **[Generics](#generics)**

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

- Ngoài ra, trong JS, cách cơ bản để nhóm và truyền dữ liệu là thông qua các đối tượng. Trong TS, chúng ta biểu diễn chúng thông qua **Object Types**

    ```ts
        // Init [person] with key [name] and [age]
        const person: {
            name: string,
            age: number
        } = {
            name: 'Phong',
            age: 25
        }
    ```

### Tuples

- **Tuples** là một kiểu dữ liệu trong **Typescript** được sử dụng để biểu diễn một mảng trong đó kiểu của một số phần tử cố định được khai báo từ ban đầu, nhưng không phải cho tất cả các phần tử. Nó cung cấp một cách để biểu diễn tập hợp các kiểu phần tử được sắp xếp cho các phần tử được sắp xếp cho các phần tử nhất định trong một mảng TS. **Tuples** luôn có một số phần tử cố định và mỗi phần tử trong số chúng có các kiểu được liên kết với chúng

    ```ts
    let point: [number, number] = [9, 10]

    const role: [string, string] = ['admin', 'user']
    ```

### Enums

- **Enums** là tập hợp các **const** được đặt tên. Sử dụng **Enums** có thể giúp ghi lại ý định dễ dàng hơn hoặc tạo một tập hợp các trường hợp riêng biệt. TS cung cấp cả enums dạng **string** và dạng **number**

- Các loại **Enums** cơ bản:

    + **Number Enums** TS xác định giá trị số của một thành phần Enums dựa trên thứ tự của thành phần đó xuất hiện trong định nghĩa Enums

        ```ts
        enum MOVE {
            Up,     // default Up = 0
            Down,   // default Down = 1
            Left,   // default Left = 2
            Right   // default Right = 4
        }

        enum MOVE {
            Up = 1, // set Up = 1
            Down,   // default set Down = 2
            Left,   // default set Left = 3
            Right   // default set Right = 4
        }
        ```

    + **String Enums** Đối với mỗi element phải được khởi tạo hằng số là một chuỗi kí tự hoặc một string enums element khác

        ```ts
        enum ROLE {
            ADMIN       = 'admin',
            READ_ONLY   = 'read only',
            WRITE_READ  = 'write read'
        }

        // Error
        enum ROLE {
            ADMIN       = 'admin',
            READ_ONLY   = 'read only',
            WRITE_READ  // Error: Enum member must have initializer
        }
        ```

### Any Types
- **Any Types** Là một kiểu dữ liệu đặc biệt của TS, **Any Types** có thể sử dụng bất cứ khi nào mà không muốn một giá trị cụ thể nào đó gây ra lỗi kiểu tra kiểu dữ liệu

- Khi một giá trị có kiểu là **any**, có thể truy cập bất kì thuộc tính vào của nó, có thể gọi nó như một hàm, gán cho nó một giá trị có kiểu dữ liệu bất kì hoặc một thứ gì đó khác miễn là hợp lệ về mặt cú pháp

    ```ts
    let obj: any = { x: 0}
    
    // No error
    obj.foo()
    obj()
    obj.bar = 100
    obj = 'Hello'
    ```

### Union Types
- **Union Types** Cho phép chỉ định nhiều loại có thể có cho một biến hoặc tham số. **Union Types** được viết dưới dạng danh sách các loại được phân tách bằng `|`

    ```js
    // variable
    const log: number | string = 'log'

    // arrow function
    const logData = (data: number | boolean | string): number | boolean | string => data
    ```

### Literal Types
- **Literal Types** Chỉ định chính xác giá trị của biến hoặc tham số thay vì chỉ định kiểu dữ liệu. **Literal Types** có thể được sử dụng để thực thi rằng một giá trị phải thuộc một kiểu cụ thể và một giá trị cụ thể

    ```ts
    let season: 'spring' | 'summer' | 'autumn' | 'winter'

    // Error: Type '"season"' is not assignable to type '"spring" | "summer" | "autumn" | "winter"'
    season = 'season'
    ```
### Custom Types / Type Aliases
- **Custom Types (Type Aliases)** Cho phép tạo ra một tên cho loại dữ liệu

    ```ts
    // create Name, Age, User type
    type Name = string;
    type Age = number;
    type User = { name: Name; age: Age };

    const user: User = { name: 'John', age: 30 };
    ```

### Unknown Types
- **Unknown Types** là một kiểu dữ liệu an toàn tương ứng của **Any Types**. Bất kì thứ gì cũng có thể gán cho **Unknown Types** tuy nhiên nó không thể được gán cho bất kì thứ gì ngoài chính nó và **Any Types**. Không có thao tác nào được phép trên **Unknown Types** mà không được khẳng định hoặc thu hẹp thành một kiểu dữ liệu cụ thể

    ```ts
    let obj: unknown;
    let variable: any;
    let age: number = 5;

    // Success
    obj = variable
    obj = age

    // Error: 'obj' is of type 'unknown'.ts(18046)
    obj.call()
    ```

### Never Types
- **Never Types**

    + Là kiểu dữ liệu mà **Typescript** để biểu diễn trạng thái không nên tồn tại. **Never Types** có thể gán cho mọi kiểu, tuy nhiên, không có kiểu dữ dữ liệu nào có thể gán cho **Never Types** (trừ chính nó)

    + Thường được sử dụng cho `Switch clause` để thực hiện kiểm tra toàn diện (khi đã loại bỏ tất cả khả năng và không còn gì nữa)

    + Ngoài ra, **Never Types** là kiểu trả về cho biểu thức hàm hoặc biểu thức hàm

    ```ts
    enum SEASON {
        SPRING,
        SUMMER,
        AUTUMN,
        WINTER
    }

    const getTemperature = (season: SEASON) => {
        switch(season) {
            case SEASON.SPRING:
                return 30
            case SEASON.SUMMER:
                return 36
            case SEASON.AUTUMN:
                return 25
            case SEASON.WINTER:
                return 15
            default:
                // Success
                const _exhaustiveCheck:never = season
                return _exhaustiveCheck
        }
    }
    // Error: Type '404' is not assignable to type 'never'.ts(2322)
    const _exhaustiveCheck:never = 404
    ```

### Intersection Types

- **Intersection Types** trong TS cho phép tạo ra kiểu dữ liệu mới bằng cách kết hợp nhiều kiểu dữ liệu lại với nhau. Kiểu mới có tất cả tính năng của các kiểu kết hợp

    ```ts
    type Admin = {
        name: string
        privileges: string[]
    }

    type Employee = {
        name: string
        startDate: Date
    }

    type ElevatedEmployee = Admin & Employee

    const e: ElevatedEmployee = {
        name: 'Phong',
        privileges: ['build-server'],
        startDate: new Date()
    }
    ```

- Với **Intersection Types** các thuộc tính có các kiểu dữ liệu khác nhau sẽ được tự động hợp nhất. Khi kiểu dữ liệu được sử dụng sau đó, TS sẽ mong đợi thuộc tính thoả mãn cả hai kiểu dữ liệu cùng một lúc, điều này có thể tạo ra kết quả không mong muốn

    ```ts
    type Numeric    = number | boolean

    type Characters = string | number

    type VarChar = Numeric & Characters // typeof VarChar = number
    ```

    ```ts
    type Numeric    = number

    type Characters = string

    type VarChar = Numeric & Characters // typeof VarChar = never
    ```

### Type Guards

- **Type Guards** là một cách để thu hẹp kiểu dữ liệu của một biến, là một pattern code kiểm tra một kiểu nhất định trước khi thực hiện điều gì đó khi thực thi chương trình

- **Toán tử instanceof** được sử dụng để kiểm tra một đối tượng có phải là một thể hiện của một class hay không

    ```ts
    class Bird {
        constructor(public flySpeed: number) {}
    }

    class Horse {
        constructor(public runSpeed: number) {}
    }

    const getAnimalSpeed = (animal: Bird | Horse) => {
        if (animal instanceof Bird) {
            return animal.flySpeed
        }
        
        return animal.runSpeed
    }
    ```

- **Toán tử typeof** được sử dụng để kiểm tra kiểu dữ liệu của một biến. Nó trả về một giá trị chuỗi biểu diễn kiểu dữ liệu của biến

    ```ts
    const logData = (data: number | string) => {
        if (typeof data === 'number') {
            data = data.toFixed(2)
        }

        return data
    }

    console.log(logData(5.2566))    // '5.26'
    ```

- **Các toán tử kiểm tra tính bằng nhau `===` `!==` `==` `!==`** TS cũng sử dụng các câu lệnh chuyển đổi và kiểm tra tính bằng nhau để thu hẹp các kiểu dữ liệu

    ```ts
    const showLimit = (x: number, y: string | number) => {
        // x === y => typeof x === typeof y
        if (x === y) {
            return `[${x.toFixed(2)}; ${y.toFixed(2)}]`
        } 
        
        return `[${x.toFixed(2)}; ${y.toString()})`
    }

    console.log(showLimit(3, '∞'))  // [3.00; ∞)
    console.log(showLimit(4, 4))    // [4.00; 4.00]
    ```

### Index Signatures (Index Properties)

- Trong TS, **Index Signatures** cho phép định nghĩa các kiểu object với các key động, trong đó các key có thể thuộc một kiểu dữ liệu cụ thể và các giá trị tương ứng có thể thuộc một kiểu khác. Điều này đặc biệt hữu ích khi muốn làm việc với các đối tượng có các thuộc tính không được biết tại thời điểm biên dịch nhưng phải tuân theo một mẫu cụ thể

    ```ts
    interface ErrorHandle {
        id: string
        [prop: string]: string
    }

    const errorHandle: ErrorHandle = {
        id: '1',
        mail: 'Incorrect mail format!',
        username: 'Username is required!',
    }

    console.log(errorHandle.mail)   // 'Incorrect mail format!'

    // Success
    console.log(errorHandle.age)    // undefined    
    ```

- Key của **Index Signatures** chỉ có thể `string`, `number` hoặc `symbol`. Các loại khác không được phép

    ```ts
    // Error: An index signature parameter type cannot be a literal type or generic type. Consider using a mapped object type instead.ts(1337)
    interface Seasion {
        [prop: 'Summer' | 'Winner']: string
    }
    ```

## 🔷 Classes

### Classes

- **Classes** là bản thiết kế để tạo đối tượng, cung cấp cách để cấu trúc đối tượng và đóng gói dữ liệu và hành vi. Một **class** trong TS được định nghĩa bằng từ khoá `class`, theo sau là tên của **class**. Định nghĩa một **class** có thể bao gồm các **thuộc tính (attributes hoặc properties)**, **phương thức (methods)** và một **constructor**

    ```ts
    class Account {
        /* properties */
        public username?: string;
        public password?: string;
        public firstName?: string;
        public lastName?: string;

        /* Constructor */
        constructor(
            username?: string,
            pass?: string,
            first?: string,
            last?: string
        ) {
            this.username = username
            this.password = pass
            this.firstName = first
            this.lastName = last
        }

        /* Methods */
        public showFullName(): string {
            return `${this.firstName} ${this.lastName}`
        }
    }

    const account = new Account('PhongNQ', '12345678', 'Phong', 'Nguyen Quoc')

    console.log(account.showFullName())
    ```

- **Constructor** Trong TS, các tham số **Constructor** có thể được khai báo với các **Access Modifiers (public, private, protected)** và chú thích kiểu dữ liệu hoặc chỉ đơn giản là tham số với kiểu dữ liệu. Với tham số được khai báo với các **Access Modifiers**, TS sẽ tự động gán cho các thuộc tính có cùng tên trong **Constructor** và có thể truy cập trong class

    ```ts
    class Account {
        public username?: string;
        public password?: string;
        public firstName?: string;
        public lastName?: string;

        // Normal signature with defaults
        constructor(
            username?: string,
            pass?: string,
            first?: string,
            last?: string
        ) {
            this.username = username
            this.password = pass
            this.firstName = first
            this.lastName = last
        }
    }

    class Account {
        constructor(
            public username?: string,
            private password?: string,
            public firstName?: string,
            public lastName?: string
        )
    }
    ```

- **Singletons Pattern với Private Constructor**

    + **Singletons Pattern** là một **Design Pattern** đảm bảo rằng một class chỉ có duy nhất một instance và có thể cung cấp một cách toàn cầu để truy cập tới instance đó

        ```ts
        class Singleton {
            static instance: Singleton

            private constructor() {}

            static getInstance() {
                if (!this.instance) {
                    this.instance = new Singleton()
                }

                return this.instance
            }
        }

        const singleton1 = Singleton.getInstance()
        const singleton2 = Singleton.getInstance()
        ```

### Getter và Setter

- **Getter** và **Setter** cho phép kiểm soát quyền truy cập vào các thuộc tính của **class**. Đối với mỗi thuộc tính, bao gồm: phương thức **getter (accessor)** trả về giá trị của thuộc tính và phương thức **setter (mutator)** cập nhật giá trị của thuộc tính

    ```ts
    class Department {
        constructor(
            private name: string,
            private employee?:string,
            private employees: string[] = []
        ) {}

        get lastEmployee() {
            if (!this.employee) {
                throw new Error(`No employees in ${this.name}`)
            }
            return this.employee
        }

        set lastEmployee(employee: string) {
            if (!employee) {
                throw new Error('Employee is required!!!')
            }

            this.employees.push(employee)
            this.employee = employee
        }
    }

    const dep = new Department('IT Department')

    // Using setter method
    dep.lastEmployee = 'PhongNQ'
    dep.lastEmployee = 'Phong'

    // Using getter method
    console.log(dep.lastEmployee)   // Return 'Phong'
    ```

### Thuộc tính và phương thức tĩnh (Static)

- **Thuộc tính và phương thức tĩnh** được chia sẻ giữa tất cả các instance của một class. Để khai báo một thuộc tính hoặc một phương thức tĩnh, sử dụng từ khoá `static` làm tiền tố

    ```ts
    class Department {
        private static count: number = 0

        constructor(
            private id: string,
            private name: string
        ) {
            // Using static property without static method
            Department.count++
        }

        static get getNumOfEmployees() {
            // Using static property with static method
            return this.count
        }
    }

    const JsDep = new Department('1', 'JS Department')
    const GxDep = new Department('2', 'GX Department')

    console.log(Department.getNumOfEmployees)   // 2
    ```

### OOP - Kế thừa (Inheritance)

- **Kế thừa (Inheritance)** là một cơ chế mà một lớp con kế thừa các thuộc tính và phương thức từ lớp cha của nó. Điều này cho phép một lớp con sử dụng lại mã và hành vi của lớp cha đồng thời có thể thêm và sửa đổi hành vi của riêng nó. Trong TS, kế thừa được thực hiện bằng cách sử dụng từ khoá `extends`

- **Kế thừa** cho phép chia sẻ một số chức năng chung và tạo ra các bản thiết kế chuyên biệt hơn

    ```ts
    class Department {
        constructor(
            private id: string,
            private name: string,
            protected employees: string[] = []
        ) { }

        get departmentName() {
            return this.name
        }
    }

    class ITDepartment extends Department {
        constructor(
            id: string,
            employees: string[],
            private mainTech: string
        ) {
            super(id, 'IT Department', employees)
        }

        getAdmin() {
            return this.employees[0]
        }

        getMainTech() {
            return this.mainTech
        }
    }

    const IT = new ITDepartment('1', ['Phong', 'PhongNQ', 'PhongNQ'], 'Web App')

    console.log(IT.getAdmin())      // 'Phong'

    console.log(IT.getMainTech())   // 'Web App'

    console.log(IT.departmentName)  // 'IT Department'
    ```

### OOP - Trừu tượng (Abstract)

- **Abstract class** trong TS là các class không thể tự khởi tạo, thay vào đó, nó phải có một class dẫn xuất để triển khai các class trừu tượng. **Abstract class** cung cấp một bản thiết kế cho các class khác. **Abstract class** có thể có các **phương thức abstract**, đây là các phương thức không có phần thân và phải được các lớp con ghi đè.

- **Abstract class** hữu ích khi để định nghĩa một giao diện chung hoặc chức năng cơ bản mà lớp khác có thể kế thừa và xây dựng dựa trên đó

    ```ts
    abstract class Department {
    
        abstract name: string

        constructor(private id: string){}

        abstract addEmployees():void
    }

    // Error: Non-abstract class 'ITDepartment' is missing implementations 
    // for the following members of 'Department': 'name', 'addEmployees'.ts(2654)
    class ITDepartment extends Department {}
    ```

    ```ts
    type Employee = {
        name: string,
        language: string
    }

    abstract class Department {

        abstract name: string

        constructor(protected id: string) { }

        abstract addEmployees(employee: Employee): void
    }

    class ITDepartment extends Department {
        constructor(
            id: string,
            public name: string = 'IT Department',
            private employees: Employee[] = []
        ) {
            super(id)
        }

        addEmployees(employee: Employee): void {
            if (!employee.language) {
                throw new Error(`Not eligible to join ${this.name}`)
            }

            this.employees.push(employee)
        }

        get employeesList() {
            return this.employees
        }
    }

    const IT = new ITDepartment('1')

    const employee: Employee = {
        name: 'PhongNQ',
        language: 'Typescript'
    }
    IT.addEmployees(employee)

    console.log(IT.employeesList)   // [ { name: 'PhongNQ', language: 'Typescript' } ]
    ```

## 🔷 Interface

### Interface

- **Interface** trong TS cung cấp một cách để xác định kiểu dữ liệu, bao gồm tập hợp các thuộc tính, phương thức và sự kiện. Nó được sử dụng để thực thi một cấu trúc cho một đối tượng, class hoặc tham số của hàm. **Interface** không được biên dịch sang JS và chỉ được TS sử dụng tại thời điểm biên dịch cho mục đích kiểm tra kiểu dữ liệu

    ```ts
    interface IDateTime {
        year: number
        month: number
        date: number
        hour: number
        minute: number
        second: number
        toString(): string
    }

    const datetime: IDateTime = {
        year: 2025,
        month: 1,
        date: 24,
        hour: 8,
        minute: 0,
        second: 0,

        toString() {
            return `${this.year}/${this.month}/${this.date} ${this.hour}:${this.minute}:${this.second}`
        }
    }

    console.log(datetime.toString())    // '2025/1/24 8:0:0'
    ```

### Sử dụng Interface với Classes

- Trong TS, mệnh đề **implements** có thể được sử dụng để xác minh rằng một class phải tuân thủ một interface cụ thể. Nếu một class không triển khai đúng interface, lỗi sẽ được sinh ra

    ```ts
    interface IDateTime {
        year: number
        month: number
        date: number
        hour: number
        minute: number
        second: number

        toString(): string
    }

    class Time implements IDateTime {
        constructor(
            public year: number,
            public month: number,
            public date: number,
            public hour: number,
            public minute: number,
            public second: number
        ) {}

        toString(): string {
            return `${this.year}/${this.month}/${this.date} ${this.hour}:${this.minute}:${this.second}`
        }

        convertTimeToDays() {
            return (this.second/(60*60*24) + this.minute/(60*24) + this.hour/24).toFixed(3)
        }
    }

    const time = new Time(2025, 2, 4, 14, 20, 20)
    console.log(time.toString())            // 2025/2/4 14:20:20
    console.log(time.convertTimeToDays())   // 0.597

    // Error: Class 'DateCustom' incorrectly implements interface 'IDateTime'.
    //        Type 'DateCustom' is missing the following properties from type 'IDateTime': hour, minute, secondts(2420)
    class DateCustom implements IDateTime {
        constructor(
            public year: number,
            public month: number,
            public date: number,
        ) {}
    }
    ```

- Một class có thể triển khai một hoặc nhiều interface cùng một lúc

    ```ts
    interface IProduct {
        name: string
        price: number
    }

    interface IBill {
        id: string
        nums: number
        discount: number
    }

    class Pay implements IProduct, IBill {
        constructor(
            public id: string,
            public nums: number,
            public discount: number,
            public name: string,
            public price: number,
        ) {}

        get payable() {
            return (this.nums * this.price) * this.discount/100
        }
    }
    ```

- Việc triển khai một interface với thuộc tính tuỳ chọn sẽ không tạo ra thuộc tính đó

    ```ts
    interface ICommonRole {
        name: string
        level: string
        sublevel?: string
    }

    class Guest implements ICommonRole {
        constructor(
            public name: string,
            public level: string = '1'
        ) { }
    }

    const guest = new Guest('Phong')

    // Error: Property 'sublevel' does not exist on type 'Guest'.ts(2339)
    console.log(guest.sublevel)
    ```

- Ngoài ra, với một biến hoặc hằng số có kiểu dữ liệu là một interface có thể thực sự được dùng để lưu trữ class

    ```ts
    const time: IDateTime = new Time(2025, 2, 4, 14, 20, 20)
    console.log(time.toString())    // 2025/2/4 14:20:20

    // Error: Property 'convertTimeToDays' does not exist on type 'IDateTime'.ts(2339)
    console.log(time.convertTimeToDays())

    const bill: IBill        = new Pay('1', 5, 4, 'Phone', 1250000)
    const product: IProduct  = new Pay('1', 5, 4, 'Phone', 1250000)
    ```

### Kế thừa với Interface

- Trong TS, có thể mở rộng interface bằng cách tạo interface mới kế thừa từ interface gốc bằng từ khoá `extends`. Interface mới có thể bao gồm các thuộc tính, phương thức của interface gốc và bổ sung thêm các thuộc tính hoặc phương thức mới

    ```ts
    interface IPerson {
        name: string
        age: number
    }

    interface IEmployee extends IPerson {
        department: string
    }

    const employee: IEmployee = {
        name: 'Phong',
        age: 25,
        department: 'IT'
    }
    ```

## 🔷 Generics

### Generics

- **Generics** trong TS là một cách để viết code có thể hoạt động với nhiều kiểu dữ liệu, thay vì bị giới hạn ở một kiểu dữ liệu duy nhất

### Generic Types

- **Generic Types** cho phép khởi tạo các đối tượng, hàm và class hoạt động với nhiều kiểu dữ liệu, thay vì bị giới hạn ở một kiểu dữ liệu duy nhất. **Generic Types** được định nghĩa bằng dấu ngoặc nhọn `<T>` và được sử dụng như một kiểu dữ liệu đại diện. Kiểu dữ liệu thực tế được chỉ định khi hàm hoặc class được sử dụng

    ```ts
    const convertString = <T>(data: T) => data?.toString()

    console.log(convertString(5))           // '5'

    console.log(convertString([1, 2, 3]))   // '1,2,3'
    ```

- Class với **Generic Types**

    ```ts
    class DataStorage<T> {
        private data: T[] = []

        add(...items: T[]) {
            this.data.push(...items)
        }

        remove(item: T) {
            this.data = this.data.filter((value) => !this.data.includes(item))
        }

        get dataList() {
            return this.data
        }
    }

    // With number type
    const numberStorage = new DataStorage<number>()

    numberStorage.add(1, 2, 4, 5, 4)

    console.log(numberStorage.dataList) // [ 1, 2, 4, 5, 4 ]

    // With string type
    const stringStorage = new DataStorage<string>()

    stringStorage.add('VietNam', 'China', 'Singapore')

    console.log(stringStorage.dataList) // [ 'VietNam', 'China', 'Singapore' ]
    ```

### Generic Constraints

- **Generic Constraints** cho phép chỉ định các yêu cầu cho các tham số kiểu dữ liệu được sử dụng trong **Generic Types**. Các ràng buộc này đảm bảo rằng các tham số kiểu dữ liệu được sử dụng trong **Generic Types** đáp ứng các yêu cầu nhất định

- **Generic Constraints** được chỉ định bằng cách sử dụng từ khoá `extends`, theo sau là kiểu dữ liệu mà tham số kiểu dữ liệu phải mở rộng hoặc triển khai

    ```ts
    function merge<T extends {}>(objA: T, objB: T) {
        return Object.assign(objA, objB)
    }

    console.log(merge({ language: 'typescript' }, { version: '1.2.3' }))    // { language: 'typescript', version: '1.2.3' }
    ```

- **`keyof` Generic Constraints** có thể sử dụng 2 kiểu như sau

    ```ts
    function getValueByKey<T>(obj: T, key: keyof T) {
        return obj[key]
    }

    const account = {
        username: 'QuanTT',
        age: 24
    }

    // return getValueByKey: string | number
    console.log(getValueByKey(account, 'username')) // 'QuanTT'
    console.log(getValueByKey(account, 'age'))      // 24
    ```

    hoặc

    ```ts
    function getValueByKey<T, K extends keyof T>(obj: T, key: K) {
        return obj[key]
    }
    ```

### Generic Utility Types Build-in

- **Utility Types** cung cấp một số kiểu tiện ích có thể được sử dụng để thao tác và chuyển đổi các kiểu hiện có. Sau đây là một số kiểu phổ biến

    + **Partial** làm cho tất cả thuộc tính của một kiểu trở thành thuộc tính tuỳ chọn

        ```ts
        interface Setting {
            id: string,
            theme: 'LIGHT' | 'DARK'
            language: string
            background: string
        }

        // Error: Property 'background' is missing in type '{ id: string; theme: "LIGHT"; language: string; }'
        //        but required in type 'Setting'.ts(2741)
        const setting: Setting = {
            id: '1',
            theme: 'LIGHT',
            language: 'VN',
        }

        // Success
        const settingP: Partial<Setting> = {
            id: '1',
            theme: 'LIGHT'
        }
        ```

    + **Readonly** làm cho tất cả thuộc tính của một kiểu thành không thể thay đổi

        ```ts
        interface Setting {
            id: string,
            theme: 'LIGHT' | 'DARK'
            language: string
            background: string
        }

        const setting: Setting = {
            id: '1',
            theme: 'LIGHT',
            language: 'VN',
            background: 'summer.jpg'
        }

        // Success
        setting.id = '2'

        const settingR: Readonly<Setting> = {
            id: '1',
            theme: 'DARK',
            language: 'EN',
            background: 'summer.jpg'
        }

        // Error: Cannot assign to 'id' because it is a read-only property.ts(2540)
        settingR.id = '1'
        ```

# 🔷 Decorators

### Decorators

- **Decorators** là một tính năng của TS cho phép sửa đổi hành vi của một class, thuộc tính, phương thức hoặc tham số. Chúng là một cách để thêm chức năng bổ sung vào code hiện có và có thể được sử dụng cho nhiều tác vụ, bao gồm ghi nhật kí, tối ưu hoá hiệu suất và xác thực

    ```ts
    function Logger(args: Function) {
        console.log(args.toString())
    }

    @Logger
    class Setting {
        constructor(
            private id?: string,
            private theme?: 'LIGHT' | 'DARK',
            private language?: string,
            private background?: string
        ) {}

        set setLanguage(lang: string) {
            this.language = lang
        }
    }

    // Output: 
    // class Setting {
    //     constructor(id, theme, language, background) {
    //         this.id = id;
    //         this.theme = theme;
    //         this.language = language;
    //         this.background = background;
    //     }
    //     set setLanguage(lang) {
    //         this.language = lang;
    //     }
    // }
    ```

- **Class Decorators** được khai báo ngay trước khi khai báo class. Class Decorator được áp dụng cho constructor của class và có thể được sử dụng để quan sát, sửa đổi hoặc thay thế định nghĩa class. 

    ```ts
    function sealed(constructor: Function) {
        Object.seal(constructor);
        Object.seal(constructor.prototype);
    }

    @sealed
    class BugReport {
        type = "report";
        title: string;
        
        constructor(t: string) {
            this.title = t;
        }
    }
    ```

- **Method Decorators** được khai báo ngay trước khi khai báo method. Method Decorator được áp dụng cho phương thức và có thể được sử dụng để quan sát, sửa đổi hoặc thay thế một định nghĩa phương thức.

    ```ts
    function enumerable(value: boolean) {
        return function (target: any, propertyKey: string, descriptor: PropertyDescriptor) {
            descriptor.enumerable = value;
        };
    }

    class Greeter {
        greeting: string;
        constructor(message: string) {
            this.greeting = message;
        }
        
        @enumerable(false)
        greet() {
            return "Hello, " + this.greeting;
        }
    }
    ```

- **Accessor Decorators** được khai báo ngay trước khi khai báo accessor. Accessor Decorator được áp dụng cho accessor và có thể được sử dụng để quan sát, sửa đổi hoặc thay thế các định nghĩa của accessor

    ```ts
    function configurable(value: boolean) {
        return function (target: any, propertyKey: string, descriptor: PropertyDescriptor) {
            descriptor.configurable = value;
        };
    }

    class Point {
        private _x: number;
        private _y: number;
        constructor(x: number, y: number) {
            this._x = x;
            this._y = y;
        }
        
        @configurable(false)
        get x() {
            return this._x;
        }
        
        @configurable(false)
        get y() {
            return this._y;
        }
    }
    ```

- **Property Decorators** được khai báo ngay trước khi khai báo thuộc tính. 

    ```ts
    import "reflect-metadata";
    const formatMetadataKey = Symbol("format");
    function format(formatString: string) {
        return Reflect.metadata(formatMetadataKey, formatString);
    }
    function getFormat(target: any, propertyKey: string) {
        return Reflect.getMetadata(formatMetadataKey, target, propertyKey);
    }

    class Greeter {
        @format("Hello, %s")
        greeting: string;
        constructor(message: string) {
            this.greeting = message;
        }
        greet() {
            let formatString = getFormat(this, "greeting");
            return formatString.replace("%s", this.greeting);
        }
    }
    ```

- **Parameter Decorators** được khai báo ngay trước khi khai báo tham số. 

    ```ts
    import "reflect-metadata";
    const requiredMetadataKey = Symbol("required");
    
    function required(target: Object, propertyKey: string | symbol, parameterIndex: number) {
        let existingRequiredParameters: number[] = Reflect.getOwnMetadata(requiredMetadataKey, target, propertyKey) || [];
        existingRequiredParameters.push(parameterIndex);
        Reflect.defineMetadata( requiredMetadataKey, existingRequiredParameters, target, propertyKey);
    }
    
    function validate(target: any, propertyName: string, descriptor: TypedPropertyDescriptor<Function>) {
    let method = descriptor.value!;
    
    descriptor.value = function () {
        let requiredParameters: number[] = Reflect.getOwnMetadata(requiredMetadataKey, target, propertyName);
        if (requiredParameters) {
            for (let parameterIndex of requiredParameters) {
                if (parameterIndex >= arguments.length || arguments[parameterIndex] === undefined) {
                t    hrow new Error("Missing required argument.");
                }
            }
        }
        return method.apply(this, arguments);
    };
    }

    class BugReport {
        type = "report";
        title: string;
        
        constructor(t: string) {
            this.title = t;
        }
        
        @validate
        print(@required verbose: boolean) {
            if (verbose) {
            return `type: ${this.type}\ntitle: ${this.title}`;
            } else {
            return this.title; 
            }
        }
    }
    ``` 