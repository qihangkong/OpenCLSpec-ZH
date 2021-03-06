# 第三章 OpenCL体系结构

OpenCL是一种开放式行业标准，用于对组织成一个平台的CPU，GPU和其他分离计算设备的异构集合进行编程。它不只是一种语言。 OpenCL是用于并行编程的框架，并包括语言，API，库和运行时系统以支持软件开发。例如，使用OpenCL，程序员可以编写在GPU上执行的通用程序，而无需将其算法映射到3D图形API（例如OpenGL或DirectX）上。

OpenCL的目标是希望编写可移植且高效代码的专业程序员。这包括库编写者，中间件供应商和面向性能的应用程序程序员。因此，OpenCL提供了底层硬件抽象和框架来支持变成，并且公开了底层硬件的许多细节。

为了描述OpenCL背后的核心思想，我们将使用模型层次结构：

- 平台模型
- 存储模型
- 执行模型
- 程序模型