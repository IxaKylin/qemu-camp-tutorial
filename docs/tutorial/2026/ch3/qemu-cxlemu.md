# 基于 CXLMemSim 和 QEMU 的 GPU 可观测系统构建

!!! tip "项目简介"

    CXLMemSim 提供了一套基于 QEMU 的 CXL Type‑2 加速器建模与 hetGPU 集成方案，用于跨平台 GPGPU 仿真。Guest 端 CUDA 应用无需改动，通过 libcuda shim 将 CUDA Driver API 翻译为 CXL 命令，并借助内核驱动配置 CXL.cache/CXL.mem 与一致性状态；Host 端在 QEMU 设备模型中模拟 Type‑2 加速器，由 hetGPU 作为后端执行命令处理与设备内存仿真，实现端到端的“像真 GPU”运行体验。

    ![](../../../image/qemu-cxl-type2-gpu.png)

!!! note "项目方向"

    待更新

!!! question "考核标准"

    1. 技术报告（必须）：包含项目成果、代码链接
    2. 其他条件，待更新