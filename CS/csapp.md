## 9 虚拟内存

### 名词解析

物理地址(Physical Address)PA: 内存中每一个字节都有一个地址
- PPO: 虚拟地址页面偏移量
- 

虚拟地址(Virtual Address)VA: 
- VPO: 虚拟页面偏移量
- VPN: 虚拟页号
- TBLI: TLB索引
- TBLT: TLB标记
 

内存管理单元(Memory Management Unit): 将虚拟地址转换为物理地址
- 翻译后备缓冲器()TBL: 虚拟寻址的缓存

虚拟页(Virtual Page)VP: 固定大小的块用来传输数据
物理页(Physical Page)||页帧(page frame)PP: 物理内存中的块

页表(page table): 在物理内存中存放虚拟页和物理页之间的映射关系
页表条目(Page Table Entry): 由有效位和地址字段组成
- 有效位: 表明虚拟页是否被缓存
- 有效地址: 物理页号
- PTE的索引: 对应在磁盘中虚拟内存的索引
页表条目地址()PTEA: 页表的地址
