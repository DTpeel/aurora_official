## Welcome to 清丰君NB Pages

清丰君的b站账号： [清丰君qfj](https://space.bilibili.com/414860281?from=search&seid=18175999809506675303) 

清丰君的非官方wiki：（纯属胡扯）[wiki](https://github.com/DTpeel/homepage/wiki)

粉丝群：105363024<a target="_blank" href="//shang.qq.com/wpa/qunwpa?idkey=44215c63afbe7ffef01a54753a3c148923c6e0bc7b061ef283f5ab59784d8f3f"><img border="0" src="//pub.idqqimg.com/wpa/images/group.png" alt="植物大战僵尸：冒险时" title="植物大战僵尸：冒险时"></a>

<embed src="//music.163.com/style/swf/widget.swf?sid=4010234&type=2&auto=1&width=320&height=66" width="340" height="86"  allowNetworking="all"></embed>

群意见反馈：[如有意见请在此反馈（无需全填）](https://docs.qq.com/form/edit/BqI21X2yZIht1QOI5S28Zx6o23ngqV2VuNpq2ufEmB36DXW34azzwf3C3fB70rLWGf2ICBVE29B7UH3NMd4r2?tdsourcetag=s_pctim_send_grpfile&ADUIN=3279587648&ADSESSION=1582451887&ADTAG=CLIENT.QQ.5603_.0&ADPUBNO=26933#/edit)
               <img src="./home/0.png">

### 游戏下载 
植物大战僵尸：冒险时光

```markdown
下载

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/DTpeel/homepage/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

#include<iostream.h>
#include<windows.h>
#include<time.h>
#include<stdlib.h>
#include<conio.h>
#define N 21
void gotoxy(int x,int y)//位置函数
{
COORD pos;
pos.X=2*x;
pos.Y=y;
SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE),pos);
}
void color(int a)//颜色函数
{
SetConsoleTextAttribute(GetStdHandle(STD_OUTPUT_HANDLE),a);
}
void init(int apple[2])//初始化函数(初始化围墙、显示信息、苹果)
{
int i,j;//初始化围墙
int wall[N+2][N+2]={{0}};
for(i=1;i<=N;i++)
{
for(j=1;j<=N;j++)
wall[i][j]=1;
}
color(11);
for(i=0;i<N+2;i++)
{
for(j=0;j<N+2;j++)
{
if(wall[i][j])
cout<<"■";
else cout<<"□" ;
}
cout<<endl;
}
gotoxy(N+3,1);//显示信息
color(20);
cout<<"按 W S A D 移动方向"<<endl;
gotoxy(N+3,2);
color(20);
cout<<"按任意键暂停"<<endl;
gotoxy(N+3,3);
color(20);
cout<<"得分:"<<endl;
apple[0]=rand()%N+1;//苹果
apple[1]=rand()%N+1;
gotoxy(apple[0],apple[1]);
color(12);
cout<<"●"<<endl;
}
int main()
{
int i,j;
int** snake=NULL;
int apple[2];
int score=0;
int tail[2];
int len=3;
char ch='p';
srand((unsigned)time(NULL));
init(apple);
snake=(int**)realloc(snake,sizeof(int*)*len);
for(i=0;i<len;i++)
snake[i]=(int*)malloc(sizeof(int)*2);
for(i=0;i<len;i++)
{
snake[i][0]=N/2;
snake[i][1]=N/2+i;
gotoxy(snake[i][0],snake[i][1]);
color(14);
cout<<"★"<<endl;
}
while(1)//进入消息循环
{
tail[0]=snake[len-1][0];
tail[1]=snake[len-1][1];
gotoxy(tail[0],tail[1]);
color(11);
cout<<"■"<<endl;
for(i=len-1;i>0;i--)
{
snake[i][0]=snake[i-1][0];
snake[i][1]=snake[i-1][1];
gotoxy(snake[i][0],snake[i][1]);
color(14);
cout<<"★"<<endl;
}
if(kbhit())
{
gotoxy(0,N+2);
ch=getche();
}
switch(ch)
{
case 'w':snake[0][1]--;break;
case 's':snake[0][1]++;break;
case 'a':snake[0][0]--;break;
case 'd':snake[0][0]++;break;
default: break;
}
gotoxy(snake[0][0],snake[0][1]);
color(14);
cout<<"★"<<endl;
Sleep(abs(200-0.5*score));
if(snake[0][0]==apple[0]&&snake[0][1]==apple[1])//吃掉苹果后蛇分数加1，蛇长加1
{
score++;
len++;
snake=(int**)realloc(snake,sizeof(int*)*len);
snake[len-1]=(int*)malloc(sizeof(int)*2);
apple[0]=rand()%N+1;
apple[1]=rand()%N+1;
gotoxy(apple[0],apple[1]);
color(12);
cout<<"●"<<endl;
gotoxy(N+5,3);
color(20);
cout<<score<<endl;
}
if(snake[0][1]==0||snake[0][1]==N||snake[0][0]==0||snake[0][0]==N)//撞到围墙后失败
{
gotoxy(N/2,N/2);
color(30);
cout<<"失败!!!"<<endl;
for(i=0;i<len;i++)
free(snake[i]);
Sleep(INFINITE);
exit(0);
}
}
return 0;
}
