## server.h

定义结构体

1. table_entry 文本类型
2. node_info 节点信息
3. file_transfer_session_info 某个线程开启下载所需信息
4. thread_pool 线程池
5. send_file_ctx 请求的context

全局变量

1. struct table_entry content_type_table[]全局静态常量
2. struct event_base *base;
3. struct evhttp *http;
4. struct evhttp_bound_socket *handle;

## server.c

主函数

1. 忽略SIGPIPE信号
2. 创建event_base base
3. 基于base创建evhttp http
4. http绑定回调函数为do_request_cb
5. http绑定socket（127.0.0.1:60000）
6. 启动事件循环监听