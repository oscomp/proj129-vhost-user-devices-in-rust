# proj129-vhost-user-devices-in-rust
使用Rust实现vhost-user设备


### 项目描述与背景
出于安全，快速，轻量的需求，使用Rust开发轻量vmm越来越被重视。轻量vmm无法像Qemu那样堆砌全面的功能，因此，面向不同的应用和业务场景，开源社区和各大云厂商使用Rust建立了众多轻量vmm项目，如cloud-hypervisor, firecracker等。

为了避免重复造轮子，[rust-vmm](https://github.com/rust-vmm)社区把vmm分割成不同的crate，期待未来实现vmm只需要根据自己面向的场景快速组装vmm。

vhost-user设备在云场景中被广泛应用，但是rust-vmm还没有开箱即用的crate支持vhost-user设备，因此需要设计并实现`vhost-user-devices` crate。

### 功能描述

#### 基础功能：

你不需要实现vhost-user后端程序，使用现有的virtiofsd，spdk等验证即可。需要注意`vhost-user-devices`的兼容性，需要兼容社区中virtio设备和vhost设备框架，可transport为virtio-mmio或virtio-pci设备。你需要具体实现：

1. 实现vhost-user协议。
2. 实现内存共享模型（仍然需要与rust-vmm内存模型兼容）。
3. 实现vhost-user-net，vhost-user-blk，vhost-user-fs设备的开箱即用。
4. 必要的测试用例，并且需要成功应用并演示于firecracker项目中。


#### 扩展功能：


### 所属赛道

2022全国大学生操作系统比赛的“OS功能设计”赛道



### 参赛要求

- 以小组为单位参赛，最多三人一个小组，且小组成员是来自同一所高校的本科生（2022年春季学期或之后本科毕业的大一~大四的学生）
- 如学生参加了多个项目，参赛学生选择一个自己参加的项目参与评奖
- 请遵循“2022全国大学生操作系统比赛”的章程和技术方案要求



### 项目导师

尹益鹏 yinyipeng@bytedance.com


### 难度

中等


### 参考资料
- [rust-vmm](https://github.com/rust-vmm)
- [firecracker](https://github.com/firecracker-microvm/firecracker)
- [cloud-hypervisor](https://github.com/cloud-hypervisor/cloud-hypervisor)
- [vhost-user protocol](https://qemu.readthedocs.io/en/latest/interop/vhost-user.html)

### License

* [GPL-2.0](https://opensource.org/licenses/GPL-2.0)



## 预期目标

完成基础的开发并输出说明文档一篇。

**注意：下面的内容是建议内容，不要求必须全部完成。选择本项目的同学也可与导师联系，提出自己的新想法，如导师认可，可加入预期目标**

参考任务描述部分。
