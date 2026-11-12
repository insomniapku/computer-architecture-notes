# Lecture-8 来源、覆盖与核验

- 获取与核验日期：2026-11-12（北京时间）。
- 课程：计算机组织与体系结构；course_id=`_103980_1`。
- 课件身份：Lecture-8；content_id=`_1728216_1`；rid=`13599212_1`。
- [教学网课程条目](https://course.pku.edu.cn/webapps/blackboard/content/listContent.jsp?course_id=_103980_1&content_id=_1728216_1)。访问需课程权限。
- [附件来源](https://course.pku.edu.cn/bbcswebdav/pid-1728216-dt-content-rid-13599212_1/xid-13599212_1)。
- 原始格式：PPTX，83 张幻灯片，3,509,636 字节。
- SHA256：`133a4a5681a5b98cdda7547cf86800a7ccf27ac27a8f50de62161cc81ec5ccb5`。
- 课件署名 Jie Zhang；改编自 KAIST Myoungsoo Jung EE488。
- 发布范围：中文笔记、8 张必要图的裁剪、索引和本核对记录；不上传原课件。

## 覆盖与去重

| 原课件页 | 笔记内容 |
|---|---|
| 2—17 | 并行计算、Flynn 分类，合并串行/并行的逐步动画 |
| 18 | UMA、NUMA、分布式内存 |
| 19—26 | coherence/consistency 区分、标志/双地址/传播链例题 |
| 27—35 | SC、TSO、两道 Store Buffer 例题、模型关系和屏障 |
| 36—42 | 监听器与 WT V/I |
| 43—62 | WB MESI，按本核和监听事件合并全部转换场景 |
| 63—67 | MEI/MSI/MOESI/MESIF、多级 Cache、snoop filter |
| 68—76 | 目录位图、分布式 home、读/写缺失与 ACK |
| 77—81 | Haswell Ring/CBox、Skylake Xeon Mesh/CHA、设计维度 |
| 83 | Peterson 互斥附录 |

标题、署名与重复结束页不作正文。Cache/DRAM 前置知识链接旧讲次，不复制整章。原文件为 PPTX；通用文档转换的重排文本页不能作为原页码，已用 PPTX 实际 83 页重新对应。使用 PowerPoint 只读渲染关键页，对第 28、31、32、62、83 页图中例题/状态转换/代码作视觉核验。8 张图分别取自第 18、30、31、32、62、71、78、79 页，裁剪装饰边框，图下文字在正文重新解释。

## 勘误与适用边界

1. 串行抽象不意味着单核内部无法指令级并行。C.mmp 的 MISD 归类不作为可靠实例。
2. I 表示无有效副本，不等于数据位一定与主存不相等；S 不保证确实存在另一共享者。
3. SC Store Buffering 的双零结果不合法，正文给出顺序环证明；TSO 允许双零，并保留同地址写缓冲转发例题。
4. TSO 的 Store→Load 放松、RMW 和 Fence 均按教学模型解释；具体 ISA 与语言还需检查相应约束。
5. 课件 S→M 用 BusRdX，正文保留并标出 BusUpgr 优化不是同一条课件事务。
6. MOESI 的 M→O 不写回主存不等于不传数据。
7. “MSI—RISC-V”不能推广成 ISA 强制协议；“L1 必须写穿”不能推广成多级 Cache 的必要条件。
8. “失效 home 副本”不解释成删除物理内存；权限转换须等待所需 ACK。
9. “flags/turn 实现 SC”改为 Peterson 在适当内存模型下实现互斥，所示代码不是 Dekker。
10. Ring→Mesh 仅按课件所述服务器代际解释，不泛化为所有客户端产品。

正文的目录空间公式、64 节点算例、双核 MESI 逐步表是依照课件机制的补充推导，不冒充课件原始数值或真实实验。本轮没有执行硬件实验，也没有对课件每个历史产品名进行外部数据手册审计。
