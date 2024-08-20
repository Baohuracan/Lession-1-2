    #include <stdio.h>
    
    // Định nghĩa cấu trúc chứa các con trỏ hàm
    typedef struct {
        void (*start)(int gpio);     // Hàm khởi động
        void (*stop)(int gpio);      // Hàm dừng
        void (*changespeed)(int gpio, int speed); // Hàm thay đổi tốc độ
    } Motocontroller;
    
    typedef int PIN; // Định nghĩa PIN là kiểu int
    
    // Các hàm điều khiển động cơ
    void startMotor(PIN pin) {
        printf("Start motor at PIN: %d\n", pin);
    }
    
    void stopMotor(PIN pin) {
        printf("Stop motor at PIN: %d\n", pin);
    }
    
    void changespeed(PIN pin, int speed) {
        printf("Change speed at PIN %d: %d\n", pin, speed);
    }
    
    // Macro khởi tạo PIN và đối tượng cho động cơ
    #define INIT_MOTOR(motorName, pinNumber) \
        PIN PIN_##motorName = pinNumber; \
        Motocontroller motorName = {startMotor, stopMotor, changespeed};
    
    int main() {
        // Sử dụng macro để khởi tạo
        INIT_MOTOR(motorA, 1);
        INIT_MOTOR(motorB, 2);
    
        // Sử dụng motorA
        motorA.start(PIN_motorA);
        motorA.changespeed(PIN_motorA, 50);
        motorA.stop(PIN_motorA);
    
        // Sử dụng motorB
        motorB.start(PIN_motorB);
        motorB.changespeed(PIN_motorB, 60);
        motorB.stop(PIN_motorB);
    
        return 0;
    }
