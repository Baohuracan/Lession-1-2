
Trình biên dịch là gì ?

	- Trình biên dịch là một chương trình máy tính  có nhiệm vụ dịch một mã nguồn được viết bằng 1 ngôn ngữ lập trình cấp cao thành một chương trình tương đương dưới dạng  ngôn ngữ máy (010101...) hoặc ngôn ngữ bậc thấp ( assembly).
![image](https://github.com/user-attachments/assets/ddc2be11-3206-4f5f-870a-c607838a7f0a)

Tại sao cần trình biên dịch?

	- Máy tính chỉ hiểu và thực thi các lệnh ở dạng mã máy, một chuỗi các số 0 và 1. Còn con người thì sử dụng và viết các lệnh bằng ngôn ngữ bậc cao. Và trình biên dịch đóng vai trò là cầu nối để máy tính hiểu và thực thi các lệnh của chúng ta.


Quá trình biên dịch của Compiler trải qua 4 bước như sau:
![image](https://github.com/user-attachments/assets/2d06f997-6d94-4985-a1ff-69125f5d2bb5)


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


