# change-first-name-and-second-name
# c program
# Let's put the first and second names in uppercase, and print the first and second names in lowercase. 성과 이름을 대문자로 입력하고 성과 이름을 소문자로 반대로 출력해보자.
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
int check(char *str);
int main(void) {
    char str[100];
    char word[]=" ";
    char *token;
    char first[10];
    char *second[10];
    int i, count=0;
    printf("성과 이름을 대문자로 입력:");
    fgets(str,sizeof(str),stdin);
    str[strlen(str)-1]=NULL;
    check(str);
    token=strtok(str,word);
    for(i=0;token!=NULL;i++){
    	if(count==0){
    		strcpy(first,token);
    		token=strtok(NULL,word);
		}
		second[i]=token;
		token=strtok(NULL,word);
		count++;
	}
	printf("변환된 이름:");
	for(i=0;i<count;i++){
		printf("%s",second[i]);
		if(i+1!=count){
			printf(" ");
		}
	}
	printf(", ");
	printf("%s",first);
    return 0;
} 
int check(char *s){
	int i;
	for(i=0;s[i]!=NULL;i++){
		if(s[i]>='A'&&s[i]<='Z')
		    s[i]+='a'-'A';
	}
}
# input--> LEE JUNGHYUN
# result--> junghyun lee
