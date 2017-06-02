---
title: "Performance Counters in the .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "performance, .NET Framework applications"
  - "performance counters"
  - "performance monitoring, counters"
ms.assetid: 06a4ae8c-eeb2-4d5a-817e-b1b95c0653e1
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Performance Counters in the .NET Framework
本主题提供位于[性能监视器](http://technet.microsoft.com/library/cc749249.aspx)中的性能计数器的列表。  
  
-   [异常性能计数器](#exception)  
  
-   [互操作性能计数器](#interop)  
  
-   [JIT 性能计数器](#jit)  
  
-   [加载性能计数器](#loading)  
  
-   [锁定和线程性能计数器](#lockthread)  
  
-   [内存性能计数器](#memory)  
  
-   [联网性能计数器](#networking)  
  
-   [安全性能计数器](#security)  
  
<a name="exception"></a>   
## 异常性能计数器  
 性能控制台 .NET CLR Exceptions（异常）类别包含的计算取提供应用程序引发的异常的相关信息。  下表描述这些性能计数器。  
  
|性能计数器|描述|  
|-----------|--------|  
|**\# of Exceps Thrown（引发的异常数）**|显示从应用程序启动以来引发的异常总数。  此数值包括 .NET 异常和转换为 .NET 异常的非托管异常。  例如，从非托管代码返回的 HRESULT 在托管代码中会被转换为异常。<br /><br /> 此计数器包括已处理和未经处理的异常。  将再次计算重新引发的异常。|  
|**\# of Exceps Thrown \/ Sec（引发的异常数\/秒）**|显示每秒引发的异常数。  此数值包括 .NET 异常和转换为 .NET 异常的非托管异常。  例如，从非托管代码返回的 HRESULT 在托管代码中会被转换为异常。<br /><br /> 此计数器包括已处理和未经处理的异常。  此数值不是一段时间内的平均值；它显示最后两个示例中观测值的差除以示例间隔所得的结果。  此计数器是一个潜在性能问题（如果引发较多数目 \(\>100\) 的异常）的指示器。|  
|**\# of Filters \/ Sec（筛选次数\/秒）**|显示每秒执行的 .NET 异常筛选次数。  无论异常是否已处理，都会计算异常筛选。<br /><br /> 此计数器不是一段时间内的平均值；它显示最近两个样本观测值的差除以取样间隔所得的结果。|  
|**\# of Finallys \/ Sec（Finally 数量\/秒）**|显示每秒执行的 finally 块的数量。  无论以何种方式退出 try 块，均会执行 finally 块。  此计数器只计算到为异常执行的 finally 块，不计算正常代码路径上的 finally 块。<br /><br /> 此计数器不是一段时间内的平均值；它显示最近两个样本观测值的差除以取样间隔所得的结果。|  
|**Throw to Catch Depth \/ Sec（引发到捕获的深度\/秒）**|显示从引发异常的帧到处理该异常的帧每秒遍历的堆栈帧数。  此计数器在输入异常处理程序后重置为零，因此嵌入的异常显示处理程序到处理程序的堆栈深度。<br /><br /> 此计数器不是一段时间内的平均值；它显示最近两个样本观测值的差除以取样间隔所得的结果。|  
  
<a name="interop"></a>   
## 互操作性能计数器  
 性能控制台 .NET CLR Interop（互操作）类别包括的计数器提供应用程序与 COM 组件、COM \+ 服务和外部类型库交互的相关信息。  下表描述这些性能计数器。  
  
|性能计数器|描述|  
|-----------|--------|  
|**\# of CCWs（CCW 数目）**|显示 COM 可调用包装 \(CCW\) 的当前数目。  CCW 是指正在从非托管 COM 客户端引用的托管对象的代理。  此计数器显示非托管 COM 代码所引用的托管对象数。|  
|**\# of marshaling（封送处理次数）**|显示从应用程序启动以来已将参数和返回值从托管代码封送至非托管代码（反之亦然）的总次数。  如果存根内联，则此计数器不会递增。  （存根负责封送处理参数和返回值）。  如果封送处理开销很小，存根通常为内联。|  
|**\# of Stubs（存根数）**|显示由公共语言运行时创建的当前存根数。  存根负责在 COM 互操作调用或平台 invoke 调用期间将参数和返回值从托管代码封送值非托管代码（或反之）。|  
|**\# of TLB exports \/ sec（TLB 导出次数\/秒）**|留待将来使用。|  
|**\# of TLB imports \/ sec（TLB 导入次数\/秒）**|留待将来使用。|  
  
<a name="jit"></a>   
## JIT 性能计数器  
 性能控制台 .NET CLR JIT 类别包括的计数器提供已进行 JIT 编译的代码的相关信息。  下表描述这些性能计数器。  
  
|性能计数器|描述|  
|-----------|--------|  
|**\# of IL Bytes JITted（实时编译的 IL 字节数）**|显示从应用程序启动以来，由实时 \(JIT\) 编译器编译的 Microsoft 中间语言 \(MSIL\) 字节总数。  此计数器等效于 **Total \# of IL Bytes Jitted**（实时编译的 IL 字节总数）计数器。|  
|**\# of Methods JITted（实时编译的方法数）**|显示从应用程序启动以来 JIT 编译的方法总数。  此计数器不包括预先进行 JIT 编译的方法。|  
|**% Time in Jit（JIT 所占时间百分比）**|显示自上次 JIT 编译阶段以来 JIT 编译所用运行占用时间的百分比。  此计数器在每个 JIT 编译阶段结束时更新。  编译方法及其依赖关系时即发生 JIT 编译阶段。|  
|**IL Bytes Jitted \/ sec（实时编译的 IL 字节\/秒）**|显示每秒 JIT 编译的 MSIL 字节数。  此计数器不是一段时间内的平均值；它显示最近两个样本观测值的差除以取样间隔所得的结果。|  
|**Standard Jit Failures（标准 JIT 失败）**|显示自应用程序启动以来 JIT 编译器编译失败的方法的高峰数量。  如果无法验证 MSIL 或者 JIT 编译器中出现内部错误，则可能发生此失败。|  
|**Total \# of IL Bytes Jitted（实时编译的 IL 字节总数）**|显示自应用程序启动以来 JIT 编译的 MSIL 字节总数。  此计数器等效于 **\# of IL Bytes Jitted**（实时编译的 IL 字节数）计数器。|  
  
<a name="loading"></a>   
## 加载性能计数器  
 性能控制台 .NET CLR Loading（加载）类别包括的计数器提供已加载的程序集、类和应用程序域的相关信息。  下表描述这些性能计数器。  
  
|性能计数器|描述|  
|-----------|--------|  
|**% Time Loading（加载时间所占百分比）**|留待将来使用。|  
|**Assembly Search Length（程序集搜索长度）**|留待将来使用。|  
|**Bytes in Loader Heap（加载程序堆中的字节数）**|显示所有应用程序域中类加载程序提交的当前内存大小（以字节为单位）。  提交的内存是磁盘页面文件中保留的物理空间。|  
|**Current appdomains（当前 Appdomain）**|显示在此应用程序中加载的应用程序域的当前数目。|  
|**Current Assemblies（当前程序集）**|显示当前运行的应用程序中所有应用程序域范围内已加载的当前程序集数量。  如果程序集以非特定于域的形式从多个应用程序域中加载，则此计数器只递增一次。|  
|**Current Classes Loaded（当前已加载的类）**|显示所有程序集中已加载类的当前数目。|  
|**Rate of appdomains（Appdomain 速率）**|显示每秒加载的应用程序域的数量。  此计数器不是一段时间内的平均值；它显示最近两个样本观测值的差除以取样间隔所得的结果。|  
|**Rate of appdomains unloaded（已卸载的 Appdomain 速率）**|显示每秒卸载的应用程序域的数量。  此计数器不是一段时间内的平均值；它显示最近两个样本观测值的差除以取样间隔所得的结果。|  
|**Rate of Assemblies（程序集速率）**|显示所有应用程序域范围内每秒加载的程序集数量。  如果程序集以非特定于域的形式从多个应用程序域中加载，则此计数器只递增一次。<br /><br /> 此计数器不是一段时间内的平均值；它显示最近两个样本观测值的差除以取样间隔所得的结果。|  
|**Rate of Classes Loaded（加载的类的速率）**|显示所有程序集中每秒加载的类的数量。  此计数器不是一段时间内的平均值；它显示最近两个样本观测值的差除以取样间隔所得的结果。|  
|**Rate of Load Failures（加载失败的速率）**|显示每秒加载失败的类的数量。  此计数器不是一段时间内的平均值；它显示最近两个样本观测值的差除以取样间隔所得的结果。<br /><br /> 加载失败的原因有很多，例如安全性不够或格式无效。  有关详细信息，请参阅分析服务帮助。|  
|**Total \# of Load Failures（加载失败总数）**|显示自应用程序启动以来加载失败的类的高峰数量。<br /><br /> 加载失败的原因有很多，例如安全性不够或格式无效。  有关详细信息，请参阅分析服务帮助。|  
|**Total Appdomains（Appdomain 总数）**|显示自应用程序启动以来已加载的应用程序域的高峰数量。|  
|**Total appdomains unloaded（卸载的 Appdomain 总数）**|显示自应用程序启动以来卸载的应用程序的高峰数量。  如果应用程序域加载和卸载多次，则此计数器将在每次卸载应用程序域时均递增。|  
|**Total Assemblies（程序集总数）**|显示自应用程序启动以来加载的程序集总数。  如果程序集以非特定于域的形式从多个应用程序域中加载，则此计数器只递增一次。|  
|**Total Classes Loaded（已加载的类总数）**|显示自应用程序启动以来所有程序集中加载的类的累计数量。|  
  
<a name="lockthread"></a>   
## 锁定和线程性能计数器  
 性能控制台 .NET CLR LocksAndThreads（锁定和线程）类别包括的计数器提供应用程序所使用的托管锁定和线程的相关信息。  下表描述这些性能计数器。  
  
|性能计数器|描述|  
|-----------|--------|  
|**\# of current logical Threads（当前逻辑线程数目）**|显示应用程序中当前托管的线程对象的数目。  此计数器保留正在运行和已停止的线程的计数。  此计数器不是一段时间内的平均值；它仅显示的上次观测的值。|  
|**\# of current physical Threads（当前物理线程数目）**|显示公共语言运行时创建和拥有以用作托管线程对象的基础线程的本机操作系统线程数。  此计数器的值不包括运行时在其内部操作中使用的线程；它是操作系统进程中线程的子集。|  
|**\# of current recognized threads（当前已识别的线程数目）**|显示当前已由运行时识别的线程数。  这些线程与对应的托管线程对象相关联。  运行时不创建这些线程，但它们在运行时内至少运行过一次。<br /><br /> 仅跟踪唯一线程；其线程 ID 与重新输入运行时或在线程退出后重新创建的线程 ID 相同的线程不会进行两次计数。|  
|**\# of current recognized Threads（当前已识别的线程数目）**|显示自应用程序启动以来已由运行时识别的线程总数。  这些线程与对应的托管线程对象相关联。  运行时不创建这些线程，但它们在运行时内至少运行过一次。<br /><br /> 仅跟踪唯一线程；其线程 ID 与重新输入运行时或在线程退出后重新创建的线程 ID 相同的线程不会进行两次计数。|  
|**Contention Rate \/ Sec（争用率\/秒）**|显示运行时中线程尝试获取托管锁定的失败率。|  
|**Disk Queue Length（磁盘队列长度）**|显示当前正在等待获取应用程序中托管锁定的线程总数。  此计数器不是一段时间内的平均值；它显示上次观测的值。|  
|**Queue Length \/ sec（队列长度\/秒）**|显示每秒内等待获取应用程序中锁定的线程数目。  此计数器不是一段时间内的平均值；它显示最近两个样本观测值的差除以取样间隔所得的结果。|  
|**Queue Length Peak（队列长度峰值）**|显示自应用程序启动以来等待获取托管锁定的线程总数。|  
|**rate of recognized threads \/ sec（已识别线程的速率\/秒）**|显示每秒内由运行时识别的线程数。  这些线程与对应的托管线程对象相关联。  运行时不创建这些线程，但它们在运行时内至少运行过一次。<br /><br /> 仅跟踪唯一线程；其线程 ID 与重新输入运行时或在线程退出后重新创建的线程 ID 相同的线程不会进行两次计数。<br /><br /> 此计数器不是一段时间内的平均值；它显示最近两个样本观测值的差除以取样间隔所得的结果。|  
|**Total \# of Contentions（争用总数）**|显示运行时中线程已尝试获取托管锁失败的总次数。|  
  
<a name="memory"></a>   
## 内存性能计数器  
 性能控制台 .NET CLR Memory（内存）类别包括的计数器提供垃圾回收器的相关信息。  下表描述这些性能计数器。  
  
|性能计数器|描述|  
|-----------|--------|  
|**\# Bytes in all Heaps（所有堆中的字节数）**|显示 **Gen 1 Heap Size**（第 1 级堆大小）计数器、**Gen 2 Heap Size**（第 2 级堆大小）计数器和 **Large Object Heap Size**（大对象堆大小）计数器的总和。  此计数器显示垃圾回收堆上分配的当前内存（以字节为单位）。|  
|**\# GC Handles（GC 句柄数）**|显示正在使用的垃圾回收句柄的当前数目。  垃圾回收句柄是指公共语言运行时和托管环境外部的资源的句柄。|  
|**\# Gen 0 Collections（第 0 代回收次数）**|显示自应用程序启动以来第 0 代对象（即最年轻、最近分配的对象）进行垃圾回收的次数。<br /><br /> 第 0 代中的可用内存不能满足分配请求时，会出现第 0 代垃圾回收。  此计数器在第 0 代垃圾回收结束时递增。  较高代的垃圾回收包含所有较低代的垃圾回收。  此计数器在较高代（第 1 或第 2 代）垃圾回收发生时显示递增。<br /><br /> 此计数器显示上次观测的值。  **\_Global\_** 计数器值不准确，应当忽略。|  
|**\# Gen 1 Collections（第 1 代回收次数）**|显示自应用程序启动以来第 1 代对象进行垃圾回收的次数。<br /><br /> 此计数器在第 1 代垃圾回收结束时递增。  较高代的垃圾回收包含所有较低代的垃圾回收。  此计数器在较高代（第 2 代）垃圾回收发生时显式递增。<br /><br /> 此计数器显示上次观测的值。  **\_Global\_** 计数器值不准确，应当忽略。|  
|**\# Gen 2 Collections（第 2 代回收次数）**|显示自应用程序启动以来第 2 代对象进行垃圾回收的次数。  此计数器在第 2 代垃圾回收结束时递增。<br /><br /> 此计数器显示上次观测的值。  **\_Global\_** 计数器值不准确，应当忽略。|  
|**\# Induced GC（已引发 GC 数）**|显示因显式调用 <xref:System.GC.Collect%2A?displayProperty=fullName> 而执行的垃圾回收最大次数。  建议让垃圾回收器微调其回收的频率。|  
|**\# of Pinned Objects（固定对象数目）**|显示在上一次垃圾回收中遇到的固定对象的数目。  钉住的对象是垃圾回收器不能移入内存的对象。  此计数器只跟踪经过垃圾回收的堆中钉住的对象。  例如，第 0 代垃圾回收只导致对第 0 代堆中的固定对象进行枚举。|  
|**\# of Sink Blocks in use（正在使用的接收器块数目）**|显示正在使用的同步块的当前数目。  同步块是分配的每个对象的数据结构，用于存储同步信息。  它们保留对托管对象的弱引用并且必须由垃圾回收器扫描。  同步块不限于只存储同步信息，也可以存储 COM 互操作元数据。  此计数器指示有关大量使用同步基元的性能问题。|  
|**\# Total committed Bytes（已提交的字节总数）**|显示垃圾回收器当前已提交的虚拟内存量（以字节为单位）。  提交内存是磁盘页面文件上为其保留了空间的物理内存。|  
|**\# Total reserved Bytes（已保留的字节总数）**|显示垃圾回收器当前保留的虚拟内存量（以字节为单位）。  保留内存是在尚未使用任何磁盘或主内存页时为应用程序保留的虚拟内存空间。|  
|**% Time in GC（GC 时间百分比）**|显示执行自上次垃圾回收周期以来执行垃圾回收所用运行时间的百分比。  此计数器通常指示垃圾回收器代表应用程序收集和压缩内存所执行的作业。  此计数器在每次垃圾回收结束时更新。  此计数器不是平均值；它反映最后观测的值。|  
|**Allocated Bytes\/second（分配的字节数\/秒）**|显示垃圾回收堆上每秒分配的字节数。  此计数器在每次垃圾回收结束时（而非每次分配时）更新。  此计数器不是一段时间内的平均值；它显示最近两个样本观测值的差除以取样间隔所得的结果。|  
|**Finalization Survivors（最终存留对象）**|显示由于等待完成而回收后仍存在的垃圾回收对象数。  如果这些对象具有对其他对象的引用，则那些对象也会存在，但是不计入此计数器内。  **Promoted Finalization\-Memory from Gen 0**（从第 0 级提升的终止内存）计数器代表所有由于生命终止而保留的内存。<br /><br /> 此计数器不是累积计数器；它在每次垃圾回收结束时更新为仅在特定回收后仍存在的对象的数量。  此计数器指示应用程序由于完成而可能会带来的额外系统开销。|  
|**Gen 0 heap size（第 0 代堆大小）**|显示第 0 代中可以分配的最大字节数；它不指示第 0 代中已分配的当前字节数。<br /><br /> 当从上一次回收以来分配的字节数超过此大小时，将触发第 0 代垃圾回收。  第 0 代大小是由垃圾回收器调整的，并且会在应用程序执行期间更改。  在第 0 代回收结束时，第 0 代堆的大小实际上为 0 字节。  此计数器显示将触发下一次第 0 代回收的分配的大小（以字节为单位）。<br /><br /> 此计数器在垃圾回收结束时更新，不在每次分配时更新。|  
|**Gen 0 Promoted Bytes\/Sec（第 0 代提升的字节数\/秒）**|显示每秒从第 0 代提升到第 1 代的字节数。  垃圾回收后仍存在的内存被提升。  此计数器是每秒创建的生存期较长的对象的指示器。<br /><br /> 计数器显示最近两个样本中观测的值的差除以样本的间隔时间所得的结果。|  
|**Gen 1 heap size（第 1 代堆大小）**|显示第 1 代中的当前字节数；此计数器不显示第 1 代的最大大小。  此代中的对象不是直接分配的；这些对象是从以前的第 0 代垃圾回收提升的。  此计数器在垃圾回收结束时更新，不在每次分配时更新。|  
|**Gen 1 Promoted Bytes\/Sec（第 1 代提升的字节数\/秒）**|显示每秒从第 1 代提升到第 2 代的字节数。  此计数器中不包括仅由于等待完成而被提升的对象。<br /><br /> 垃圾回收后仍存在的内存被提升。  由于第 2 代是最早的，因此不会从第 2 代提升任何内容。  此计数器是每秒创建的生存期很长的对象的指示器。<br /><br /> 计数器显示最近两个样本中观测的值的差除以样本的间隔时间所得的结果。|  
|**Gen 2 heap size（第 2 代堆大小）**|显示在第 2 代中的当前字节数。  此代中的对象不是直接分配的；这些对象是在以前的第 1 代垃圾回收过程中从第 1 代提升的。  此计数器在垃圾回收结束时更新，不在每次分配时更新。|  
|**Large Object Heap size（大型对象堆大小）**|显示大型对象堆的当前大小（以字节为单位）。  垃圾回收器将大于 85,000 字节左右的对象视作大对象并且直接在特殊堆中分配大对象；它们不是按照这些级别提升的。  此计数器在垃圾回收结束时更新，不在每次分配时更新。|  
|**进程 ID**|显示被监视的 CLR 进程实例的进程 ID。|  
|**Promoted Finalization\-Memory from Gen 0（从第 0 代提升的最终内存）**|显示仅由于等待完成而从第 0 代提升到第 1 代的内存字节数。  此计数器不是累积计数器；它显示在上一次垃圾回收结束时观测的值。|  
|**Promoted Memory from Gen 0（从第 0 代提升的内存）**|显示垃圾回收后仍存在并从第 0 代提升到第 1 代的内存字节数。  此计数器中不包括仅由于等待完成而被提升的对象。  此计数器不是累积计数器；它显示在上一次垃圾回收结束时观测的值。|  
|**Promoted Memory from Gen 1（从第 1 代提升的内存）**|显示垃圾回收后仍存在并从第 1 代提升到第 2 代的内存字节数。  此计数器中不包括仅由于等待完成而被提升的对象。  此计数器不是累积计数器；它显示在上一次垃圾回收结束时观测的值。  如果上一次垃圾回收只是第 0 代回收，则此计数器将重置为 0。|  
  
<a name="networking"></a>   
## 联网性能计数器  
 性能控制台 .NET CLR Networking（网络）类别包括的计数器提供应用程序通过网络发送和接收的数据的相关信息。  下表描述这些性能计数器。  
  
|性能计数器|描述|  
|-----------|--------|  
|**Bytes Received（已接收的字节数）**|自进程启动以来，<xref:System.AppDomain> 中的所有 <xref:System.Net.Sockets.Socket> 对象接收到的字节的累积总数。  此数字包括数据和 TCP\/IP 协议未定义的任何协议信息。|  
|**Bytes Sent（已发送的字节数）**|自进程启动以来，<xref:System.AppDomain> 中的所有 <xref:System.Net.Sockets.Socket> 对象已发送的字节的累积总数。  此数字包括数据和 TCP\/IP 协议未定义的任何协议信息。|  
|**Connections Established（已建立的连接）**|自进程启动以来，<xref:System.AppDomain> 中曾连接的任何流套接的 <xref:System.Net.Sockets.Socket> 对象的累积总数。|  
|**Datagrams Received（已接收的数据报）**|自进程启动以来，<xref:System.AppDomain> 中的所有 <xref:System.Net.Sockets.Socket> 对象接收到的数据报包的累积总数。|  
|**Datagrams Sent（已发送的数据报）**|自进程启动以来，<xref:System.AppDomain> 中的所有 <xref:System.Net.Sockets.Socket> 对象已发送的数据报包的累积总数。|  
|**HttpWebRequest Average Lifetime（HttpWebRequest 平均生存期）**|自进程启动以来，<xref:System.AppDomain> 中在上一个间隔中结束的所有 <xref:System.Net.HttpWebRequest> 对象的平均完成时间。|  
|**HttpWebRequest Average Queue Time（HttpWebRequest 平均排队时间）**|自进程启动以来，<xref:System.AppDomain> 中在上一个间隔中结束的所有 <xref:System.Net.HttpWebRequest> 对象的平均排队时间。|  
|**HttpWebRequests Created\/sec（创建的 HttpWebRequest\/秒）**|<xref:System.AppDomain> 中每秒创建的 <xref:System.Net.HttpWebRequest> 对象的数目。|  
|**HttpWebRequests Queued\/sec（已排队的 HttpWebRequest\/秒）**|<xref:System.AppDomain> 中每秒添加到队列的 <xref:System.Net.HttpWebRequest> 对象的数量。|  
|**HttpWebRequests Aborted\/sec（已终止的 HttpWebRequest\/秒）**|<xref:System.AppDomain> 中其中每秒应用程序调用 <xref:System.Net.HttpWebRequest.Abort%2A> 方法的 <xref:System.Net.HttpWebRequest> 对象的数量。|  
|**HttpWebRequests Failed\/sec（失败的 HttpWebRequest\/秒）**|<xref:System.AppDomain> 中每秒从服务器接收失败状态的 <xref:System.Net.HttpWebRequest> 对象的数量。|  
  
 几类受支持的网络性能计数器如下：  
  
-   事件计数器，用于测量某些事件的发生次数。  
  
-   数据计数器，用于测量已发送或已接收的数据量。  
  
-   持续时间计数器，测量不同进程花费的时间。  测量对象每个间隔（通常以秒计）退出不同状态后的次数。  
  
-   每间隔计数器，用于测量每个间隔（通常以秒计）中正在进行特定转换的对象数。  
  
 适用于事件的网络性能计数器包括：  
  
-   **Connections Established（已建立的连接）**  
  
-   **Datagrams Received（已接收的数据报）**  
  
-   **Datagrams Sent（已发送的数据报）**  
  
 这些性能计数器提供自进程启动以来的计数。  已建立的 <xref:System.Net.Sockets.Socket> 连接的计数包括显式 <xref:System.Net.Sockets.Socket> 方法调用（由已建立的流套接连接的应用程序执行）以及其他类（例如 <xref:System.Net.HttpWebRequest>、<xref:System.Net.FtpWebRequest>、<xref:System.Net.WebClient> 和 <xref:System.Net.Sockets.TcpClient>）对 <xref:System.Net.Sockets.Socket> 类执行的内部调用  
  
 **已接收的数据报**和**以发送的数据报**计数包括使用显式 <xref:System.Net.Sockets.Socket> 方法调用（由应用程序执行）和其他类（例如 <xref:System.Net.Sockets.UdpClient>）对 <xref:System.Net.Sockets.Socket> 类执行的内部调用而发送或接收的数据报包。  类的新实例。  **已接收的数据报**和**已发送的数据报**的计数也可能用于通过假定数据报的平均大小粗略测量使用数据报发送或接收的字节数。  
  
 适用于数据的网络性能计数器包括：  
  
-   **Bytes Received（已接收的字节数）**  
  
-   **Bytes Sent（已发送的字节数）**  
  
 上述计数器提供自进程启动以来的字节计数。  
  
 有如下两个持续时间计数器可测量 <xref:System.Net.HttpWebRequest> 对象经过整个或部分生命周期所花费的时间：  
  
-   **HttpWebRequest Average Lifetime（HttpWebRequest 平均生存期）**  
  
-   **HttpWebRequest Average Queue Time（HttpWebRequest 平均排队时间）**  
  
 对于 **HttpWebRequest Average Lifetime**（HttpWebRequest 平均排队时间）计数器，大多数 <xref:System.Net.HttpWebRequest> 对象的生存期总是开始于创建对象时，而在应用程序关闭响应流时结束。  有两种不常见的情况：  
  
-   如果应用程序从未调用 <xref:System.Net.HttpWebRequest.GetResponse%2A> 或 <xref:System.Net.HttpWebRequest.BeginGetResponse%2A> 方法，则忽略 <xref:System.Net.HttpWebRequest> 对象的生存期。  
  
-   如果 <xref:System.Net.HttpWebRequest>对象在调用 <xref:System.Net.HttpWebRequest.GetResponse%2A> 或 <xref:System.Net.HttpWebRequest.EndGetResponse%2A> 方法时引发 <xref:System.Net.WebException>，则在引发异常时生存期结束。  从技术上来说，此时（返回至用户的响应流实际上为包含响应流副本的内存流）也关闭基础响应流。  
  
 有 4 个计数器可在每个间隔跟踪某些 <xref:System.Net.HttpWebRequest> 对象问题。  这些性能计数器可帮助应用程序开发人员、管理员和支持人员更好地了解 <xref:System.Net.HttpWebRequest> 对象的当前行为。  这些计数器包括：  
  
-   **HttpWebRequests Created\/sec（创建的 HttpWebRequest\/秒）**  
  
-   **HttpWebRequests Queued\/sec（已排队的 HttpWebRequest\/秒）**  
  
-   **HttpWebRequests Aborted\/sec（已终止的 HttpWebRequest\/秒）**  
  
-   **HttpWebRequests Failed\/sec（失败的 HttpWebRequest\/秒）**  
  
 对于 **HttpWebRequests Aborted\/sec**（已终止的 HttpWebRequest\/秒）计数器，同时对 <xref:System.Net.HttpWebRequest.Abort%2A> 的内部调用进行计数。  这些内部调用通常由应用程序可能要测量的超时导致。  
  
 **HttpWebRequests Failed\/sec**（失败的 HttpWebRequest\/秒）计数器包含每秒从服务器接收失败状态的 <xref:System.Net.HttpWebRequest> 对象的数量。  这意味着在请求结束时从 Http 服务器接收的状态代码不在 200 到 299 的范围内。  已处理并引发新请求的状态代码（例如多个 401 未授权状态代码）是否失败取决于重试结果。  如果应用程序可基于重试查看错误，则此计数器递增。  
  
 网络性能计数器可以通过使用 <xref:System.Diagnostics> 命名空间中的 <xref:System.Diagnostics.PerformanceCounter> 和相关类进行访问和管理。  它还可以通过使用 Windows 性能监视器控制台进行查看。  
  
 需要在要使用的配置文件中启用网络性能计数器。  通过配置文件中的单个设置即可启用或禁用所有网络性能计数器。  不能启用或禁用单个网络性能计数器。  有关详细信息，请参阅 [\<performanceCounter\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)。  
  
 如果启用了网络计数器，此操作将创建并更新每个 AppDomain 和全局性能计数器。  如果禁用，则应用程序将不提供任何网络性能计数器数据。  
  
 性能计数器均分组到类别中。  应用程序可列出具有以下示例代码的所有类别：  
  
```  
PerformanceCounterCategory[] Array = PerformanceCounterCategory.GetCategories();  
for (int i = 0; i < Array.Length; i++)  
{  
    Console.Out.WriteLine("{0}. Name={1} Help={2}", i, Array[i].CategoryName, Array[i].CategoryHelp);  
}  
  
```  
  
 网络性能计数器包含在连个类别中：  
  
-   “.NET CLR 网络”\- .NET Framework 版本 2 上引入且在 .NET Framework 版本 2 及更高版本上受支持的原始性能计数器。  
  
-   “.NET CLR 网络 4.0.0.0”\- 所有上述套接计数器和 .NET Framework 版本 4 及更高版本上受支持的新的性能计数器。  这些新的计数器提供有关 <xref:System.Net.HttpWebRequest> 对象的性能信息。  
  
 有关访问和管理应用程序中性能计数器的详细信息，请参阅[Performance Counters](../../../docs/framework/debug-trace-profile/performance-counters.md)。  
  
<a name="security"></a>   
## 安全性能计数器  
 性能控制台 .NET CLR Security（安全性）类别包括的计数器提供公共语言运行时针对应用程序执行的安全检查的相关信息。  下表描述这些性能计数器。  
  
|性能计数器|描述|  
|-----------|--------|  
|**\# Link Time Checks（链接时检查次数）**|显示自应用程序启动以来链接时代码访问安全检查的总次数。  当调用方要求实时 \(JIT\) 编译时的特定权限时，执行链接时代码访问安全检查。  每个调用方执行一次链接时检查。  此计数不指示严重的性能问题；它仅指示安全系统活动。|  
|**% Time in RT checks（RT 检查所占的时间百分比）**|此计数器显示自上一次取样以来执行运行时代码访问安全检查所用运行时间的百分比。  此计数器在 .NET Framework 安全检查结束时更新。  它不是平均值；而表示上次观测的值。|  
|**% Time Sig Authenticating（Sig 身份验证所占时间百分比）**|留待将来使用。|  
|**Stack Walk Depth（堆栈审核深度）**|显示在上次运行时代码访问安全检查期间的堆栈深度。  运行时代码访问安全检查通过审核堆栈执行。  此计数器不是平均值；它仅显示最后观测的值。|  
|**Total Runtime Checks（运行时检查总数）**|显示自应用程序启动以来执行的运行时代码访问安全检查的总数。  当调用方要求特定权限时，执行运行时代码访问安全检查。  运行时检查在调用方每次调用时都会执行，并会检查调用方的当前线程堆栈。  此计数器与**Stack Walk Depth**（堆栈审阅深度）计数器一起使用时指示安全检查出现的性能损失。|  
  
## 请参阅  
 [Performance Counters](../../../docs/framework/debug-trace-profile/performance-counters.md)   
 [运行时分析](../../../docs/framework/debug-trace-profile/runtime-profiling.md)