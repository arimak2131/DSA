#include<stdio.h>
#include<stdlib.h>
typedef struct DLL
{
    struct DLL *prev;
    long long int PhNo;
    int sal;
    char name[50],SSN[10],Dept[10], designation[20];
    struct DLL *next;
}node;
node *start=NULL;
node* getnode()
{
    node *p;
    p=(node *)malloc(sizeof(node));
    printf("Enter Name, Employee No, Department, salary, phone number and designation of the employee respectively : ");
    scanf("%s%s%s%d%lld%s",p->name,p->SSN,p->Dept,&(p->sal),&(p->PhNo),p->designation);
    p->prev=p->next=NULL;
    return p; 
}
void Ins_front()
{
    node *p;
    p=getnode();
    if (start==NULL)
    {
      start=p;
      return;
    }
    p->next=start;
    start->prev=p;
    start=p;
}
void  Del_front()
{
   node *temp=start;
   if(start==NULL)
   {
     printf("List is empty ");
     return;
   }
   start=start->next;
   printf("The %s employee's data is deleted\n",temp->SSN);
   free(temp);
   start->prev=NULL;
}
void display()
{
    int count=0;
    node *temp=start;
    if(temp==NULL)
    {
      printf("List is empty\n");
      return;
    }
    printf("\n\tName\tEmployee No\tDepartment\tsalary\t\tphone number\tdesignation");  
    while(temp!=NULL)
    {
        printf("\n\t%s\t%s\t\t%s\t\t%d\t\t%lld\t%s",temp->name,temp->SSN,temp->Dept,temp->sal,temp->PhNo,temp->designation);
        temp=temp->next;
        count++;
    }
    printf("\n\t\tThere are %d nodes \n",count);
}
void Ins_end()
{
  node *p,*temp=start;
  p=getnode();
  if(start==NULL)
  {
    start=p;
    return;
  }
  while (temp->next!=NULL)
    temp=temp->next;
  temp->next=p;  
  p->prev=temp;
}
void Del_end()
{
   node *temp=start,*prev;
   if(start==NULL)
   {
     printf("List is empty ");
     return;
   }
   while (temp->next!=NULL)   
     temp=temp->next;
   (temp->prev)->next=NULL;
   printf("The %s Employees's data is deleted\n",temp->SSN);
   free(temp);
}
int main()
{
    int n,i,op;
    printf("Enter\n\t\t1 to Create a DLL of N Employees Data by using end insertion.\n\t\t2 to Display the status of DLL and count the number of nodes in it.\n\t\t3 to Insert the node at front of DLL\n\t\t4 to Delete the node at front of DLL\n\t\t5 to Insert the node at end of DLL\n\t\t6 to Delete the node at end of DLL\n\t\t7 to exit");
    while(1)
    {
         printf("\n\t\tEnter your choice -->");
            scanf("%d",&op);
        switch(op)
        {
        case 1:
            printf("Enter the number of Employees : ");
            scanf("%d",&n);
            for(i=0;i<n;i++)
                Ins_end();
            break;
        
        case 2:
            display();
            break;

        case 3:
            Ins_front();
            break;

        case 4:
            Del_front();
            break;

        case 5:
            Ins_end();
            break;

        case 6:
            Del_end();
            break;

        case 7:
            exit(0);

        default:
            printf("\nInvalid Choice");
            break;
        }
    }
    return 0;
}
