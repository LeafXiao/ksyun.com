 KS3显示bucket下所有的文件名，对于敏感数据是允许的，或者漏扫工具也会检查到文件权限而告警提示，因此如何解决这个问题呢？
 具体的问题现象：
 在浏览器中输入KS3 Bucket对应的endpoint地址和Bucket名字（具体格式http://ks3-cn-beijing.ksyun.com/具体Bucket名字）能罗列出Bucket下所有的文件名称。
 
 问题原因：
 Bucket的权限为公开所有允许列出文件名信息，是正常现象。
 
 对于敏感数据客户需求不列出文件信息，该如何处理？
 
 具体有两种方法：
 
 方法1：简单直接；因为是公开的Bucket权限能列出文件信息，所以设置Bucket权限为私密。
 
 方法2：有些客户的业务很特殊，需要公开权限，此时可以通过“空间策略设置”来实现需求，具体配置如下。
 
 一、Bucket的权限继续为公开不变；
![image](https://github.com/LeafXiao/pics/blob/master/1.png)

 二、设置“空间策略”，对所有的用户配置listBucket权限为deny；
 ![image](https://github.com/LeafXiao/pics/blob/master/2.png)
 
 三、如果部分用户还需要列出文件（listBucket）权限，则在“空间策略”上述第二步deny配置的后面加上具体需要listBucket权限的allow配置即可。
 ![image](https://github.com/LeafXiao/pics/blob/master/3.png)
 
 
 
 
