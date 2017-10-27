# 10-26

### 上午

程序流程：

1. preparation_process -> get_node_alive
2. send_ev & win_ev

用utils.h打印log，自定义程度更高，修改utils.h模板，删掉了不需要的部分。

# 10-27

### 下午

将程序中的printf换成utils.h提供的PEAR_LOG

发现时间主要浪费在ticktick

怀疑是glib线程池不是按顺序启动的线程

正在pool.s中测试