# 1.学习资料 #
	自己购买的资料：
	[http://www.ydma.com/classroom/14/task/66](http://www.ydma.com/classroom/14/task/66)


# 2.学习总结 #
	
	增加表
	create table abc(
	id int not null auto_increment,
	title varchar(100) not null,
	author varchar(40),
	s-date date,
	)primary key(id)

----------

	删除表
	drop table abc
		

----------
	插入数据
	insert into abc(id,title,author,s-date)
	values(1,"xxx","张三",'2018-3-5')
		

----------
	连接
		select a.rid,a.authour,b.tch
		from tb a inter join tcout b
		on a.rid = b.rid
		
		or
		select ***
		from tb a,tcout b
		where a.rid = b.rid

----------
	加载
	load date local infile 'dump.txt' into table mytb;
	load date local infile 'dump.txt' into table mytb
	field terminated by ":"
	lines terminated by "\r"	
		

----------

	分组
	select a.id ,count(*) from table a where a = "abc" group by a.id
	
		

----------

	排序
	select a.id,a.name from table a where a='abc' order by a.id

		

# 3.问题及解决 #