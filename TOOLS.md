TOOLS.md - 工具使用指南

## 📋 工具使用基本原则

### 🚫 严格禁止项（核心原则）
**禁止凭自己记忆判断工具使用**
- 必须查看具体的skill内容、文档描述和参数要求
- 严格按照文档中的规范和格式执行
- 不得凭记忆或经验自行判断工具使用方式
- 对于不明确的地方，必须先读取相关文档确认
- 执行任务前必须先查看相应的skill或文档内容

### ✅ 必须遵守的规范
- 先查看：执行任何工具前必须先查看对应的skill内容
- 严格按规：严格按照skill中描述的格式、规范执行
- 不脑补：只做skill中明确要求的内容，不自行添加
- 保留原始：保留原始记录和格式要求

## Codex API 错误修复技能（plug-codex-api-error-repair）

**指针**：`D:\微云同步助手\1055534912\AI Tool\AI人工智能\Cherry Studio\Agent\plugs\plug-codex-api-error-repair\`
**核心技能文件**：`plug-codex-api-error-repair\SKILL.md`

### 调用方式
Codex 出现 API 错误（如 `messages.content.type 参数非法`、`modelCode 不存在`、连接重连失败等）时 → 先读 `SKILL.md` 了解修复流程 → 按步骤执行

### 能力范围
1. **API 格式错误修复**：解决 `messages.content.type 参数非法` 等格式问题
2. **模型配置修复**：处理 `modelCode 不存在` 等模型相关错误
3. **连接问题修复**：解决 `Reconnecting...` 重连失败问题
4. **API 端点配置**：正确设置 cc-switch Gateway、OpenAI、本地模型等
5. **认证配置**：设置 experimental_bearer_token、API key 等

### 触发场景
- `Codex 报错 messages.content.type 参数非法`
- `modelCode 不存在` 或 `模型不存在`
- `Reconnecting...` 重连失败
- `API 端点连接错误`
- `wire_api 配置错误`

---

## DeepSeek Harness 修复技能（plug-deepseek-harness-repair）

**指针**：`D:\微云同步助手\1055534912\AI Tool\AI人工智能\Cherry Studio\Agent\plugs\plug-deepseek-harness-repair\`
**核心技能文件**：`plug-deepseek-harness-repair\SKILL.md`

### 调用方式
DeepSeek Harness 无法启动、报错 "is not a symlink" 或端口冲突时 → 先读 `SKILL.md` 了解修复流程 → 按步骤执行

### 能力范围
1. **错误诊断**：识别符号链接错误、端口占用、配置问题
2. **彻底修复**：清理 node_modules 符号链接问题
3. **端口管理**：解决 Windows 系统进程端口占用
4. **重启验证**：重新启动 web profile 并验证访问
5. **问题预防**：提供操作避免再次出现相同问题

### 触发场景
- `DeepSeek Harness 启动失败`
- `dsh 报错 is not a symlink`
- `DeepSeek 端口冲突`
- `Harness web 无法访问`

---

## GitHub Pages网页发布技能（plug-github-pages）

**指针**：`D:\微云同步助手\1055534912\AI Tool\AI人工智能\Cherry Studio\Agent\plugs\plug-github-pages\`
**核心技能文件**：`plug-github-pages\SKILL.md`

### 调用方式
需要将HTML网页发布到GitHub Pages时 → 先读 `plug-github-pages\SKILL.md` 了解完整流程 → 按步骤执行

### 能力范围
1. **HTML生成**：读取8个配置文件，生成带Tab切换的交互式网页
2. **Git仓库管理**：git init/config/add/commit/push全流程
3. **GitHub仓库创建**：使用API自动创建仓库
4. **gh-pages分支发布**：orphan分支部署Pages
5. **验证发布结果**：curl检查HTTP 200确认上线

### 触发场景
- `生成配置文件网页并发布`
- `把配置文档上线到Github Pages`
- `做一份个人Agent配置网页`

**指针**：`D:\微云同步助手\1055534912\AI Tool\AI人工智能\Cherry Studio\Agent\plugs\plug-ppt\`
**核心技能**：`pptx`（pptxgenjs引擎，位置：Skills/pptx/）
**技能目录**：`D:\微云同步助手\1055534912\AI Tool\AI人工智能\Cherry Studio\CherryStudio\Data\Skills\pptx\`

### 调用方式
需要制作PPT时 → 先读 `plug-ppt\way*/SKILL.md` 了解方案管线 → 调 `pptx` skill（pptxgenjs引擎）执行生成

### 9种方案速查

| # | 方案 | 目录 | 核心引擎 | 适合场景 |
|:-:|:----|:-----|:---------|:---------|
| 1 | Baidu-PPT | `way1-baidu-ppt/` | SVG模板→DrawingML | 正式商务/行业报告 |
| 2 | sn-ppt | `way2-sn-ppt/` | 商汤LLM全自动 | 快速草稿/视觉稿 |
| 3 | sn-baidu-mixed | `way3-sn-baidu-mixed/` | 商汤规划+百度SVG | 2-5页向上汇报 |
| 4 | HTML→pptx | `way4-html-pptx/` | HTML三技能→pptx | 精美视觉+图标 |
| 5 | AI-image | `way5-ai-image/` | gpt-image/MiniMax | 产品/品牌/营销 |
| 6 | Scene-Specific | `way6-scene-specific/` | business-report/course | 商业报告/课件 |
| 7 | HTML-Convert | `way7-html-convert/` | guizang真转换 | HTML存量转PPTX |
| 8 | Visual-Content | `way8-visual-content/` | ppt-master/baoyu | 杂志风/视觉稿 |
| 9 | coze-harries | `way9-coze-harries/` | 方法论+四步法 | 正式汇报（4件套交付） |

### 底层引擎
- **pptxgenjs**（⭐ 首推）：Node.js，支持阴影/圆角/图表/react-icons图标
- **python-pptx**：纯Python，数据表格密集型
- **Baidu SVG管线**：原生DrawingML可编辑
- **sn-ppt管线**：LLM全自动→HTML→PPTX

## 核心工具配置

### 网络搜索工具
- **mcp__exa__web_search_exa**: 网络搜索 功能：搜索网络内容，获取清洁的文本结果 参数： query（必需）：搜索查询，用自然语言描述理想页面 numResults（可选）：返回结果数量，默认10个 使用场景：查找最新信息、公司资料、技术文档 搜索技巧：site:限定域名、组合关键词、freshness控时效

### 网页抓取工具
- **mcp__exa__web_fetch_exa**: 网页内容抓取 功能：获取指定网页的完整内容，转换为干净的markdown格式 参数： urls（必需）：要抓取的网页URL列表 maxCharacters（可选）：每页最大字符数，默认3000 使用场景：获取详细文章内容、技术文档、新闻全文

### 文档处理工具
- **mcp__claw__config**: 配置文件管理 功能：管理配置文件、设置参数 用途：系统配置、工作环境设置

- **mcp__agent-memory__memory**: 记忆管理 功能：管理长期记忆和工作记忆 操作：append、read、search、clear 用途：保存重要信息、工作进度记录

### 数据分析工具
- **excel-xlsx**: Excel文件处理 功能：创建、编辑、分析Excel工作簿 支持格式：.xlsx、.xlsm、.xls、.csv、.tsv 特点：公式计算、数据验证、样式保持

### PPT制作工具链
- **create-ppt技能**: PPT生成 功能：AI生成专业级演示文稿 流程：需求理解→风格定位→数据收集→结构设计→Prompt编写→生成导出 风格：A_infographic_general_blue（信息图风·商务通用）

- **echart技能**: 数据图表 功能：生成复杂的数据可视化图表 支持类型：折线图、饼图、柱状图、散点图 用途：专业数据展示

## 行业信息优先搜索网站

### 无人车垂直类
- 1号无人车网(1umv.com) 低速无人驾驶网(www.wrdrive.com) 无人系统网(www.youuvs.com)

### 交通智能类
- 赛文交通网(www.7its.com) 518智能装备在线(zhineng518.com)

### 物流平台
- 罗戈网(www.logclub.com) 物流指闻(www.headscm.com) 运联网、传物T-Log(www.translog.cn)

### 研报平台
- 慧博投研(www.hibor.com.cn) 三个皮匠报告(www.sgpjbg.com) 发现报告(www.fxbaogao.com) 洞见研报(www.djyanbao.com)

### 综合新闻媒体
- 百度(www.baidu.com) — 综合搜索，能搜到百家号、各类新闻 今日头条(www.toutiao.com) — 综合资讯/自媒体 腾讯新闻(news.qq.com) 网易新闻(www.163.com) 新浪财经(finance.sina.com.cn) 新华网(app.xinhuanet.com) — 官方权威媒体

### 财经资讯
- 财联社(www.cls.cn) 每日经济新闻(www.nbd.com.cn) 金融界(www.jrj.com.cn) 投资界(www.pedaily.cn) 证券日报(www.zqrb.cn)

### 汽车/商用车行业媒体
- 易车网(www.bitauto.com) 运输人网(www.yunshuren.com) 商车邦(cvzone.com.cn) 提加商用车网(www.cntplus.com) 卡车网(www.chinatruck.org)

## 文件处理技巧

### Excel数据处理
- **多渠道交叉验证**：优先卡车之家、品牌官网、运输人网 **批量修正**：openpyxl批量读写，错误数据红色标记 **数据验证**：关键参数至少2来源验证

## Excel专业技能（新增）

### 1. excel-studio - 专业Excel制作
- **功能**：专业级Excel表格生成，支持多格式、图表、公式
- **用途**：制作专业报表、数据分析表格、工作总结
- **特点**：
  - 📊 多格式支持：.xlsx、.xls、.csv
  - 📈 图表支持：柱状图、折线图、饼图、散点图
  - 🔢 公式支持：SUM、AVERAGE、VLOOKUP、IF等
  - 🎨 专业格式：表头样式、边框、对齐、字体
  - 📑 多Sheet管理：多个工作表交叉引用
  - 🌍 多语言支持：中文、英文、日文
  - ✅ 跨平台兼容：Excel、WPS、LibreOffice
- **触发词**：制作Excel、生成表格、数据分析、制作报表
- **使用场景**：需要专业格式和完整功能的Excel制作

### 2. sn-da-excel-workflow - Excel数据分析流程
- **功能**：完整的Excel数据分析端到端流程
- **用途**：数据分析、清洗、统计、可视化、导出
- **特点**：
  - 📊 读取多Sheet文件并统计行数
  - 🔄 大文件检测（≥10k行自动Parquet优化）
  - 🧹 数据清洗（缺失值、文本标准化、无效字符）
  - 📈 条件筛选与分类提取
  - 📊 跨Sheet统计聚合
  - 💾 导出Excel/CSV并提供下载链接
- **触发词**：Excel分析、表格分析、数据分析、数据清洗、汇总统计、透视表、生成报表
- **使用场景**：复杂的数据分析任务，需要完整流程

### 3. excel-formula - Excel公式生成器
- **功能**：根据描述生成Excel公式，诊断表格错误
- **用途**：公式编写、错误调试、公式转换
- **特点**：
  - 📝 支持中英双语
  - 🔍 公式错误诊断
  - 💡 智能公式建议
  - 📚 丰富的公式模板
- **触发词**：公式、VLOOKUP、SUMIF、IF函数
- **使用场景**：需要编写或调试Excel公式时

### 4. wps-excel - WPS表格智能助手
- **功能**：通过自然语言操控Excel，解决公式编写、数据清洗、图表创建问题
- **用途**：WPS表格操作、公式生成、图表创建
- **特点**：
  - 💬 自然语言交互
  - 🧮 公式类（VLOOKUP、IF、SUMIF等）
  - 📊 图表创建
  - 🧹 数据清洗
- **触发词**：WPS表格、Excel操作、自然语言控制
### 5. openclaw-gateway-start - OpenClaw Gateway 启动
- **功能**：一键启动/重启 OpenClaw Gateway 服务，连接飞书等IM通道
- **用途**：启动后台网关、飞书通道重连、诊断修复
- **路径**：`D:\微云同步助手\1055534912\AI Tool\AI人工智能\openclaw`
- **触发关键词**：启动openclaw、重启网关、重连飞书、openclaw掉线
- **执行流程**（3种方式，按推荐顺序）：
  **方式1 - PowerShell Start-Process（推荐，完全无窗口）**：
  1. 检查端口状态：`powershell -Command "netstat -ano | Select-String ':18790'"`
  2. 如未监听，启动：
     ```
     powershell -Command "Start-Process -FilePath 'node' -ArgumentList 'C:\Users\HP\AppData\Roaming\npm\node_modules\openclaw\dist\index.js', 'gateway', '--port', '18790' -WorkingDirectory 'D:\微云同步助手\1055534912\AI Tool\AI人工智能\openclaw' -WindowStyle Hidden"
     ```
  3. 等待8-12秒，验证端口：`netstat -ano | Select-String ':18790'` → 应显示 LISTENING
  **方式2 - VBS脚本**：运行 `.openclaw\gateway.vbs`（内部 WScript.Shell.Run 0=隐藏窗口）
  **方式3 - CMD脚本**：`.openclaw\gateway.cmd`（设置环境变量后启动 node，需配合方式1/方式2隐藏窗口）
- **验证成功标志**：端口 18790 LISTENING
- **Dashboard**：http://127.0.0.1:18790
- **注意事项**：
  - ⚠️ 不能用 bash run_in_background=true 启动（bash结束进程即被杀）
  - ⚠️ 不能用 start "" cmd /c（会弹可见DOS窗口）
  - 飞书通道需要 WebSocket 长连接方式
  - 安全警告（明文API密钥）不影响正常使用
  - Windows 锁屏/注销会终止所有用户进程

### 5.1 feishu-channel - CherryClaw 飞书通道配置修复
- **功能**：CherryClaw 飞书通道的配置、排查与修复
- **用途**：飞书收不到消息、飞书下行通上行断、飞书通道重配
- **路径**：`D:\微云同步助手\1055534912\AI Tool\AI人工智能\Cherry Studio\Agent\tools\feishu-channel\README.md`
- **触发关键词**：飞书通道、飞书收不到、飞书配置、重配飞书、飞书上行、飞书下行
- **核心铁律**：
  - ⚠️ **CherryClaw 飞书 ≠ OpenClaw 飞书，两个独立应用！**
  - CherryClaw 用 `cli_aacd75b544f8dbeb` / `J1OkubQDgr2caBiC1aYTFbKvFiwN5OBz`
  - OpenClaw 用 `cli_a97554668af91bcf` / `CrDHyYnFjNMqhZjFICE9TdLA1NGNipgA`
  - 用错凭据会报 `invalid receive_id` / `Bot can NOT be out of the chat`
- **关键配置**：
  - 数据库：`CherryStudio\Data\agents.db` 的 `channels` 表
  - 已绑定群聊：`oc_ed81a5c147a6bd826c0e54c114cef6ec`, `oc_9073131ca4a60db0ad70e70746f1a075`
  - 通道ID：`9928134a-9596-4dac-a0b1-92c23e14ad5c`
- **修复命令**：`mcp__claw__config update_channel` 带 app_id/app_secret/allowed_chat_ids
- **报错对照**：
  - `0 chat(s)` → 通道没绑定聊天，补 allowed_chat_ids
  - `invalid receive_id` → app_id 用错
  - `Bot can NOT be out of the chat` → 群ID错误/机器人不在群里
- **教训**：删除通道前必须先备份；改配置用 update_channel 而不是 remove+add

### 6. model-switcher - OpenClaw 模型切换器
- **功能**：切换OpenClaw主模型，支持单模型直接切换/多模型测试选最优
- **用途**：更换Agent工作模型、切换不同大模型供应商
- **路径**：`D:\\微云同步助手\\1055534912\\AI Tool\\AI人工智能\\Cherry Studio\\Agent\\.claude\\skills\\model-switcher\\`
- **触发关键词**：切换模型、更换模型、换model、openclaw换模型、模型测试
- **工作流程**：
  1. 单模型：直接切换，不测试
  2. 多模型（逗号分隔）：逐个测试API响应时间，自动选最快的切换
- **可用模型列表**（预配置10个）：
  - `cherry-shangtang/deepseek-v4-flash`（默认）
  - `cherry-shangtang/sensenova-6.7-flash-lite`
  - `cherry-nvidia/deepseek-ai/deepseek-v4-pro`
  - `cherry-deepseek/deepseek-v4-flash`
  - `cherry-cherryin/agent/deepseek-v3.2(free)`
  - 更多在 `config.json` 中查看
- **调用方式**：
  - `/model-switcher "模型名称"` → 切换到指定模型
  - `/model-switcher "模型A,模型B,模型C"` → 测试多个后选最优
- **注意事项**：可用模型列表需与Cherry Studio配置的供应商一致
- **调用方法**：打开模型切换技能 → `/model-switcher "模型名称"` 直接切换，不需要手动改JSON或重启gateway

### 7. CherryStudio/Claude 模型切换记录（2026-08-03）

> **这是 CherryStudio（Claude Code）层面的操作**，跟 OpenClaw Gateway 没关系。

| 场景 | 正确做法 | 错误做法 |
|------|---------|---------|
| **切换我的工作模型** | 调 `model-switcher` 技能 → `/model-switcher "模型名"` | ❌ 手动改openclaw.json + 重启gateway（完全绕路了） |
| **指定模型不在列表里** | 先更新 `config.json` 的 `available_models`，再切换 | ❌ 不更新直接写模型名，报错说找不到 |

**关键教训**：换模型是CherryStudio的事，跟OpenClaw Gateway无关。model-switcher技能一步到位，不要动JSON。

### 8. OpenClaw Gateway 操作经验总结（2026-08-03）

> **这是 OpenClaw Gateway 层面的操作**，跟 CherryStudio 无关。

| 场景 | 正确做法 | 错误做法 |
|------|---------|---------|
| **飞书通道WARN/掉线** | `openclaw plugins install @openclaw/feishu --force` → 重启gateway | ❌ 只跑 `doctor --fix` 没用，要装插件 |
| **飞书WebSocket连不上** | 飞书开发者后台→事件与回调→订阅方式=长连接 | ❌ 默认是webhook，不改连不上 |
| **修改openclaw.json后** | `openclaw gateway stop` → `openclaw gateway` 重启 | ❌ 改了不重启=没改 |
| **Gateway启动超时(timeout)** | 等12-15秒预热，`openclaw status --deep` 检查 | ❌ 看到timeout就以为挂了 |
| **exit code 78启动失败** | `openclaw doctor --fix` → 再启动 | ❌ 直接重试反复exit 78 |
| **VBS弹窗报错** | `Unregister-ScheduledTask` 删掉坏的定时任务 | ❌ 重装OpenClaw或删文件 |

**核心原则**（OpenClaw专用）：
1. **改配置必重启** — openclaw.json、插件、模型配置，改了不重启都不生效
2. **doctor不是万能药** — 插件缺失 doctor 修不了，要 `plugins install`
3. **VBS弹窗无害** — 删ScheduledTask就行，gateway不需要它也能跑
4. **预热是正常的** — 启动后12-15秒延迟是预热，不是挂了

### 8. ws-excel - Excel操作助手
- **功能**：Excel数据处理、公式、表格操作
- **用途**：基本Excel操作
- **特点**：
  - 🔧 基础功能
  - 💻 简洁实用
- **触发词**：Excel、表格操作
- **使用场景**：简单的Excel操作任务

### 9. excel-xlsx - 专业Excel处理
- **功能**：创建、检查、编辑Excel工作簿，处理公式、日期、格式等
- **用途**：需要精确控制Excel格式和结构
- **特点**：
  - 📊 完整的Excel功能
  - 🔢 可靠的公式计算
  - 📅 日期时间支持
  - 🎨 格式保持
  - 🔗 工作簿结构管理
- **触发词**：Excel、xlsx、xlsm、csv、tsv
- **使用场景**：需要精确控制和专业处理的Excel任务

### 10. excel-reader - Excel文件读取
- **功能**：读取Excel文件内容
- **用途**：获取Excel数据
- **特点**：
  - 📖 简单易用
  - 🔍 数据提取
- **触发词**：读取Excel、Excel内容
- **使用场景**：只需要读取Excel数据时

## Excel技能选择指南

| 场景 | 推荐技能 | 原因 |
|------|----------|------|
| 制作专业报表 | excel-studio | 最全面的制作功能，格式专业 |
| 复杂数据分析 | sn-da-excel-workflow | 完整的分析流程 |
| 公式相关 | excel-formula | 专业的公式生成和调试 |
| WPS用户 | wps-excel | 自然语言交互，中文友好 |
| 简单操作 | ws-excel | 基础功能，简洁实用 |
| 精确控制 | excel-xlsx | 专业级控制 |
| 只读数据 | excel-reader | 轻量级读取 |

### 11. 半年报合并技能 - 1-6月关键结果合并
- **功能**：将1-6月相似的关键结果合并到同一单元格，保留月份信息
- **用途**：制作半年工作总结，跨月事项整合
- **核心特点**：
  - 📅 保留原始月份标注（【1月】【2月】等）
  - 🔗 相同事项跨月合并，体现工作连续性
  - 📝 不曲解、不脑补、不润色，完全保留原始内容
  - 📊 生成3Sheet专业Excel（合并表、对照表、统计表）
  - 🔍 按事项分类，非按标签分类
- **触发词**：半年报合并、1-6月合并、相似内容合并、跨月事项整理
- **使用场景**：需要将分散在1-6月的关键结果进行相似内容合并整理
- **关键经验**：
  - **合并粒度**：同项目、同合作方、同主题合并，保持事项独立性
  - **月份标注**：每条内容前明确标注月份，体现推进脉络
  - **质量保证**：必须验证索引准确性，确保覆盖率100%
  - **格式规范**：专业Excel格式，包含原始对照表便于溯源

### PDF文档处理
- **PDF解析**：用pdf技能提取重组内容 **文档转换**：markdown格式便于编辑和搜索

### 法规翻译经验总结（EU 168/2013，2026-07-25实践）
- **适用技能**：`ENCH-regulation-translator`（位置：Skills/ENCH-regulation-translator/）
- **4阶段流水线**：
  - Stage 1：原文提取（PDF→TXT→Markdown结构化）
  - Stage 2：术语基线建立（先翻译第1-5条，提取第3条定义作为固定术语库）
  - Stage 3：并行翻译（主线程处理第6-28条，3个Agent并行处理第29-53条、第54-82条+附件、或其他分块）
  - Stage 4：合并+验证+Word输出

- **技能文件结构**：
  - `SKILL.md`：技能主文档（包含触发条件、质量红线）
  - `references/terminology.md`：12大类200+术语对照表
  - `scripts/validate_translation.py`：验证脚本（检验章节、条款、附件覆盖率 + 术语一致性）
  - `scripts/split_markdown.py`：结构分析工具（识别章节边界，推荐分块方案）

- **术语红线（禁止译法）**：
  | 错误译法 | 正确译法 | 英文原文 |
  |---------|---------|----------|
  | 上市 | 投放市场 / 在市场上提供 | placing/making available on the market |
  | 上路 | 投入使用 | entry into service |
  | 会员国 | 成员国 | Member State |
  | 条例 | 法规 | Regulation |
  | 型式认可 | 型式批准 | type-approval |
  | 审批机关 | 批准机构 | approval authority |
  | 市场监管 | 市场监督 | market surveillance |
  | 委任法案 | 授权法案 | delegated act |
  | 实施法案 | 执行法案 | implementing act |
  | 一致性证书 | 合格证书 | certificate of conformity |

- **中文输出要求**：
  - `-X utf8` 或 `PYTHONUTF8=1` 解决Windows GBK编码问题
  - python-docx生成Word时需手动设置中文字体（eastAsia）

- **验证标准**（脚本自动检查）：
  - ✅ 章标题数匹配（18章）
  - ✅ 条款1-N全覆盖（82条无断裂）
  - ✅ 附件数匹配（9个附件，注意罗马数字I-IX）
  - ✅ 中文字数统计（约4.7万字）
  - ✅ 术语一致性抽查

- **本次翻译经验总结**：
  1. **术语必须先打表**：翻译前建立terminology_ref.md，所有agent共享，避免术语混乱
  2. **第3条定义是关键锚点**：96个定义是最重要的术语基线，必须由主线程先完成
  3. **附件标题罗马数字**：`## 附件I`格式不会被`## 附件[一二三四五六七八九十]+`正则匹配到，需扩充
  4. **合并顺序**：序言(preamble) → 第1-5条 → 第6-28条 → 第29-53条 → 第54-82条+附件
  5. **后期修复术语**：Part_1中6处"提供上市"被Agent生成，需逐一修复为"在市场上提供"
  6. **中文字体设置**：python-docx必须设置`w:eastAsia`属性，否则Word显示方块

### 图片处理
- **图标资源**：emojipedia.org（emoji）、iconfont.cn（扁平）、iconscout.com（3D） **视觉设计**：遵循A_infographic_general_blue风格规范

### 图片识别技能库（2026-06-10更新）
#### 当前可用技能：
1. **Image Processor**（已安装）
   - 本地Tesseract OCR，支持中英文
   - 表格、图表、文字图片识别
   - 双层级联策略

2. **百度智能识图**（从OpenClaw复制）
   - 实际功能：图片搜索（返回相似图片和相关网页）
   - 注意：非OCR文字识别功能
   - API密钥：已内置
   - 脚本路径：images/baidu-image-ocr/scripts/image_ocr.py

3. **可安装视觉技能**：
   - **Azure AI Vision**：微软云图片分析API
   - **Gemini Image Analysis**：Google Gemini视觉分析
   - **LLaVA**：视觉对话模型
   - **Computer Vision Pipeline**：专业CV流水线
   - **AI Multimodal**：Google Gemini多模态处理
   - **Vision**：综合视觉分析工具

#### 图片识别优先级：
1. **文字识别**：Image Processor（本地Tesseract OCR）
2. **图片搜索**：百度智能识图（查找相关内容）
3. **深度文档分析**：商汤Vision API（专业文档处理）
4. **复杂分析**：可安装云端技能（更强大）
5. **多模态任务**：AI Multimodal（音频、视频、图片）

### 图片识别技能配置（2026-06-11更新）
- **技能位置**：`images/image-recognition/`
- **核心脚本**：
  - `scripts/improved_tesseract.py` - 改进的Tesseract OCR
  - `scripts/baidu_api_custom.py` - 百度智能识图
  - `scripts/baidu_text_recognition.py` - 百度文字识别
  - `tools/direct_ocr.py` - 直接调用Tesseract（推荐）
- **Tesseract OCR安装状态**：✅ 已安装（v5.4.0 UB-Mannheim版本）
  - 安装路径：`C:\Program Files\Tesseract-OCR\tesseract.exe`
  - 中文语言包：❌ 未安装（需要手动下载）
  - 英文识别：✅ 完全正常
  - 工具脚本：`tools/direct_ocr.py` - 直接调用Tesseract
- **环境依赖**：
  - Tesseract OCR v5.4.0（Windows包管理器安装）
  - 中文语言包：需手动下载 chi_sim.traineddata
  - Python库：pytesseract, Pillow, requests
- **使用方法**：
  1. 英文识别：`python tools/direct_ocr.py`（已可用）
  2. 中文识别：需要先安装中文语言包
  3. 或使用image-processor技能
- **中文语言包下载**：
  ```bash
  # 下载地址
  https://raw.githubusercontent.com/tesseract-ocr/tessdata/main/chi_sim.traineddata
  # 保存到
  C:/Program Files/Tesseract-OCR/tessdata/chi_sim.traineddata
  ```

## 工作流程模板

### 月报整理输出（两种格式）

**格式A：明细版（Excel直接粘贴）**
1. **输入**：周报/工作日志原始内容
2. **处理**：合并重复事项 → 理顺逻辑顺序 → 去口头语和冗余
3. **输出**：Markdown表格 | 序号 | 事项内容 |，①、②、③编号
4. **质量控制**：不曲解、不脑补、不润色。数据具体、进度明确

**用户确认的月报朴实风格范例**：
- ① 金融公司台账：完善对接表和数据台账，部分事项线上化
- ② 中交212台抵押：13城已完成1城，再寄1本营业执照  
- ③ 远通汽车项目：50台、6.5F、1.5T，已报价，价格偏高在沟通
- ④ 协助进行京津冀投促会和北京经信局到访公司的接待，进行后续合作相关政策、资金、订单扶持等事项了解，以及进行后续对方邀请京津冀区域建厂的保持沟通
- ⑤ 建立无人车行业信息库，从竞品、公司、新闻三个角度收集更新，本月共整理行业新闻、企业动态信息等>84条相关基础数据库信息
- ⑥ 远通汽车【项目客户订单取消】，已完成该项目的二次报价、车辆设计和方案实现的沟通，原先客户方案需求是：需求量50台、箱体6.5F、载重1.5T，新石器无人车方案已按13万/台报价
- ⑦ 拟定公司车辆资质维护方案报告，进行相关金融部分数据整理与金融公司的沟通，集团金融部该批车辆融资事项需求提出
- ⑧ 数字化和线上化实现：进行金融贷后管理对接线上化试运行，对应完善融资车辆管理模块线上化和数据格式清理，进行资产数据台账46个资产数据字段格式清洗，并按六个模块进行拆解
5. **用途**：直接复制粘贴到Excel给老板汇报

**格式B：key任务汇总版（OKR维度）**
1. **输入**：同份周报内容
2. **处理**：归类同类事项 → 提炼key描述（一句话说清"干了哪类事"）
3. **输出**：Markdown表格 | key | 事项内容 |
4. **key写法**：不空、不大、不计划，是总结不是计划。如"行业智驾技术公司合作沟通推进"而非"数字化和线上化的实现"（太具体）
5. **用途**：给老板看关键任务归类，一眼知道重点方向

### 半年报合并流程（新增）
**适用场景**：需要将1-6月的关键结果进行相似内容合并整理

**核心步骤**：
1. **数据提取**：读取原始Excel，提取关键结果和月份信息
2. **人工识别**：人工判断相似内容，非自动化分类
3. **合并组定义**：按具体项目/合作方/主题定义合并组
4. **内容合并**：按月份顺序排列，保留【月份】标注
5. **专业输出**：生成3Sheet Excel文件

**关键经验**：
- **合并原则**：按事项合并，不是按分类合并
- **月份标注**：每条内容前明确标注月份
- **质量控制**：验证索引准确性，确保覆盖率100%
- **格式规范**：包含原始对照表便于溯源

### PPT制作七步法
1. **需求理解**：明确内容、受众、页数，不泛化理解
2. **风格定位**：默认A_infographic_general_blue风格
3. **数据收集**：search_web搜行业数据，至少2权威来源交叉验证
4. **结构设计**：秋叶金字塔框架，结论先行，一页一事
5. **Prompt编写**：融合式写法，内容+排版一一对应
6. **调脚本生成**：create-ppt技能生成，失败重试
7. **交付检查**：确认生成成功，关键数字提示用户确认

### 数据分析方法
1. **来源优先级**：官方渠道>行业媒体>专业机构
2. **搜索策略**：site:限定域名、品牌+车型+核心参数组合
3. **数据验证**：多渠道交叉验证，确保准确性
4. **呈现方式**：表格优先，图表辅助，结论清晰

### 质量控制标准
- **数据来源**：必须标注来源机构，无来源数据不使用 **品牌准确性**：专业术语100%准确，如"奇瑞轻卡叫零米" **交付质量**：专业级内容，用户无需二次修改 **响应速度**：高效完成，主动推进工作进度

## 工具配置说明

### 核心技能工具链
- **image-processor**: 图片识别和处理，支持中文/英文OCR、表格检测
- **report-generator**: 专业级报告生成，自动处理周报、月报总结
- **pptx**: PPT制作工具，支持创建、编辑、导出演示文稿
- **excel-xlsx**: Excel文件处理，支持多Sheet数据操作
- **excel-reader**: Excel文件读取和解析
- **create-ppt**: AI生成PPT，支持A_infographic_general_blue风格
- **echart**: 专业数据可视化，生成复杂图表
- **skill-creator**: 创建和管理技能
- **init**: 初始化代码库文档
- **review**: 代码审查
- **security-review**: 安全审查

### 行业分析工具
- **search_web**: 网络搜索，支持site限定、关键词组合、时效控制
- **fetch_web**: 网页抓取，获取指定网页完整内容
- **sessions_spawn**: 深度调研，调用deep_research做专业分析

### 文档处理工具
- **Read**: 文件读取，支持多种格式
- **Write**: 文件写入，支持文本生成
- **Edit**: 文件编辑，支持精确修改
- **Glob**: 文件模式匹配，快速查找文件
- **Grep**: 内容搜索，支持正则表达式

### 数据验证工具
- **数据验证等级**: A级（官方/上市）> B级（券商/协会）> C级（媒体/企业）
- **交叉验证**: 关键数据至少两个权威来源确认
- **来源标注**: 所有数据必须标注来源机构

## 配置文件说明

- **SOUL.md**: 灵魂文件，核心价值观和行为准则
- **USER.md**: 用户画像，了解用户偏好和需求
- **MEMORY.md**: 长期记忆，工作经验和技能积累
- **FACT.md**: 事实知识，重要决策和关键信息（包括迁移prompt学习总结）
- **JOURNAL.jsonl**: 日志记录，历史对话和工作进度
- **EMAIL_RULES.md**: 邮件处理规则，自动分类和通知机制

## Agent相关工具
- **Agent**: 启动专业代理处理复杂任务
- **TaskOutput**: 获取任务输出和状态
- **TaskStop**: 停止运行中的任务
- **ScheduleWakeup**: 定时任务调度

## CherryClaw工具
- **mcp__claw__config**: 配置文件管理，添加/更新/删除IM通道
- **mcp__claw__cron**: 定时任务调度，创建/列出/删除任务
- **mcp__claw__notify**: 消息通知，通过IM通道发送更新
- **mcp__agent-memory__memory**: 记忆管理，更新/追加/搜索记忆

## 月度回顾与计划插件 (plug-summar&plan)

### 插件概述
**位置**: `plugs/plug-summar&plan/`  
**功能**: 提供月度工作总结和月度工作计划的完整技能体系  
**特色**: 集成多个专业技能，支持工作回顾与规划的标准化流程

### 核心技能来源
基于 AGENTS.md 中定义的两个专业技能：
- **Monthly_Work_Summary_Master** - 月度工作总结专家
- **Monthly_Work_Planning_Master** - 月度工作计划专家

### 快速选择指南

#### 月度工作总结与月报整理
- **方式一**：`way1-monthly-summary/`
  - **月度工作总结（提炼式）**：从周报、工作日志中提炼总结
  - **月报整理（整理式）**：对已有月报内容进行整理汇总
  - **核心原则**：不曲解、不脑补、不润色、量化优先
  - **特色功能**：
    - 9步提炼法：合并同类、删过程词、保硬数据、方向明确、动词统一、成果导向、1-2句话、整体概况、状态前置+冒号分层
    - 合作方归类提炼：按合作方分类，每个合作方一句话总结
    - 项目式总结：①项目名称[关键条件]：核心内容 + 当前状态

#### 半年度报告合并（2026-07-03 全面修正版）
- **方式三**：`semi-annual-merge/`
  - **核心**：将1-6月相似关键结果精确合并，月份与事项一一对应
  - **关键修正**：月份列从 Unnamed:0（序号）修正为 **Unnamed:4（时限）**
  - **合并方法**：关键字自动匹配替代手动硬编码索引
  - **数据预检**：必须先读源文件确认列结构再动手
  - **输出**：3Sheet专业Excel（合并表/对照表/统计表）
  - **关键教训**：先读数据再写代码，不模拟数据替代真实数据
  - **文档结构**：
    - SKILL.md：技能详细说明和操作流程（含错误排查清单）
    - 半年度总结修正版.md：修正经验总结和验证清单

#### 月度工作计划
- **方式二**：`way2-monthly-planning/`
  - **适用场景**：月度工作规划、任务分解
  - **特色**：四象限法则、SMART目标、PDCA循环
  - **计划结构**：
    1. **核心目标**：本月要达成的3-5个核心目标
    2. **关键任务**：每个目标下的具体任务清单
    3. **时间节点**：关键里程碑和完成时限
    4. **资源需求**：所需的人员、预算、工具支持
    5. **风险预案**：可能遇到的问题和解决方案

### 使用方法

#### 月度工作总结调用
**触发词**：
- "整理下这个月的工作"
- "做个月度总结"
- "把周报汇总成月报"
- "月度工作汇报"
- "总结一下这个月"
- "月报整理" / "整理月报"

**自动方式判断**：
| 用户输入特征 | 自动选择方式 |
|-------------|-------------|
| "这是我的周报/工作日志..." | 提炼式（方式一） |
| "这是我写的月报草稿..." | 整理式（方式一） |
| "把这几个人的周报汇总..." | 整理式（方式一） |
| "月报写得有点乱，帮我理顺" | 整理式（方式一） |

#### 半年度报告合并调用
**触发词**：
- "半年报合并"
- "1-6月合并"
- "相似内容合并"
- "跨月事项整理"
- "制作半年总结"

**关键步骤**：
1. 读取源文件确认列结构（df.columns.tolist() + df.head()）
2. 确认正确月份列（Unnamed:4）
3. 定义合并组（按事项/合作方/主题）
4. 按关键字自动匹配相似内容
5. 生成3Sheet专业Excel

#### 月度工作计划调用
**触发词**：
- "制定月度计划"
- "月度工作规划"
- "下月工作安排"
- "月度目标制定"

**特色功能**：
- 四象限法则分类（重要紧急、重要不紧急、紧急不重要、不紧急不重要）
- SMART目标制定（具体的、可衡量的、可实现的、相关的、有时限的）
- PDCA循环管理（计划、执行、检查、调整）

### 质量控制标准

#### 月度工作总结质量
- **不曲解**：原文说什么就是什么，不多解释
- **不脑补**：对方没说"为什么""后面怎么安排"，就不写
- **去口语化**："已经完成了"→"已完成"
- **量化优先**："很多"→"84条"

#### 半年度报告合并质量
- **验证索引准确性**：确保52条全部覆盖，无遗漏
- **月份标注清晰**：每条合并内容前标注【1月】【2月】等
- **原始对照表**：提供Sheet2便于溯源
- **月度统计**：Sheet3提供工作分布统计

#### 月度工作计划质量
- **目标明确**：3-5个核心目标，SMART原则
- **任务分解**：每个目标下有具体任务清单
- **时间节点**：关键里程碑和完成时限明确
- **风险预案**：可能遇到的问题和解决方案

### 配置文件说明
- **SOUL.md**: 灵魂文件，核心价值观和行为准则
- **USER.md**: 用户画像，了解用户偏好和需求
- **MEMORY.md**: 长期记忆，工作经验和技能积累
- **FACT.md**: 事实知识，重要决策和关键信息（包括迁移prompt学习总结）
- **JOURNAL.jsonl**: 日志记录，历史对话和工作进度
- **EMAIL_RULES.md**: 邮件处理规则，自动分类和通知机制

---

*最后更新：2026-08-03*
*版本：v1.2 (新增模型切换经验、飞书通道修复经验、OpenClaw操作速查表)*

---
*最后更新：2026-06-01*
*版本：v1.0*

## ⚠️ 工具使用警示

### 🔍 违反原则的常见错误示例
1. **凭记忆执行**：
   - ❌ "我知道格式应该是这样..." 
   - ✅ "根据skill中的规范，应该是..."
   
2. **不查看文档**：
   - ❌ "根据我之前的经验..."
   - ✅ "需要先查看skill内容确认要求"

3. **自行脑补**：
   - ❌ "这里应该是这样的格式..."
   - ✅ "严格按照skill中的规范执行"

### 💡 正确的工作流程
1. **查看skill**：执行任务前先阅读相关skill内容
2. **严格按规**：按照skill中的规范和格式执行
3. **保留原始**：保留原始记录，不做曲解或脑补
4. **确认格式**：按照skill要求的格式输出结果

**记住：先看文档，再执行，严格按规！**