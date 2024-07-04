如何生成SSH key并添加到Github

1.查看是否有SSH key

先输入下列命令然后回车

```shell
~/.ssh
```

如果有，则显示【Is a directory】，

如果没有，则显示【No such file or directory】。



2.如果没有，则需要进行这一步生成SSH key

```shell
ssh-keygen -t rsa -C "xxx@qq.com"
```

xxx@qq.com是自己的邮箱，创建的时候会有提示，连续3次回车即可，注意要带双引号。



3.登录自己的Github，在【settings】里找到【SSH and GPG keys】

点击【New SSH key】



4.在git bash输入【~/.ssh ls】可以查看key的路径，Github上的title随意填，Key填刚才生成的key文件，

添加成功后会有邮件通知。



5.测试一下SSH key

```shell
ssh -T git@github.com
```

提示【Hi xxx! You've successfully authenticated...】则代表通过验证。



6.使用命令

```shell
git push origin branchName
```

把本地git仓库推送到远程仓库。