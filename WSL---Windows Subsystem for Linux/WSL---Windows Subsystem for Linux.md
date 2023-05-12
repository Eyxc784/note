WSL---Windows Subsystem for Linux

挖个坑

冷知识: WSL 和 WSL2(the Windows Subsystem for Linux)是一个或多个完整的，运行在Windows 10上的本地 Linux。这些Linux系统是完整且真实的。WSL2通过虚拟技术，提供了一个真正的 Linux 内核，并在 Windows 上运行。而Cygwin不是真正的 Linux。Cygwin 是 GNU 和开源工具的一个大集合，它们提供了类似于 Windows 上的 Linux 的功能——但它不是 Linux。这是一个幻影。它是针对 Win32 编译的 GNU utils。这很不错，但重要的是你要知道它们之间的区别。Cygwin 可以让您运行 bash shell 脚本，但它不会运行 Apache、 Docker 或其他真正的 ELF-binaries 和 Linux 应用程序。

