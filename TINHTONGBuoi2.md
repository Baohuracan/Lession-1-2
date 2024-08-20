        #include<stdio.h>
        // thu vien cung cap cac macro ho tro viet ham bien doi
        #include<stdarg.h> 
        
        // ham bien doi, count chi so luong doi so tiep theo
        int tong(int count,...)
        {
        int sum =0;
        // khai bao bien va kieu valist de luu danh sach doi so
        va_list va;
        // khoi tao danh sach tham so va
        va_start(va,count);
        
        for(int i =0; i< count;i++)
        {
            // moi lan trich xuat mot gia tri cua tham so kieu int
            sum += va_arg(va,int);
        }
        // ket thuc va giai phong tai nguyen
        va_end(va);
        
        return sum;
        }
        
        
        
        int main()
        {
            printf("Tong cua 3 so: %d\n",tong(3,1,2,3));
            printf("Tong cua 5 so: %d\n",tong(5,1,2,3,4,5));
            return 0;
        }
