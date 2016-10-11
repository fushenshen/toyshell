#####一个简单的shell
实现shell的管道，处理如下的重定向

```shell
○ls△-l△-R○>○file1○
○cat○<○file1○|○wc△-c○>○file1○
○表示零个或多个空格，△表示一个或多个空格

```

- 如何从ex: ls -l中得到输入

    ex:ls -l > file 使用dup2将标准输出重定向到文件中

- 如何从 解析 ls -l > file 中的 `>`

- 如何在管道间传输 数据
对于管道类型的，从前一个命令获取输出，
传递给后一个命令作为输入

**基本实现**

```c
    int fd[2];
    if(/*parent proccess*/)
    {
        close(fd[0]);
        write ;/*write to another proccess*/
    }
    else if(/*child proccess*/)
    {
        close (fd[1]);
        /*read proccess*/
        read;
    }
    then write to stdout
```
