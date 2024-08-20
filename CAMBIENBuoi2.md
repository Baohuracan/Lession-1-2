`  #include <stdio.h>
  #include <stdarg.h>`
  
  `// Định nghĩa kiểu liệt kê
  typedef enum {
      Sensor1T,
      Sensor2P,
      Sensor3L,
      Sensor4H
  } typesensor;`
  `
  // Hàm biến đổi
  void Sensordata(typesensor type, ...) {
     // Khai báo
      va_list va;
      // Khởi tạo
      va_start(va, type);`
  
      // Kiểm tra loại cảm biến
      switch (type) {
      case Sensor1T: {
          // Khai báo biến cục bộ ở đầu khối case
          int numva = va_arg(va, int);
          int SenSorId = va_arg(va, int);
          double temperature = va_arg(va, double);  // Sử dụng double thay vì float khi dùng va_arg
          printf("ID Sensor: %d \t Temperature: %.2f\n", SenSorId, temperature);
  
          // Nếu số lượng lớn hơn 2
          if (numva > 2) {
              // Lấy tham số kiểu char* đại diện cho 1 con trỏ
              char* additional = va_arg(va, char*);
              printf("Additional data: %s\n", additional);
          }
          break;
      }
      case Sensor2P: 
      {
          // Khai báo biến cục bộ ở đầu khối case
          int numva = va_arg(va, int);
          int SenSorId = va_arg(va, int);
          double Pressure = va_arg(va, double);  // Sử dụng double thay vì float khi dùng va_arg
          printf("ID Sensor: %d \t Pressure: %.2f\n", SenSorId, Pressure);
  
          // Nếu số lượng lớn hơn 2
          if (numva > 2) {
              // Lấy tham số kiểu char* đại diện cho 1 con trỏ
              char* additional = va_arg(va, char*);
              printf("Additional data: %s\n", additional);
          }
      }
          break;
      case Sensor3L:
          {
          int numva = va_arg(va,int);
          int SenSorId = va_arg(va,int);
          float light = va_arg(va,double);
          printf("ID Sensor: %d \t Light: %.2f\n", SenSorId, light);
          if(numva > 2)
          {
              char* additional = va_arg(va,char*);
              printf("Additional data: %s\n",additional);
          }
          }
          break;
      case Sensor4H:
          {
          int numva = va_arg(va,int);
          int SenSorId = va_arg(va,int);
          float humidity = va_arg(va,double);
          printf("ID Sensor: %d \t Humidity: %.2f\n", SenSorId, humidity);
          if(numva > 2)
          {
              char* additional = va_arg(va,char*);
              printf("Additional data: %s\n",additional);
          }
          }
          break;
      default:
              printf("Entered Wrong");
          break;
      }
      // Kết thúc việc sử dụng và  giải phóng tài nguyên
      va_end(va);
`  }
`  
 ` int main() `
  `{
      // Gọi hàm với loại cảm biến Sensor1, với 3 tham số: số lượng, ID, nhiệt độ và dữ liệu bổ sung
      Sensordata(Sensor1T, 3, 1, 34.4,"Room Temperature Sensor");
      Sensordata(Sensor2P, 3, 2, 6.4, "Room Pressure Sensor");
      Sensordata(Sensor3L, 3, 3, 10.4,"Room Light Sensor");
      Sensordata(Sensor4H, 3, 4, 0.86,"Room Humidity Sensor");
      return 0;
  }`
