# 10-19

**安装glib**，依赖libffi，libmount，libpcre

**libffi**

[下载地址](download.chinaunix.net/download/0006000/5819.shtml) 下载 *libffi-3.0.11-rc1.tar.gz*

解压，然后安装

```sh
./configure
make
sudo make install
```

**libmount**

```sh
sudo apt-get install libmount-dev
```

**libpcre**

[下载地址](http://sourceforge.net/projects/pcre/files/pcre/) 版本8.39

```sh
./configure --enable-utf8 --enable-unicode-properties
make
sudo make install
```

安装后输入`pcretest -C`看看是否能打印版本信息，不能的话建立两个软连接：

```sh
ln -s /usr/local/lib/libpcre.so.1 /lib
ln -s /usr/local/lib/libpcreposix.so.0 /lib
```

可能出现的错误及处理方式：[链接](http://www.cnblogs.com/pcat/p/5520317.html)

**glib**

```sh
./configure
make
sudo make install
```

**测试glib**

hello.c

```c
#include <glib.h>
#include <stdio.h>
int main(int argc, char** argv){
    GList* list=NULL;
    list=g_list_append(list,"Hello world!");
    list=g_list_append(list,"made by pcat");
    list=g_list_append(list,"http://pcat.cnblogs.com");
    printf("The first item is %s\n",g_list_first(list)->data);
    return 0;
}
```

编译命令

```sh
gcc hello.c -o hello $(pkg-config --cflags --libs glib-2.0)
```

运行`./hello`

```
The first item is Hello world!
```



