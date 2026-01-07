# 这里是一级标题

!!! note "主要贡献者"
    - 作者：[@zevorn](https://github.com/zevorn)

## 这里是二级标题

关于 Rust for QEMU（官方称 Rust in QEMU）的发展历史，最早可以追溯到 2020 年。彼时 QEMU 社区的维护者 Stefan Hajnoczi 发表了一篇名为 [Why QEMU should move from C to Rust][why-c-to-rust] 的文章，系统地阐述了 QEMU 的安全需求，获得了社区的广泛关注，由此进入构想与社区讨论阶段。

2021 年 KVM Forum 2021 [针对 Rust 展开专题讨论][rust-talk]，聚焦具体的技术路径和核心挑战。此后，Rust for QEMU 开始在 QEMU 主线外进行早期开发。

2024 年进入实验性探索阶段，QEMU 9.2 首次官方支持 Rust，默认禁用需手动开启，该版本引入构建系统支持，创建核心 Crate，提供 PL011 串口设备作为概念验证。

2025 年进入功能完善阶段，QEMU 10.0 实现了 Rust 相关源码的构建稳定和测试覆盖，新增 HPET 设备支持，同时大幅减少设备代码所需的 unsafe 代码量，并提升 Safe Rust 代码比例，以及日志记录、迁移支持等核心功能的完善。

!!! example "温馨提示"
    - 本文档使用的 QEMU 源码仓库地址是：[rust-for-qemu-insides-src][rust-for-qemu];


[why-c-to-rust]: https://blog.vmsplice.net/2020/08/why-qemu-should-move-from-c-to-rust.html
[rust-talk]: https://etherpad.opendev.org/p/KVMForum2021-QEMU+Rust-BoF
[rust-for-qemu]: https://github.com/hust-open-atom-club/qemu/tree/rust-for-qemu-insides
