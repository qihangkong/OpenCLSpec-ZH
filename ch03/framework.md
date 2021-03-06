# 3.4 OpenCL 框架
OpenCL框架允许应用程序将主机和一个或多个OpenCL设备用作单个异构并行计算机系统。该框架包含以下组件：
- OpenCL平台层：平台层允许主机程序发现OpenCL设备及其功能，并创建上下文。
- OpenCL运行时：运行时允许宿主程序在创建上下文后对其进行操作。
- OpenCL编译器：OpenCL编译器创建包含OpenCL内核的程序可执行文件。编译器支持较早的OpenCL规范提供的SPIR-V中间语言，OpenCL C，OpenCL C ++和OpenCL C语言版本。某些实现可能支持其他输入语言。

## 3.4.1 OpenCL框架：混合版本支持

OpenCL在单个平台上支持具有不同功能的设备。这包括符合OpenCL规范的不同版本的设备。对于OpenCL系统，要考虑三个版本标识符：平台版本，设备版本以及设备上支持的内核语言或IL的版本。

平台版本指示受支持的OpenCL运行时的版本。这包括主机可用于与OpenCL运行时公开的资源进行交互的所有API。包括上下文，内存对象，设备和命令队列。

设备版本指示设备功能与运行时和编译器分开，如clGetDeviceInfo返回的设备信息所表示 。与设备版本关联的属性的示例是资源限制（例如，每个计算单元的本地内存的最小大小）和扩展功能（例如，受支持的KHR扩展的列表）。返回的版本与设备符合的OpenCL规范的最高版本相对应，但不高于平台版本。

设备的语言版本表示开发人员可以假定在给定设备上支持的OpenCL编程语言功能。报告的版本是所支持语言的最高版本。

向后兼容性是OpenCL标准的重要目标。期望向后兼容，以便设备将使用具有以下最低要求的早期版本的SPIR-V和OpenCL C编程语言：
- OpenCL 1.x设备必须至少支持一种OpenCL C编程语言的1.x版本。
- 除OpenCL C 2.0编程语言外，OpenCL 2.0设备还必须支持OpenCL 1.x设备的所有要求。如果支持多种语言版本，则编译器默认使用设备支持的最高OpenCL 1.x语言版本（通常为OpenCL 1.2）。要使用OpenCL 2.0内核编程语言，程序员必须专门设置适当的编译器标志（-cl-std = CL2.0）。语言版本不得高于平台版本，但可以超过设备版本。
- 除1.0或更高版本的SPIR-V中间语言外，OpenCL 2.1设备还必须支持OpenCL 2.0设备的所有要求。中间语言版本控制被编码为二进制对象的一部分，并且不需要将标志传递给编译器。
- 除了版本1.2或更高版本的SPIR-V中间语言之外，OpenCL 2.2设备还必须支持OpenCL 2.0设备的所有要求。中间语言版本控制被编码为二进制对象的一部分，并且不需要将标志传递给编译器。

