%{
	#include<stdio.h>
        #include<string.h>
	int i=0,j=0,count=0,n=0,mcom=0,scom=0;
	char ch[20][20];
	int look_up(char ch[20][20],char *id,int n);
%}
digit [0-9]*
id [a-zA-Z][a-zA-Z0-9]*
num [0-9]\.[0-9]
%%
\n {scom=0;n++;}
"//" {scom=1;fprintf(yyout,"\n Single line comments \n\n");}
"/*" {mcom=1;fprintf(yyout,"\n Multi line comment starts here \n");}
"*/" {mcom=0;fprintf(yyout,"\n Multi line comment ends here \n");}
int |
return |
scanf |
printf |
for |
if |
else |
break |
float |
char |
double |
void {if(!mcom&&!scom) fprintf(yyout," \n %s \t It is a keyword",yytext);}
"{" {fprintf(yyout,"\n %s \t It is an Opening Brace. ",yytext);}
"}" {fprintf(yyout,"\n %s \t It is an Closing Brace. ",yytext);}
"(" {fprintf(yyout,"\n %s \t It is an Opening Paranthesis. ",yytext);}
")" {fprintf(yyout,"\n %s \t It is an Closing Paranthesis. ",yytext);}
"%" {fprintf(yyout,"\n %s \t Used for Print values. ",yytext);}
"&" {fprintf(yyout,"\n %s It is an Store values. ",yytext);}
";" {fprintf(yyout,"\n %s It is End of the line. ",yytext);}
"++" {fprintf(yyout,"\n %s It is an Increment Operator. ",yytext);}
"<=" {if (!mcom&&!scom) fprintf(yyout,"\n %s \t It is a Relational operator Lessthan or Equal to. ",yytext);}
"<" {if(!mcom&&!scom) fprintf(yyout,"\n %s \t It is a Relational operator Lessthan. ",yytext);}
">=" {if(!mcom) fprintf(yyout,"\n %s \t It is a Relational operator Greaterthan or Equal to. ",yytext);}
">" {if(!mcom&&!scom) fprintf(yyout,"\n %s \t It is a Relational operator Greaterthan. ",yytext);}
"==" {if(!mcom&&!scom) fprintf(yyout,"\n %s \t It is a Relational operator Equal to. ",yytext);}
"!=" {if (!mcom&&!scom) fprintf(yyout,"\n %s \t It is a Relational operator Not Equal to. ",yytext);}
"=" {fprintf(yyout,"\n %s \t It is an Assignment operator. ",yytext);}
{id} {fprintf(yyout,"\n %s \t It is an identifier. ",yytext);
	if (!lookup(ch,yytext,i)){
		strcpy(ch[i++],yytext);count++;}
}
{num} {fprintf(yyout,"\n %s \t It is a floating point number. ",yytext);}
{digit} {fprintf(yyout,"\n %s \t It is a digit",yytext);}
%%
main(int argc, char **argv)
{
	yyin=fopen(argv[1],"r");
	yyin =fopen("input.txt","r");
	yyout=fopen("output.txt","w");
	yylex();
	printf(" No of Identifiers are : %d ",count);
	printf("\n The contents of symbol table are :\n");
	for(j=0;j<i;j++)
		printf("\n %s",ch[j]);
	printf(" \n\n\n no of lines = %d\n\n",n);
	return 0;
}
int lookup(char ch[10][10],char *id,int n)
{
	for(j=0;j<n;j++)
	if(!strcmp(ch[j],id))
	return 1;
	return 0;
}
int yywrap()
{
return 1;
}
