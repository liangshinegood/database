# 1.学习资料 #
	自己购买的资料：
	[http://www.ydma.com/classroom/14/task/66](http://www.ydma.com/classroom/14/task/66)


# 2.学习总结 #
	增加表
	create table partition-test(
	member-id string,
	name string
	)
	partitioned by(stat-date string,province string)
	row format delimited
		fields terminated by '\n'
	stored as sequencefile

----------

	删除表
	drop table partition-test	

----------
	插入数据
	from src
	insert overwrite table dest
	select src.*
	where src.key<100

	alter table partition-test add partition(stat-date='20100728',province="jiangsu")
	

----------
	连接
	无where 
	select * from dual a join dual b on a.key = b.key
		

----------
	加载
	load date local inpath './files/1.txt'
	overwrite into table src;	
		

----------

	分组,排序同mysql
		

----------

	行转列，列转行
	explode 一行变多行
	poseexplode 多行变一行
	lateral view 行转列，列转行

	select pagid,adid from page lateral view explode(adid-list) adtable as adid

		
# 3.问题及解决 #