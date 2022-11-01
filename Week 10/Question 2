#include<stdio.h>
#include<stdlib.h>
void pop(),push(char),display();
char stack[100]="\0", input[100], *ip;
int top=-1;
void push(char c)
{
	top++;
	stack[top]=c;
}
void pop()
{
	stack[top]='\0';
	top--;
}
void display()
{
	printf("\n%s\t%s\t",stack,ip);
}

int main()
{
	printf("S->0S0\n");
	printf("S->1S1\n");
	printf("S->2\n");
	printf("Enter the Input string followed by $ \n");
	scanf("%s",input);
	ip=input;
	push('$');
	printf("STACK\t Input \t ACTION\n");
	printf("-----\t ------- \t------ \n");
	display();
	if(stack[top]=='$' && *ip=='$'){
		printf("Null Value");
		exit(0);
	}
	do
	{
		if((stack[top]=='S' && stack[top-1]=='$') && (*(ip)=='$'))
		{
			display();
			printf(" It is an Valid String.....!\n\n\n");
			break;
		}
		if(stack[top]=='$')
		{
			push(*ip);
			ip++;
			printf("SHIFT");
		}
		else if(stack[top]=='2')
		{
			display();
			pop();
			push('S');
			printf("Reduce S->2");
		}
		else if(stack[top]=='0' && stack[top-1]=='S' && stack[top-2]=='0'&& *ip!='1')
		{
			display();
			pop();
			pop();
			pop();
			push('S');
			printf("Reduce S->0S0");
		}
		else if(stack[top]=='1' && stack[top-1]=='S' && stack[top-2]=='1')
		{
			display();
			pop();
			pop();
			pop();
			push('S');
			printf("Reduce S->1S1");
		}
		else if(*ip=='$')
		{ 
			printf("It is an Invalid String......!\n\n\n");
			break;
		}
		else
		{
			display();
			push(*ip);
			ip++;
			printf("SHIFT");
		}
	}while(1);
}
