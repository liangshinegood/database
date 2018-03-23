# 1.学习资料 #
	自己购买的资料：
	[http://www.ydma.com/classroom/14/task/66](http://www.ydma.com/classroom/14/task/66)


# 2.学习总结 #
	
	创建数据库
	use runoob
	db.runoob.insert({"name":"文本"})
	show dbs
	

----------

	删除数据库
	db.dropDatabase()
		

----------
	创建集合
	db.createcollection("runoob",{"ok":1}
	db.createcollection("mycol",{capped:true,autoindexid:true,size:1111,max:10000})
	
----------
	删除集合
	db.mycol.drop()	

----------
	插入文档，更新文档，删除文档
	db.mycol.insert({"name":"xxx"})
	document = ({
					title:'abc',
					description:'xxx',
					by:"ddd",
					url:"http://xxxxx.com",
					tags:['mongb','database','nosql'],
					like:100		
				})
	db.mycol.insert(document)

	db.col.update({'title':'abc'},{$set:{'title':'abcd'}})

	db.col.find().pretty()

	db.collection.save(<document>,{writeconcerm:<document>})

	db.col.remove({'title':'MongeDb'})
		
----------

	查询条件，限定
	db.col.find({"by":"abc"}).pretty() === where by = "abc"
	
	db.col.find({"like":{$lt:50}}).pretty() === where like < 50
	同理：$lte === <=,$gt === > , $gte === >= , $ ne === !=

	db.col.find({"by":'abc',"title":"md"}) === where by='abc' and title='md'
	
	db.col.find({$or:[{"by":"abc",{"title":"md"}}]}).pretty() === where by="abc" or title="md"

	db.col.find({"likes":{$gt:50},$or:[{"by":"abc"},{"title":'md'}]}).pretty() === where likes >50 and (by='abc' or title='md')
		

----------

	排序，函数，管道符
	db.col.find({"title":{$type:2}}) 获取title 为string的数据
	db.col.find({},{"title":1,id:0}).limit(2) 限定查询条数
	db.col.find({},{"title":1,id:0}).limit(2).skip(1)跳过指定数量的数据
	db.col.find({},{}).sort({"likes":-1}) 1为升序，-1为降序
	db.col.ensureIndex({"title":1,"descript":-1}) 升降序建立索引
	db.mycol.aggregate([{$group:{id:"$by-user",num_tu:{$sum:1}}}])  sum,avg,min,max,push,first,last,addtoset

	group,sort,project,match,limit,skip,unwind,geoNear

		

# 3.问题及解决 #