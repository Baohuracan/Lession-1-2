`   
        #include <stdio.h>`
        `#include <stdarg.h>`
      
      
      //B1 Dinh nghia ham
      double average(int num,...)
      {
      //B2 Tao mot bien kieu va_list
          va_list valist;
          // ham tong
          double sum;
      //B3 Khoi tao va_list la mot danh sach doi so 
          va_start(valist,num);
      //B4 Dung macro va_arg va bien va_list de truy cap va xu ly cac doi so
          //va_arg la macro lay doi so tiep theo tu valist da xac dinh 
          //int chi dinh kieu du lieu ma ban muon lay
          for (int i = 0; i < num; i++)
          {
              sum += va_arg(valist,int);
          }
      //B5 Goi macro va_end de don dep bo nho duoc gan cho valist
      va_end(valist);
      // tra ve ket qua trung binh duoi dang so thuc
      return sum/num;
      }
      
      int main()
      {
          printf("average of 1 2 3 4 5: %lf\n",average(5,1,2,3,4,5));
      }
`
