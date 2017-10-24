# 10.17

1. 最后一个tick tick结束后，有三个get_file_range error 28: 超时错误
2. pthread_kill()发送SIGKILL信号后会导致整个进程退出，子线程和父线程共享默认信号处理函数
3. 用pthread_detach, detach之后还是会回来继续join
4. TerminateThread强行终止线程，然而ndk不支持

## 下午用sigaction指定子线程的信号处理函数

1. 在主线程中用sigaction指定信号SIGINT的处理函数（SIGKILL和SIGSTOP无法被捕获和忽略），在处理函数中调用pthread_exit(NULL); **解决了超时问题**



#### 待解决的问题

关闭服务的时间太长

可能原因是关闭服务前有几个get_file_range error code: 28 超时错误