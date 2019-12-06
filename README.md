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

