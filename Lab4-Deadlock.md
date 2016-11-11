#1.	死锁停在第212次：
![deadlock.png](http://upload-images.jianshu.io/upload_images/3243720-99f465c358ebf450.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#2.	产生死锁的4个必要条件:
1.资源互斥（Mutual exclusion）: 一个资源每次只能被一个进程使用
2.占有及等待（Hold and wait）: 一个进程因请求资源而阻塞时，对已获得的资源保持占有
3.非抢占（No preemption）: 进程已获得的资源，在末使用完之前，不能强行剥夺
4.循环等待（Circular wait）: 若干进程之间形成一种头尾相接的循环等待资源关系

#3.	对上述程序产生死锁的解释：
![AB.png](http://upload-images.jianshu.io/upload_images/3243720-a9dd409eef79fe68.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![deadlock.png](http://upload-images.jianshu.io/upload_images/3243720-4b613aec24aa0926.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
当一个线程访问object的一个synchronized同步代码块或同步方法时，其他线程对object中所有其它synchronized同步代码块或同步方法的访问将被阻塞。
t.start()之后，线程t被插入调度队列中，当t被调度的时候就执行run()中的代码：b.methodB(a)，其中调用a.last(); 若与此同时执行了a.methodA(b)，其中调用b.last(); 那么由于a.methodA()在执行中，且被synchronized字段修饰，b.methodB(a)无法访问同样为synchronized的函数a.last()；同时由于b.methodB()正在被访问，且被synchronized字段修饰，a.methodA(b)无法访问同样为synchronized的函数b.last()。那么这两个线程产生了循环等待，将无限制地互相等待释放资源，从而产生了死锁。
