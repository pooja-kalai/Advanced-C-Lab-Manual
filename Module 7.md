EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:
```
#include<stdio.h>
struct d
{
    int n;
    char name[90];
};
int main()
{
    struct d s;
    scanf("%d",&s.n);
    scanf("%s",s.name);
    if(s.n>18)
    printf("Age:%d\nName:%svaccine:%d\neligibility:yes",s.n,s.name,s.n);
    else
    printf("Age:%d\nName:%svaccine:%d\neligibility:no",s.n,s.name,s.n);
}
```
Output:
<img width="1182" height="327" alt="image" src="https://github.com/user-attachments/assets/92a6d50e-b34e-4ee5-b64e-65c27428080f" />
Result:
Thus, the program is verified successfully. 



EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:
```
#include <stdio.h>
union book {
   int bookno;
char bookname[20];
float price;
} j;
int main()
{
    scanf("%d",&j.bookno);
    printf("Book Number:%d\n",j.bookno);
    scanf("%s",j.bookname);
    printf("Book Name:%s\n",j.bookname);
    scanf("%f",&j.price);
    printf("BooK Price:%.2f\n",j.price);
}
```
Output:
<img width="837" height="542" alt="image" src="https://github.com/user-attachments/assets/75c9f7ba-7b1b-4d49-b04f-1636b079030c" />

Result:
Thus, the program is verified successfully
 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```
#include <stdio.h>

int main() {
    char s[100];  
    FILE *fp;

    scanf("%s", s);
    fp = fopen(s, "w");

    if (fp != NULL) {
        printf("%s File Created Successfully\n%s File Opened\n", s, s);
        fclose(fp);
        printf("%s File Closed\n", s);
    } else {
        printf("Error: Could not create %s\n", s);
    }

    return 0;
}
```
Output:
<img width="883" height="591" alt="image" src="https://github.com/user-attachments/assets/843d247d-62a6-4ba6-b2c9-966223c9400f" />
<img width="853" height="462" alt="image" src="https://github.com/user-attachments/assets/205761d5-553a-4e4d-9348-5c0c6546a999" />
Result:
Thus, the program is verified successfully
 
EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```
#include <stdio.h>
struct d
{
    int r;
    char n[100];
    float m;
};
int main()
{
    FILE* fp;
    char c[100];
    scanf("%s",c);
    fp=fopen(c,"w");
    if(fp!=NULL)
    {
        printf("%s Opened\n",c);
    }
    int n;
    scanf("%d",&n);
    struct d t[n];
    while(n!=0)
    {
        scanf("%d %s %f",&t[n].r,t[n].n,&t[n].m);
        fprintf(fp,"%d %s %.2f\n",t[n].r,t[n].n,t[n].m);
        n--;
    }
    printf("Data added Successfully");
    fclose(fp);
}
Output:
<img width="837" height="467" alt="image" src="https://github.com/user-attachments/assets/ea1f4d3f-cf3a-4a42-8113-06589f507d72" />
Result:
Thus, the program is verified successfully

Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:
```
#include <stdio.h>
  #include<string.h>
   struct student
   {
       int regno;
       char name[20];
       int no_of_present;
       int jun;
       int july;
       int aug;
       int sep;
       float avg;
       char eligibilty[5];
   };
   int main()
   { 
       struct student stu1;
   scanf("%d%s",&stu1.regno,stu1.name);
   scanf("%d%d%d%d",&stu1.jun,&stu1.july,&stu1.aug,&stu1.sep);
   if(stu1.jun<=21 && stu1.july<=21 && stu1.aug<=21 && stu1.sep<=21)
   {
   stu1.no_of_present=stu1.jun+stu1.july+stu1.aug+stu1.sep;
   stu1.avg=(float)stu1.no_of_present/84 * 100;
   if(stu1.avg>75)
   strcpy(stu1.eligibilty,"yes");
   else
   strcpy(stu1.eligibilty,"no");
   printf("Reg.no:%d\nName:%s\nTotal.No.of.present days:%d\n",stu1.regno,stu1.name,stu1.no_of_present);
   printf("Attendence:%.2f\neligibility:%s",stu1.avg,stu1.eligibilty);
   }
   else
   {
   printf("Invalid data:No.of.present days is greater than working day");
   }
   return 0;
   }
```
Output:
<img width="818" height="566" alt="image" src="https://github.com/user-attachments/assets/b5dddc40-3825-4f1f-bec0-193e5c50b095" />
Result:
Thus, the program is verified successfully
