翻译中国手机号码的md5值
解决过程记录：
一是导入`gorm.io/driver/sqlite`包后，编译或者直接运行时会报错.
```shell
# runtime/cgo
cgo: C compiler "gcc" not found: exec: "gcc": executable file not found in %PATH%
```
解决方法：
从此处`https://sourceforge.net/projects/mingw-w64/files/`找到`86_64-win32-seh`并下载。
将下载的压缩包全部解压到任意路径，如`c:\mingw`下，
打开命令行，使用`set PATH=C:\mingw\bin;%PATH%`将`gcc.exe`临时加入到环境变量中，再通过执行`go env -w CGO_ENABLED=1`将gcc编译打开。
最后，可正常编译或运行。而且编译后的程序不再依赖`mingw-w64`等外部工具。

set path=C:\Users\Administrator\Desktop\手机哈希破译\bin;%path%