//Projectile Simulation
#include<conio.h>
#include<stdlib.h>
#include<stdio.h>
#include<math.h>
#include<graphics.h>
#include<time.h>
#include<dos.h>
#include<iostream.h>

float calculate_dist(float u,float t,float a)
{
	return (u*t*1.0+a*t*t/2.0);
}

void draw_circle(int x,int y,int r,int c)
{
	circle(x,y,r);
	setfillstyle(1,c);
	floodfill(x,y,15);
}
struct coor
{
	int x;
	int y;
};
void main()
{
	clrscr();
	textbackground(YELLOW);
	textcolor(0);
	int ch,flag=0;

	char user[30],pas[30],h[30];
	//................welcome page ..........
	for(int i=57;i>0;i--)
	{
		clrscr();
		textbackground(YELLOW);
		cout<<"\n\n\n\t\t----------------------------------------------------";
		cout<<"\n\t\t\t!!!!!  PROJECTILE SIMULATION !!!!";
		cout<<"\n\t\t----------------------------------------------------" ;
		textcolor(0);
		gotoxy(i,11);
		cout<<"      @@@@@@@@@@@";
		gotoxy(i,12);
		cout<<"    @@@@@'''''''";
		gotoxy(i,13);
		cout<<"   @ ____ __________   ";
		gotoxy(i,14);
		cout<<"  II__[w] | [i] [z] |   ";
		gotoxy(i,15);
		cout<<" {======|_|~~~~~~~~~|    ";
		gotoxy(i,16);
		cout<<" /oO--000'"<<"`-OO---OO-'   ";
		gotoxy(0,17);
		cout<<"\n--------------------------------------------------------------------------------";
		delay(70);
		cout<<"\n\n\n\t\t\t\t press any key to continue..../";
	}
	getch();
	clrscr();
	int gd=DETECT,gm;
	initgraph(&gd,&gm,"C:\\TC\\BGI");
	settextstyle(DEFAULT_FONT,HORIZ_DIR,2);
	outtextxy(170,180," LOADING,PLEASE WAIT");
	int x=170;
	for(i=0;i<300;i++)
	{
		delay(2);
		line(x,200,x,220);
		x++;
	}
	cleardevice();
	int v,ht;
	printf("\n\n\n\n\n\n\t\tEnter the Height(300 max and 10 min): \t");
	scanf("%d",&ht);
	printf("\n\n\t\tEnter the Velocity(15 max): \t");
	scanf("%d",&v);
	textcolor(15);
	coor arr[1000];
	int k=0;
	if(ht>300 || ht<10)
	{
		printf("\n\nheight value exceeds");
		getch();
		return;
	}
	if(v<0 || v>30)
	{
		printf("/n/nvelocity value exceeds");
		getch();
		return;
	}
	cleardevice();
	settextstyle(DEFAULT_FONT,HORIZ_DIR,2);
	outtextxy(170,180," LOADING,PLEASE WAIT");
	x=170;
	for(i=0;i<300;i++)
	{
		delay(8);
		line(x,200,x,220);
		x++;
	}
	clrscr();
	setbkcolor(BLUE);
	float height=100+ht;
	float g=9.8;
	float u1=0,u2x=v,u2y=0;
	float x1=10,x2=10,y1=100,y2=100;
	float t=00.1;
	int times=(height/1.3);
	while(times--)
	{
		while(y1+10<=height)
		{
			line(0,height,getmaxx(),height);
			y1+=calculate_dist(u1,t,g);
			x2+=calculate_dist(u2x,t,0);
			y2+=calculate_dist(u2y,t,g);
			arr[k].x=x2;
			arr[k].y=y2;
			k++;
			draw_circle(x1,y1,10,14);
			draw_circle(x2,y2,10,4);
			u1+=g*t;
			u2y+=g*t;
			delay(200*t);
			cleardevice();
			setbkcolor(BLUE);
		}
		u1*=-1.0/1.3;
		u2y*=-1.0/1.3;
		while(u1<=0)
		{
			line(0,height,getmaxx(),height);
			y1+=calculate_dist(u1,t,g);
			x2+=calculate_dist(u2x,t,0);
			y2+=calculate_dist(u2y,t,g);
			draw_circle(x1,y1,10,14);
			draw_circle(x2,y2,10,4);
			arr[k].x=x2;
			arr[k].y=y2;
			k++;
			u1+=g*t;
			u2y+=g*t;
			delay(200*t);
			cleardevice();
			setbkcolor(BLUE);
			textcolor(6);
		}
		u1*=-1;
		u2y*=-1;
	}
	delay(200*t);
	line(0,height,getmaxx(),height);
	for(i=0;i<k;i++)
	{
		int x=arr[i].x;
		int y=arr[i].y;
		putpixel(x,y,15);
		delay(200*t);
	}
	float range=(v*1.0)*sqrt(2*ht/9.8);
	float energy_lost_factor=0.23;
	float time=sqrt(2*ht/9.8);
	gotoxy(200,200);
	printf("\t\t\t\t\t\tRANGE: %f\n\t\t\t\t\t\tENERGY_LOST_FACTOR: %f\n\t\t\t\t\t\tTime: %f",range,energy_lost_factor,time);
	getch();
	closegraph();
}
