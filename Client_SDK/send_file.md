# send_file.h

声明send_file.c中定义的函数：

####       const char * guess_content_type(const char *path);

* guess_content_type


 * 猜测请求的文件类型

 * path: 请求的文件路径
 * return: 返回文件类型

  #### void close_connection_cb(struct evhttp_connection * evcon, void * ctx);

* close_connection_cb

 * 非正常结束的请求的清空函数
 * return

    #### void send_file_cb(int fd, short events, void *ctx);

* send_file_cb

 * 发送缓存文件的回调函数
 * return

    #### void window_slide_cb(int fd, short events, void *ctx);

* window_slide_cb

 * 窗口滑动的回调函数
 * return

    #### void do_request_cb(struct evhttp_request *req, void *arg);

* do_request_cb

 * 响应对本地文件的请求的libevent的回调函数
 * return

    #### 
