# 安装MongoDB

安装前新建文件夹,文件树如下

```
 --mongodb
   |
   |--data
   |   |
   |   |--db
   |
   |--log

```

MongoDB文件安装在上述路径



安装后，通过管理员权限打开`cmd.exe` ，移动到安装文件夹下，输入

`mongod --directoryperdb --dbpath __yourpath1 --logpath __yourpath2 --logappend -rest --install `

mongod --directoryperdb --dbpath   D:\nodejs_projects\mongodb\data\db --logpath D:\nodejs_projects\mongodb\log\mongodb.log --logappend -rest --install

D:\nodejs_projects\mongodb

启动MongoDB

`net start MongoDB`



管理MongoDB

`mongo`



查看数据库

`db`



。。。。

`show dbs`



....

`use nodeauth`//创建数据库



`show collections`

`db.createCollection('users')`//创建表

```javascript
db.users.insert({name:"Tom Simith",email:"tom@gmail.com",username:"ts",password:"123456"})
//插入记录
```

`db.users.find()`或`db.users.find().pretty()`//查找数据库（后者显示更规范）



 ```
db.users.update({username:"ts"},{$set:{email:"tom2@gmail.com"}})
//更新记录
 ```
