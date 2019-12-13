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
