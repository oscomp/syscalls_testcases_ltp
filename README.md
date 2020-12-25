# Quick guide
Linux syscalls testcases from LTP.<br>
Please configure the compilation environment first:
```
export PATH=/path/to/your/riscv/toolchain:$PATH
```

<br>
Run a single syscall testcase:

```
$ cd testcases/kernel/syscalls/foo
$ make
$ PATH=$PATH:$PWD ./foo01
```

Install all syscalls testcases:

```
cd testcases/kernel/syscalls
make -j8
make install
```
This will install testcases to `/opt/ltp`

---
In regard to riscv64-nommu-uClibc-toolchain, you have to deal with this stuff:<br>
- `pthread.h`, `pthread_*`,`fork()`;
- `FILTER_OUT_MAKE_TARGETS` is usefull for removing unused modules;
- add `LDFLAGS += -Wl,-elf2flt=-r` to compile BFLT executable;
- OR just use my [Prebuilt](https://cloud.tsinghua.edu.cn/d/216d048d297444ee96e4/files/?p=%2Fk210-uclibc-testcases.tgz)

