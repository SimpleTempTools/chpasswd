# chpasswd

批量改服务器帐号的密码, 把执行的结果按照类型分类放在文件中

1. 把要修改的机器列表放到 node.list文件中,每个机器一行

2. 修改my.config,(不要用引号去把key或者value因起来，这个不是yaml)：

   ssh：就是当前执行的ssh

   password: 要修改成最后的密码

   user: 修改的帐号名


3. 运行批量修改命令， ./run 

    (可以多次重复执行，已经成功的会跳过，成功的机器存在Success文件中，失败的机器会存在Fail＊ 中, Success 加上Fail＊ 的机器就是全部的机器)

4. 运行失败的机器从试命令, ./run.Fail 
    
    (这个命令下可能会重启sshd服务)
