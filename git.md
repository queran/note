##git-ssh配置与使用
####1.设置git的username和email：
    $ git config --global user.name "name"
    $ git config --global user.email "example@gmail.com"

####2.生成秘钥
    $ ssh-keygen -t rsa -C "humingx@yeah.net"![Alt text](./1447552659668.png)
连续按三个回车键
最后得到了两个文件：id_rsa和id_rsa.pub
> $ ssh-keygen -t rsa -C "example@gmail.com"
 Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/qiyun/.ssh/id_rsa):
Created directory '/c/Users/qiyun/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/User/.ssh/id_rsa.
Your public key has been saved in /c/Users/User/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:9wbvjKlWZZRWroc15QE7xrJaXLA2tz/X+SBTbUnG5gA example@gmail.com
The key's randomart image is:
+---[RSA 2048]----+
|           E +o..|
|            O.oo.|
|           B O+=.|
|          o X+Oo.|
|        S o*o.ooo|
|         .++ o..o|
|         o  * .+o|
|        .  * o .+|
|       ...o o   .|
+----[SHA256]-----+  
####4.登陆Github, 添加 ssh 。
登录后，选择Setting -> SSH keys ->ADD SSH keys，将id_rsa.pub文件里的内容复制key文本框中，输入title名称，点击ADD key 按钮。
![Alt text](./1.png)
![Alt text](./2.png)
![Alt text](./3.png)
####5.测试
 命令行输入  

    $ ssh -T git@github.com
出现提示输入yes，看到Hi之后的用户名说明成功。
>$ ssh -T git@github.com
The authenticity of host 'github.com (192.30.252.129)' can't be established.
RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no)? yes
Please type 'yes' or 'no': yes
Warning: Permanently added 'github.com,192.30.252.129' (RSA) to the list of know                                                                                                                                                 n hosts.
Hi name! You've successfully authenticated, but GitHub does not provide shell                                                                                                                                                  access.
