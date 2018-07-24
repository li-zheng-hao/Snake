# 贪吃蛇大作战Demo
## 2018年7月24日 v0.1
### 游戏的界面一共四个：开始界面，规则界面，皮肤商店界面，游戏界面</br>
## 1 游戏的主界面
![image](https://github.com/li-zheng-hao/Snake/raw/master/DisplayGIF/游戏功能完整.gif)</br>
## 2 商店的皮肤
![image](https://github.com/li-zheng-hao/Snake/raw/master/DisplayGIF/皮肤功能.gif)</br>
## 3 游戏规则的介绍
![image](https://github.com/li-zheng-hao/Snake/raw/master/DisplayGIF/规则功能.gif)</br>

# 游戏实现的一些主要的功能包括：
## 1 游戏界面UI的设计以及适配
##### 项目采用的是UGUI 屏幕适配通过将Canvas的Scaler中的Scale Mode设置为Scale With Screen Size，在设计时采用的分辨率为1334×750（因此参考分辨率也是这个）,优先参考宽度；同时设置UI元素的锚点到相应的位置，使得在分辨率发生变化的情况下，UI元素在屏幕中的相对位置不会发生变化。（四个锚点集中在一点，不相对父容器进行拉伸）


## 2 蛇身体跟随蛇头移动
##### 通过一个List<Position>来保存蛇头移动过的坐标，然后蛇身体按照一定的步长step来分配自己的位置，每一次调整位置之后都要删除最后的一部分元素，保证容器内的坐标点不会过多导致占用太多内存。
  
  
## 3 AI蛇的初步智能
##### 在蛇头上增加一个碰撞盒，大概范围为蛇头的3倍半径，在触碰到其他蛇的身体或者墙之后说明即将要撞到墙，这时候给蛇一个反向160-200度的Vector3的向量，让蛇掉头。


## 4 食物的无限生成
##### 通过一个内存回收的List来保存所有的食物（目前是200个），当食物被吃掉之后，不是将食物对象进行销毁，而是获得这个被吃掉的食物并随机改变它的坐标。


## 5 游戏的排行榜
##### 通过脚本获取游戏中所有的蛇对象，可以通过蛇对象获取它目前的长度和蛇名字，通过冒泡排序（时间复杂度为O（n²），如果要再进一步提高效率可采用快排）将蛇对象进行一个排序，排序完成之后按照顺序把蛇的名字和身体长度显示在排行榜的UI元素上。


  

