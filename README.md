# SAMS  学生成绩管理系统<br/>

>开发环境: windows 8.1  
JDK版本: 1.8  
开发工具: Intellij idea 2017.1  
数据库:Mysql5.6  
调试浏览器:Chrome 56


本系统分为学生成绩管理和后台资源管理
## 后台资源管理<br>
### 1.教师管理<br>
需管理员权限, 支持增加修改和删除教师的功能   
普通教师可以对自身的信息进行修改, 不可删除和新增<br><br>
权限控制:
控制字段, Teacher的tea_permission字段  
1. permission = 1: 管理员权限, 拥有一切的操作权限;
2. permission = 2: 教师权限, 除自身的信息修改, 无法操作后台资源;
### 2.系统路径资源管理<br>
需要管理员权限, 管理目前系统中的页面路径配置  
支持新增, 修改, 删除系统的页面路径<br><br>
### 3.学期管理<br>
管理系统中的学期, 目前没有提供操作功能<br><br>
### 4.学生管理<br>
展示学生的信息, 目前没有提供操作功能<br><br>
### 5.课程管理<br>
展示课程的信息, 主要展示老师和课程的关系<br><br>
### 6.班级管理<br>
展示班级的信息, 目前没有提供操作功能<br><br>

## 学生成绩管理<br>
学生成绩管理模块: 根据当前登录的老师, 默认的学期进行其所授课程的班级学生的成绩管理<br>
### 1.实验分组管理(update 2017.03.31 todo)<br>
实验分组在一个学期开始的时候, 就已经可以确定, 所以单独分成一个模块进行管理.  
默认的学期查询条件是根据当前系统的时间进行判断学期, 根据登录老师, 查找登录的老师该学期代课的班级, 如果有已经存在的班级分组, 就进行查找,如果没有, 那就不展示分组.<br> <br>
<b>此模块的功能为</b>:<br>根据登录的当前老师(非管理员), 通过指定的课程, 和选修此课程的班级来  
<b>添加, 修改或者删除</b>该班级该门课程的实验分组  

<br><br> 
### 2.分组实验成绩管理<br>
根据当前登录的老师(非管理员), 通过指定的课程, 实验次数和选修此课程的班级来  
取出该状态下已经有的所有的分组<br><b>注:</b>此模块不提供分组操作功能, 需要在<code>实验分组管理</code>模块中进行分组管理.<br>   
<b>此模块的功能为</b>:<br>支持对检索出的分组进行分数记录, 分为三种分数记录:预习成绩, 实验成绩, 报告成绩,并在后台根据相应的算法填充入该次的总成绩.  
支持对现有的分组的成绩进行修改.  
支持新增实验成绩<br><br>
### 3.作业成绩管理<br>
根据当前登录的老师(非管理员), 通过指定的课程, 作业次数和选修此课程的班级来  
取出该状态下的班级的学生.  
联合主键: 学生学号, 课程号, 学期号, 作业次数  
数据库设计:  
> 学生学号 课程号 学期号 作业次数 作业成绩 登分人 登分时间 修改时间 

<br>
<b>此模块的功能为</b>:  
支持对学生作业的成绩的填充, 修改  
支持新增作业次数<br><br>
### 4.考勤管理<br>
根据当前登录的老师(非管理员), 通过指定的课程, 考勤次数和选修此课程的班级来  
去除改状态下的班级学生.<br><br>
<b>此模块的功能为</b>:  
支持对学生考勤进行信息记录 / 修改  
支持新增考勤次数<br><br>
### 5.期末成绩管理<br>
根据当前登录的老师(非管理员), 通过指定的课程, 指定的班级, 来调取学生的信息和学生
的相关成绩(分组实验, 平时作业, 考勤), 展示相关课程的信息.<br><br>
<b>此模块的功能为</b>:  
支持对成绩模块的成绩比重修改(需总和为100%);  
支持对成绩录入 / 修改;  
支持报表形成;  
### 6.补考成绩管理<br>
根据当前登录的老师(非管理员), 通过指定的课程, 可以查询到所有需要补考的学生.<br><br>

## 项目技术栈<br>  
### 前端技术栈:  

html5, css3, javascript (es5, es6)
>框架/插件列表

* bootstarp  
* jqxWidgets控件  
* Vue  
* fontAwesome(字体UI)

### 服务端技术栈
JAVA
>框架/插件列表  

* 项目整体框架: Spring + SpringMVC + Mybaits  
* 连接池: dbcp  
* 日志: log4j

    






