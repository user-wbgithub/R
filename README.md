<<<<<<< HEAD

R 数据类型、方法、作图
向量、序列、矩阵、数据框

函数数据类型：

	向量：
	> x<-c(1,2,3)
	> x
	[1] 1 2 3

	序列：
	> data<-seq(2,10)
	> data
	[1]  2  3  4  5  6  7  8  9 10

	> data<-seq(2,10,by=2)
	> data
	[1]  2  4  6  8 10

	> data<-seq(length=4,from=4,by=2)
	> data
	[1]  4  6  8 10

	rep()重复函数重复序列：

	> data2<-rep(data)
	> data2
	[1]  4  6  8 10

	> data3<-rep(data,3)
	> data3
	[1]  4  6  8 10  4  6  8 10  4  6  8 10
	
	> data4<-rep(data,c(2,2,3,3))
	> data4
	[1]  4  4  6  6  8  8  8 10 10 10

	paste()连接成字符串：

	> data<-paste("a","b",1,2)
	> data
	[1] "a b 1 2"
	
	> data<-paste("a","b",1,2,sep=",")
	> data
	[1] "a,b,1,2"
	
	> data<-paste("a","b",1,2,sep="")
	> data
	[1] "ab12"

	[]数据子集修改：

	> data<-seq(1,10)
	> data<-data[data>3]
	> data
	[1]  4  5  6  7  8  9 10

	summary()查看信息:
	
	> data<-seq(1,10)
	> summary(data)
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
   1.00    3.25    5.50    5.50    7.75   10.00 
   
   	factor()相当于去重set:

   	> data<-c("h","h","h","e","l","l","o")
	> factor(data)
	[1] h h h e l l o
	Levels: e h l o

	matrix()矩阵

	> data<-matrix(1:6,3,2)
	> data
     	[,1] [,2]
	[1,]    1    4
	[2,]    2    5
	[3,]    3    6

	> data<-matrix(1:2,3,2)
	> data
     	[,1] [,2]
	[1,]    1    2
	[2,]    2    1
	[3,]    1    2

	> data<-matrix(1:3,2,3)
	> data
     	[,1] [,2] [,3]
	[1,]    1    3    2
	[2,]    2    1    3
	> t(data)
     	[,1] [,2]
	[1,]    1    2
	[2,]    3    1
	[3,]    2    3

	cbind()rbind()列/行连接矩阵
	
	> x1<-c(1,2,3,4)
	> x2<-c(5,6,7,8)
	
	> data<-cbind(x1,x2)
	> data
    	 x1 x2
	[1,]  1  5
	[2,]  2  6
	[3,]  3  7
	[4,]  4  8
	> data<-rbind(x1,x2)
	> data
   		[,1] [,2] [,3] [,4]
	x1    1    2    3    4
	x2    5    6    7    8

	data.frame()数据框相当于表

	> x1<-data.frame(name=c("tom","jary","rose","jim"),age=c(12,12,14,15))
	> x1
	  name age
	1  tom  12
	2 jary  12
	3 rose  14
	4  jim  15
	对数据框中的元素进行操作
	> x1$name
	[1] tom  jary rose jim 
	Levels: jary jim rose tom

	attach()detach()挂接/卸载挂接
	
	挂接以后可以直接操作数据框中的元素
	> attach(x1)
	> name
	[1] tom  jary rose jim 
	Levels: jary jim rose tom
	> age
	[1] 12 12 14 15

	不想挂接时卸载挂接
	> detach(x1)
	> name
	错误: 找不到对象'name'

	read.table()读取文件中的内容

	> data<-read.table("blood.txt",header=T)

	
R做图

	plot()

	plot(a,b,xlab="单价",ylab="利润",type="h",main="单间-利润散点图")

	boxplot()箱线图