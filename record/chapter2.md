为确保操作系统的安全，对应用程序而言，需要限制的主要有两个方面：

应用程序不能访问任意的地址空间（这个在第四章会进一步讲解，本章不会涉及）
应用程序不能执行某些可能破坏计算机系统的指令（本章的重点）

```shell
root@lin-master:~/zhihui/ros/user# make build
   Compiling user_lib v0.1.0 (/root/zhihui/ros/user)
    Finished release [optimized] target(s) in 0.48s
rust-objcopy --binary-architecture=riscv64 target/riscv64gc-unknown-none-elf/release/priv_inst --strip-all -O binary  target/riscv64gc-unknown-none-elf/release/priv_inst.bin;
root@lin-master:~/zhihui/ros/user# cd target/riscv64gc-unknown-none-elf/release/
root@lin-master:~/zhihui/ros/user/target/riscv64gc-unknown-none-elf/release# qemu-riscv64 ./priv_inst
Try to execute privileged instruction in U Mod
Kernel should kill this application!
Illegal instruction (core dumped)

