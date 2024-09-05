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

Mục đích sử dụng là tối ưu bộ nhớ, lưu trữ và quản lý thông tin.

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



