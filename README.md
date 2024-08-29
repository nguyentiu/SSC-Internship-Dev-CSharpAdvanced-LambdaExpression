# SSC-Internship-Dev-CSharpAdvanced-LambdaExpression
# Hướng Dẫn Về Lambda Expression trong C#
## 1. Giới Thiệu
Lambda expression là một cú pháp mạnh mẽ trong C# cho phép bạn định nghĩa các phương thức ẩn danh (anonymous methods) một cách ngắn gọn và dễ hiểu. Lambda expression rất hữu ích trong việc làm việc với các delegate và các phương thức LINQ, giúp mã nguồn trở nên gọn gàng và dễ bảo trì hơn. Trong bài viết này, chúng ta sẽ tìm hiểu về lambda expression, cách sử dụng chúng, và các ví dụ cụ thể để minh họa cách chúng có thể được áp dụng trong các tình huống khác nhau.

## 2. Lambda Expression Là Gì?
Lambda expression là một cách viết ngắn gọn cho các phương thức delegate. Nó cho phép bạn tạo một phương thức inline mà không cần phải khai báo phương thức đầy đủ với tên và kiểu trả về. Cú pháp của lambda expression rất đơn giản và trực quan.

Cú pháp cơ bản của lambda expression:

```csharp
 
(parameters) => expression
```
- `parameters`: Danh sách các tham số đầu vào (có thể không có tham số).
- `=>`: Toán tử lambda, phân cách giữa tham số và biểu thức.
- `expression`: Biểu thức hoặc khối lệnh cần thực hiện.
## 3. Các Ví Dụ Cụ Thể
### 3.1 Lambda Expression Với Một Tham Số
Lambda expression có thể được sử dụng với một tham số để thực hiện các phép toán đơn giản.

Ví dụ:

```csharp
 
// Declare a lambda expression that squares a number
Func<int, int> square = x => x * x;

// Use the lambda expression
int result = square(5);

// Output the result
Console.WriteLine("The square of 5 is: " + result); // Output: The square of 5 is: 25
```
Giải thích:

- `Func<int, int>`: Đây là delegate kiểu `Func` với một tham số kiểu `int` và trả về giá trị kiểu `int`.
- `x => x * x`: Lambda expression nhận đầu vào x và trả về bình phương của `x`.
### 3.2 Lambda Expression Với Nhiều Tham Số
Lambda expression cũng có thể làm việc với nhiều tham số.

Ví dụ:

```csharp
 
// Declare a lambda expression that adds two numbers
Func<int, int, int> add = (a, b) => a + b;

// Use the lambda expression
int sum = add(10, 15);

// Output the result
Console.WriteLine("The sum of 10 and 15 is: " + sum); // Output: The sum of 10 and 15 is: 25
```
Giải thích:

- `Func<int, int, int>`: Đây là delegate kiểu `Func` với hai tham số kiểu `int` và trả về giá trị kiểu `int`.
- `(a, b) => a + b`: Lambda expression nhận hai tham số `a` và `b`, sau đó trả về tổng của chúng.
### 3.3 Lambda Expression Với Khối Lệnh
Khi cần thực hiện nhiều lệnh, bạn có thể sử dụng khối lệnh trong lambda expression.

Ví dụ:

```csharp
 
// Declare a lambda expression with a block of statements
Action<string> printMessage = message =>
{
    Console.WriteLine("Message: " + message);
    Console.WriteLine("Message length: " + message.Length);
};

// Use the lambda expression
printMessage("Hello, Lambda!");

// Output:
// Message: Hello, Lambda!
// Message length: 13
```
Giải thích:

- `Action<string>`: Đây là delegate kiểu `Action` với một tham số kiểu `string` và không trả về giá trị.
- `message => { ... }`: Lambda expression thực hiện nhiều lệnh, bao gồm việc in ra thông điệp và chiều dài của thông điệp.
### 3.4 Lambda Expression Trong LINQ
Lambda expression rất hữu ích trong LINQ để thực hiện các truy vấn dữ liệu.

Ví dụ:

```csharp
 
using System;
using System.Linq;

class Program
{
    static void Main()
    {
        int[] numbers = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

        // Use a lambda expression to filter even numbers
        var evenNumbers = numbers.Where(n => n % 2 == 0);

        // Output the result
        Console.WriteLine("Even numbers:");
        foreach (var num in evenNumbers)
        {
            Console.WriteLine(num); // Output: 2 4 6 8 10
        }
    }
}
```
Giải thích:

- `numbers.Where(n => n % 2 == 0)`: Lambda expression được sử dụng để lọc các số chẵn trong mảng `numbers`.
## 4. Tổng Kết
Lambda expression cung cấp một cách viết ngắn gọn và linh hoạt cho các phương thức delegate. Chúng giúp làm giảm sự phức tạp của mã nguồn và tăng tính dễ đọc. Dưới đây là một số điểm nổi bật về lambda expression:

- Cú pháp ngắn gọn: Giảm thiểu số lượng mã cần viết.
- Tính linh hoạt: Có thể sử dụng với một hoặc nhiều tham số, và có thể thực hiện các khối lệnh.
- Tích hợp với LINQ: Hỗ trợ các truy vấn dữ liệu một cách dễ dàng và hiệu quả.
