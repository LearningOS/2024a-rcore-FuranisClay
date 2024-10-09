### 一、实现功能
实现系统调用 SYSCALL_TASK_INFO 对应的功能，并通过相关函数实现相关功能，以及跟踪任务调用
1. 通过构造结构体 TaskInfo记录task的相关内容，如任务状态，调用次数等等，实现任务间的信息传递。TaskInfo包含了TaskControlBlock原有的Status属性，增强代码的可读性以及程序的清晰结构
2. 实现函数fetch_current_task_info 通过静态对象TASK_MANAGER实现该函数供各个模块调用，通过传入的TaskInfo精准定位查找的是哪一个任务的相关信息，获取当前task信息，并更新了last_time以及time属性。
3. 实现函数trace_syscall 同样通过静态对象TASK_MANAGER管理，通过传入的taskid来查找任务，实现分别记录各个任务调用次数的管理，每次进行syscall的时候调用该函数，既对所有任务进行管理，包括fetch_task_info方法，符合实验需求。

### 二、简答作业
1. 