# lady_hunter_tiger.c
similar game to stone paper scissors in c
#include<stdio.h>
#include<stdlib.h>
#include<time.h>
int ladyhuntertiger(char you, char comp){
	if(you==comp){
		return 0;
	}
	if(you=='l' && comp=='h'){
		return 1;
	}
	else if(you=='h' && comp=='l'){
		return -1;
	}
	if(you=='l' && comp=='t'){
		return -1;
	}
	else if(you=='t' && comp=='l'){
		return 1;
	}
	if(you=='h' && comp=='t'){
		return 1;
	}
	else if(you=='t' && comp=='h'){
		return -1;
	}
}
int main(){
	int n;
	char you, comp;
	srand(time(0));
	n=rand()%100+1;
	printf("enter l for lady t for tiger h for hunter\n");
	scanf("%c",&you);
	if(n<33){
		comp='h';
	}
	else if(n>33 && n<66){
		comp='l';
	}
	else{
		comp='t';
	}
	if(you=='h' || you=='l' || you=='t'){
		int result=ladyhuntertiger(you, comp);
		printf("you chose %c and comp chose %c\n",you, comp);
		if(result==0){
			printf("game draw\n");
		}
		else if(result==1){
			printf("you won\n");
		}
		else{
			printf("comp won\n");
		}
	}
	else{
		printf("learn the game\n");
	}
	
}
