### 小红的linux学习记录

#### 常用命令

- 查看当前文件：ls 

  -l 参数含义：

  - -表文件，d表目录，l表软链接

  - 所有者所属组其他人的权限

- 新建目录：mkdir

- 路径移动：cd

  .. 回到上级

  .当前目录
  
- 显示当前所在的工作目录：pwd

- 删除空目录：rmdir（用的不多）

- 复制：cp

  复制文件：cp 【文件路径+名】【目标目录】

  复制目录：cp -r 【路径】【目标路径】（还可以改文件名）

  保存文件属性：cp -p

- 剪切和改名：mv

  mv 【文件/目录】【目标目录】

  mv 【文件】【改后文件名】

- 删除：rm

- 创建空文件：touch

- 显示文件：cat 

  -r 显示具体某一行

- 分页显示文件内容：

  - more
  
    分页：空格/f   分行：回车  退出：q 
  
  -  less
  
    往上翻页：page up 
  
    往上翻行：上箭头
  
    搜索：/关键词	，n表示next
  
- 


- 权限管理：chmod

  **不常用**：

  chmod 【{ugoa}{+-=}{rwx}】【文件或目录】

  eg： chmod u+x,o-r  xiaohong.list

  逗号分隔多个操作，a表示所有用户

  **常用**：

  r=4,w=2,x=1（其实就是二进制）

  rwx都有就是7,532 对应的是r-x-wx-w-

  chmod 640 xiaohong.list

  -R 表示递归修改，即修改该目录以及子目录所有文件的权限

  eg：chmod -R 777 xiaohong


- 

### mongodb

在linux上的基本操作

https://blog.csdn.net/weixin_43453386/article/details/83347385

db.adminCommand(nameOrDocument)// 切换到admin数据库,并且运行命令 
db.AddUser(username,password[, readOnly=false])  //添加用户   `
db.auth(usrename,password)     // 设置数据库连接验证  
db.cloneDataBase(fromhost)     // 从目标服务器克隆一个数据库  
db.commandHelp(name)           // returns the help for the command  
db.copyDatabase(fromdb,todb,fromhost)  // 复制数据库fromdb---源数据库名称，todb---目标数据库名称，fromhost---源数据库服务器地址  
db.createCollection(name,{size:3333,capped:333,max:88888})  // 创建一个数据集，相当于一个表  
db.createView(name, viewOn, [ { $operator: {...}}, ... ], { viewOptions } ) // 创建视图
db.createUser(userDocument)    // 创建用户
db.currentOp()                 // 取消当前库的当前操作  
db.dropDataBase()              // 删除当前数据库  
db.eval(func,args)             // (已过时) run code server-side  
db.fsyncLock()                 // 将数据保存到硬盘并且锁定服务器备份
db.fsyncUnlock() unlocks server following a db.fsyncLock()
db.getCollection(cname)        // 取得一个数据集合，同用法：db['cname'] or db.cname
db.getCollenctionNames()       // 取得所有数据集合的名称列表  
db.getLastError()              // 返回最后一个错误的提示消息  
db.getLastErrorObj()           // 返回最后一个错误的对象  
db.getLogComponents()
db.getMongo()                  // 取得当前服务器的连接对象get the server  
db.getMondo().setSlaveOk()     // allow this connection to read from then nonmaster membr of a replica pair  
db.getName()                   // 返回当操作数据库的名称  
db.getPrevError()              // 返回上一个错误对象  
db.getProfilingLevel()         // 获取profile level  
db.getReplicationInfo()        // 获得重复的数据  
db.getSisterDB(name)           // get the db at the same server as this onew  
db.killOp()                    // 停止（杀死）在当前库的当前操作 
db.listCommands()              // lists all the db commands
db.loadServerScripts()         // loads all the scripts in db.system.js
db.logout()
db.printCollectionStats()      // 返回当前库的数据集状态  
db.printReplicationInfo()      // 打印主数据库的复制状态信息  
db.printSlaveReplicationInfo() // 打印从数据库的复制状态信息  
db.printShardingStatus()       // 返回当前数据库是否为共享数据库  
db.removeUser(username)        // 删除用户  
db.repairDatabase()            // 修复当前数据库  
db.resetError()  
db.runCommand(cmdObj)          // run a database command. if cmdObj is a string, turns it into {cmdObj:1}  
db.runCommand(cmdObj)          // run a database command.  if cmdObj is a string, turns it into { cmdObj : 1 }
db.serverStatus()
db.setLogLevel(level, <component>)
db.setProfilingLevel(level, <slowms>)    // 设置profile level 0=off,1=slow,2=all 
db.setWriteConcern( <write concern doc> ) // sets the write concern for writes to the db
db.unsetWriteConcern( <write concern doc> ) // unsets the write concern for writes to the db
db.setVerboseShell(flag)       // display extra information in shell output
db.shutdownServer()            // 关闭当前服务程序  
db.stats()                     // 返回当前数据库的状态信息
db.version()                   // 返回当前程序的版本信息