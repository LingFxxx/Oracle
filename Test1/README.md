# 实验一

*查询 1：

```SQL
SELECT d.department_name，count(e.job_id)as "部门总人数"，
avg(e.salary)as "平均工资"
from hr.departments d，hr.employees e
where d.department_id = e.department_id
and d.department_name in ('IT'，'Sales')
GROUP BY department_name;
```

运行结果如下：
![](./01.png '查询 1 结果')

-查询 2：

```SQL
SELECT d.department_name，count(e.job_id)as "部门总人数"，
avg(e.salary)as "平均工资"
FROM hr.departments d，hr.employees e
WHERE d.department_id = e.department_id
GROUP BY department_name
HAVING d.department_name in ('IT'，'Sales');
```

运行结果如下：
![](./02.png '查询 2 结果')

相同之处：以部门名称分组查询所有部门及以下员工的总数与平均工资。


不同之处：“Where”是一个约束声明，在查询数据库的结果返回之前对数据库中的查询条件进行约束，即在结果返回之前起作用； “Having”是一个过滤声明，所谓过滤是在查询数据库的结果返回之后进行过滤，即在结果返回之后起作用。



自定义查询语句：
```SQL
SET AUTOTRACE ON
SELECT R.REGION_ID,COUNT(C.REGION_ID)AS "国家数"
FROM HR.REGIONS R, HR.COUNTRIES C
WHERE R.REGION_ID=C.REGION_ID
group by R.REGION_NAME, R.REGION_ID
HAVING R.REGION_ID IN ('1', '3');
```

运行结果如下：
![](./03.png '自定义查询结果')



该条查询语句的作用：查询ID为1和3的所在地区的国家数目。
