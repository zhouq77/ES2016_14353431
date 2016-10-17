# DOL实例分析&编程实验
       
本次实验主要内容是理解dol实例example1和example2的具体结构和代码，并修改example1中的中间处理方式和example2中的square模块数目来观察结果，以此加深对dol实例结构的理解。

##### Task 1：修改example2，让3个square模块变成两个    

通过阅读example2.xml的代码，我们了解到“N"表示迭代次数，也就是square模块的个数，在整个结构中，squqre模块表示由生产者到消费者中间经过的处理模块，经过的square模块数可以理解为处理次数。     

观察square.c的代码可以看到square的fire函数中，进行的处理是平方。而example2中原本由三个square模块，也就是平方三次，相当于八次方。观察结果我们可以看到原来的example2跑出来的结果是(ppt上的图）：
![Alt text](http://i1.piimg.com/567571/c81c26293c010d65.png)    

将example2.xml中"N"的值改为2后，就可以看到结果变为了
![Alt text](http://p1.bqimg.com/567571/672eec4af9fbc1c7.png)    
可以看到由原来的八次方变为了四次方。
    
打开dot文件可以看到实例2的结构变成了：    
![Alt text](http://p1.bqimg.com/567571/81ff2aea9d7ae4f1.png)   

##### Task 2:修改example1，使其输出3次方数    
实例1中square的处理方式为将生产者产生的信息平方，题目要求改为三次方，其实只需要像下图中所示将原来的'i\*i' 改为 'i\*i\*i':
![Alt text](http://i1.piimg.com/567571/0d2ce8ea3213a1a2.png)
    
修改之后的结果如下图所示（输出结果为三次方）：    
![Alt text](http://i1.piimg.com/567571/478ca18416850976.png)    

##### 实验感想：    
本次实验还是比较简单的，主要是熟悉dol的实例，同时了解生产者消费者以及square之间的关系。通过本次实验我们熟悉了dol实例1和2的xml文件，理解了dol结构如何建立，以及理解了conection,channel等概念。希望能在之后的实验中对这些知识有更深刻的认识，并且能将它们运用于之后的实验中。