#include<stdio.h>
#include<conio.h>
#include<dos.h>
void add();
void show();
void modify();
void search();
void del();
struct dob
{
	char date;
	char month;
	int year;
};
typedef struct dob dob;
struct address
{
	char city[15];
	char state[15];
	long zip;
};
typedef struct address address;
struct emp
{
	int id;
	char name[25];
	char age;
	dob d;
	char desi[15];
	long sal;
	address add;
};
typedef struct emp emp;
void main()
{
	int choice,li,lp;
	char ch,ch1;
	clrscr();
	for(li=10;li<71;li++)		//uper horizontal
	{
		gotoxy(li,15);
		delay(30);
		printf("/");
	}
	for(li=70;li>=10;li--)		//lower horizontal
	{
		gotoxy(li,22);
		delay(30);
		printf("\\");
	}
	for(lp=16;lp<=21;lp++)		//left vertical
	{
		gotoxy(10,lp);
		delay(100);
		printf("=");
	}
	for(lp=21;lp>=16;lp--)		//right vertical
	{
		gotoxy(70,lp);
		delay(100);
		printf("=");
	}
	gotoxy(16,17);
	textcolor(BLINK + MAGENTA);
	cprintf(" Welcome To The MICROSOFT Recruitment Department");
	gotoxy(12,20);
	cprintf("            Designed and Coded in C Language");
	gotoxy(36,28);
	textcolor(LIGHTGREEN);
	cprintf("Coded By:");
	gotoxy(24,31);
	textcolor(9);
	cprintf("SAHIL SONI, Roll No: 645/IT/09, B.Tech");
	gotoxy(26,34);
	textcolor(4);
	cprintf("TUSHAR VERMA, Roll No: 660/IT/09, B.Tech");
	gotoxy(44,48);
	textcolor(WHITE);
	cprintf("Press Any Key To ..........Continue");
	getch();
	start:
	clrscr();
	printf("\n1-Add Employee Record");
	printf("\n2-Search Employee Record");
	printf("\n3-Modify Employee Record");
	printf("\n4-Delete Employee Record");
	printf("\n5-List of Employes");
	printf("\n6-Exit");
	printf("\nEnter Choice: ");
	scanf("%d",&choice);
	switch(choice)
	{
		case 6:
			clrscr();
			c6:
			printf("\nReally want to exit...Press Y/N");
			ch=getch();
			if(ch=='y'||ch=='Y')
			{
				clrscr();
				gotoxy(20,17);
				textcolor(2);
				cprintf("\nThanks for Visiting our Application");
				delay(2000);
				exit(0);
			}
			else if(ch=='n'||ch=='N')
				goto start;
			else
			{
				clrscr();
				printf("\nWrong Choice...");
				goto c6;
			}
		break;
		case 1:
			add();
		break;
		case 2:
			search();
		break;
		case 3:
			modify();
		break;
		case 4:
			del();
		break;
		case 5:
			show();
		break;
	}
	printf("\n\nWant to continue...press Y/N");
	ch=getch();
	if(ch=='y'||ch=='Y')
		goto start;
	else
		return;
}
void add()
{
	char ch;
	FILE *p_add;
	emp obj;
	c1:
	p_add=fopen("d:\\emprec","a");
	printf("\nEnter Employee ID: ");
	scanf("%d",&obj.id);
	fflush(stdin);
	printf("\nEnter Employee Name: ");
	gets(obj.name);
	printf("\nEnter Employee Age: ");
	scanf("%d",&obj.age);
	fflush(stdin);
	printf("\nEnter Employee Date of Birth:");
	printf("\nEnter Date: ");
	scanf("%d",&obj.d.date);
	printf("\nEnter Month: ");
	fflush(stdin);
	scanf("%d",&obj.d.month);
	fflush(stdin);
	printf("\nEnter Year: ");
	scanf("%d",&obj.d.year);
	printf("\nEnter Employee Designation: ");
	fflush(stdin);
	gets(obj.desi);
	fflush(stdin);
	printf("\nEnter Salary: ");
	scanf("%ld",&obj.sal);
	printf("\nEnter Address:");
	fflush(stdin);
	printf("\nEnter City: ");
	gets(obj.add.city);
	printf("\nEnter State: ");
	fflush(stdin);
	gets(obj.add.state);
	printf("\nEnter Zip: ");
	scanf("%ld",&obj.add.zip);
	fwrite(&obj,sizeof(obj),1,p_add);
	fclose(p_add);
	printf("\nWant to add more records...press Y/N");
	ch=getch();
	if(ch=='y'||ch=='Y')
		goto c1;
	else
		return;
}
void show()
{
	FILE *p_show;
	emp obj;
	p_show=fopen("d:\\emprec","r");
	fread(&obj,sizeof(obj),1,p_show);
	printf("\nEmployee Record");
	printf("\n\n%-5s%-11s%-5s%-11s%-14s%-10s%s","ID","Name","Age","DOB","Designation","Salary","Address");
	while(!feof(p_show))
	{
		printf("\n%-5d%-11s%-4d%2d/%2d/%-6d%-14s%-10ld%s,%s-%ld",obj.id,obj.name,obj.age,obj.d.date,obj.d.month,obj.d.year,obj.desi,obj.sal,obj.add.city,obj.add.state,obj.add.zip);
		fread(&obj,sizeof(obj),1,p_show);
	}
	fclose(p_show);
}
void modify()
{
	char ch;
	int choice,f=-1;
	FILE *p_src=fopen("d:\\emprec","r");
	FILE *p_dest=fopen("d:\\temp","w");
	emp obj;
	int i;
	char nm[20];
	c3:
	printf("\n1-Modify by ID");
	printf("\n2-Modify by Name");
	printf("\nEnter Choice: ");
	scanf("%d",&choice);
	switch(choice)
	{
		case 1:
			printf("\nEnter the ID to be modify: ");
			scanf("%d",&i);
			fread(&obj,sizeof(obj),1,p_src);
			while(!feof(p_src))
			{
				if(obj.id==i)
				{
					printf("\nEnter New Details");
					printf("\n\nEnter Employee Name: ");
					gets(obj.name);
					printf("\nEnter Employee Age: ");
					scanf("%d",&obj.age);
					fflush(stdin);
					printf("\nEnter Employee Date of Birth:");
					printf("\nEnter Date: ");
					scanf("%d",&obj.d.date);
					printf("\nEnter Month: ");
					fflush(stdin);
					scanf("%d",&obj.d.month);
					fflush(stdin);
					printf("\nEnter Year: ");
					scanf("%d",&obj.d.year);
					printf("\nEnter Employee Designation: ");
					fflush(stdin);
					gets(obj.desi);
					fflush(stdin);
					printf("\nEnter Salary: ");
					scanf("%ld",&obj.sal);
					printf("\nEnter Address:");
					fflush(stdin);
					printf("\nEnter City: ");
					gets(obj.add.city);
					printf("\nEnter State: ");
					fflush(stdin);
					gets(obj.add.state);
					printf("\nEnter Zip: ");
					scanf("%ld",&obj.add.zip);
					f=1;
				}
				fwrite(&obj,sizeof(obj),1,p_dest);
				fread(&obj,sizeof(obj),1,p_src);
			}
			fclose(p_src);
			fclose(p_dest);
			if(f==-1)
			{
				printf("\nRecord not found");
				system("del d:\\temp");
			}
			else
			{
				system("del d:\\emprec");
				system("ren d:\\temp emprec");
				printf("\nRecord is modified");
			}
		break;
		case 2:
			printf("\nEnter the name to be modified: ");
			fflush(stdin);
			gets(nm);
			fread(&obj,sizeof(obj),1,p_src);
			while(!feof(p_src))
			{
				if(strcmp(obj.name,nm)==0)
				{
					printf("\nEnter New Details");
					printf("\n\nEnter Employee ID: ");
					scanf("%d",obj.id);
					printf("\nEnter Employee Age: ");
					scanf("%d",&obj.age);
					fflush(stdin);
					printf("\nEnter Employee Date of Birth:");
					printf("\nEnter Date: ");
					scanf("%d",&obj.d.date);
					printf("\nEnter Month: ");
					fflush(stdin);
					scanf("%d",&obj.d.month);
					fflush(stdin);
					printf("\nEnter Year: ");
					scanf("%d",&obj.d.year);
					printf("\nEnter Employee Designation: ");
					fflush(stdin);
					gets(obj.desi);
					fflush(stdin);
					printf("\nEnter Salary: ");
					scanf("%ld",&obj.sal);
					printf("\nEnter Address:");
					fflush(stdin);
					printf("\nEnter City: ");
					gets(obj.add.city);
					printf("\nEnter State: ");
					fflush(stdin);
					gets(obj.add.state);
					printf("\nEnter Zip: ");
					scanf("%ld",&obj.add.zip);
					f=1;
				}
				fwrite(&obj,sizeof(obj),1,p_dest);
				fread(&obj,sizeof(obj),1,p_src);
			}
			fclose(p_src);
			fclose(p_dest);
			if(f==-1)
			{
				printf("\nRecord not found");
				system("del d:\\temp");
			}
			else
			{
				system("del d:\\emprec");
				system("ren d:\\temp emprec");
				printf("\nRecord is modified");
			}
		break;
	}
	printf("\nWant to modify more records...press Y/N");
	ch=getch();
	if(ch=='y'||ch=='Y')
		goto c3;
	else
		return;
}
void search()
{
	char ch;
	int choice,f=-1;
	FILE *p_src=fopen("d:\\emprec","r");
	emp obj;
	int i;
	char nm[20];
	c2:
	printf("\n1-Delete by ID");
	printf("\n2-Delete by Name");
	printf("\nEnter Choice: ");
	scanf("%d",&choice);
	switch(choice)
	{
		case 1:
			printf("\nEnter the ID to be searched: ");
			scanf("%d",&i);
			fread(&obj,sizeof(obj),1,p_src);
			while(!feof(p_src))
			{
				if(obj.id==i)
				{
					printf("\n\n%-5s%-11s%-5s%-11s%-14s%-10s%s","ID","Name","Age","DOB","Designation","Salary","Address");
					printf("\n%-5d%-11s%-4d%2d/%2d/%-6d%-14s%-10ld%s,%s-%ld",obj.id,obj.name,obj.age,obj.d.date,obj.d.month,obj.d.year,obj.desi,obj.sal,obj.add.city,obj.add.state,obj.add.zip);
					f=1;
				}
				fread(&obj,sizeof(obj),1,p_src);
			}
			if(f==-1)
				printf("\nRecord not found");
		break;
		case 2:
			printf("\nEnter the name to be searched: ");
			gets(nm);
			fread(&obj,sizeof(obj),1,p_src);
			while(!feof(p_src))
			{
				if(strcmp(obj.name,nm)==0)
				{
					printf("\n\n%-5s%-11s%-5s%-11s%-14s%-10s%s","ID","Name","Age","DOB","Designation","Salary","Address");
					printf("\n%-5d%-11s%-4d%2d/%2d/%-6d%-14s%-10ld%s,%s-%ld",obj.id,obj.name,obj.age,obj.d.date,obj.d.month,obj.d.year,obj.desi,obj.sal,obj.add.city,obj.add.state,obj.add.zip);
					f=1;
				}
				fread(&obj,sizeof(obj),1,p_src);
			}
			if(f==-1)
				printf("\nRecord not found");
		break;
	}
	printf("\nWant to search more records...press Y/N");
	ch=getch();
	if(ch=='y'||ch=='Y')
		goto c2;
	else
		return;
}
void del()
{
	char ch;
	int choice,f=-1;
	FILE *p_src=fopen("d:\\emprec","r");
	FILE *p_dest=fopen("d:\\temp","w");
	emp obj;
	int i;
	char nm[20];
	c4:
	printf("\n1-Delete by ID");
	printf("\n2-Delete by Name");
	printf("\nEnter Choice: ");
	scanf("%d",&choice);
	switch(choice)
	{
		case 1:
			printf("\nEnter the ID to be deleted: ");
			scanf("%d",&i);
			fread(&obj,sizeof(obj),1,p_src);
			while(!feof(p_src))
			{
				if(obj.id!=i)
					fwrite(&obj,sizeof(obj),1,p_dest);
				else
					f=1;
				fread(&obj,sizeof(obj),1,p_src);
			}
			fclose(p_src);
			fclose(p_dest);
			if(f==-1)
			{
				printf("\nRecord not found");
				system("del d:\\temp");
			}
			else
			{
				system("del d:\\emprec");
				system("ren d:\\temp emprec");
				printf("\nRecord is deleted");
			}
		break;
		case 2:
			printf("\nEnter the name to be deleted: ");
			fflush(stdin);
			gets(nm);
			fread(&obj,sizeof(obj),1,p_src);
			while(!feof(p_src))
			{
				if(strcmp(obj.name,nm)!=0)
					fwrite(&obj,sizeof(obj),1,p_dest);
				else
					f=1;
				fread(&obj,sizeof(obj),1,p_src);
			}
			fclose(p_src);
			fclose(p_dest);
			if(f==-1)
			{
				printf("\nRecord not found");
				system("del d:\\temp");
			}
			else
			{
				system("del d:\\emprec");
				system("ren d:\\temp emprec");
				printf("\nRecord is deleted");
			}
		break;
	}
	printf("\nWant to delete more records...press Y/N");
	ch=getch();
	if(ch=='y'||ch=='Y')
		goto c4;
	else
		return;
}