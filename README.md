//Write a function to sort employees according to their names [refer structure from
#include<stdio.h>
#include<string.h>
struct Employee
{
    int id;
    char name[20];
    float salary;
};
struct Employee input()
{
    struct Employee e;
    printf("Enter The Name Id And Salary :- ");
    fgets(e.name,20,stdin);
    scanf("%d %f",&e.id,&e.salary);
    getchar();
    return e;
}
void sort(struct Employee *ptr)
{
    struct Employee temp;
    int i,j,r;
    for(i=0;i<10;i++)
    {
        for(j=i+1;j<10;j++)
        {
            if(strcmp(ptr[i].name,ptr[j].name)==1)
            {
                temp = ptr[i];
                ptr[i] = ptr[j];
                ptr[j] = temp;
            }
            
        }
    }
}
int main()
{
    struct Employee e[10];
    int i;
    printf("Enter Details Of 10 Employee \n");
    for(i=0;i<10;i++)
    {
        printf("Employee %d: ",i+1);
        e[i] = input();
    }
    sort(e);

    printf("Sorted According To Their Name : -\n");
    for(i=0;i<10;i++)
    {
        printf("%d %s %f\n",e[i].id,e[i].name,e[i].salary);
    }

    return 0;
}
