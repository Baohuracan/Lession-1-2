# **BÀI 1:**

## Trình biên dịch là gì ?

![image](https://github.com/user-attachments/assets/d9ccbc68-f8a5-4c55-adb5-96b8c404b769)


 Trình biên dịch là một chương trình máy tính  có nhiệm vụ dịch một mã nguồn được viết bằng 1 ngôn ngữ lập trình cấp cao thành một chương trình tương đương dưới 
 dạng  ngôn ngữ máy (010101...) hoặc ngôn ngữ bậc thấp ( assembly).

## Tại sao cần trình biên dịch?

 Máy tính chỉ hiểu và thực thi các lệnh ở dạng mã máy, một chuỗi các số 0 và 1. Còn con người thì sử dụng và viết các lệnh bằng ngôn ngữ bậc cao. Và trình biên 
dịch đóng vai trò là cầu nối để máy tính hiểu và thực thi các lệnh của chúng ta.


![image](https://github.com/user-attachments/assets/44627f00-df30-468e-9e94-0cede4491f25)




Quá trình biên dịch của Compiler trải qua 4 bước như sau:


## Bước 1: Tiền xử lý (Preprocessing)

 Đầu tiên file chúng ta code sẽ được lưu dưới dạng file.c / file.cpp

 Sau đó trình biên dịch xóa bỏ comment sẽ xử lý các chỉ thị tiền xử lý ( preprocessor directives ) như #include, `#define`, `#if` và các macro khác thành một tệp  file.i
 
 Tệp này bao gồm mã nguồn đã được mở rộng và các chỉ thị tiền xử lý đã được xử lý.

## Bước 2: Biên dịch (Compilation)

  Chuyển đổi mã nguồn C đã được tiền xử lý thành mã hợp ngữ (assembly code ) thành một tệp dạng file.s

 Một số lệnh hợp ngữ cơ bản: 

	• MOV: Di chuyển dữ liệu từ nguồn đến đích.

	• LOAD: Nạp dữ liệu từ bộ nhớ vào thanh ghi.

	• STORE: Lưu dữ liệu từ thanh ghi vào bộ nhớ.

	• ADD: Cộng hai số.

	• SUB: Trừ hai số.

	• MUL: Nhân hai số.

	• DIV: Chia hai số.

	• CMP: So sánh hai số.

	• TEST: Kiểm tra các bit của một số

	• JMP: Nhảy không điều kiện đến một địa chỉ khác.

	• JZ: Nhảy nếu kết quả của phép so sánh trước đó bằng 0.

	• JNZ: Nhảy nếu kết quả của phép so sánh trước đó khác 0.

	• LOOP: Lặp lại một đoạn mã.

## Bước 3: Hợp dịch (Assembly)

 - Chuyển đổi mã hợp ngữ thành mã máy hay mã đối tượng.

 - Các lệnh hợp ngữ như 'MOV', 'ADD' được chuyển thành mã nhị phân (0,1) mà CPU có thể hiểu được.

 - Sau đó tạo ra file.o hay file.obj

## Bước 4: Liên kết (Linking)

-  Kết hợp các mã đối tượng (file.o/ file.obj ) và thư viện tiêu chuẩn( file.lib)  lại với nhau tạo  thành file thực thi cuối cùng (file.exe đối với windows).


## Macro là gì?

- Macro là một cơ chế của trình tiền xử lý giúp chúng ta định nghĩa các hằng số, đoạn mã lệnh ngắn gọn có thể thay thế hoặc mở rộng trước khi chương trình được biên dịch

## Tại sao dùng Macro?

 - Để tăng cường tính tái sử dụng đối với những đoạn mã lặp lại, định nghĩa hằng số một cách ngắn gọn.

 - Giúp mã nhanh hơn  hơn so với hàm trong một số trường hợp. Vì macro được xử lý trong giai đoạn tiền xử lý và không tạo ra lời gọi hàm.

 - Dễ dàng bảo trì mã. Khi chúng ta cần thay thế hoặc sửa đổi bạn chỉ cần làm với macro thay vì thay đổi mọi nơi mà đoạn mã hay hằng số đó xuất hiện. 

 - Có thể dùng macro để kiểm tra điều kiện biên dịch giúp chương trình có thể điều chỉnh dựa trên cấu hình hoặc môi trường biên dịch khác nhau.

	


## Có một số macro sau:

#include

 Cho phép chèn nội dung của  tệp khác vào tệp hiện tại trước khi biên dịch.

 Sử dụng dấu '< >' cho các tệp tiêu chuẩn như các tệp tiêu đề header file trong các thư mục mục thư viện chuẩn của hệ thống.

 Sử dụng dấu ' " " ' cho các tệp của người dùng.

#define

Để định nghĩa macro chúng ta dùng cú pháp như sau:

	`#define Tên_macro  giá_trị_hoặc_đoạn_mã`

Các loại macro gồm:

 Macro có tham số: Có thể nhận tham số và thực hiện thao tác trên những tham số đó.

	`#define SQUARE(x) ((x) * (x))`

 Macro không tham số: Định nghĩa một giá trị cố định

	`#define PI 3.14159`

 Để loại bỏ macro ta sử dụng #undef
	

`#if`

-  Nếu điều kiện này đúng thì thực hiện đoạn mã phía dưới.
  
`#elif`

-  Được sử dụng sau #if hoặc #elif để kiểm tra điều khiện thêm nếu điều kiện trước sai.
  
`#else`

- Nếu không có điều kiện nào trước đó đúng thì sẽ thực hiện các câu lệnh sau #else.
  
`#ifdef`

- Dùng để kiểm tra xem macro đã được định nghĩa hay chưa.
  
`#ifndef`

- Dùng để kiểm tra xem macro chưa được định nghĩa.

# **BÀI 2:** 

## Thư viện Stdarg.h dùng để làm gì?


Thư viện này dùng trong trường hợp đầu vào của 1 hàm không xác định về số lượng và kiểu. 


Thư viện giúp chúng ta tạo ra một hàm có lượng đối số biến thiên bằng các macro.


## Các macro chính trong thư viện:


1. Va_list 
	
	- Dùng để khai báo 1 biến kiểu dữ liệu lưu trữ thông tin của danh sách đối số biến đổi

	- Cú pháp: `va_list args;`
	
2. Va_start()
	
	- Dùng để khởi tạo biến lưu trữ danh sách kiểu va_list vừa lưu.

	- Cú pháp: `va_start( args, last_fixed_agr);`

	- ` last_fixed_agr ` là đối số cố định cuối cùng trước khi bắt đầu danh sách đối số biến thiên.

	- Ở đây sẽ bắt đầu trỏ từ đối số đầu tiên sau   `last_fixed_agr`

3. Va_arg()
	
	- Dùng để truy xuất từng đối số trong danh sách đối số biến đổi.

	- Mỗi lần gọi sẽ truy xuất trả về đối số tiếp theo và di chuyển con trỏ tới đối số kế tiếp.

	- Cú pháp:`va_agr(args, int);`

4. Va_end()

	- Dùng để kết thúc việc sử dụng danh sách đối số biến đổi, dọn sạch đối tượng va_list và giải phóng tài nguyên.

	- Cú pháp:`va_end(args);`

## Thư viện Assert.h để làm gì?

 - Dùng để kiểm tra một điều kiện trong mã nguồn và phát hiện lỗi.

 - Thư viện cung cấp 1 macro assert kiểm tra một điều kiện luôn luôn đúng. Nếu sai thì chương trình sẽ dừng và báo lỗi.
 
Cú pháp: `assert(biểu_thức);`

# **Bài 3: Pointer**

![image](https://github.com/user-attachments/assets/8ce0ba7d-98d6-47b5-ac88-908a6f13218b)


## Pointer là gì?

Con trỏ là một loại biến như các biến khác nhưng nó thay vì lưu giá trị trực tiếp thì nó lưu địa chỉ

 của một biến khác trong bộ nhớ. Nó sẽ trỏ tới biến đó và cho phép chúng ta truy cập và thao tác 

với dữ liệu thông qua địa chỉ của biến đó.

Để khai báo con trỏ ta sử dụng cú pháp:

 kiểu _dữ_liệu_*_tên_con_trỏ 

Kích thước của con trỏ dựa vào kiến trúc máy tính và trình biên dịch ( 4 byte - 32 bit, 8 byte - 64 bit)

## Tại sao cần con trỏ?

1. Để truyền tham chiếu trong hàm

	- Khi bạn truyền một biến mà không sử dụng con trỏ, hàm chỉ nhận một bản sao của biến 

	đó. Bất kỳ thay đổi nào trong hàm sẽ không ảnh hưởng tới biến gốc bên ngoài.
	
	- Còn khi dùng con trỏ thì sẽ trực tiếp truy cập và thay đổi biến gốc.
	
2. Quản lý bộ nhớ động
	
	- Có thể yêu cầu cấp phát và giải phóng thông qua các hàm `malloc`, `calloc`, `free`.
	
3. Làm việc với mảng và chuỗi

	- Có thể truy cập và thao tác các phần tử mà không cần chỉ số index.


Ngoài ra nó còn giúp tối ưu hóa hiệu suất chương trình, truy cập và thao tác với phần cứng.

## Các loại  pointer?



### Pointer trỏ đến biến

Đây là con trỏ trỏ đến biến dữ liệu cơ bản

Ví dụ:

 `int a = 5;` 

`int *ptr = &a;`

### Pointer trỏ đến mảng

Con trỏ này sẽ trỏ đến phần tử đầu tiên của mảng

Ví dụ:

`int arr[5];`

`int *ptr = arr;`


### Pointer trỏ đến hàm

Tương tự như cách con trỏ lưu địa chỉ của biến, con trỏ cũng có thể lưu địa chỉ của hàm.

 Con trỏ này lưu giá trị của địa chỉ nơi hàm bắt đầu trong bộ nhớ. Nó thường được sử dụng để 
gọi hàm thông qua con trỏ hoặc thực hiện callback hàm khác khi nó là tham số của hàm.

	void Function(int a) {
 
    printf("Value: %d\n", a);
	}

	void (*funcPtr)(int) = &Function;
 
	funcPtr(10); // Gọi hàm Function thông qua con trỏ
	

### Null Pointer

Null Pointer là con trỏ không trỏ đến bất kỳ đối tượng nào và có giá trị và địa chỉ là 0x0.

 Đây là con trỏ đặc biệt thường được sử dụng để kiểm tra xem con trỏ có hợp lệ hay không 

 trước khi truy cập vào vùng nhớ mà nó trỏ tới.

### Void Pointer

Void Pointer (con trỏ vô định) là con trỏ có thể trỏ đến bất kỳ loại dữ liệu nào,

 nhưng khi truy xuất dữ liệu, bạn cần phải ép kiểu con trỏ này sang kiểu con trỏ thích hợp.


`void *ptr;`

`int a = 5;`

`ptr = &a;`

`printf("%d\n", *(int *)ptr); // Ép kiểu sang int* trước khi dereference`


### Const Pointer

Const Pointer là con trỏ trỏ đến một địa chỉ và không thể thay đổi địa chỉ mà nó trỏ tới sau khi 

đã được khởi tạo.  

`
int a = 5;`

`int b = 10;`

`int *const ptr = &a;`

`ptr = &b; // Lỗi: không thể thay đổi địa chỉ mà ptr trỏ tới`


### Pointer to const

Pointer to const là con trỏ trỏ tới một giá trị không thể thay đổi, nhưng bản thân con trỏ có thể

 được thay đổi để trỏ đến một địa chỉ khác.

`
const int a = 5;`

`const int b = 10;`

`const int *ptr = &a;`

`ptr = &b; // Hợp lệ, nhưng không thể thay đổi giá trị của b thông qua ptr
`

### Dangling Pointer

Dangling Pointer là con trỏ trỏ đến một địa chỉ không còn hợp lệ, thường xảy ra sau khi bộ nhớ 

đã bị giải phóng. 

### Pointer trỏ đến Pointer

![image](https://github.com/user-attachments/assets/5740e966-0a17-4e9f-ad5d-3a644bfeef92)


Đây là con trỏ lưu địa chỉ của một con trỏ khác. Nó được sử dụng trong các trường hợp cần xử lý

 nhiều cấp độ tham chiếu.

`int a = 5;`

`int *ptr = &a;`

`int **ptr2 = &ptr; // ptr2 trỏ đến con trỏ ptr`



