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
![查询 1](https://github.com/LingFxxx/Oracle/edit/master/Test1/01.png '查询 1 结果')

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
![](./01.png '查询 1 结果')





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
![](./01.png '查询 1 结果')


