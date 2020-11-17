
## {内含音乐} Welcome to aurora_official历史墙 Pages

<head>
  <title>
    深空aurora发展墙
  </title>
</head>
<body>
  <h3>
这里是深空盒子aurorabox的发展墙，用于记录深空从社区到盒子的发展征程
我们为什么会创立深空
  </h3> 
</body>


aurora_official的b站账号： [aurora_official](https://space.bilibili.com/) 

粉丝群：
深空盒子官方①群：
<a href="https://jq.qq.com/?_wv=1027&k=4jYm7Ks3">
  <img src="./home/join_aurorachat_1.jpg">
  </a>


<div class="clearfix g-search search-container">
  <input type="text" placeholder="无法搜索的框wwww">
  <span class="icon search-btn">
  </span>
</div>

<img src="./home/.jpg">


# 宣传片
<iframe src="//player.bilibili.com/player.html?aid=712802738&bvid=BV1fD4y1Q7NA&cid=256284881&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>
### 我的世界

链接合集：
<img src="./home/2.png">

```markdown
链接
# 1Fi.盒子历史 box_history

 ## 2020年10月10日，盒子丶重启计划启动
  ### 2020年10月12日，盒子宣布于10月15日全面停止服务
 ## 2020年10月12日，深空论坛测试版发布
  ### 2020年10月15日，盒子开始逐步关闭服务器
 ## 2020年10月13日，深空论坛正式发布
 ## 2020年10月16日，功能基本完善
 ## 2020年10月23日，深空论坛发布新版，标志着深空论坛正式拓展为深空社区
 ## 2020年11月12日，深空盒子内测版正式发布，尽管此时仍然没有悬浮窗
 ## 2020年11月15日，深空盒子悬浮窗正式发布，标志深空正式作为社区开始发展
  ### 2020年11月15日，深空盒子历史墙正式创立，而正是你现在浏览的网站
 ## 2020年11月17日，深空盒子官方英文译名确立为aurobox，全称aurora toolbox for minecraft
 
# 2.盒子下载

# 3Th.qita
 ## 暂无
```

For more details see [aurora_official’bilibili](https://space.bilibili.com/).

<span class="h-f-btn h-follow">
  <i class="关注">
  </i>
        </span>
### 赞助？
您的支持便是我们的动力，看完视频记得一键三连就是最大的赞助，不要忘记每日充电哦！
<img src="./home/3.png">

[测试](测试.html)

友情链接：

<li class="downloads"><a href="https://bilibili.com">
  <img src="./home/4.png">
  </a>

</li>
作者的广告：
【原创】<持续更新中>[内含音乐]minecraft1.13+全命令逐一详解/指令教程
https://www.mcbbs.net/thread-1033335-1-1.html
(出处: Minecraft(我的世界)中文论坛)


<head>

<meta charset="UFT-8">

<title>²âÊÔ</title>

<style>

html,body{

margin:0px;

width:100%;

height:100%;

overflow:hidden;

  background:#000;

}

#canvas{

position:absolute;

width:100%;

height:100%;

}

</style>

</head>

<body>

<canvas id="canvas"></canvas>

<script>

function project3D(x,y,z,vars){

var p,d;

x-=vars.camX;

y-=vars.camY-8;

z-=vars.camZ;

p=Math.atan2(x,z);

d=Math.sqrt(x*x+z*z);

x=Math.sin(p-vars.yaw)*d;

z=Math.cos(p-vars.yaw)*d;

p=Math.atan2(y,z);

d=Math.sqrt(y*y+z*z);

y=Math.sin(p-vars.pitch)*d;

z=Math.cos(p-vars.pitch)*d;

var rx1=-1000;

var ry1=1;

var rx2=1000;

var ry2=1;

var rx3=0;

var ry3=0;

var rx4=x;

var ry4=z;

var uc=(ry4-ry3)*(rx2-rx1)-(rx4-rx3)*(ry2-ry1);

var ua=((rx4-rx3)*(ry1-ry3)-(ry4-ry3)*(rx1-rx3))/uc;

var ub=((rx2-rx1)*(ry1-ry3)-(ry2-ry1)*(rx1-rx3))/uc;

if(!z)z=0.000000001;

if(ua>0&&ua<1&&ub>0&&ub<1){

return {

x:vars.cx+(rx1+ua*(rx2-rx1))*vars.scale,

y:vars.cy+y/z*vars.scale,

d:(x*x+y*y+z*z)

};

}else{

return { d:-1 };

}

}

function elevation(x,y,z){

var dist = Math.sqrt(x*x+y*y+z*z);

if(dist && z/dist>=-1 && z/dist <=1) return Math.acos(z / dist);

return 0.00000001;

}

function rgb(col){

col += 0.000001;

var r = parseInt((0.5+Math.sin(col)*0.5)*16);

var g = parseInt((0.5+Math.cos(col)*0.5)*16);

var b = parseInt((0.5-Math.sin(col)*0.5)*16);

return "#"+r.toString(16)+g.toString(16)+b.toString(16);

}

function interpolateColors(RGB1,RGB2,degree){

var w2=degree;

var w1=1-w2;

return [w1*RGB1[0]+w2*RGB2[0],w1*RGB1[1]+w2*RGB2[1],w1*RGB1[2]+w2*RGB2[2]];

}

function rgbArray(col){

col += 0.000001;

var r = parseInt((0.5+Math.sin(col)*0.5)*256);

var g = parseInt((0.5+Math.cos(col)*0.5)*256);

var b = parseInt((0.5-Math.sin(col)*0.5)*256);

return [r, g, b];

}

function colorString(arr){

var r = parseInt(arr[0]);

var g = parseInt(arr[1]);

var b = parseInt(arr[2]);

return "#"+("0" + r.toString(16) ).slice (-2)+("0" + g.toString(16) ).slice (-2)+("0" + b.toString(16) ).slice (-2);

}

function process(vars){

if(vars.points.length<vars.initParticles) for(var i=0;i<5;++i) spawnParticle(vars);

var p,d,t;

p = Math.atan2(vars.camX, vars.camZ);

d = Math.sqrt(vars.camX * vars.camX + vars.camZ * vars.camZ);

d -= Math.sin(vars.frameNo / 80) / 25;

t = Math.cos(vars.frameNo / 300) / 165;

vars.camX = Math.sin(p + t) * d;

vars.camZ = Math.cos(p + t) * d;

vars.camY = -Math.sin(vars.frameNo / 220) * 15;

vars.yaw = Math.PI + p + t;

vars.pitch = elevation(vars.camX, vars.camZ, vars.camY) - Math.PI / 2;

var t;

for(var i=0;i<vars.points.length;++i){

x=vars.points[i].x;

y=vars.points[i].y;

z=vars.points[i].z;

d=Math.sqrt(x*x+z*z)/1.0075;

t=.1/(1+d*d/5);

p=Math.atan2(x,z)+t;

vars.points[i].x=Math.sin(p)*d;

vars.points[i].z=Math.cos(p)*d;

vars.points[i].y+=vars.points[i].vy*t*((Math.sqrt(vars.distributionRadius)-d)*2);

if(vars.points[i].y>vars.vortexHeight/2 || d<.25){

vars.points.splice(i,1);

spawnParticle(vars);

}

}

}

function drawFloor(vars){

var x,y,z,d,point,a;

for (var i = -25; i <= 25; i += 1) {

for (var j = -25; j <= 25; j += 1) {

x = i*2;

z = j*2;

y = vars.floor;

d = Math.sqrt(x * x + z * z);

point = project3D(x, y-d*d/85, z, vars);

if (point.d != -1) {

size = 1 + 15000 / (1 + point.d);

a = 0.15 - Math.pow(d / 50, 4) * 0.15;

if (a > 0) {

vars.ctx.fillStyle = colorString(interpolateColors(rgbArray(d/26-vars.frameNo/40),[0,128,32],.5+Math.sin(d/6-vars.frameNo/8)/2));

vars.ctx.globalAlpha = a;

vars.ctx.fillRect(point.x-size/2,point.y-size/2,size,size);

}

}

}

}

vars.ctx.fillStyle = "#82f";

for (var i = -25; i <= 25; i += 1) {

for (var j = -25; j <= 25; j += 1) {

x = i*2;

z = j*2;

y = -vars.floor;

d = Math.sqrt(x * x + z * z);

point = project3D(x, y+d*d/85, z, vars);

if (point.d != -1) {

size = 1 + 15000 / (1 + point.d);

a = 0.15 - Math.pow(d / 50, 4) * 0.15;

if (a > 0) {

vars.ctx.fillStyle = colorString(interpolateColors(rgbArray(-d/26-vars.frameNo/40),[32,0,128],.5+Math.sin(-d/6-vars.frameNo/8)/2));

vars.ctx.globalAlpha = a;

vars.ctx.fillRect(point.x-size/2,point.y-size/2,size,size);

}

}

}

}

}

function sortFunction(a,b){

return b.dist-a.dist;

}

function draw(vars){

vars.ctx.globalAlpha=.15;

vars.ctx.fillStyle="#000";

vars.ctx.fillRect(0, 0, canvas.width, canvas.height);

drawFloor(vars);

var point,x,y,z,a;

for(var i=0;i<vars.points.length;++i){

x=vars.points[i].x;

y=vars.points[i].y;

z=vars.points[i].z;

point=project3D(x,y,z,vars);

if(point.d != -1){

vars.points[i].dist=point.d;

size=1+vars.points[i].radius/(1+point.d);

d=Math.abs(vars.points[i].y);

a = .8 - Math.pow(d / (vars.vortexHeight/2), 1000) * .8;

vars.ctx.globalAlpha=a>=0&&a<=1?a:0;

vars.ctx.fillStyle=rgb(vars.points[i].color);

if(point.x>-1&&point.x<vars.canvas.width&&point.y>-1&&point.y<vars.canvas.height)vars.ctx.fillRect(point.x-size/2,point.y-size/2,size,size);

}

}

vars.points.sort(sortFunction);

}

function spawnParticle(vars){

 

var p,ls;

pt={};

p=Math.PI*2*Math.random();

ls=Math.sqrt(Math.random()*vars.distributionRadius);

pt.x=Math.sin(p)*ls;

pt.y=-vars.vortexHeight/2;

pt.vy=vars.initV/20+Math.random()*vars.initV;

pt.z=Math.cos(p)*ls;

pt.radius=200+800*Math.random();

pt.color=pt.radius/1000+vars.frameNo/250;

vars.points.push(pt);

}

function frame(vars) {

if(vars === undefined){

var vars={};

vars.canvas = document.querySelector("canvas");

vars.ctx = vars.canvas.getContext("2d");

vars.canvas.width = document.body.clientWidth;

vars.canvas.height = document.body.clientHeight;

window.addEventListener("resize", function(){

vars.canvas.width = document.body.clientWidth;

vars.canvas.height = document.body.clientHeight;

vars.cx=vars.canvas.width/2;

vars.cy=vars.canvas.height/2;

}, true);

vars.frameNo=0;

 

vars.camX = 0;

vars.camY = 0;

vars.camZ = -14;



pt={};

p=Math.PI*2*Math.random();

ls=Math.sqrt(Math.random()*vars.distributionRadius);

pt.x=Math.sin(p)*ls;


x:vars.cx+(rx1+ua*(rx2-rx1))*vars.scale,



y:vars.cy+y/z*vars.scale,



d
var b = parseInt((0.5-Math.sin(col)*0.5)*16);



return "#"+r.toString(16)+g.toString(16)+b.toString(16);



}



function interpolateColors(RGB1,RGB2,degree){



r b = parseInt((0.5-Math.sin(col)*0.5)*256);



return [r, g, b];



}



function colorString(arr){



var r = parseInt(arr[0]);




var t;



for(var i=0;i<vars.points.length;++i){



x=vars.points[i].x;



y=vars.points[i].y;



z=vars.points[i].z;



d
if(vars.points[i].y>vars.vortexHeight/2 || d<.25){



vars.points.splice(i,1);






z = j*2;



y = vars.floor;



d = Math.sqrt(x * x + z * z);



point = project3D(x, y-d*d/85, z, vars);



if (point.d != -1) {






}



}



}



}




d = Math.sqrt(x * x + z * z);



point = project3D(x, y+d*d/85, z, vars);



if (point.d != -1) {



size = 1 + 15000 / (1 + point.d);



a = 0.15 - Math.pow(d / 50, 4) * 0.15;




