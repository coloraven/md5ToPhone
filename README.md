翻译中国手机号码的md5值

## 优势
可多核心同时处理
## 用法
`main.go -hashfile=c:\dds.txt -pre=pre.txt -memory=false`
如果不带参数运行，则默认读取hashes.txt和pre.txt（两个文本都为一行一条记录），并使用内存模式运行。


**编译或者直接运行时会报`gcc not found`错误的解决方法：**
```shell
# runtime/cgo
cgo: C compiler "gcc" not found: exec: "gcc": executable file not found in %PATH%
```
1. 从此处`https://sourceforge.net/projects/mingw-w64/files/`找到`86_64-win32-seh`并下载；
2. 将下载的压缩包全部解压到任意路径，如`c:\mingw`下；
3. 打开命令行，使用`set PATH=C:\mingw\bin;%PATH%`将`gcc.exe`临时加入到环境变量中；
4. 执行`go env -w CGO_ENABLED=1`将gcc编译打开。

最后，可正常编译或运行,而且编译后的程序**不再依赖**`mingw-w64`等外部工具。

## sqlite3的并发写入的问题
参考此文章解决：https://www.cnblogs.com/failymao/p/17197166.html
## todo
1. 分批次读取超大文件
