# 实验3：图书管理系统顺序图绘制
|学号|班级|姓名|
|:-------:|:-------------: | :----------:|
|201710414208|软件(本)17-2|李云东|
## 图书管理系统的顺序图
### 1. 借出资源用例
### 1.1. 借出资源用例PlantUML源码
```cpp
@startuml
actor 图书管理员
participant 读者
participant 资源项
participant 馆藏资源品种
participant 借书记录

activate 图书管理员
图书管理员 -> 读者 :验证读者
activate 读者

读者 --> 图书管理员 :读者身份非法
deactivate 读者

图书管理员 -> 读者 :取读者限额
activate 读者
读者 --> 图书管理员 :图书超出限额
deactivate 读者

图书管理员 -> 资源项 :获取资源项
activate 资源项
资源项 --> 图书管理员 :未获取资源项

资源项 -> 馆藏资源品种 :查找资源品种
activate 馆藏资源品种

馆藏资源品种 --> 资源项 :查找失败
资源项 --> 图书管理员 :查找失败

deactivate 资源项
deactivate 馆藏资源品种

图书管理员 -> 借书记录 :创建借书记录
activate 借书记录
deactivate 借书记录

图书管理员 -> 资源项 :借出资源
activate 资源项


资源项 -> 馆藏资源品种 :减少可借数量
activate 馆藏资源品种
deactivate 资源项
deactivate 馆藏资源品种

图书管理员 -> 读者 :减少可用限额
activate 读者
deactivate 读者

图书管理员 -> 借书记录 :打印借书清单
activate 借书记录
deactivate 借书记录

@enduml
```
### 1.2. 借出资源用例顺序图
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200412131230300.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2x5ZGRhc2h1YWlnZQ==,size_16,color_FFFFFF,t_70)
### 1.3. 借书用例顺序图说明
1.首先验证读者身份是否合法正确，正确进去下一步，否则返回生上层。<br/>
2.读取读者的阅读图书限额，若限额在范围内，进入下一步。超出限额返回上层。<br/>
3.获取图书资项，若资源向存在，进入下一步。未查找获取到资源项，返回上层。<br/>
4.查找资源项中的资源品种，若品种存在，进入下一步。若查到失败，逐层返回。<br/>
5.找到书籍，创建借书记录，进入下一步。<br/>
6.借出资源，然后在读者限额中减少可借书籍数量以及可用限额。<br/>
7.打印出借书清单。<br/>
### 2. 归还资源用例
### 2.1. 归还资源用例PlantUML源码
```cpp
@startuml
actor 图书管理员
participant 资源项
participant 借书记录
participant 馆藏资源品种
participant 读者
participant 逾期记录


activate 图书管理员
图书管理员 -> 资源项 :获取资源信息
activate 资源项

资源项 -> 借书记录 :取借书记录
activate 借书记录
deactivate 借书记录

资源项 -> 馆藏资源品种 :取资源的品种
activate 馆藏资源品种
deactivate 馆藏资源品种
deactivate 资源项

图书管理员 -> 读者 :获取资源信息
activate 读者
deactivate 读者

图书管理员 -> 资源项 :归还资源
activate 资源项
资源项 -> 馆藏资源品种 :增加可借数量
activate 馆藏资源品种
deactivate 馆藏资源品种
deactivate 资源项

图书管理员 -> 借书记录 :登记还书日期
activate 借书记录
deactivate 借书记录

图书管理员 -> 逾期记录 :登记逾期日期
activate 逾期记录
deactivate 逾期记录

@enduml
```

### 2.2. 归还资源用例顺序图
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020041213033365.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2x5ZGRhc2h1YWlnZQ==,size_16,color_FFFFFF,t_70)

### 2.3. 归还资源用例顺序图说明
1.首先在资源项中获取到被借书籍信息。<br/>
2.取出借书记录，以及书籍的品种信息。<br/>
3.获取读者所有信息（限额，可借数量，是否有逾期记录）。<br/>
4.归还资源，在读者信息中增加可借书籍数量。<br/>
5.登陆还书日期。<br/>
6.若超过最大还书日期（逾期情况），则进行其他处理。<br/>
