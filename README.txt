BÀI 1:
Trình biên dịch là gì ?


	- Trình biên dịch là một chương trình máy tính  có nhiệm vụ dịch một mã nguồn được viết bằng 1 ngôn ngữ lập trình cấp cao thành một chương trình tương đương dưới dạng  ngôn ngữ máy (010101...) hoặc ngôn ngữ bậc thấp ( assembly).

Tại sao cần trình biên dịch?

	- Máy tính chỉ hiểu và thực thi các lệnh ở dạng mã máy, một chuỗi các số 0 và 1. Còn con người thì sử dụng và viết các lệnh bằng ngôn ngữ bậc cao. Và trình biên dịch đóng vai trò là cầu nối để máy tính hiểu và thực thi các lệnh của chúng ta.


Quá trình biên dịch của Compiler trải qua 4 bước như sau:


Bước 1: Tiền xử lý (Preprocessing)
	- Đầu tiên file chúng ta code sẽ được lưu dưới dạng file.c / file.cpp
	- Sau đó trình biên dịch xóa bỏ comment sẽ xử lý các chỉ thị tiền xử lý ( preprocessor directives ) như #include, #define, #if và các macro khác thành một tệp  file.i
	- Tệp này bao gồm mã nguồn đã được mở rộng và các chỉ thị tiền xử lý đã được xử lý.
Bước 2: Biên dịch (Compilation)
	-  Chuyển đổi mã nguồn C đã được tiền xử lý thành mã hợp ngữ (assembly code ) thành một tệp dạng file.s
	- Một số lệnh hợp ngữ cơ bản: 
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
Bước 3: Hợp dịch (Assembly)
	- Chuyển đổi mã hợp ngữ thành mã máy hay mã đối tượng.
	- Các lệnh hợp ngữ như 'MOV', 'ADD' được chuyển thành mã nhị phân (0,1) mà CPU có thể hiểu được.
	- Sau đó tạo ra file.o hay file.obj
Bước 4: Liên kết (Linking)
	- Kết hợp các mã đối tượng (file.o/ file.obj ) và thư viện tiêu chuẩn( file.lib)  lại với nhau tạo  thành file thực thi cuối cùng (file.exe đối với windows).


Macro là gì?
Macro là một cơ chế của trình tiền xử lý giúp chúng ta định nghĩa các hằng số, đoạn mã lệnh ngắn gọn có thể thay thế hoặc mở rộng trước khi chương trình được biên dịch

Tại sao dùng Macro?
	- Để tăng cường tính tái sử dụng đối với những đoạn mã lặp lại, định nghĩa hằng số một cách ngắn gọn.
	- Giúp mã nhanh hơn  hơn so với hàm trong một số trường hợp. Vì macro được xử lý trong giai đoạn tiền xử lý và không tạo ra lời gọi hàm.
	- Dễ dàng bảo trì mã. Khi bạn cần thay thế hoặc sửa đổi bạn chỉ cần làm với macro thay vì thay đổi mọi nơi mà đoạn mã hay hằng số đó xuất hiện. 
	- Có thể dùng macro để kiểm tra điều kiện biên dịch giúp chương trình có thể điều chỉnh dựa trên cấu hình hoặc môi trường biên dịch khác nhau.

	


Có một số macro sau:
#include
	- Cho phép chèn nội dung của  tệp khác vào tệp hiện tại trước khi biên dịch.
	- Sử dụng dấu '< >' cho các tệp tiêu chuẩn như các tệp tiêu đề header file trong các thư mục mục thư viện chuẩn của hệ thống.
	- Sử dụng dấu ' " " ' cho các tệp của người dùng.
#define
	- Để định nghĩa macro chúng ta dùng cú pháp như sau:
	#define Tên_macro  giá_trị_hoặc_đoạn_mã
Các loại macro gồm:
	- Macro có tham số: Có thể nhận tham số và thực hiện thao tác trên những tham số đó.
	#define SQUARE(x) ((x) * (x))
	- Macro không tham số: Định nghĩa một giá trị cố định
	#define PI 3.14159
	- Để loại bỏ macro ta sử dụng #undef
	

#if
	- Nếu điều kiện này đúng thì thực hiện đoạn mã phía dưới.
#elif
	- Được sử dụng sau #if hoặc #elif để kiểm tra điều khiện thêm nếu điều kiện trước sai.
#else
	- Nếu không có điều kiện nào trước đó đúng thì sẽ thực hiện các câu lệnh sau #else.
#ifdef
	- Dùng để kiểm tra xem macro đã được định nghĩa hay chưa.
#ifndef
	- Dùng để kiểm tra xem macro chưa được định nghĩa.

BÀI 2: 
Thư viện Stdarg.h dùng để làm gì?

Thư viện này dùng trong trường hợp đầu vào của 1 hàm không xác định về số lượng và kiểu. 

Thư viện giúp chúng ta tạo ra một hàm có lượng đối số biến thiên bằng các macro.

Các macro chính trong thư viện:


	1. Va_list 
	
	- Dùng để khai báo 1 biến kiểu dữ liệu lưu trữ thông tin của danh sách đối số biến đổi
	- Cú pháp: args;
	
	2. Va_start()
	
	- Dùng để khởi tạo biến lưu trữ danh sách kiểu va_list vừa lưu.
	- Cú pháp: va_start( args, last_fixed_agr);
	- ' last_fixed_agr ' là đối số cố định cuối cùng trước khi bắt đầu danh sách đối số biến thiên.
	- Ở đây sẽ bắt đầu trỏ từ đối số đầu tiên sau   last_fixed_agr
	3. Va_arg()
	
	- Dùng để truy xuất từng đối số trong danh sách đối số biến đổi.
	- Mỗi lần gọi sẽ truy xuất trả về đối số tiếp theo và di chuyển con trỏ tới đối số kế tiếp.
	- Cú pháp: va_agr(args, int);
	4. Va_end()
	- Dùng để kết thúc việc sử dụng danh sách đối số biến đổi, dọn sạch đối tượng va_list và giải phóng tài nguyên.
	- Cú pháp: va_end(args);
