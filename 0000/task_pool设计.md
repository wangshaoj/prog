taskpool的想法的设计问题：

#### 如何给工作的处理者这个类命名？
HandlerPool; ceph中有通用用法，WorkQueue，感觉更好。

#### taskpool怎么知道要做什么工作？
taskpool不需要知道做什么工作。那是HandlerPool的事情。

#### TaskPool是否需要提供"请求添加"接口
不需要，那是HandlerPool的工作。

#### TaskPool是否可复制？
不可以。

#### HandlerPool是个通用类怎么设定需要做什么工作？
HanlderPool本身不需要知道工作接口的实现，继承者来做这个具体的场景处理。

#### 如何解决函数重入问题以及并发问题。
#### 如果需要提供请求添加接口，如何命名：push_req(), attach_req()
#### TaskPool 和WorkTask的类型前置申明如何解决
无法避免

#### cct定义在子类还是父类？

#### cct是public还是private

#### 头文件define保护是否需要
必须

#### filling_eq是private好还是public好
private

#### filling_eq是指针好还是对象好

#### assert一条错误信息的简单写法
```
assert("No allowing to use static timer" == nullptr);
```
