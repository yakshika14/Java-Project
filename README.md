# Java-Project

#include<graphics.h>
#include<conio.h>
#include<stdio.h>
#include<dos.h>

void main(void)
{
int gd =DETECT ,gm,j=0,i,size;
void *a[20];

initgraph(&gd,&gm,"c:\tc\bgi");

setfillstyle(0,0);
floodfill(1,1,1);

setcolor(9);

settextstyle(1,0,4);
outtextxy(190,130,"L");

for(i=0;i<639;i++)
  {
  circle(i,2,2);
  circle(i,477,2);
  }

for(i=0;i<480;i++)
  {
  circle(2,i,2);
  circle(637,i,2);
  }

setcolor(8);
for(i=4;i<475;i++)
 circle(275,i,2);
setcolor(14);
settextstyle(5,1,4);
outtextxy(245,110,"MIRROR");
settextstyle(5,0,2);
outtextxy(190,100,"Real");
for(i=190;i<=205;i++)
 {
 size=imagesize(i,140,i,162);
 a[j]=malloc(size);
 getimage(i,140,i,162,a[j]);
 j++;
 }
getch();
settextstyle(5,0,2);
outtextxy(345,100,"Inverted");
j=15;
for(i=345;i<=360;i++)
 {
 putimage(i,140,a[j],0);
 j--;
 }
getch();
closegraph();
}
