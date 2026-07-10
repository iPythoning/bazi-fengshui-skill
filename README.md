# 八字风水分析 Skill (Bazi Fengshui Skill)

<!-- bmc:front -->
<p align="center"><a href="https://buymeacoffee.com/dayongfan"><img src="https://img.buymeacoffee.com/button-api/?text=Buy%20me%20a%20coffee&amp;emoji=&amp;slug=dayongfan&amp;button_colour=FFDD00&amp;font_colour=000000&amp;font_family=Cookie&amp;outline_colour=000000&amp;coffee_colour=ffffff" alt="Buy me a coffee"></a></p>
<!-- /bmc:front -->

> WorkBuddy Skill — 输入出生年月日，自动推算八字喜忌五行，生成个性化方位吉凶判断、板块推荐、风水优化与搬迁规划。

## 概述

本 Skill 是面向所有用户的通用八字风水分析工具。用户输入出生年月日（含时辰更佳）和所在城市后，自动推算八字喜忌五行，生成个性化的风水行动指南。

覆盖五大分析模块：
1. **八字推算** — 四柱排法、日主旺衰判断、喜用神与忌神确定
2. **方位吉凶判断** — 结合城市地理的方位五行分析与吉凶评级
3. **板块推荐** — 按五行契合度分梯队推荐，含价格区间参考
4. **住址/办公地优化** — 楼层化解、环境五行分析、室内布局优化
5. **搬迁优先级排序** — P0-P4 分级体系，结合流年与经济状况

## 可视化 UI

访问 [GitHub Pages](https://ipythoning.github.io/bazi-fengshui-skill/) 体验交互式可视化界面：

- 八字排盘计算器（四柱推算 + 五行分布 + 喜忌分析）
- 方位吉凶指南针（SVG 交互式罗盘）
- 分析流程管线（七步分析可视化）
- 五行对照速查表

## Skill 结构

```
bazi-fengshui-general/
├── SKILL.md                          # 主技能文件
└── references/
    ├── bazi-calculation.md            # 四柱排法、旺衰判断、喜忌确定
    ├── direction-analysis.md          # 方位五行、吉凶评级、板块推荐方法
    ├── optimization-guide.md          # 楼层化解、环境分析、布局对照表
    ├── relocation-plan.md             # P0-P4 体系、流年配合、行动模板
    └── output-templates.md            # 标准输出格式与模板
```

### 渐进式加载设计

- **Level 1**：metadata（name + description）— 始终在上下文中（~100 words）
- **Level 2**：SKILL.md body — 当 skill 触发时加载（<1.5k words）
- **Level 3**：references 文件 — 按需加载，不占用初始上下文

## 使用方式

<!-- bmc:middle -->
<p align="center"><a href="https://buymeacoffee.com/dayongfan"><img src="https://img.buymeacoffee.com/button-api/?text=Buy%20me%20a%20coffee&amp;emoji=&amp;slug=dayongfan&amp;button_colour=FFDD00&amp;font_colour=000000&amp;font_family=Cookie&amp;outline_colour=000000&amp;coffee_colour=ffffff" alt="Buy me a coffee"></a></p>
<!-- /bmc:middle -->

### 在 WorkBuddy 中使用

安装 Skill 后，直接在对话中提问：

```
我1990年6月15日出生，现在住在杭州，帮我分析一下风水方位
```

Skill 会自动触发，按照七步分析流程生成完整报告。

### 输出格式

完整报告包含：
1. 八字喜忌分析
2. 方位吉凶表
3. 分梯队推荐表
4. 优化方案表
5. 优先级行动表
6. 一句话总结

## 技术细节

### 八字推算方法

- 年柱：以公历尾数推算天干，生肖推算地支（立春为界）
- 月柱：以节气为界确定月支，五虎遁推算月干
- 日柱：以 1900-01-01（甲戌日）为参考，计算天数差取模 60
- 时柱：按时辰确定时支，五鼠遁推算时干

详细方法见 `skill/references/bazi-calculation.md`。

### 方位五行分析

基于后天八卦（洛书方位）的五行对应，结合实际地理环境修正：

| 方位 | 八卦 | 基础五行 |
|------|------|----------|
| 正东 | 震 | 木 |
| 东南 | 巽 | 木 |
| 正南 | 离 | 火 |
| 西南 | 坤 | 土 |
| 正西 | 兑 | 金 |
| 西北 | 乾 | 金 |
| 正北 | 坎 | 水 |
| 东北 | 艮 | 土/水木过渡 |

## 重要声明

- 本工具基于传统五行生克理论，供学习参考使用
- 精确排盘建议使用专业软件（如 [lunar-python](https://github.com/6tail/lunar-python)）
- 风水建议仅供参考，重大决策请咨询专业人士
- 月柱以节气为界，可视化 UI 中使用近似日期划分

## License

MIT

<!-- bmc:end -->
<p align="center"><a href="https://buymeacoffee.com/dayongfan"><img src="https://img.buymeacoffee.com/button-api/?text=Buy%20me%20a%20coffee&amp;emoji=&amp;slug=dayongfan&amp;button_colour=FFDD00&amp;font_colour=000000&amp;font_family=Cookie&amp;outline_colour=000000&amp;coffee_colour=ffffff" alt="Buy me a coffee"></a></p>
<!-- /bmc:end -->
