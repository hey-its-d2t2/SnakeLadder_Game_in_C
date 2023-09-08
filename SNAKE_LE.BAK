#include<stdio.h>
#include<graphics.h>
#include<dos.h>
#include<stdlib.h>
union REGS i,o,in,out;
int x,y;
//Functions
void button_mouse();
void exitx();
void red_ball(),green_ball();
//void restrict_mouse();
/* Mouse */
int initialize_mouse()
{
    i.x.ax=0;
    int86(0x33,&i,&o);
    return 0;
}
int show_mouse()
{
    i.x.ax=1;
    int86(0x33,&i,&o);
    return 0;
}
int get_mouse()
{
    i.x.ax=3;
    int86(0x33,&i,&o);
    return 0;
}
/*
void restrict_mouse()
{
	in.x.ax=7;
	in.x.cx=151;
	in.x.dx=500;
	int86(0x33,&in,&out);
	in.x.ax=8;
	in.x.cx=163;
	in.x.dx=430;
	int86(0x33,&in,&out);
}
*/
void main()
{
	int x1=5,y1=0,x2=634,y2=0,i;
	int x2_1=5,y2_1=0,x2_2=5,y2_2=350;
	void player1(),player2(),dice1(),dice2(),exitx(),design();
	int gd=DETECT,gm;
	initgraph(&gd,&gm,"c:\\turboc3\\bgi");
	cleardevice();setbkcolor(0);
	//setcolor(9);setfillstyle(1,3);bar(5,0,634,350);
       //Vertical Line
       for(i=0;i<=10;i++){setcolor(4);line(x1,y1,x2,y2);y1+=35;y2+=35;}
       //Horizontal Line
       for(i=0;i<=11;i++){setcolor(4);line(x2_1,y2_1,x2_2,y2_2);
       x2_2+=63;x2_1+=63;}

	  //Color For Each Box
  //  rectangle(5,0,67,40);
	 // for(i=0;i<=11;i++){
	  //setfillstyle(11,co);
	 // floodfill(c,c2,4);
	 // c+=50;c2+=0;co++;
	   //   if(c>=0){c2+=20;}if(c2>=400){c+=100;} c+=20;c2+=20;
	   //   }

		design();
	       //	player1();
	       //	player2();
		 button_mouse();
	       //	exitx();
	      //	dice1();
		getch();
		closegraph();

}
void design()
{
	int i,xlp=438,y=422,x=5,xn=5,yn=19;
	setcolor(13);
	rectangle(3,365,636,422);
	setcolor(11);
	rectangle(90,367,547,420);
	for(i=0;i<=315;i++){ setcolor(i+6);
	line(x,351,x,364); x++;x++;}
	for(i=0;i<=50;i++){setcolor(i+3);
	line(4,y,636,y);y++;}
	for(i=0;i<=30;i++){setcolor(i+1);
	line(4,422,269,xlp);line(636,422,350,xlp);xlp++;}
	//Button 1
	    setcolor(12);
	    rectangle(5,367,90,420);
	    setfillstyle(1,11);
	    floodfill(10,369,12);
	    setcolor(4);
	    circle(45,393,25);
	    setfillstyle(1,4);
	    floodfill(51,400,4);
	//Button 2
	     setcolor(2);
	     rectangle(547,367,634,420);
	     setfillstyle(1,11);
	     floodfill(557,369,2);
	     setcolor(10);
	     circle(590,393,25);
	     setfillstyle(1,10);
	     floodfill(600,400,10);

	//Exit Button
       setcolor(14);
       rectangle(270,440,350,470);
       setfillstyle(1,3);
       bar(271,441,349,469);
       setcolor(14);
       settextstyle(7,0,3);
       outtextxy(280,440,"EXIT");
       //Number
       xn=5; yn=2;
       for(i=100;i>=91;i--){gotoxy(xn,yn);printf("%d",i);xn+=8;} xn=5;yn=4;
       for(i=81;i<=90;i++){gotoxy(xn,yn);printf("%d",i);xn+=8;}xn=5;yn=6;
       for(i=80;i>=71;i--){gotoxy(xn,yn);printf("%d",i);xn+=8;}xn=5;yn=8;
       for(i=61;i<=70;i++){gotoxy(xn,yn);printf("%d",i);xn+=8;}xn=5;yn=10;
       for(i=60;i>=51;i--){gotoxy(xn,yn);printf("%d",i);xn+=8;}xn=5;yn=13;
       for(i=41;i<=50;i++){gotoxy(xn,yn);printf("%d",i);xn+=8;}xn=5;yn=15;
       for(i=40;i>=31;i--){gotoxy(xn,yn);printf("%d",i);xn+=8;}xn=5;yn=17;
       for(i=21;i<=30;i++){gotoxy(xn,yn);printf("%d",i);xn+=8;}xn=5;yn=19;
       for(i=20;i>=11;i--){gotoxy(xn,yn);printf("%d",i);xn+=8;} xn=5;yn=21;
       for(i=1;i<=10;i++){gotoxy(xn,yn);printf("%d",i);xn+=8;}
       // Balls
       red_ball();
       green_ball();
}
void dice1()
{
	int i,j,drpl=140,drpt=371,drpr=185,drpb=415,xp=21,yp=25;
		for(j=1;j<=6;j++){
		srand((unsigned)time(0));
		i=(rand()%6+1);delay(100);
		gotoxy(xp,yp);delay(900);printf("%d",i);
		setcolor(14);sound(1300);
		rectangle(drpl,drpt,drpr,drpb);
		if(j==6){delay(900);}
		delay(900);nosound();
		setcolor(0);
		rectangle(drpl,drpt,drpr,drpb);
		gotoxy(xp,yp);printf("   ");
		xp+=7;drpl+=57;drpr+=57;
		}
}
void dice2()
{
		int i,j,drpl=440,drpt=371,drpr=485,drpb=415,xp=58,yp=25;
		for(j=1;j<=6;j++){
		srand((unsigned)time(0));
		i=(rand()%6+1);delay(100);
		gotoxy(xp,yp);delay(900);printf("%d",i);
		setcolor(14);sound(1300);
		rectangle(drpl,drpt,drpr,drpb);
		if(j==6){delay(900);}
		delay(900); nosound();
		setcolor(0);
		rectangle(drpl,drpt,drpr,drpb);
		gotoxy(xp,yp);printf("   ");
		xp-=7;drpl-=57;drpr-=57;
		}

}
/*
void player1()
{
     //Player 1
     setcolor(12);
     rectangle(5,367,90,420);
     setfillstyle(1,4);
     floodfill(10,369,12);

}
*/
/*
void player2()
{
     //Player 2
     setcolor(2);
     rectangle(547,367,634,420);
     setfillstyle(1,10);
     floodfill(557,369,2);

}
*/
void red_ball()
{
	setcolor(4);
	circle(20,332,14);
	setfillstyle(1,4);
	floodfill(21,332,4);
}
void green_ball()
{
	setcolor(10);
	circle(35,332,14);
	setfillstyle(1,10);
	floodfill(36,333,10);
}
void button_mouse()
{

	initialize_mouse();
	show_mouse();
	while(1)
	{
		o.x.bx=0;
		get_mouse();
	       //	restrict_mouse();
	       if(o.x.bx==1&&o.x.cx<350&&o.x.cx>270&&o.x.dx<470&&o.x.dx>440)
	       {
			//Exit
			sound(999);
			setcolor(14);
			rectangle(270,440,350,470);
			setfillstyle(1,5);
			bar(271,441,349,469);
			setcolor(14);
			settextstyle(7,0,3);
			outtextxy(280,440,"EXIT");
			delay(300);
			nosound();
			exitx();
			cleardevice();

		 }
		if(o.x.bx==1&&o.x.cx<90&&o.x.cx>5&&o.x.dx<420&&o.x.dx>367)
		{
			//Player_1
			sound(900);
			setcolor(12);
			rectangle(5,367,90,420);
			setfillstyle(1,11);
			floodfill(10,369,12);
			delay(300);
			nosound();
			dice1();
			setcolor(12);
			rectangle(5,367,90,420);
			setfillstyle(1,11);
			floodfill(10,369,12);
			setcolor(4);
			circle(45,393,25);
			setfillstyle(1,4);
			floodfill(50,400,4);
		}
		if(o.x.bx==1&&o.x.cx<634&&o.x.cx>547&&o.x.dx<420&&o.x.dx>367)
		{
			//Player 2
			  sound(900);
			  setcolor(2);
			  rectangle(547,367,634,420);
			  setfillstyle(1,11);
			  floodfill(557,369,2);
			  delay(300);
			  nosound();
			  dice2();
			  setcolor(2);
			  rectangle(547,367,634,420);
			  setfillstyle(1,11);
			  floodfill(557,369,2);
			  setcolor(10);
			  circle(590,393,25);
			  setfillstyle(1,10);
			  floodfill(600,400,10);
		}

	}
}
void exitx()
{
	cleardevice();
	setcolor(15);
	setlinestyle(0,0,2);
	rectangle(109,94,531,306);
	setfillstyle(1,5);
	bar(110,95,530,305);
	rectangle(115,100,525,299);
	//
	setfillstyle(1,4);
	bar(116,102,524,298);
	settextstyle(1,0,3);
	setcolor(14);
	outtextxy(224,100,"Thanks For Using...");
	outtextxy(225,100,"Thanks For Using...");
	setcolor(15);
	line(115,137,525,137);
	setcolor(2);
	setlinestyle(0,1,2);
	setcolor(15);
	settextstyle(1,0,1);
	outtextxy(120,142,"Design & Developed By :-");
	setfillstyle(1,10);
	bar(116,170,524,203);
	settextstyle(1,0,4);
	setcolor(1);
	outtextxy(185,165," DEEPAK SINGH ");
	setcolor(1);
	outtextxy(185,166," DEEPAK SINGH ");
	outtextxy(185,167," DEEPAK SINGH ");
	setcolor(1);
	outtextxy(185,168," DEEPAK SINGH ");

	setcolor(15);
	settextstyle(7,0,3);
	outtextxy(120,202,"Contact for more...");
	line(117,230,335,230);

	setcolor(10);
	settextstyle(1,0,2);
	outtextxy(118,237,"Phone :- 9525357044");
	settextstyle(1,0,2);
	outtextxy(118,260,"Email :- deepsinghkumar01@gmail.com");
	setcolor(14);
	line(170,330,460,330);
	setcolor(15);
	settextstyle(1,0,2);
	outtextxy(210,330,"Exiting please wait !...");
	setcolor(14);
	line(170,360,460,360);
	setcolor(15);
	settextstyle(1,0,2);
	outtextxy(265,370,"-d..$!ng#");
	delay(5000);
	sound(9999);
	cleardevice();
	delay(30);
	nosound();
	cleardevice();
	exit(0);

}
