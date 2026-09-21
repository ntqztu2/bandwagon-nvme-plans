# 搬瓦工 NVMe VPS：哪些机房已升级 EPYC 硬盘，全部套餐价格与选购避坑指南

搜“搬瓦工 NVMe VPS”的人，关心的问题其实就两个：搬瓦工现在到底哪些机房用上了 NVMe，以及带 NVMe 的套餐值不值得多花钱。这篇文章基于官网当前在售目录和官方新闻整理，把机房硬件状态、全部套餐价格和选购思路一次讲清楚。

## 先说结论

搬瓦工从 2025 年开始分批把机房升级到 AMD EPYC 处理器加 NVMe RAID-10 存储，洛杉矶 DC9、香港、纽约等主要机房都已完成。截至本文撰写，官网在售目录里的所有套餐都显示有货，价格从 $49.99/年 的入门 KVM 到香港顶配的 $18,989.99/年 都有，区间拉得很开。

如果你只想快速做决定：纯练手或建普通站点，Basic 系列年付 $49.99 起步够用；要国内访问速度快，选 CN2 GIA-E 系列，最低 $169.99/年；对稳定性有硬性要求，看洛杉矶 SLA 系列；预算充足追求低延迟，再考虑香港和东京。

👉 [去官网套餐页查看实时价格和库存](https://bit.ly/BandwagonHost)

## 哪些机房已经用上 NVMe

搬瓦工的硬件升级是分批推的，官网新闻页有明确记录：

| 机房 | 位置 | 硬件状态 | 升级时间 |
| --- | --- | --- | --- |
| 洛杉矶 DC9（USCA_9） | 美国洛杉矶 | AMD EPYC + NVMe RAID-10 | 2025 年 7 月 |
| 香港（HK3/HK8） | 中国香港 | AMD EPYC + NVMe RAID-10 | 2025 年 9 月 |
| 纽约（USNY_6 / USNY_8） | 美国纽约 | AMD EPYC + NVMe RAID-10 | 2026 年 5 月 |
| 温哥华（CABC_1 / CABC_6） | 加拿大 | AMD-F + NVMe | 官网目录已标注 |
| 阿姆斯特丹（EUNL_1） | 荷兰 | AMD + NVMe | 官网目录已标注 |
| 东京（JPTY_1） | 日本 | AMD + NVMe | 官网目录已标注 |
| 洛杉矶 DC5（USCA_5） | 美国洛杉矶 | AMD + NVMe（SLA 专用机房） | 官网目录已标注 |

注意，这是搬瓦工目前公开标注 NVMe 的全部机房。东京 CN2 GIA（JPTY_8）、大阪、新加坡等机房在官网目录里只标注了 AMD 处理器，没有标注 NVMe，买之前别想当然。

已经买了老硬件 VPS 的用户也不用重新购买。官方在升级公告里说明，现有 VPS 可以通过 KiwiVM 后台免费迁移到新硬件节点，多个中文站也确认了这个一键升级流程。等于说硬件升级对老用户是免费福利，不用额外花钱。

## NVMe 到底带来什么

RAID-10 阵列意味着硬盘数据是镜像写入的，单盘故障不会丢数据，这对 VPS 来说比单盘速度更实际。配合 EPYC 处理器，随机读写和小文件场景（数据库、建站、跑应用）的响应会明显好于老一代 Intel Xeon 加 SAS 盘的组合。

但要说明一点：NVMe 解决的是磁盘性能，不解决线路问题。搬瓦工的价格差异主要来自线路（CN2 GIA、普通 BGP），NVMe 是全系逐步标配的硬件基础。别把“NVMe 版套餐”理解成一个单独的付费升级项，它更像机房基础设施的换代。

## 四条产品线怎么分

搬瓦工官网目录目前分四个层级，选错层级比选错配置更浪费钱：

- **Basic VPS**：最便宜的入门线，年付 $49.99 起，多数机房走本地对等互联，不针对中国优化。可在多个机房间免费迁移，数据不丢。
- **E-Commerce VPS（CN2 GIA-E）**：主打中国方向优化线路，电信走 CN2 GIA/CTGNet，联通走 Premium，移动走 CMIN2，带宽 2.5Gbps 起步，可选机房多达 15 个。
- **E-Commerce+SLA**：部署在洛杉矶 USCA_5 机房，带 99.99% 在线率服务等级协议，硬件同样标注 AMD + NVMe，适合对稳定性有合同级要求的用户。
- **Ultra VPS**：香港、东京、大阪、新加坡的 CN2 GIA 顶配线，延迟最低，价格也最贵。

一个经常被忽略的特性：Basic 和 GIA-E 系列都支持在各自可选机房之间免费迁移，数据保留。比如 GIA-E 可以从洛杉矶 DC6 迁到 DC9 或东京，换机房不用换套餐。

## 全部套餐价格整理

以下价格全部来自官网当前在售目录（美元计价）。每个套餐的购买链接已带上对应商品直达入口，点击后会直接进入该套餐的订购页面。

### Basic VPS 系列（年付 $49.99 起，5 个机房可选）

| 套餐 | 配置（CPU/内存/SSD/月流量/带宽） | 价格 | 购买 |
| --- | --- | --- | --- |
| 20G KVM | 2核 / 1GB / 20GB / 1TB / 1Gbps | $49.99/年 | [订购 20G KVM](https://bandwagonhost.com/aff.php?aff=79616&pid=44) |
| 40G KVM | 3核 / 2GB / 40GB / 2TB / 1Gbps | $52.99/半年（年付 $99.99） | [订购 40G KVM](https://bandwagonhost.com/aff.php?aff=79616&pid=45) |
| 80G KVM | 4核 / 4GB / 80GB / 3TB / 1Gbps | $19.99/月起（年付 $199.99） | [订购 80G KVM](https://bandwagonhost.com/aff.php?aff=79616&pid=46) |
| 160G KVM | 5核 / 8GB / 160GB / 4TB / 1Gbps | $39.99/月起（年付 $399.99） | [订购 160G KVM](https://bandwagonhost.com/aff.php?aff=79616&pid=47) |
| 320G KVM | 6核 / 16GB / 320GB / 5TB / 1Gbps | $79.99/月起（年付 $799.99） | [订购 320G KVM](https://bandwagonhost.com/aff.php?aff=79616&pid=48) |
| 480G KVM | 7核 / 24GB / 480GB / 6TB / 1Gbps | $119.99/月起（年付 $1,199.99） | [订购 480G KVM](https://bandwagonhost.com/aff.php?aff=79616&pid=49) |

Basic 系列可在荷兰、洛杉矶、弗里蒙特、温哥华、纽约五个位置之间自由选择和迁移。

### CN2 GIA-E 系列（国内访问优化，15 个机房可选）

| 套餐 | 配置 | 价格 | 购买 |
| --- | --- | --- | --- |
| 20G | 2核 / 1GB / 20GB / 1TB / 2.5Gbps | $49.99/季（年付 $169.99） | [订购 GIA-E 1GB](https://bandwagonhost.com/aff.php?aff=79616&pid=87) |
| 40G | 3核 / 2GB / 40GB / 2TB / 2.5Gbps | $89.99/季（年付 $299.99） | [订购 GIA-E 2GB](https://bandwagonhost.com/aff.php?aff=79616&pid=88) |
| 80G | 4核 / 4GB / 80GB / 3TB / 2.5Gbps | $56.99/月起（年付 $549.99） | [订购 GIA-E 4GB](https://bandwagonhost.com/aff.php?aff=79616&pid=89) |
| 160G | 6核 / 8GB / 160GB / 5TB / 5Gbps | $86.99/月起（年付 $879.99） | [订购 GIA-E 8GB](https://bandwagonhost.com/aff.php?aff=79616&pid=90) |
| 320G | 8核 / 16GB / 320GB / 8TB / 5Gbps | $159.99/月起（年付 $1,599.99） | [订购 GIA-E 16GB](https://bandwagonhost.com/aff.php?aff=79616&pid=91) |
| 640G | 10核 / 32GB / 640GB / 10TB / 10Gbps | $289.99/月起（年付 $2,759.99） | [订购 GIA-E 32GB](https://bandwagonhost.com/aff.php?aff=79616&pid=92) |
| 1280G | 12核 / 64GB / 1280GB / 12TB / 10Gbps | $549.99/月起（年付 $5,499.99） | [订购 GIA-E 64GB](https://bandwagonhost.com/aff.php?aff=79616&pid=93) |
| 1280G 大流量版 | 同上，月流量 15TB | $679/月起（年付 $6,790） | [订购 GIA-E 64GB 15T](https://bandwagonhost.com/aff.php?aff=79616&pid=160) |
| 1280G 大流量版 | 同上，月流量 20TB | $899/月起（年付 $8,999） | [订购 GIA-E 64GB 20T](https://bandwagonhost.com/aff.php?aff=79616&pid=161) |

可选机房覆盖洛杉矶 DC6/DC9、圣何塞、纽约、温哥华、阿姆斯特丹、迪拜、大阪软银、东京等 15 个位置，下单时选择，后续可免费迁。

### E-Commerce+SLA 系列（洛杉矶 USCA_5，99.99% SLA）

| 套餐 | 配置 | 价格 | 购买 |
| --- | --- | --- | --- |
| 20G | 2核 / 约1GB / 20GB / 1TB / 2.5Gbps | $65.89/季（年付 $239.99） | [订购 SLA 1GB](https://bandwagonhost.com/aff.php?aff=79616&pid=164) |
| 40G | 3核 / 约2GB / 40GB / 2TB / 2.5Gbps | $116.99/季（年付 $399.99） | [订购 SLA 2GB](https://bandwagonhost.com/aff.php?aff=79616&pid=165) |
| 80G | 4核 / 约4GB / 80GB / 3TB / 2.5Gbps | $69.99/月起（年付 $699.99） | [订购 SLA 4GB](https://bandwagonhost.com/aff.php?aff=79616&pid=166) |
| 160G | 6核 / 约8GB / 160GB / 5TB / 5Gbps | $109.99/月起（年付 $1,099.99） | [订购 SLA 8GB](https://bandwagonhost.com/aff.php?aff=79616&pid=167) |
| 320G | 8核 / 约16GB / 320GB / 8TB / 5Gbps | $199.99/月起（年付 $1,999.99） | [订购 SLA 16GB](https://bandwagonhost.com/aff.php?aff=79616&pid=168) |
| 640G | 10核 / 约32GB / 640GB / 10TB / 10Gbps | $369.99/月起（年付 $3,699.99） | [订购 SLA 32GB](https://bandwagonhost.com/aff.php?aff=79616&pid=169) |
| 1280G | 12核 / 64GB / 1280GB / 12TB / 10Gbps | $699.99/月起（年付 $6,999.99） | [订购 SLA 64GB](https://bandwagonhost.com/aff.php?aff=79616&pid=170) |
| 1280G 大流量版 | 同上，月流量 15TB | $879.99/月起（年付 $8,799.99） | [订购 SLA 64GB 15T](https://bandwagonhost.com/aff.php?aff=79616&pid=171) |
| 1280G 大流量版 | 同上，月流量 20TB | $1,159.99/月起（年付 $11,598.99） | [订购 SLA 64GB 20T](https://bandwagonhost.com/aff.php?aff=79616&pid=172) |

SLA 系列目前只有洛杉矶 USCA_5 一个机房，这个系列带双路冗余供电、独立 IPv4、每两周一次免费换 IP 等企业级配置。

### Ultra 系列：香港 / 东京 CN2 GIA

香港和东京的套餐配置、价格完全相同，东京带宽略高（1.2Gbps 对 1Gbps）。

| 套餐 | 配置 | 价格 | 香港 | 东京 |
| --- | --- | --- | --- | --- |
| 40G | 2核 / 2GB / 40GB / 500GB / 1Gbps | $89.99/月起（年付 $899.99） | [订购香港 2GB](https://bandwagonhost.com/aff.php?aff=79616&pid=95) | [订购东京 2GB](https://bandwagonhost.com/aff.php?aff=79616&pid=108) |
| 80G | 4核 / 4GB / 80GB / 1TB / 1Gbps | $155.99/月起（年付 $1,559.99） | [订购香港 4GB](https://bandwagonhost.com/aff.php?aff=79616&pid=96) | [订购东京 4GB](https://bandwagonhost.com/aff.php?aff=79616&pid=109) |
| 160G | 6核 / 8GB / 160GB / 2TB / 1Gbps | $299.99/月起（年付 $2,999.99） | [订购香港 8GB](https://bandwagonhost.com/aff.php?aff=79616&pid=97) | [订购东京 8GB](https://bandwagonhost.com/aff.php?aff=79616&pid=110) |
| 320G | 8核 / 16GB / 320GB / 4TB / 1Gbps | $589.99/月起（年付 $5,899.99） | [订购香港 16GB](https://bandwagonhost.com/aff.php?aff=79616&pid=98) | [订购东京 16GB](https://bandwagonhost.com/aff.php?aff=79616&pid=111) |
| 640G | 10核 / 32GB / 640GB / 6TB / 1Gbps | $989.99/月起（年付 $9,989.99） | [订购香港 32GB](https://bandwagonhost.com/aff.php?aff=79616&pid=122) | [订购东京 32GB](https://bandwagonhost.com/aff.php?aff=79616&pid=123) |
| 1280G | 12核 / 64GB / 1280GB / 8TB / 1Gbps | $1,889.99/月起（年付 $18,989.99） | [订购香港 64GB](https://bandwagonhost.com/aff.php?aff=79616&pid=124) | [订购东京 64GB](https://bandwagonhost.com/aff.php?aff=79616&pid=125) |

### Ultra 系列：大阪 / 新加坡 CN2 GIA

大阪和新加坡价格一致，带宽 1.5Gbps 起，比香港东京的流量额度更宽松。

| 套餐 | 配置 | 价格 | 大阪 | 新加坡 |
| --- | --- | --- | --- | --- |
| 40G | 2核 / 2GB / 40GB / 500GB / 1.5Gbps | $49.99/月起（年付 $499.99） | [订购大阪 2GB](https://bandwagonhost.com/aff.php?aff=79616&pid=134) | [订购新加坡 2GB](https://bandwagonhost.com/aff.php?aff=79616&pid=173) |
| 80G | 4核 / 4GB / 80GB / 1TB / 1.5Gbps | $86.99/月起（年付 $869.99） | [订购大阪 4GB](https://bandwagonhost.com/aff.php?aff=79616&pid=135) | [订购新加坡 4GB](https://bandwagonhost.com/aff.php?aff=79616&pid=174) |
| 160G | 6核 / 8GB / 160GB / 2TB / 1.5-2.5Gbps | $165.99/月起（年付 $1,665.99） | [订购大阪 8GB](https://bandwagonhost.com/aff.php?aff=79616&pid=136) | [订购新加坡 8GB](https://bandwagonhost.com/aff.php?aff=79616&pid=175) |
| 320G | 8核 / 16GB / 320GB / 4TB / 1.5-2.5Gbps | $329.99/月起（年付 $3,199） | [订购大阪 16GB](https://bandwagonhost.com/aff.php?aff=79616&pid=137) | [订购新加坡 16GB](https://bandwagonhost.com/aff.php?aff=79616&pid=176) |
| 640G | 10核 / 32GB / 640GB / 6TB / 1.5-5Gbps | $549.99/月起（年付 $5,549.99） | [订购大阪 32GB](https://bandwagonhost.com/aff.php?aff=79616&pid=138) | [订购新加坡 32GB](https://bandwagonhost.com/aff.php?aff=79616&pid=177) |
| 1280G | 12核 / 64GB / 1280GB / 8TB / 1.5-5Gbps | $1,059.99/月起（年付 $10,559.99） | [订购大阪 64GB](https://bandwagonhost.com/aff.php?aff=79616&pid=139) | [订购新加坡 64GB](https://bandwagonhost.com/aff.php?aff=79616&pid=178) |

同样是大阪和新加坡，40G 款月付只要 $49.99，比香港同款便宜接近一半。如果对延迟没有极致要求，亚洲机房里这两个的性价比明显更高。

## 怎么选：按预算和用途给几个判断

**预算 50 美元一年，纯练手或挂个小站**：Basic 20G KVM，年付 $49.99，1GB 内存对静态站和轻量应用够用。注意它不针对中国优化，国内访问走普通线路，晚高峰体验看运气。

**主要给国内用户访问**：CN2 GIA-E 是绝大多数人的答案。1GB 版年付 $169.99，三网走优化线路，15 个机房随便迁。从多个社区测评汇总看，美西 GIA 机房延迟大约在 140-180ms 区间，晚高峰稳定性明显好于普通线路。香港东京的 CN2 GIA 延迟可以压到 30-60ms，但月付 $89.99 起的价格不是个人用户轻松承受的。

**业务对宕机敏感**：看 SLA 系列。99.99% 的在线率承诺折算下来一年宕机时间不超过约 53 分钟，1GB 款季付 $65.89 起步，比普通 GIA-E 贵 30% 左右，换来的是合同级保障和企业机房配置。

**想蹲便宜限量款**：搬瓦工时不时会放出 THE PLAN 这类限量套餐（比如 2 核 2G / 40G / 1TB / 2.5Gbps，年付 $99.99，可选机房覆盖香港和 GIA 线路），卖完即下架，补货时间无法预测。目前官网在售目录里没有这类套餐，遇到补货属于可遇不可求。

👉 [查看官网全部套餐和限量款上架情况](https://bit.ly/BandwagonHost)

## 优惠和省钱的几条实际信息

关于优惠码，现状需要说实话。流传最广的循环折扣码 BWHCGLUKKB（约 6.77% 折扣）目前处于说法不一的状态：有 2026 年的社区记录称它在 2025 年双十一后随一批老码一起下线，也有站点在近期仍将其列为可用。比较务实的做法是下单时顺手在结算页试一下，能抵扣就省一笔，不能就按原价走，不值得为它等待。

计费周期的选择上，多数套餐年付比月付划算不少。以 GIA-E 4GB 为例，月付一年累计 $683.88，年付只要 $549.99。但反过来，如果你只是短期项目，月付灵活性更高，不用被周期绑住。

付款方面，搬瓦工支持支付宝，国内用户注册和付款流程都不复杂。

退款政策要留意限制条件：账户注册 30 天内可申请退款，但需要满足账户下 VPS 总数少于 3 个、累计支付金额低于 100 美元、支付次数少于 10 次。退款是全自动流程，申请后账户下所有服务会被删除且不可恢复，所以数据要先备份。官网同时标注 99.9% 在线率保障。

## 购买前要注意的三件事

第一，IP 问题。多个 2026 年的社区教程提到，搬瓦工已不再提供免费换 IP，只保留付费更换渠道，而且 IP 被封后不能靠迁移机房来规避。买之前建议先用官方公布的各机房测试 IP 测一下延迟和连通性，再决定机房。

第二，限量款缺货是常态。THE PLAN、DC9 限量版这类高性价比套餐经常处于售罄状态，第三方有实时库存监控站可以盯，但没必要为蹲货耽误正事，常规 GIA-E 套餐长期稳定有货。

第三，系统选择。KiwiVM 面板提供 AlmaLinux、RockyLinux、Debian、Ubuntu 等主流发行版，也支持自行挂 ISO 安装。重装系统免费，操作是即时的，选错了随时可以重来。

## 常见问题

**搬瓦工 NVMe VPS 是单独的套餐吗？**

不是。NVMe 是机房硬件升级，NVMe RAID-10 存储会自动部署在已完成升级的机房里，同一套餐在不同机房拿到的硬件可能不同。目前官方目录没有“NVMe 版套餐”这个独立分类。

**老套餐能免费升级到 NVMe 硬件吗？**

可以。官方公告说明现有 VPS 能通过 KiwiVM 后台迁移到新硬件节点，属于免费操作，数据保留。

**香港 CN2 GIA 为什么这么贵？**

CN2 GIA 是中国电信等级最高的国际回程线路，容量稀缺、采购成本高。搬瓦工官方页面明确说过，这条线路的转发成本在部分市场每兆比特高达 120 美元，1Gbps 的月账单可以到六位数，香港套餐贵主要是线路成本，不是品牌溢价。

**VPS 是自己管理的吗？**

是。搬瓦工全部套餐都是自助管理（self-managed），这也是它能压低价格的原因。没有人工运维服务，遇到问题靠 KiwiVM 面板自助操作和工单。

买 VPS 这件事，配置表只能帮你排除明显不合适的选项，最终决定还是取决于你的用户在哪里、预算是多少。如果看完还是拿不准，从 GIA-E 1GB 年付 $169.99 这档入手是风险最小的选择——它有 30 天退款期兜底，机房还能免费迁，试错成本不高。

👉 [前往搬瓦工官网选购套餐](https://bit.ly/BandwagonHost)
