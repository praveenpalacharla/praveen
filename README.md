#include <stdio.h>
#include <string.h>
struct student{
    char name[20];
    int rollno;
    float grade;
};
int main( ){
    int number_of_students;
    printf("Enter the no of students : ");
    scanf("%d",&number_of_students);
    struct student s[number_of_students];
    for(int i=0;i<number_of_students;i++){
        printf("STUDENT %d DETAILS : \n",i+1);
        printf("NAME    : ");
        scanf("%s",s[i].name);
        printf("ROLL NO : ");
        scanf("%d",&s[i].rollno);
        printf("GRADE   : ");
        scanf("%f",&s[i].grade);
    }int temp1; float temp2; char n[30];
    
    int choice;
    printf("\nGET DETAILS IN FOLLOWING ORDER \n1.ORDER IN ROLL NO\n2.ORDER IN GRADE\n\nCHOOSE 1 0R 2 : ");
    scanf("%d",&choice);
    for(int i=0;i<number_of_students;i++){
        for (int j=i+1; j<number_of_students; j++) {
            if(choice==1){
                if(s[i].rollno > s[j].rollno){
                    temp1=s[i].rollno;
                    s[i].rollno=s[j].rollno;
                    s[j].rollno=temp1;
                
                    strcpy(n,s[i].name);
                    strcpy(s[i].name,s[j].name);
                    strcpy(s[j].name,n);
                    
                    temp2=s[i].grade;
                    s[i].grade=s[j].grade;
                    s[j].grade=temp2;
                }
            }else {
                if(s[i].grade > s[j].grade){
                    temp2=s[i].grade;
                    s[i].grade=s[j].grade;
                    s[j].grade=temp2;
                    
                    strcpy(n,s[i].name);
                    strcpy(s[i].name,s[j].name);
                    strcpy(s[j].name,n);
                    
                    temp1=s[i].rollno;
                    s[i].rollno=s[j].rollno;
                    s[j].rollno=temp1;
                }
            }
        }
    }
    printf("\nDETAILS OF ALL STUDENTS \n");
    for (int i=0; i<number_of_students; i++) {
        printf("NAME    : %s\n",s[i].name);
        printf("ROLL NO : %d\n",s[i].rollno);
        printf("GRADE   : %.2f\n",s[i].grade);
    }
    
    int index;
    printf("\nEnter the roll no to get the details of the student : ");
    scanf("%d",&index);
    printf("DETAILS OF THE STUDENT \n");
    for(int i=0;i<number_of_students;i++){
        if(s[i].rollno == index){
            printf("NAME    : %s\n",s[i].name);
            printf("ROLL NO : %d\n",s[i].rollno);
            printf("GRADE   : %.3f\n",s[i].grade);
            break;
        }
    }
    return 0;
}
