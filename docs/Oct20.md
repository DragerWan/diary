# 10-20

**用glib实现线程池**

外部需要访问的东西：

* 线程池正在下载的chunk
* 线程池已经下载完的chunk

然而这些在thread_pool中已经有外部变量实现了