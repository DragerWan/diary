# 10-23

成功改用线程池

### 问题

1. 编译命令gcc send_file.c get_file.c first_aid.c server.c -levent -lcurl -ljansson -pthread -o server $(pkg-config --cflags --libs glib-2.0)写在Makefile中的时候无法正确执行，必须用命令行执行
2. 拖拽进度条太多会卡死，程序循环开启和结束下载，视频无法播放，并且用ctrl + C无法使程序退出，老版本也有这种问题，但是用ctrl+C可以退出。

## 加速安卓应用播放视频

chunk 0 与 chunk 2下载比较慢，可用节点只有3到5个，而且目前没有实现节点的打分机制。

想法：

1. 第一个window download只下载0-4的chunk（作用不大）
2. winslide间隔从10s改为5s（作用不大）
3. 测速时用detach代替pthread_join(进程会崩)
4. 测速线程超时设为1s（可以节省几秒钟）





