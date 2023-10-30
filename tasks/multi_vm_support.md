# 多VM支持

# 任务描述：

虚拟化的一个重要作用在于：允许用户在一台物理设备上同时运行多台虚拟机，并使其协同工作。在这类场景中，Hypervisor的工作内容要明显多于运行单台虚拟机时：不仅要负责内存、CPU、物理设备等物理资源的隔离、分配与动态调度，也负责虚拟设备的模拟，虚拟机间通信的处理等。

目前arceos的Hypervisor仅支持单台虚拟机和单个虚拟CPU运行。这限制了arceos的能力，本任务要求在arceos的Hypervisor中实现对多虚拟机的支持。

为了支持多虚拟机的正常运行，至少要解决下列问题：首先作为一切的基础，需要实现多台虚拟机多个虚拟CPU的管理和调度；同时，目前对虚拟设备的访问是不区分虚拟机的，为了正常运行多个虚拟机，需要让不同虚拟机拥有自己的虚拟设备；最后，目前虚拟机的运行参数（内存映射方案，虚拟设备配置，代码入口地址等）是硬编码在代码中的，要有效运行多个虚拟机，需要以配置文件等方式保存这些参数。

# 任务要求：

1.【基础】至少在一个架构上实现：在单个物理核心上并发运行至少2台虚拟机，每台虚拟机1个虚拟CPU。要求实现虚拟机和虚拟CPU相关信息的管理和切换、虚拟CPU的调度、不同虚拟机间虚拟设备的隔离。

2.【进阶】支持从配置文件读取虚拟机的运行参数并依此创建虚拟机。

  a.虚拟设备的配置可以采用DTB；其他配置可以自定方案；

  b.配置文件如何传递给arceos？
  
3.【可选】实现2台虚拟机之间的虚拟串口通信；

4.【高难、合作】结合多核支持，实现多个虚拟机多个虚拟CPU在多个物理核心上的调度。

# 任务考核

1.现场演示；

2.开发文档；