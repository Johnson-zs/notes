# SYSCALL_DEFINE

在使用系统调用的时候，想去了解下内核 (5.10.1) 如何实现的，但是并没有找打系统调用函数的直接定义，只找到了宏定义，例如 open 函数：

```C
// fs/open.c
// 宏中的 3 : 函数参数个数
SYSCALL_DEFINE3(open, const char __user *, filename, int, flags, umode_t, mode)
{
	if (force_o_largefile())
		flags |= O_LARGEFILE;
	return do_sys_open(AT_FDCWD, filename, flags, mode);
}
```

与 `SYSCALL_DEFINE3` 宏的定义有 7 个，均为可变参的宏

```C
// include/linux/syscalls.h
#ifndef SYSCALL_DEFINE0
#define SYSCALL_DEFINE0(sname)					\
	SYSCALL_METADATA(_##sname, 0);				\
	asmlinkage long sys_##sname(void);			\
	ALLOW_ERROR_INJECTION(sys_##sname, ERRNO);		\
	asmlinkage long sys_##sname(void)
#endif /* SYSCALL_DEFINE0 */

#define SYSCALL_DEFINE1(name, ...) SYSCALL_DEFINEx(1, _##name, __VA_ARGS__)
#define SYSCALL_DEFINE2(name, ...) SYSCALL_DEFINEx(2, _##name, __VA_ARGS__)
#define SYSCALL_DEFINE3(name, ...) SYSCALL_DEFINEx(3, _##name, __VA_ARGS__)
#define SYSCALL_DEFINE4(name, ...) SYSCALL_DEFINEx(4, _##name, __VA_ARGS__)
#define SYSCALL_DEFINE5(name, ...) SYSCALL_DEFINEx(5, _##name, __VA_ARGS__)
#define SYSCALL_DEFINE6(name, ...) SYSCALL_DEFINEx(6, _##name, __VA_ARGS__)

```

除了 `SYSCALL_DEFINE0`, 其他 6 个宏做了参数转换后，均传入了宏 `SYSCALL_DEFINEx` 中

## 参考资料

- [Linux系统调用之SYSCALL_DEFINE](https://blog.csdn.net/hxmhyp/article/details/22699669)