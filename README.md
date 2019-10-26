## <易校园>
# 需求规格说明书
## 团队名称：FutureOfLight 
## 完成时间：   2019.10.25  
## 修订历史记录

<table>
   <tr>
      <td>日期</td>
      <td>版本</td>
      <td>说明</td>
      <td>作者</td>
   </tr>
   <tr>
      <td>2019.10.25</td>
      <td>V1.0</td>
      <td>第一个版本，根据项目设想生成。</td>
      <td>33</td>
   </tr>
</table>

## 1.引言
### 1.1目的
该文档首先给出项目的整体结构和功能结构概貌，试图从总体架构上给出整个系统的轮廓。同时对功能需求、性能需求进行了详细的描述。便于用户、开发人员进行理解和交流，反映出用户问题的结构，可以作为软件开发工作的基础和依据以及确认测试和验收的依据。

本文档面向多种读者对象：

（1）项目经理：项目经理可以根据该文档了解预期产品的功能，并据此进行系统设计、项目管理。

（2）设计员：对需求进行分析，并设计出系统，包括数据库的设计。

（3）程序员：了解系统功能，编写《用户手册》。

（4）测试员：根据本文档编写测试用例，并对软件产品进行功能性测试和非功能性测试。

（5）用户：了解预期产品的功能和性能，并与分析人员一起对整个需求进行讨论和协商。

在阅读本文档时，首先要了解产品的功能概貌，然后可以根据自身的需要对每一功能进行适当的了解。

### 1.2背景
本次待开发的软件为“易校园”。

商家可在该平台发布兼职信息，学生可在该平台发布代取快递或顺风车信息，并可进行相应的接单与申请操作。
### 1.3定义

<table>
   <tr>
      <td>序号</td>
      <td>缩写</td>
      <td>定义</td>
   </tr>
   <tr>
      <td>1</td>
      <td>web</td>
      <td>一种基于超文本和HTTP的、动态交互的、跨平台的分布式图形信息系统。</td>
   </tr>
   <tr>
      <td>2</td>
      <td>js</td>
      <td>js为JavaScript的缩写，JavaScript是一种直译式脚本语言。</td>
   </tr>
   <tr>
      <td>3</td>
      <td>Bootstraps</td>
      <td>Bootstrap是基于HTML、CSS、JavaScript开发的简洁、直观、强悍的前端开发框架。</td>
   </tr>
</table>

###  1.4参考资料
[1].（美）Roger S.Pressman著，郑人杰等译.软件工程[M].第七版.北京：机械工业出版社,2011

## 2.项目概述
### 2.1产品描述
易校园是基于web的信息发布与管理平台，希望解决目前顺风车、代取快递、兼职等信息获取困难的问题。

### 2.2 功能
目前兼职、代取快递、顺风车等信息的发布多在表白墙等，信息并没有进行分类且查询较为不便。易校园希望通过简洁的页面、便捷的搜索解决这些问题。

首先通过用例图了解一下角色分工：
![](https://github.com/33lc/33/blob/master/%E7%94%A8%E4%BE%8B%E5%9B%BEuser.jpg?raw=true)
![](https://github.com/33lc/33/blob/master/%E7%94%A8%E4%BE%8B%E5%9B%BEc.jpg?raw=true)

用户场景如下：

同学A觉得宿舍区到教室太远了，骑共享自行车很累，又不会骑电动车，校车小白队伍又很长，希望有人能载他一程。

同学B有车，想挣点外快。

同学C住在生活一区，而他的快递送到了四区岐安商业街，他希望有人能帮他拿到宿舍。

同在一区的同学D也有快递到了四区岐安商业街，他想知道有没有同学需要他顺路把快递带回去。

同学E在寻找兼职。

商家A由于活动在寻找临时的学生进行兼职。

易校园的解决方式：

同学A在易校园上发布顺风车订单（包括出发地、目的地、出发时间、联系方式、报酬等信息）。同学B在浏览时看到了同学A的订单，发现两个人的起终点很相似，便点了接单，同时与同学A取得联系。到达目的地后完成本次行程。易校园同时支持有车的同学发布顺风车请求，寻找无车的同学。

同学C在易校园上发布代取快递订单（包括快递公司、取件码、姓名、手机号、宿舍地址等信息）。同学D在浏览时看到了同学C的订单（仅显示快递公司、宿舍地址等，而不显示取件码），发现他可以顺路帮同学C代取快递，便点了接单，系统将提供取件码。同学D取件完毕将快递交给同学C，本次代取快递结束。

商家A在易校园上发布兼职需求（包括商家名称、工作时间段、兼职待遇、需要的人数等信息）。同学E在浏览时看到了商家A的需求，便点了申请，与商家取得联系，完成本次申请。

### 2.3用户特点
用户主要以高校学生为主，其次是商家。高校学生学习能力较强，能够较快地适应该软件，同时能够提出合理的改进意见。

操作与维护人员也均是在校学生，能够深入用户交流，便于调整软件功能，实现用户需求。

### 2.4假定与约束
进行本次开发工作的约束条件如下：

(1)开发时间短：仅有不足一个月的时间进行开发。

(2)人员技术水平有限：大部分成员没有相关的开发经验，在开发的过程中需要学习多种技术和能力。

本项目是否能够成功实施，主要取决于以下的条件：

(1)开发任务的合理分配

(2)团队成员的积极配合


## 3.具体需求
引入类图明确该项目中的角色分类及其角色间的相互联系。
![](https://github.com/33lc/33/blob/master/%E7%B1%BB.jpg?raw=true)
### 3.1功能需求
#### 3.1.1首页
首页设置轮播图用于向用户介绍易校园的用途，并且设置登录注册入口。
![](https://github.com/33lc/33/blob/master/%E9%A6%96%E9%A1%B5.jpg?raw=true)
#### 3.1.2登录与注册
通过点击页面右上角的“登录”按钮，可进入登录页面进行登录操作。账号密码输入正确即可进入系统，反之将收到报错。
![](https://github.com/33lc/33/blob/master/%E7%99%BB%E5%BD%95new.jpg?raw=true)
没有注册过的的用户可以点击“注册”按钮进去注册页，根据页面进行注册操作，输入的信息需符合提示要求。
![](https://github.com/33lc/33/blob/master/%E6%B3%A8%E5%86%8C1.png?raw=true)
#### 3.1.3顺风车
用户在登录后，将显示顺风车页面，若需要选择其他模块，可通过“代取快递”、“校园兼职”的按钮进行切换。

在顺风车的列表页将显示顺风车的部分信息（如出发地、目的地、出发时间、报酬），具体信息（如车型、备注等）可点击“查看详情”进入详情页查看。同时由于顺风车的发布者可能是乘客和骑手，不同类型发布者的订单以不同的底色呈现，同时设置了“分类查看”的选项，用户可通过点击“我是乘客”或“我是骑手”进入仅包括对应订单的列表。页面的左上角设置了“发布新订单”的按钮，用户可通过点击进入订单发布页面。
![](https://github.com/33lc/33/blob/master/%E9%A1%BA%E9%A3%8E%E8%BD%A6%E5%88%97%E8%A1%A8.jpg?raw=true)
下方是按乘客与骑手的分类显示的列表，保留了“发布新订单”的按钮，便于用户发布订单，新增了“返回完整列表”的按钮。
![](https://github.com/33lc/33/blob/master/%E9%A1%BA%E9%A3%8E%E8%BD%A6%20c.jpg?raw=true)
![](https://github.com/33lc/33/blob/master/%E9%A1%BA%E9%A3%8E%E8%BD%A6s.jpg?raw=true)
用户通过点击“发布新订单”按钮可进入订单发布页面。乘客和骑手需填写的内容有一定的差别。

乘客需填写出发地、目的地、出发时间、手机号、报酬、理想车型，填写完毕后可点击“发布”进行发布操作。
![](https://github.com/33lc/33/blob/master/1791984-20191024161057245-144538668.png?raw=true)
骑手需填写出发地、目的地、出发时间、手机号、最低报酬、车型、车牌号，填写完毕后可点击“发布”进行发布操作。
![](https://github.com/33lc/33/blob/master/%E9%A1%BA%E9%A3%8E%E8%BD%A6%E5%8F%91%E5%B8%83s.jpg?raw=true)
用户通过点击“查看详情”可进入详情页，可以查看出发的、目的地、出发时间、（最低）报酬、（希望的）车型以及备注，同时可以点击“接单”按钮进行接单。
![](https://github.com/33lc/33/blob/master/%E9%A1%BA%E9%A3%8E%E8%BD%A6%E8%AF%A6%E6%83%85.jpg?raw=true)
如果用户是在该订单中的身份是骑手，在点击接单后需填写您的车牌号，然后点击“确认接单”完成接单操作
![](https://github.com/33lc/33/blob/master/%E9%A1%BA%E9%A3%8E%E8%BD%A6%E6%8E%A5%E5%8D%95.jpg?raw=true)
点击完接单，用户可以在详情页获得对方的联系方式，同时订单状态改为“已接单”。
![](https://github.com/33lc/33/blob/master/%E9%A1%BA%E9%A3%8E%E8%BD%A6%E6%8E%A5%E5%8D%95%E6%88%90.jpg?raw=true)
#### 3.1.4代取快递
通过点击上分选项栏的“代取快递”按钮，可以进入代取快递列表。

列表页将展示订单的部分信息（如快递公司、宿舍楼位置、报酬），查看其余信息可以点击“查看详情”按钮进入详情页。页面的左上角设置了“发布新订单”的按钮，用户可通过点击进入订单发布页面。右上角为搜索栏，同样可以通过输入关键字寻找订单。
![](https://github.com/33lc/33/blob/master/%E5%BF%AB%E9%80%92%E5%88%97%E8%A1%A8.jpg?raw=true)
进入订单发布页后，用户需填写快递公司、单号、宿舍地址、姓名、与快递对应的手机号、取件码、报酬以及截止时间，然而点击“发布”即可。
![](https://github.com/33lc/33/blob/master/%E5%BF%AB%E9%80%92%E5%8F%91%E5%B8%83.jpg?raw=true)
进入详情页后，用户可以获得取件截止时间、备注等剩余信息，暂不显示取件码等信息以保障发布者的财产安全。用户可点击“接单”按钮进行接单操作。
![](https://github.com/33lc/33/blob/master/%E5%BF%AB%E9%80%92%E8%AF%A6%E6%83%85.jpg?raw=true)
接单完成后，可获得发布者的快递单号、取件码、姓名、电话等取件必备信息，同时下方的状态更改为“已接单”。
![](https://github.com/33lc/33/blob/master/%E5%BF%AB%E9%80%92%E6%8E%A5%E5%8D%95.jpg?raw=true)
#### 3.1.5校园兼职
通过点击上分选项栏的“校园兼职”按钮，可以进入代取快递列表。

列表页将展示订单的部分信息（如商家名称、兼职时间、报酬），查看其余信息（如地址、联系电话、兼职内容、需要人数、备注）可以点击“查看详情”按钮进入详情页。页面的左上角设置了“发布新兼职”的按钮，用户可通过点击进入兼职发布页面。右上角为搜索栏，同样可以通过输入关键字寻找兼职。
![](https://github.com/33lc/33/blob/master/%E5%85%BC%E8%81%8C%E5%88%97%E8%A1%A8.jpg?raw=true)
进入兼职发布页面后，填写商家名称、商家地址、兼职时间段、兼职内容、兼职薪酬、需要人数后，即可发布。
![](https://github.com/33lc/33/blob/master/%E5%85%BC%E8%81%8C%E5%8F%91%E5%B8%83.jpg?raw=true)
用户在详情页查看完详细信息后，可选择“申请”也可选择返回列表继续寻找。
![](https://github.com/33lc/33/blob/master/%E5%85%BC%E8%81%8C%E8%AF%A6%E6%83%85.jpg?raw=true)
申请后，订单状态改变。
![](https://github.com/33lc/33/blob/master/%E5%85%BC%E8%81%8C%E7%94%B3%E8%AF%B7.jpg?raw=true)
#### 3.1.6个人主页
个人主页分为个人资料、我的订单、帮助三个模块。

我的订单将显示用户发布或接收的订单，便于用户查看。
![](https://github.com/33lc/33/blob/master/%E6%88%91%E7%9A%84%E8%AE%A2%E5%8D%95.jpg?raw=true)
在详情页，用户可以对订单进行修改与删除。但对于已被接单的订单，用户无法修改，需与接单者取得联系。
![](https://github.com/33lc/33/blob/master/%E6%88%91%E7%9A%84%E8%AE%A2%E5%8D%95%E8%AF%A6%E6%83%85.jpg?raw=true)
个人资料页显示用户的手机号、用户名、身份证号、姓名等消息，同时提供个人信息修改和密码修改服务。
![](https://github.com/33lc/33/blob/master/%E8%B5%84%E6%96%99.jpg?raw=true)
用户在使用过程中遇到困难，可通过“帮助”联系我们。
![](https://github.com/33lc/33/blob/master/%E5%B8%AE%E5%8A%A9%E4%B8%8D.jpg?raw=true)
#### 3.1.7后台
本系统设置了后台页面，管理人员能够在这个页面上对用户资料及订单进行管理。

页面左侧设置个人资料、顺风车、代取快递、校园兼职的选择按钮，便于管理人员选择需要管理的模块。页面上方设置了按钮，便于以进行数据的增删改操作。具体数据以列表的形式展现，较为直观。
![](https://github.com/33lc/33/blob/master/%E5%90%8E%E5%8F%B0-%E8%B5%84%E6%96%991.jpg?raw=true)

### 3.2性能需求
##### 3.2.1精度需求
<table>
   <tr>
      <td>类别</td>
      <td>名称</td>
      <td>精度</td>
   </tr>
   <tr>
      <td rowspan="5">用户资料</td>
      <td>手机号</td>
      <td>11位数字</td>
   </tr>
   <tr>
      <td>用户名</td>
      <td>6-18位数字或字母</td>
   </tr>
   <tr>
      <td>密码</td>
      <td>6-18位数字或字母</td>
   </tr>
   <tr>
      <td>真实姓名</td>
      <td>20位以内的中文或字母或“·”</td>
   </tr>
   <tr>
      <td>身份证号</td>
      <td>18位数字或字母“X”</td>
   </tr>
   <tr>
      <td rowspan="9">顺风车</td>
      <td>是否有车</td>
      <td>有车为true，无车为false</td>
   </tr>
   <tr>
      <td>车型</td>
      <td>电动车为ture，自行车为false</td>
   </tr>
   <tr>
      <td>车牌号</td>
      <td>5位数字或字母</td>
   </tr>
   <tr>
      <td>出发地</td>
      <td>40位以内的中文或字母或数字</td>
   </tr>
   <tr>
      <td>目的地</td>
      <td>40位以内的中文或字母或数字</td>
   </tr>
   <tr>
      <td>出发时间</td>
      <td>时间类型</td>
   </tr>
   <tr>
      <td>联系方式</td>
      <td>11位数字</td>
   </tr>
   <tr>
      <td>费用</td>
      <td>doule类型非负数</td>
   </tr>
   <tr>
      <td>备注</td>
      <td>60位以内的中文或字母或符号</td>
   </tr>
   <tr>
      <td rowspan="8">校园兼职</td>
      <td>商家名</td>
      <td>20位以内的中文或字母或数字</td>
   </tr>
   <tr>
      <td>商家地址</td>
      <td>40位以内的中文或字母或数字</td>
   </tr>
   <tr>
      <td>商家电话</td>
      <td>11位数字</td>
   </tr>
   <tr>
      <td>兼职时间段</td>
      <td>30位以内的中文或数字</td>
   </tr>
   <tr>
      <td>兼职内容</td>
      <td>60位以内的中文或字母或数字</td>
   </tr>
   <tr>
      <td>兼职待遇</td>
      <td>30位以内的中文或数字</td>
   </tr>
   <tr>
      <td>需要人数</td>
      <td>整型正数字</td>
   </tr>
   <tr>
      <td>备注</td>
      <td>60位以内的中文或字母或符号</td>
   </tr>
   <tr>
      <td rowspan="9">代取快递</td>
      <td>快递单号</td>
      <td>0-20位数字</td>
   </tr>
   <tr>
      <td>快递公司</td>
      <td>20位以内的中文或字母</td>
   </tr>
   <tr>
      <td>取件码</td>
      <td>12位以内的数字或“-”</td>
   </tr>
   <tr>
      <td>姓名</td>
      <td>20位以内的中文或字母或“·”</td>
   </tr>
   <tr>
      <td>手机号</td>
      <td>11位数字</td>
   </tr>
   <tr>
      <td>宿舍地址</td>
      <td>40位以内的中文或字母或数字</td>
   </tr>
   <tr>
      <td>报酬</td>
      <td>double非负数</td>
   </tr>
   <tr>
      <td>最迟取件时间</td>
      <td>时间类型</td>
   </tr>
   <tr>
      <td>备注</td>
      <td>60位以内的中文或字母或符号</td>
   </tr>
</table>

##### 3.2.2时间特性要求
更新时间设置为1分钟。
##### 3.2.3灵活性
使用bootstrap响应式框架以自适应屏幕大小的切换  
### 3.3输入输出要求
采用js前端校验的方法，对于不合法的输入进行报错并拦截在前端，直到输入格式正确为止。
### 3.4数据管理能力要求 
对注册用户的数量、用户接单和下单的数量进行记录。
### 3.5故障处理要求
服务器故障或是在上线用户体验的过程中根据用户的反馈需要增加功能时，提前向所有用户通过手机短信的方式发送我们的维护信息。
### 3.6其他专门要求
暂无特殊要求。
## 4.运行环境规定
### 4.1设备
暂无特殊要求。
### 4.2支持软件
暂无特殊要求。
### 4.3接口
(1)TCP/IP通信协议接口。

(2)socket：服务器监听双方约定的端口号，用户请求连接，连接成功后，得到socket的输入输出流进行通信。
### 4.4控制
将项目部署在云端，用户通过给定的地址即可访问。
## 5.验收验证标准

<table>
   <tr>
      <td>模块</td>
      <td>功能</td>
      <td>序号</td>
      <td>操作</td>
      <td>预期结果</td>
      <td>验收情况</td>
   </tr>
   <tr>
      <td>首页</td>
      <td>轮播图</td>
      <td>1</td>
      <td>查看轮播图</td>
      <td>轮播图播放正常</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="7">登录与注册</td>
      <td rowspan="3">登录</td>
      <td>2</td>
      <td>浏览登录页面</td>
      <td>页面完整且有提示</td>
      <td></td>
   </tr>
   <tr>
      <td>3</td>
      <td>输入正确的账号和密码</td>
      <td>登录成功，跳转首页</td>
      <td></td>
   </tr>
   <tr>
      <td>4</td>
      <td>输入错误的账号或密码</td>
      <td>登录不成功，显示“账号或密码错误”提示</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="4">注册</td>
      <td>5</td>
      <td>浏览注册页面</td>
      <td>页面完整且有提示</td>
      <td></td>
   </tr>
   <tr>
      <td>6</td>
      <td>输入尚未注册的身份证号、姓名、密码等个人信息</td>
      <td>注册成功，跳转登录页面</td>
      <td></td>
   </tr>
   <tr>
      <td>7</td>
      <td>输入已注册过的身份证号或手机号</td>
      <td>注册失败，显示“账号已注册”提示</td>
      <td></td>
   </tr>
   <tr>
      <td>8</td>
      <td>输入的个人信息格式不符合要求</td>
      <td>注册失败，显示“信息格式有误”提示</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="9">顺风车</td>
      <td rowspan="4">发布</td>
      <td>9</td>
      <td>浏览发布页面</td>
      <td>页面完整且有提示</td>
      <td></td>
   </tr>
   <tr>
      <td>10</td>
      <td>无车用户填写出发地、目的地、联系方式等内容后发布订单</td>
      <td>订单发布成功</td>
      <td></td>
   </tr>
   <tr>
      <td>11</td>
      <td>有车用户填写车型、联系方式等内容后发布订单</td>
      <td>订单发布成功</td>
      <td></td>
   </tr>
   <tr>
      <td>12</td>
      <td>部分必填内容未填或格式错误</td>
      <td>订单发布失败，并提示</td>
      <td></td>
   </tr>
   <tr>
      <td>查询</td>
      <td>13</td>
      <td>输入关键字查询</td>
      <td>查询成功，显示结果；查询失败，显示提示</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="2">浏览</td>
      <td>14</td>
      <td>查看已发布的顺风车信息</td>
      <td>页面完整，显示正常</td>
      <td></td>
   </tr>
   <tr>
      <td>15</td>
      <td>按分类查看顺风车信息</td>
      <td>页面完整，显示正常</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="2">接单</td>
      <td>16</td>
      <td>点击接单，填写相关信息</td>
      <td>接单成功，订单状态更改</td>
      <td></td>
   </tr>
   <tr>
      <td>17</td>
      <td>由于浏览时间过长，该订单已被别人接单时点击接单</td>
      <td>接单失败并提示</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="7">校园兼职</td>
      <td rowspan="3">发布</td>
      <td>18</td>
      <td>浏览发布页面</td>
      <td>页面完整且有提示</td>
      <td></td>
   </tr>
   <tr>
      <td>19</td>
      <td>商家正确填写兼职时间段、内容、待遇、人数等内容后发布</td>
      <td>订单发布成功</td>
      <td></td>
   </tr>
   <tr>
      <td>20</td>
      <td>商家填写信息时，部分必填内容未填或格式错误</td>
      <td>订单发布失败，并提示</td>
      <td></td>
   </tr>
   <tr>
      <td>查询</td>
      <td>21</td>
      <td>输入关键字查询</td>
      <td>查询成功，显示结果；查询失败，显示提示</td>
      <td></td>
   </tr>
   <tr>
      <td>浏览</td>
      <td>22</td>
      <td>查看已发布的兼职信息</td>
      <td>页面完整，显示正确</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="2">申请</td>
      <td>23</td>
      <td>点击申请</td>
      <td>申请成功，人数已满则更改订单状态</td>
      <td></td>
   </tr>
   <tr>
      <td>24</td>
      <td>申请人数已满时，点击申请</td>
      <td>接单失败并提示</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="7">代取快递</td>
      <td rowspan="3">发布</td>
      <td>25</td>
      <td>浏览发布页面</td>
      <td>页面完整且有提示</td>
      <td></td>
   </tr>
   <tr>
      <td>26</td>
      <td>需取件的用户正确填写快递公司、取件码、宿舍地址等内容后发布</td>
      <td>订单发布成功</td>
      <td></td>
   </tr>
   <tr>
      <td>27</td>
      <td>用户填写信息时，部分必填内容未填或格式错误</td>
      <td>订单发布失败，并提示</td>
      <td></td>
   </tr>
   <tr>
      <td>查询</td>
      <td>28</td>
      <td>输入关键字查询</td>
      <td>查询成功，显示结果；查询失败，显示提示</td>
      <td></td>
   </tr>
   <tr>
      <td>浏览</td>
      <td>29</td>
      <td>查看已发布的代取快递信息</td>
      <td>页面完整，显示正确</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="2">接单</td>
      <td>30</td>
      <td>点击接单</td>
      <td>接单成功，订单状态更改</td>
      <td></td>
   </tr>
   <tr>
      <td>31</td>
      <td>由于浏览时间过长，该订单已被别人接单时点击接单</td>
      <td>接单失败并提示</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="5">我的订单</td>
      <td>查看</td>
      <td>32</td>
      <td>点击查看历史订单</td>
      <td>页面完整，显示正确</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="2">编辑</td>
      <td>33</td>
      <td>暂未有人接单或申请时，点击编辑已发布的订单并正确提交修改</td>
      <td>修改成功</td>
      <td></td>
   </tr>
   <tr>
      <td>34</td>
      <td>若已有人接单或申请时，点击编辑订单</td>
      <td>无法编辑，提示与接单人联系</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="2">删除</td>
      <td>35</td>
      <td>暂未有人接单或申请时，发布者点击删除订单</td>
      <td>删除成功</td>
      <td></td>
   </tr>
   <tr>
      <td>36</td>
      <td>若订单尚未完成时，发布者点击删除订单</td>
      <td>无法删除，提示与接单人联系</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="3">个人资料</td>
      <td>查看</td>
      <td>37</td>
      <td>点击查看个人资料</td>
      <td>页面完整，显示正确</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="2">编辑</td>
      <td>38</td>
      <td>点击修改，对手机号、用户名等进行编辑</td>
      <td>修改成功</td>
      <td></td>
   </tr>
   <tr>
      <td>39</td>
      <td>编辑时，部分资料格式错误</td>
      <td>修改失败并提示</td>
      <td></td>
   </tr>
   <tr>
      <td>关于我们</td>
      <td>联系我们</td>
      <td>40</td>
      <td>点击“帮助”</td>
      <td>显示相关信息</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="6">后台管理</td>
      <td>查看</td>
      <td>41</td>
      <td>点击相应模块按钮</td>
      <td>显示对应模块内容列表</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="3">编辑</td>
      <td>42</td>
      <td>正确编辑订单内容</td>
      <td>编辑成功</td>
      <td></td>
   </tr>
   <tr>
      <td>43</td>
      <td>编辑时，部分必填内容未填或格式错误</td>
      <td>编辑失败，并提示</td>
      <td></td>
   </tr>
   <tr>
      <td>44</td>
      <td>编辑时订单已被删除</td>
      <td>编辑失败，并提示</td>
      <td></td>
   </tr>
   <tr>
      <td rowspan="2">删除</td>
      <td>45</td>
      <td>点击删除按钮</td>
      <td>删除成功</td>
      <td></td>
   </tr>
   <tr>
      <td>46</td>
      <td>自动删除超时订单</td>
      <td>删除成功</td>
      <td></td>
   </tr>

</table>

## 6.未来预期
在达成现有目标的前提下，进一步完善已有功能，同时适当的增加少许功能（例如排行榜），改善用户体验。
## 7.团队分工
技术总监：胡成宇

需求分析与原型设计：邹旖、吴姗姗

前端开发：王星雨、叶艳玲

后端开发：温俊欣、张启荣、林国钦、黄槟鸿

博客编辑：邱炜旭
