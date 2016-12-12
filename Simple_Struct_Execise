#include <stdio.h>
#include <stdlib.h>

#define FEET_PER_METER	3.28
#define INCH_PER_FEET   12

typedef struct Length Length;
struct Length{
	float meter;
	float feet;
	float inch;
	Length* next;
};

void add(Length*);
void show(Length*);
int main()
{
	Length* First=NULL;
	Length* previous=NULL;
	Length* pLen=NULL;
	char answer=0;
	char rubbish=0;
	for(;;)
	{
		system("clear");
		printf("Would you like to input another set of data? Press [n] to quit\n");
		scanf("%c%c",&answer,&rubbish);
		if('n'==answer)
			break;
		pLen=(Length*)malloc(sizeof(Length));
		if(First==NULL)
		{
			printf("Enter the first set of data\n");
			printf("Which unit you would like to input?\n1.Meter 2.Feet 3.Inch\n");
			pLen->next=NULL;
			scanf("%c%c",&answer,&rubbish);
			if('1'==answer)
			{
				printf("Enter Value\n> ");
				scanf("%f%c",&pLen->meter,&rubbish);
				pLen->feet=pLen->meter*FEET_PER_METER;
				pLen->inch=pLen->feet*INCH_PER_FEET;
			}
			else if('2'==answer)
			{
				printf("Enter Value\n> ");
				scanf("%f%c",&pLen->feet,&rubbish);
				pLen->meter=pLen->feet/FEET_PER_METER;
				pLen->inch=pLen->feet*INCH_PER_FEET;
			}
			else if('3'==answer)
			{
				printf("Enter Value\n> ");
				scanf("%f%c",&pLen->inch,&rubbish);
				pLen->feet=pLen->inch/INCH_PER_FEET;
				pLen->meter=pLen->feet/FEET_PER_METER;
			}
			else
			{
				printf("Invalid input\n");
				continue;
			}
			First=pLen;
			previous=pLen;
		}
		else
		{
			previous->next=pLen;
			pLen->next=NULL;				
			printf("Which unit you would like to input?\n1.Meter 2.Feet 3.Inch\n");
			scanf("%c%c",&answer,&rubbish);
			if('1'==answer)
			{
				printf("Enter Value\n> ");
				scanf("%f%c",&pLen->meter,&rubbish);
				pLen->feet=pLen->meter*FEET_PER_METER;
				pLen->inch=pLen->feet*INCH_PER_FEET;
			}
			else if('2'==answer)
			{
				printf("Enter Value\n> ");
				scanf("%f%c",&pLen->feet,&rubbish);
				pLen->meter=pLen->feet/FEET_PER_METER;
				pLen->inch=pLen->feet*INCH_PER_FEET;
			}
			else if('3'==answer)
			{
				printf("Enter Value\n> ");
				scanf("%f%c",&pLen->inch,&rubbish);
				pLen->feet=pLen->inch/INCH_PER_FEET;
				pLen->meter=pLen->feet/FEET_PER_METER;
			}
			else
			{
				printf("Invalid input\n");
				continue;
			}
			previous=pLen;
		}
	}
	for(;;)
	{
		pLen->next=NULL;
		printf("Which function you would like to use?\n 1 add, 2 show\n> ");
		scanf("%c%c",&answer,&rubbish);
		if('1'==answer)
		{
			add(First);
			return 0;
		}
		else if('2'==answer)
		{
			show(First);
			return 0;
		}
		else{
			printf("Illegal Choice\n");
			continue;
		}
	}
	return 0;
}
void add(Length* plen)
{
	system("clear");
	Length* pCurrent=plen;
	Length sum={0,0,0,NULL};
	while(NULL!=pCurrent)
	{
		sum.meter+=pCurrent->meter;
		sum.feet +=pCurrent->feet;
		sum.inch +=pCurrent->inch;
		pCurrent=pCurrent->next;
	}
	printf("The total length of all data sets are\nMeters:%10.2f\nFeet:%10.2f\nInches:%10.2f\n",sum.meter,sum.feet,sum.inch);
	
}
void show(Length* plen)
{
	system("clear");	
	int count=1;
	Length* pCurrent=plen;
	while(NULL!=pCurrent)
	{
		printf("#### Data set No.%d ###\n\n",count);
		printf("Meter: %10.2f\nFeet: %10.2f\nInches: %10.2f\n\n",pCurrent->meter,pCurrent->feet,pCurrent->inch);
		pCurrent=pCurrent->next;
		count++;
	}
}
