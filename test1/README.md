# 流程图1：考试及成绩管理流程
## PlantUML源码如下：
@startuml
|教务处|
:安排考试;
:考试安排表;
|教师|
:出卷;
split
    :A、B试卷;
split again
    :打印审批表;
|系主任|
:审批签字; 
:打印审批表;
end split
|教务处|
:打印试卷;
:试卷;
|学生|
:参加考试;
:答卷;
|教师|
:阅卷出成绩;
split
   :答卷;
   :装订存档;
   fork
   :期末流程结束;
   end fork
   end
split again
   :成绩单;
|教务处|
if(有不及格？)then(有)
   endif
   :安排考试;
   split
   :补考安排表;
   end
   split again
   |教师|
   fork
   :期末流程结束;
   end fork
end
@enduml

## 业务流程图如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200315154824201.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2x5ZGRhc2h1YWlnZQ==,size_16,color_FFFFFF,t_70)
# 流程图2： 客户维修服务流程
## PlantUML源码如下：
@startuml
|客户|
start
:申请服务;
|业务经理|
if(新客户吗？)then(是)
    :客户登记;
else(不是)
endif
   :上门勘察;
   :制定方案;
   |客户|
if (满意吗？)then(否)
   stop
   else(是)
   endif
   :签订服务合同;
   |业务经理|
   fork
   :安排工人;
       fork again
       :安排材料;
       endfork
       :填写派工单;
    |工人|
    :领取材料;
    :上门服务;
    |客户|
    :验收并填写反馈意见;
    |业务经理|
    :交会派工单;
    |财务人员|
    :结算收款;
    stop
@enduml
## 业务流程图如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200315144041239.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2x5ZGRhc2h1YWlnZQ==,size_16,color_FFFFFF,t_70)




