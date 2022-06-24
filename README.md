# linux-cmd

1. 跨账户传输文件：首先到要复制的文件夹下，然后 scp -r * zdliu@192.168.126.181:~/jhli_data/

2. 查看文档有多上行：wc -l train.en

3. 裁剪文件前n行：head -n $filename > $newfilename

4. 查看文件大小：du -h 文件名

5. 查看环境变量：vim ~/.bashrc，修改之后编辑 source ~/.bashrc

6. 查看文件前5行：head -n 5 $filename

7. 根据进程id查看用户名： top p 12345

8. 去掉test.tran中的@（逆子词化）：sed -r 's/(@@ )|(@@ ?$)//g' test.tran > test.tran1

9. 替换@-@但是好像不需要用：sed -i 's/( @-@ )/(-)/g' test.tran1 > test.tran2

10. 将file1.txt和file2.txt合并到file.txt: cat file1.txt file2.txt > file.txt

11. 比较两个文件的不同点： vimdiff test.tran1 ../test.de

12. 服务器不显示进程的路径，只显示python3:进入train.sh，修改里面的参数，然后直接执行这个脚本（bash train.sh）

13. 行首添加字符串：sed 's/^/[1] /' abc.txt >> test.txt
    行尾添加字符串：sed 's/$/ [1]/' abc.txt >> test.txt
    开头和结尾同时添加：sed '/./{s/^/[1] /;s/$/ [1]/}' train.de >> ../pa_token_nmt/train.de

14. 随机按行打乱文件：shuf file1.txt -o file2.txt
    
15. 删除文件所在行：首先vim file1.txt, 将光标移动到所在行，然后按下dd。相当于windows下的ctrl+X，假如文件有n行，怎么删除所有文件呢？光标移动到第一行按下3个字母：ndd。就把所有行都删除了。

16. 查看GPU使用情况：nvidia-smi

17. 解压文件：unzip -n zip文件

18. top -p pid

    top -u username
 
19. 查看动态更新的log文件：tail -f train.log

20. 一次复制多个文件：cp /home/usr/dir/{file1,file2,file3,file4} /home/usr/destination/

21. 注释多行文本
    1. Ctrl+V，进入VISUAL BLOCK模式。
    2. 使用上下的方向键移动光标，选择你需要注释的行。
    3. shift+i ， 输入注释符号 #，按esc。这三步都要操作完。 稍微等待2秒，修改成功。
    
22. 取消注释多行文本
    1. Ctrl+V，进入VISUAL BLOCK模式。
    2. 使用上下的方向键移动光标，选择你需要取消注释的行。
    3. 输入 x，删除所有的 #，同时退出visual block模式。
    
23. 行跳转和列跳转方法：https://www.cnblogs.com/dylancao/p/9792103.html

24. 查看多个文件的BLEU并排序：grep 'BLEU' *000/valid.tran.evalmb | sort -rk 2

25. 去空行：sed '/^$/d' sources.list   去行首空格： sed 's/^ *//g' test

26. 去重：sort -n cn.txt | uniq

27. 去掉windows下的回车符（注意^M在linux下写法，按住CTRL+v，松开v，按m）：sed -i 's/^M//g' 文件名

28. 抽取偶数行：awk '{if (NR%2 == 0)  print $0; }' 文件名 > 重定向文件名

29. 本地提交到github， github上没有这个项目<br/>
    git init<br/>
    git add .<br/>
    git commit -m "提交的注释"<br/>
    git remote add origin yourRepositoryAddress<br/>
    git push origin master<br/>
30. 本地提交到github， github上有这个项目<br/>
    git add .<br/>
    git commit -m "提交的注释"<br/>
    git pull origin master   # 如果冲突需要从origin主机拉取master分支<br/>
    git push origin master<br/>
31. 查看进程信息： ps -x pid | less
32. 删除一个文件的前5行:  tail -n +5 file1.txt > file2.txt
33. 删除一个文件的后5行： head -n -5 file1.txt > file2.txt
34. 把stories文件夹下以.story结尾的文件复制到stories文件夹下：find stories/ -name "*.story" | xargs -i cp {} ../stories/
35. 查看一个进程的完整命令： ps pid | less
36. 有的脚本可能不能执行，使用 chmod 命令能够给予脚本执行模式或者权限。chmod +x myscript.py
37. 删除三天之前的文件：find /usr/local/backups -mtime +10 -name "*.*" -exec rm -rf {} \;
38. 打包压缩文件，把当前文件夹下所有文件打包压缩到corpus.tar.gz：tar -zcvf corpus.tar.gz * 
