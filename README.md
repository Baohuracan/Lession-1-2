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


# Bài 4: Extern - Static - Volatile - Register




## `Extern`

Từ khóa `extern` được dùng để khai báo biến hoặc hàm đã được định nghĩa ở một tệp khác và cần được sử dụng trong tệp hiện tại.


### Ví dụ

**Tệp `main.c`:**
```c
#include <stdio.h>
extern void display();

int main() {
    printf("Hello");
    display();
}
```

**Tệp `other.c`:**
```c
#include <stdio.h>

void display() {
    printf("Bao");
}
```

### Để chạy hai tệp này liên kết với nhau, chúng ta làm như sau:

1. Biên dịch từng tệp thành các tệp đối tượng:
    ```bash
    gcc -c main.c
    gcc -c other.c
    ```

2. Sử dụng `gcc` để liên kết các tệp đối tượng thành một tệp thực thi:
    ```bash
    gcc main.o other.o -o main
    ```

3. Chạy chương trình:
    ```bash
    ./main.exe
    ```

---

## `Static`

Biến `static` sẽ tồn tại suốt vòng đời chương trình, không chỉ trong phạm vi hàm.

- Thường được sử dụng khi viết thư viện mà bạn không muốn người dùng can thiệp vào các biến, họ chỉ có thể sử dụng thư viện của bạn.

- Đối với biến static cục bộ trong hàm, biến này chỉ được khởi tạo một lần duy nhất và giữ nguyên giá trị giữa các lần gọi hàm.

### Ví dụ đếm biến `count`:

**Tệp `main.c`:**
```c
#include <stdio.h>

void dem() {
    static int count = 0;
    count++;
    printf("count: %d\n", count);
}

int main() {
    for (int i = 0; i < 4; i++) {
        dem();
    }
}
```

**Kết quả:**
```
count: 1
count: 2
count: 3
count: 4
```

---

## `Register`

![image](https://github.com/user-attachments/assets/601de82b-2f52-4cc5-8261-5f6145fa3c70)


Khi sử dụng biến `register`, biến sẽ được lưu trữ trong thanh ghi, giúp xử lý nhanh hơn.

- Không phải tất cả các biến đều được lưu trong thanh ghi vì giới hạn số lượng thanh ghi.

- Trình biên dịch hiện đại như `gcc` đã được tối ưu hóa tốt để quyết định liệu có nên đặt biến trong thanh ghi hay không.

### Ví dụ đo thời gian thực thi của một đoạn mã:

**Tệp `main.c`:**
```c
#include <stdio.h>
#include <time.h>

int main(void) {
    register unsigned long i;
    clock_t start, end;
    double cpu_time_used;

    // Bắt đầu đo thời gian
    start = clock();

    // Vòng lặp trống để tiêu tốn thời gian CPU
    for (i = 0; i < 99999999; i++);

    // Kết thúc đo thời gian
    end = clock();

    // Tính toán thời gian CPU đã sử dụng
    cpu_time_used = ((double)(end - start)) / CLOCKS_PER_SEC;

    // In ra thời gian thực thi
    printf("Time: %f seconds\n", cpu_time_used);

    return 0;
}
```

**Kết quả:**
```
Time: 0.024000 seconds
```

---

## `Volatile`

Biến `volatile` sẽ không bị trình biên dịch tối ưu hóa.

- Thường sử dụng cho các trường hợp biến có thể thay đổi đột ngột từ bên ngoài (ví dụ: ngắt, đầu đọc USB).

- Trình biên dịch không được tối ưu hóa việc truy cập đến biến `volatile`, tức là mỗi lần truy cập, giá trị của biến sẽ được đọc trực tiếp từ bộ nhớ, không phải từ thanh ghi.

- Từ khóa này thường được sử dụng trong các ứng dụng hệ thống nhúng, nơi mà giá trị của biến có thể thay đổi mà không được chương trình trực tiếp thay đổi, như từ một phần cứng khác.

### Ví dụ:

**Tệp `main.c`:**
```c
volatile int flag = 0;

void checkFlag() {
    while (flag == 0) {
        // Trình biên dịch sẽ không tối ưu hóa và sẽ liên tục đọc giá trị từ bộ nhớ.
    }
}
```

**Lưu ý:**
- **Lưu trữ biến trong thanh ghi:** Nhanh nhưng không thể thay đổi giá trị từ bên ngoài mà trình biên dịch biết được ngay lập tức.
- **Lưu trữ biến trong bộ nhớ:** Chậm hơn nhưng cho phép giá trị biến có thể thay đổi từ bên ngoài.
- **volatile** đảm bảo rằng biến được đọc từ bộ nhớ mỗi lần truy cập, giúp chương trình xử lý đúng với những thay đổi không dự đoán được, như từ ngắt hoặc phần cứng.

---



---

# Bài 5: `goto` và `setjmp.h`

## 1. `goto` là gì?

`goto` là một lệnh trong ngôn ngữ lập trình C cho phép bạn nhảy tới một nhãn (label) trong cùng một hàm. Nó thường được sử dụng để điều khiển dòng chảy của chương trình một cách rõ ràng, chẳng hạn như để thoát khỏi các vòng lặp phức tạp hoặc các khối mã lồng nhau.

### Khi nào nên dùng `goto`?
- Thoát khỏi nhiều vòng lặp lồng nhau.
- Xử lý lỗi hoặc tình huống khẩn cấp khi không có cách nào khác rõ ràng và sạch sẽ hơn.

### Khi nào không nên dùng `goto`?
- Khi có thể đạt được mục đích bằng cách sử dụng các cấu trúc điều khiển dòng chảy khác như `break`, `continue`, hoặc `return`.
- Tránh lạm dụng `goto` vì nó có thể làm cho mã trở nên khó hiểu và khó bảo trì.

### Ví dụ về `goto`:

```c
#include <stdio.h>

int main() {
    int count = 0;
    
    while (1) {
        count++;
        printf("Count: %d\t", count);
        
        if (count > 9) {
            printf("Stop!");
            goto exit;  // Nhảy đến nhãn "exit" để thoát khỏi vòng lặp
        }
    }
    
exit:  // Nhãn "exit"
    return 0;
}
```

**Giải thích:**
- Trong ví dụ trên, `goto` được sử dụng để thoát khỏi vòng lặp khi biến `count` lớn hơn 9. Lệnh `goto` nhảy đến nhãn `exit`, làm kết thúc vòng lặp.

---

## 2. `setjmp` và `longjmp` trong C

### `setjmp.h` là gì?

Thư viện `setjmp.h` trong C cung cấp hai hàm chính là `setjmp` và `longjmp`, cho phép bạn lưu trạng thái của chương trình tại một điểm và khôi phục lại trạng thái đó ở một điểm khác, tương tự như cơ chế xử lý ngoại lệ.

- **`setjmp(jmp_buf env)`**: Lưu trạng thái hiện tại của chương trình vào biến `env` và trả về giá trị 0 khi được gọi lần đầu.
- **`longjmp(jmp_buf env, int val)`**: Khôi phục lại trạng thái đã lưu trong `env` và trả về giá trị `val` cho hàm `setjmp`.

### Khi nào dùng `setjmp` và `longjmp`?
- Xử lý lỗi hoặc ngoại lệ mà không sử dụng cấu trúc try-catch.
- Thoát khỏi các hàm lồng nhau hoặc vòng lặp khi gặp phải lỗi.

### Ví dụ sử dụng `setjmp` và `longjmp`:

```c
#include <stdio.h>
#include <setjmp.h>

jmp_buf buf;

int main() {
    int exception_code = setjmp(buf);

    if (exception_code != 10) {
        for (int i = 0; i < 10; i++) {
            printf("Lần thứ %d: 2\n", i + 1);
        }
        longjmp(buf, 10);  // Quay lại `setjmp` và trả về giá trị 10
    }
    
    if (exception_code == 10) {
        printf("Dừng\n");
    }

    return 0;
}
```

**Giải thích:**
- Khi `setjmp(buf)` được gọi lần đầu, nó trả về 0 và chương trình tiếp tục thực hiện in số "2" mười lần.
- Sau khi in xong, `longjmp(buf, 10)` được gọi, làm khôi phục lại trạng thái đã lưu bởi `setjmp` và trả về giá trị 10.
- Giá trị 10 được kiểm tra, và khi khớp, chương trình in ra "Dừng" và kết thúc.

---



# **Bài 6**: Bitmask

## Bitmask là gì

![image](https://github.com/user-attachments/assets/5f21a57b-3a08-426e-8200-c7f3f716a82d)



Là một dãy các bit được dùng để thao tác với các bit cụ thể thông qua các toán tử bitwise 

Bitmask cho phép chúng ta kiểm soát (bật,tắt, kiểm tra) một bit cụ thể trong một số khác

## Tại sao sử dụng bit fields?

Mục đích sử dụng là tối ưu bộ nhớ, lưu trữ và quản lý thông tin.

Tiết kiệm bộ nhớ: Thay vì dùng cả một biến 8-bit, 16-bit hoặc 32-bit cho từng giá trị nhỏ, bạn có thể chỉ định chính xác số bit cần thiết.

Điều khiển chi tiết: Bit fields hữu ích khi bạn cần lưu trữ và quản lý thông tin có cấu trúc nhỏ, chẳng hạn như trạng thái của phần cứng trong hệ thống nhúng.

Ứng dụng trong lập trình cấp thấp nơi mà hiệu quả bộ nhớ và hiệu suất là điều quan trọng ví dụ như viết drive hoặc hệ thống nhúng.

## Gồm những loại nào?

Những toán tử phổ biến như sau:

### AND : &

- Thường dùng để kiểm tra một bit có được bật hay không
- AND chỉ trả về  những nơi cả hai có bit là 1 nên có thể kiểm tra các bit cụ thể
  
![image](https://github.com/user-attachments/assets/60251f53-40a4-4a1d-8a1c-7a70d24cf813)

Ví dụ:
 
	   0101 1010 (trạng thái hiện tại của LED)
	&  1111 0111 (bitmask để tắt LED thứ 3)
	--------------
	   0101 0010 (trạng thái mới của LED sau khi tắt LED thứ 3)
	
	Giả sử phép toán AND theo bit của hai số nguyên 12 và 25.


### OR : |

- Thường dùng để bật (set) các bit
- OR trả về 1 nếu một trong hai bit là 1. Giúp bật một bit cụ thể mà không thay đổi các bit khác.
![image](https://github.com/user-attachments/assets/62e8616f-29d1-4f00-8b16-ad2b6592f45a)

Ví dụ:
		`   0101 0010 (trạng thái hiện tại của LED)
		|  0000 1000 (bitmask để bật LED thứ 4)
		--------------
		   0101 1010 (trạng thái mới của LED sau khi bật LED thứ 4)`


### XOR : ^

- Thường dùng để đảo ngược các bit cụ thể
- XOR trả về 1 nếu hai bit khác nhau. Giúp đổi trạng thái (toggle) của 1 bit
![image](https://github.com/user-attachments/assets/f7da0918-82af-4347-b827-cc7bdf9a5f79)

Ví dụ:

		   0101 1010 (trạng thái hiện tại của LED)
		^  0000 1000 (bitmask để đảo trạng thái LED thứ 4)
		--------------
		   0101 0010 (trạng thái mới của LED sau khi đảo trạng thái LED thứ 4)


### NOT: ~

 - Thường dùng để đảo ngược toàn bộ các bit ( từ 0 thành 1, từ 1 thành 0)
	
![image](https://github.com/user-attachments/assets/ff06d315-c372-423d-afb7-2ec479be6d79)

Ví dụ:

	   0101 1010 (trạng thái hiện tại của LED)
	~  ------------
	   1010 0101 (trạng thái mới của LED sau khi dùng NOT)




---

# Bài 7: Struct - Union
![image](https://github.com/user-attachments/assets/d0d8dc11-451a-4b48-9296-43cafc30f64d)

## Struct là gì?
Struct (cấu trúc) là một kiểu dữ liệu do người dùng tự định nghĩa, cho phép lưu trữ nhiều kiểu dữ liệu khác nhau trong một đối tượng duy nhất.

### Cú pháp:
```c
struct structure_name {
    data_type member1;
    data_type member2;
    ...
    data_type memberN;
};
```

### Ví dụ:
```c
struct employee {
    int id;
    char name[50];
    float salary;
};
```

## Mục đích của Struct
Struct giúp lưu trữ một tập hợp dữ liệu liên quan, giúp việc quản lý dữ liệu dễ dàng và rõ ràng hơn.

## Các thao tác với Struct

### Khởi tạo thành viên
- **Khai báo trong hàm main**:
```c
struct employee e1, e2;
```
- **Khai báo trực tiếp khi định nghĩa cấu trúc**:
```c
struct employee {
    int id;
    char name[50];
    float salary;
} e1, e2;
```

### Truy cập thành viên
- Sử dụng toán tử chấm (`.`) để truy cập các thành viên của struct.
- Sử dụng toán tử con trỏ (`->`) khi làm việc với con trỏ trỏ tới struct.

### Ví dụ:
```c
#include <stdio.h>

struct employee {
    int id;
    char name[50];
    float salary;
};

int main() {
    struct employee e1;
    struct employee *ptr = &e1;

    e1.id = 1;
    ptr->id = 2;
    
    printf("ID: %d\n", ptr->id);
    return 0;
}
```

### Sử dụng typedef để tạo bí danh cho struct
```c
#include <stdio.h>

typedef struct employee {
    int id;
    char name[50];
    float salary;
} Employee;

int main() {
    Employee e1 = {1, "John", 5000.50};

    printf("ID: %d, Name: %s\n", e1.id, e1.name);
    return 0;
}
```

## Cách tính kích thước của struct
Kích thước của một struct được tính bằng tổng kích thước của tất cả các thành viên cộng thêm bộ nhớ lấp đầy (nếu có). Mỗi thành viên của struct sẽ có vùng nhớ riêng biệt.


```c

#include <stdio.h>
#include <stdint.h>

typedef struct sizeofstruct
{
//1byte    
uint8_t arr1[5]; 
//4byte    
uint32_t arr3[1];
//2byte    
uint16_t arr2[3];

} frame;
int main()
{
    printf("kich thuoc:%d",sizeof(frame));
}
```


   	kich thuoc:20
---


![image](https://github.com/user-attachments/assets/1cc8268c-024b-4f73-a205-47dd68a75278)


## Union là gì?
Union cũng là một kiểu dữ liệu do người dùng tự định nghĩa, tương tự như struct. Tuy nhiên, các thành viên của union sử dụng chung một vùng nhớ và chỉ một thành viên có thể được lưu trữ tại một thời điểm.
![image](https://github.com/user-attachments/assets/a5395718-0d51-4612-8d8b-0c87a36aa7d4)

### Cú pháp:
```c
union union_name {
    data_type member1;
    data_type member2;
    ...
    data_type memberN;
};
```

### Ví dụ:
```c
union employee {
    int id;
    char name[50];
    float salary;
};
```

## Mục đích của Union
Union được sử dụng khi bạn cần lưu trữ và truy cập nhiều kiểu dữ liệu, nhưng chỉ cần sử dụng một thành viên tại một thời điểm, giúp tiết kiệm bộ nhớ.

## Cách tính kích thước của Union
Kích thước của một union bằng kích thước của thành viên lớn nhất, vì tất cả các thành viên dùng chung một vùng nhớ.

```c

#include <stdio.h>
#include <stdint.h>
typedef union sizeofunion
{
    uint8_t arr1; //1 byte
    uint32_t arr3; // 4 byte
    uint16_t arr2; //  2 byte
    
} frame;



int main()
{
    frame data;
    //data.arr1 = 5;
    data.arr2 =65530;
    //data.arr3 = 2;
    printf("arr1: %d\n",data.arr1);
    printf("arr1: %d\n",data.arr2);
    printf("arr1: %d\n",data.arr3);
    printf("%d",sizeof(frame));

}
```

`
arr1: 250
arr1: 65530
arr1: 65530
4 `

![image](https://github.com/user-attachments/assets/69a19bc5-1206-4b0e-98af-674bd3f549e4)

### Ví dụ:
```c
#include <stdio.h>

union data {
    int int_val;
    float float_val;
    char char_val[20];
};

int main() {
    union data d;
    
    d.int_val = 42;
    printf("Int value: %d\n", d.int_val);
    
    d.float_val = 3.14;
    printf("Float value: %.2f\n", d.float_val);  // Lúc này int_val bị ghi đè
    
    return 0;
}
```

### Sự khác biệt giữa Struct và Union:
- **Struct**: Các thành viên có vùng nhớ riêng, có thể truy cập đồng thời nhiều thành viên.
- **Union**: Các thành viên dùng chung một vùng nhớ, chỉ một thành viên có thể được truy cập tại một thời điểm.

---


### Ứng dụng trong truyền dữ liệu trong Nhúng

```c
#include <stdio.h>
#include <stdint.h>
#include <string.h>

typedef union {
    struct {
        uint8_t id[2];
        uint8_t data[4];
        uint8_t check_sum[2];
    } data;
    uint8_t frame[8];
} Data_Frame;

int main(int argc, char const *argv[])
{
    Data_Frame transmitter_data;
    
    strcpy(transmitter_data.data.id, "10");
    strcpy(transmitter_data.data.data, "1234");
    strcpy(transmitter_data.data.check_sum, "70");
        Data_Frame receiver_data;
    strcpy(receiver_data.frame, transmitter_data.frame);
    
    
    return 0;
}
```


• Data_Frame là một union, cho phép truy cập dữ liệu theo hai cách:
	• Qua data (một cấu trúc gồm các thành phần con id, data, và check_sum).
	• Qua frame (một mảng uint8_t với 8 phần tử).
• Lý do sử dụng union ở đây là để tiết kiệm bộ nhớ và dễ dàng truyền hoặc sao chép toàn bộ khung dữ liệu một cách đơn giản bằng cách truy cập frame.


#  **Bài 8: Stack - Queue** 

## Stack là gì ?
Stack là cấu trúc dữ liệu tuyến tính tuân theo nguyên tắc Last in, First out (LIFO) về chèn và xóa dữ liệu.

![image](https://github.com/user-attachments/assets/e4014af7-1752-41bf-9b73-35fa24b5cbb6)


## Mục đích của Stack là gì? 

Stack thường được dùng cho các tác vụ như :

	- Đánh giá biểu thức (Expression Evaluation)
	- Quản lý bộ nhớ và lời gọi hàm (Fuction call management)
	- Thuật toán quay lui xử lý bởi đệ quy (Backtracking Algorithms) 
	- Duyệt đồ thị/cây: Trong thuật toán duyệt theo chiều sâu (DFS), stack đóng vai trò lưu trữ các nút đang được xử lý.

## Cách hoạt động của Stack?

Phần tử được thêm vào cuối cùng sẽ là phần tử được lấy ra đầu tiên.

Cấu trúc của Stack:

![image](https://github.com/user-attachments/assets/cfa760d1-bece-4a68-8fc0-98b5b3684824)



	- Stack có thể được triển khai bằng mảng (array) hoặc danh sách liên kết ( linked list )
	- Các thao tác chính trên Stack là:
		○ Push: Thêm phần tử vào đỉnh Stack
		○ Pop: Lấy phần tử khỏi đỉnh Stack
		○ Peek (Top): Xem phần tử trên đỉnh mà không xóa nó
		○ IsEmpty: Kiểm tra xem stack có rỗng không
		○ IsFull: Kiểm tra xem  stack có đầy không


### Các hoạt động cơ bản của Stack trong C

#### Push

Hàm push sẽ thêm hoặc đẩy một phần tử vào ngăn xếp. Chúng ta phải kiểm tra xem ngăn xếp đã đầy chưa trước khi chèn một phần tử mới để tránh tràn ngăn xếp (stack overflow).

** Algorithm of stack push**

	1. Kiểm tra xem ngăn xếp đã đầy chưa
	2. Nếu ngăn xếp đã đầy thì thông báo tràn
	3. Nếu ngăn xếp chưa đầy thì tăng con trỏ trên cùng lên một đơn vị
	4. Tiến hành thêm một phần tử mới vào vị trí con trỏ trỏ tới



![image](https://github.com/user-attachments/assets/bc471509-9b64-4f16-aeac-432777b8d90e)



#### Pop

Khi thực hiện thao tác pop, phần tử trên đỉnh của stack sẽ bị lấy ra. Sau đó đỉnh của stack sẽ giảm xuống để trỏ đến phần tử kế tiếp.

 Khi chúng ta muốn xóa phần tử trên cùng khi ngăn xếp đã rỗng thì đó gọi là tràn ngăn xếp hay là rỗng ngăn xếp (stack underflow).

**Algorithms of stack pop**

	1. Kiểm tra xem ngăn xếp có trống không
	2. Nếu ngăn xếp trống thì hiển thị tràn bộ nhớ
	3. Nếu ngăn xếp không rỗng thì xóa phần tử ở vị trí trên cùng
	4. Giảm con trỏ trên cùng của ngăn xếp

![image](https://github.com/user-attachments/assets/5f157cee-30a7-4903-93f0-ced3a31abfcc)


Bạn không cần phải gán phần tử đã lấy ra thành null trong C. Khi sử dụng ngăn xếp, chỉ số top chính là công cụ để quản lý việc thêm/xóa phần tử.

 Sau khi phần tử được "lấy ra", top sẽ giảm, và những phần tử nằm sau top sẽ không còn được coi là hợp lệ trong ngăn xếp nữa.

#### Top (Peek)

Hàm top này sẽ trả về phần tử hiện đang nằm trên cùng của ngăn xếp mà không xóa nó.

**Algorithms for stack top function**

	1. Kiểm tra xem có trống không.
	2. Nếu trống, trả về -1.
	3. Nếu không trống thì trả về phần tử stack.data[top].

Việc sử dụng hàm peek() thay vì truy xuất trực tiếp phần tử trên đỉnh stack giúp:

	• Đảm bảo an toàn cho chương trình.
	• Giảm sự lặp lại mã nguồn.
	• Giữ mã dễ đọc và bảo trì.
	• Tạo tính linh hoạt và dễ mở rộng khi cần thêm chức năng.
	
Việc này cũng phù hợp với nguyên tắc lập trình tốt là viết mã an toàn và dễ bảo trì


	
#### IsFull function

Hàm này cung cấp thông tin về việc ngăn xếp có còn chỗ trống không hay đã đầy hoàn toàn. 

Dung lượng tối đa của ngăn xếp là MAX_SIZE phần tử. Vậy giá trị tối đa của top có thể là MAX_SIZE - 1.

** Algorithms of stack IsFull**

	1. Nếu top >= MAXSIZE - 1, trả về giá trị true.
	2. Nếu không trả về false.


#### IsEmpty

Hàm này kiểm tra xem ngăn xếp có rỗng hay không. Khi ngăn xếp rỗng thì top = -1. 

**Algorithms of Stack IsEmpty

	1. Nếu con trỏ trên cùng == -1 trả về true 
	2. Nếu không thì trả về false.

#### Cách hoạt động cụ thể

Giả sử ta có một stack có kích thước 5, và ta thực hiện các thao tác:

	1. Push 10:
		○ Stack sau khi thêm 10: [10]
		○ Đỉnh của stack trỏ đến 10.
	2. Push 20:
		○ Stack sau khi thêm 20: [10, 20]
		○ Đỉnh của stack giờ trỏ đến 20.
	3. Push 30:
		○ Stack sau khi thêm 30: [10, 20, 30]
		○ Đỉnh của stack trỏ đến 30.
	4. Pop:
		○ Lấy phần tử trên đỉnh là 30, và đỉnh giảm xuống trỏ đến 20.
		○ Stack sau khi lấy phần tử: [10, 20]
	5. Peek:
		○ Xem phần tử trên đỉnh hiện tại là 20, nhưng không xóa nó.
	6. IsEmpty:
		○ Kiểm tra stack có rỗng không. Stack hiện có phần tử, nên kết quả là "Không rỗng".


---
# **Queue trong C**

## Queue là gì?

Là một cấu trúc dữ liệu theo nguyên tắc FIFO (First In First Out). Phần tử được thêm vào đầu tiên sẽ lấy ra đầu tiên.

## Mục đích của Queue là gì?

	- Quản lý tài nguyên trong hệ thống
	- Truyền thông giữa các tiến trình (Interprocess Communication)
	- Sử dụng trong các hệ thống đệm I/O (Buffering I/O Systems)
	- Tìm kiếm theo chiều rộng (Breadth-first-search)

## Cách hoạt động của Queue 

Chúng ta có thể triển khai Queue trong C bằng cách sử dụng mảng hoặc danh sách liên kết. Ở đây chúng ta sẽ sử dụng cấu trúc dữ liệu mảng để lưu trữ các phần tử.

Việc chèn hàng đợi được thực hiện ở phía sau còn việc xóa được thực hiện ở phía trước. Vì vậy chúng ta duy trì 2 con trỏ chỉ mục rear để theo dõi phía sau và front để theo dõi phía trước hàng đợi.

Queue gồm hai thao tác cơ bản đó là thêm các phần tử mới vào hàng đợi là enqueue (insertion) từ con trỏ rear và xóa phần tử khỏi hàng đợi là dequeue (deletetion) từ con trỏ front.

![image](https://github.com/user-attachments/assets/9d03e227-1101-494b-9cab-c6cc29714340)


### Biểu diễn Queue trong C

Queue có thể được biểu diễn dưới một cấu trúc chứa một mảng cố định. Có con trỏ trỏ đến đầu và cuối.

```C
Struct Queue
{
	Int arr[MAX_SIZE];
	Int front;
	Int rear;

}
```

• front luôn trỏ đến phần tử sắp bị lấy ra (nếu bạn thực hiện thao tác dequeue).

Con trỏ phía trước (front pointer):
	• Con trỏ front (phía trước) thường dùng để chỉ đến phần tử đầu tiên trong hàng đợi. Khi ta thực hiện thao tác dequeue, con trỏ này sẽ di chuyển đến phần tử kế tiếp, trỏ đến phần tử mà sẽ bị lấy ra trong lần dequeue tiếp theo.
	• Giá trị khởi tạo của con trỏ front là -1, có nghĩa là hàng đợi đang trống, chưa có phần tử nào được thêm vào.


• rear trỏ đến vị trí trống tiếp theo (nếu bạn thực hiện thao tác enqueue).

. Con trỏ phía sau (rear pointer):
	• Con trỏ rear (phía sau) dùng để chỉ đến vị trí cuối cùng trong hàng đợi. Khi ta thực hiện thao tác enqueue, con trỏ này sẽ di chuyển đến phần tử trống tiếp theo, nơi mà phần tử mới được thêm vào.
	• Giá trị khởi tạo của con trỏ rear là -1 (tương tự như front), nghĩa là hàng đợi ban đầu trống.


Ví dụ minh họa:

Giả sử hàng đợi của bạn có kích thước tối đa là 5 và bạn thực hiện các thao tác trên hàng đợi:

	1. Hàng đợi rỗng:


	front = -1
	rear = -1
	[ - , - , - , - , - ]
	2. Thêm phần tử đầu tiên (enqueue): Thêm 10 vào hàng đợi.

	front = 0
	rear = 0
	[ 10 , - , - , - , - ]
	3. Thêm phần tử thứ hai (enqueue): Thêm 20 vào hàng đợi.


	front = 0
	rear = 1
	[ 10 , 20 , - , - , - ]
	4. Lấy phần tử đầu tiên (dequeue): Lấy 10 ra khỏi hàng đợi.

	front = 1
	rear = 1
	[ - , 20 , - , - , - ]
	5. Thêm phần tử mới (enqueue): Thêm 30 vào hàng đợi.

	front = 1
	rear = 2
	[ - , 20 , 30 , - , - ]


### Cách thao tác chính với Queue

Các hoạt động cơ bản của Queue:

- Enqueue: Chèn một phần tử vào hàng đợi thông qua rear pointer.
- Dequeue: Xóa một phần tử khỏi hàng đợi thông qua front pointer.
- Peek/front: Trả về phần tử đầu tiên của hàng đợi.
- isFull: Trả về true nếu hàng đợi đã đầy, nếu không trả về false.
- isEmpty: Trả về true nếu hàng đợi trống, nếu không trả về false.
- Size: trả về số lượng phần tử hiện tại đang trong hàng đợi.

#### EnQueue

Hàm này chèn một phần tử thông qua rear pointer. Phải kiểm tra xem hàng đợi đã đầy hay chưa  để tránh Queue overflow.

** Algorithmes of Enqueue function **
	1. Kiểm tra hàng đợi có đầy không.
	2. Nếu hàng đợi đầy thì hiển thị thông báo tràn.
	3. Nếu hàng đợi chưa đầy thì tăng giá trị của con trỏ rear
	4. Thêm phần tử mới vào vị trí con trỏ rear trỏ tới.

``` C
void enqueue(struct Queue* q, int value) {
    if (isFull(q)) {
        printf("Hàng đợi đầy, không thể thêm phần tử.\n");
    } else {
        if (q->front == -1) {
            q->front = 0;  // Đặt front cho phần tử đầu tiên
        }
        q->rear++;
        q->items[q->rear] = value;
        printf("Đã thêm %d vào hàng đợi.\n", value);
    }
}
```

#### Dequeue

Hàm này xóa một phần tử khỏi phía trước hàng đợi thông qua con trỏ front. Chúng ta cần kiểm tra xem hàng đợi có trống không trước khi xóa phần tử để tránh queue underflow.


**Algorithms of Dequeue function **

	1. Kiểm tra xem hàng đợi có trống không
	2. Nếu hàng đợi trống thì hiển thị thông báo rỗng hàng đợi
	3. Nếu không thì tăng con trỏ đầu tiên của hàng đợi lên
	4. Loại bỏ phần tử ở phía trước


```C
int dequeue(struct Queue* q) {
    int item;
    if (isEmpty(q)) {
        printf("Hàng đợi rỗng, không thể lấy phần tử.\n");
        return -1;
    } else {
        item = q->items[q->front];
        if (q->front == q->rear) {
            // Nếu chỉ còn một phần tử, đặt lại hàng đợi về trạng thái rỗng
            q->front = -1;
            q->rear = -1;
        } else {
            q->front++;
        }
        printf("Đã lấy %d khỏi hàng đợi.\n", item);
        return item;
    }
}

```


#### Peek / front

Hàm này trả về phần tử đầu tiên của hàng đợi, nếu rỗng nó trả về -1.

**Algorithms of front  function **

	1. Kiểm tra xem hàng đợi có trống không
	2. Nếu trống thì trả về -1
	3. Nếu không thì trả về queue.items[queue.front]

```C
int peek(struct Queue* q) {
    if (isEmpty(q)) {
        printf("Hàng đợi rỗng, không có phần tử để xem.\n");
        return -1;
    } else {
        return q->items[q->front];
    }
}


```
#### isFull

Hàm này sẽ kiểm tra xem hàng đợi có đầy hay không


**Algorithms of isFull function **

	1. Nếu rear == MAX_SIZE đúng thì trả về true
	2. Nếu không thì trả về false

```C
#define MAX_SIZE 5

struct Queue {
    int items[MAX_SIZE];
    int front;
    int rear;
};

// Hàm isFull kiểm tra xem hàng đợi có đầy không
int isFull(struct Queue* q) {
    if (q->rear == MAX_SIZE - 1) {
        return 1; // true - hàng đợi đầy
    } else {
        return 0; // false - hàng đợi chưa đầy
    }
}

```


#### isEmpty

Hàm này sẽ kiểm tra xem hàng đợi có trống hay không.

**Algorithms of isEmpty **

	1. Nếu front == -1 thì trả về true
	2. Nếu không thì trả về false

```C
int isEmpty(struct Queue* q) {
    if (q->front == -1) {
        return 1; // true - hàng đợi rỗng
    } else {
        return 0; // false - hàng đợi không rỗng
    }
}

```

#### size

Hàm này sẽ trả về số lượng phần tử hiện tại trong queue

** Algorethms of size function **

	1. Nếu hàm isFull trả về true thì  trả về MAX_SIZE
	2. Nếu hàm isEmpty trả về false thì trả về 0
	3. Nếu không thì tính kích thước bằng cách: (rear - front) + 1

```C
int size(struct Queue* q) {
    if (isEmpty(q)) {
        return 0; // Hàng đợi rỗng
    } else if (isFull)
{
Return 5;
{ else {
        return (q->rear - q->front) + 1;
    }
}

```




