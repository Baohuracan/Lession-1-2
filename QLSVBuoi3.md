	  #include <stdio.h>
	  #include <string.h>
	  #include <stdlib.h>
	  // cau truc sinh vien
	  typedef struct 
	  {
	      char name[50];
	      float average;
	      int id;
	  }sinhVien;
	  
	  // ham so sanh comparator_funtion ten sinh vien theo thu tu
	  int compareName(const void* a,const void* b)
	  {
	      // ep kieu a tu void* thanh sinhVien*
	      const sinhVien * sv1 =  (const sinhVien *)a;
	      const sinhVien * sv2 =  (const sinhVien *)b;
	      // tra lai ket qua so sanh dung ham strcmp
	      return(strcmp(sv1->name,sv2->name));
	  
	  }
	  // ham so sanh diem trung binh sinh vien
	  int compareAverage(const void* a,const void* b)
	  {
	      const sinhVien * sv1 =  (const sinhVien *)a;
	      const sinhVien * sv2 =  (const sinhVien *)b;
	      if (sv1->average > sv2->average)  {return 1;}
	      if (sv1->average < sv2->average)  {return-1;}
	      return 0;    
	  }
	  
	  // ham so sanh id
	  int compareId(const void* a,const void* b)
	  {
	      const sinhVien * sv1 =  (const sinhVien *)a;
	      const sinhVien * sv2 =  (const sinhVien *)b;
	      if (sv1->id > sv2->id)  {return 1;}
	      if (sv1->id < sv2->id)  {return-1;}
	      return 0;    
	  }
	  // ham sap xep dung ham qsort
	  
	  void sortStudents(sinhVien* list ,size_t size, int (*comparator)(const void*, const void*))
	  {
	      qsort(list,size,sizeof(sinhVien),comparator);
	  }
	  int main()
	  {
	      // khoi tao mot mang cao truc
	      sinhVien danhSach[] = 
	      {
	          {"Bao", 9.9,11},
	          {"Nam",8,2},
	          {"Ly",9,4}
	      };
	      //tinh so luong phan tu trong mang
	      size_t size = sizeof(danhSach)/sizeof(danhSach[0]);
	  
	  
	      // sap xep theo diem trung binh
	      sortStudents(danhSach,size,compareAverage);
	  
	      // in ra ket qua 
	      for (int i = 0; i < size; i++)
	      {
	          printf("%d %s : %.2f\n",danhSach[i].id,danhSach[i].name,danhSach[i].average);
	      }
	      return 0;
	  }
