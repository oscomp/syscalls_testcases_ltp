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

