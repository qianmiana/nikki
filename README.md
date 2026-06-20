一、项目介绍
📝 配置随笔

    本项目的配置文件适用于 Mihomo 核心 的工具使用，如：OpenWrt（Clash / Nikki 插件）、Clashmi、FlClash、Clash Meta ……。
    使用需完善 订阅链接 与 机场名，并将 nameserver 修改为运营商提供的 DNS 地址，以提升解析速度。

🛠️ 配套工具

    Windows端一键生成工具 （推荐使用）：Seven1_Yaml_生成工具.exe
    流程：模板下载 → 用户输入 → YAML结构替换 → 输出文件

🗂️ 配置区分
类型 	Geo 	Rule-Set 	Overwrite
说明 	使用GeoSite / GeoIP 数据库分流 	使用Rule-Set 规则集分流 	软件覆写文件
文件 	Seven1_fallback_Geo.yaml 	Seven1_fallback_Rule-Set.yaml 	***_Clashmi_Overwrite.yaml
📚 图文教程

👉 Nikki_Yaml 使用教程    ｜    👉 Clashmi_Yaml 使用教程    ｜    👉 Clashmi_Overwrite 使用教程
🎬 视频教程

OpenWrt · Nikki 插件配置 	
Clash Mi · YAML文件&多端同步 	
Clash Mi · 自定义覆写技巧
二、运行模式
📌 出站策略建议

日常使用建议优先选择 「故障转移」，其核心原则为：稳定优先。
在当前区域节点可用时保持连接；当节点不可用或连接失败时，系统会自动切换至同一策略组内的其他可用节点，在保证连接连续性的同时，避免跨区域切换（跳区）。
🔁 故障转移机制说明

故障转移策略通常由「手动」与「自动」两类节点构成：

    手动节点：用户手动指定的优先节点（最高优先级）
    自动节点：系统基于延迟自动筛选的最优节点（作为备用）

🌟 示例：日本故障转移（日本故转）

以「日本故转」为例，其结构如下：

    日本手动
    日本自动

🚀 实际运行逻辑：

    默认使用 「日本手动」 中的节点
    当该节点不可用时，自动切换至 「日本自动」 中延迟最低的节点

✅ 优势

    高稳定性：节点异常时自动切换，减少人工干预
    高可用性：单节点失效不影响整体连接
    避免跳区：始终在同一地区内进行节点切换

image
三、Zashboard 界面
zashboard# nikki
