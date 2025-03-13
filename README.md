 http://233.yanghuiyang.us.kg/
静态博客
在Ubuntu系统中，进入 /etc/ssh/sshd_config 文件并进行修改、保存、重启SSH服务的步骤如下：
 
1. 获取管理员权限：打开终端，输入命令 sudo -i ，输入当前用户密码，切换为root用户。
 
2. 备份原配置文件：执行 cp /etc/ssh/sshd_config /etc/ssh/sshd_config.bak ，对原配置文件进行备份。
 
3. 打开配置文件：使用命令 sudo nano /etc/ssh/sshd_config 或 sudo vim /etc/ssh/sshd_config ，用nano或vim编辑器打开配置文件。
 
4. 在nano编辑器中操作：用方向键移动光标，按 Ctrl+W 输入要查找的配置项进行查找。确保 PasswordAuthentication 的值为 yes ， ChallengeResponseAuthentication 的值为 yes 。若文件中没有 ChallengeResponseAuthentication yes 和 UsePAM yes ，在文件末尾或适当位置添加这两行。
 
5. 保存并退出nano：按 Ctrl+O 保存文件，按 Ctrl+X 退出编辑器。
 
6. 在vim编辑器中操作：进入编辑模式 i ，使用 / 搜索关键词。按 Shift+G 跳转到文件末尾，添加缺失配置项。完成后按 Esc ，输入 :wq 回车保存并退出。
 
7. 重启SSH服务：输入 sudo systemctl restart ssh 或 sudo service ssh restart 重启SSH服务。
 
8. 验证修改：执行 sshd -T | grep -E 'passwordauthentication|challengeresponseauthentication|usepam' ，查看配置是否修改成功。
