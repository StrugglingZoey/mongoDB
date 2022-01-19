# mongoDB的安装及配置过程中用到的命令&语句

1. 创建新文件夹：mkdir data log
2. 赋予文件夹读写权限：sudo chown username /usr/local/mongodb/data
3. 添加环境变量：export PATH=${PATH}:/usr/local/mongodb/bin
4. 手动指定目录启动mongoDB：mongod --fork --dbpath data --logpath log/mongo.log --logappend
5. 根据配置文件启动mongoDB：mongod -f /usr/local/mongodb/etc/mongodb.conf 
6. 关闭mongoDB：
   use admin
   db.shutdownServer({force:true})
7. 建立root用户：db.createUser({user:"root",pwd:"123456",roles:[{role:"root",db:"admin"}]})
8. 登录：db.auth('root','123456')
9. 赋予权限：db.grantRolesToUser( "root" , [{role: "hostManager", db: "admin"}])
