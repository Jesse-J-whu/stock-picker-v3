# 鸭口选股 V3

六大指标 × 三个时间周期（月线 / 周线 / 日线）全部满足才选入。

## 选股逻辑

### 一、BOLL（布林带开口扩张）
- 月线：12个月内出现过 UB↑ & BOLL↑ & LB↓
- 周线：26周内出现过 UB↑ & BOLL↑ & LB↓
- 日线：22日内出现过 UB↑ & BOLL↑ & LB↓

### 二、MACD（金叉后 DIF 持续在 DEA 上方）
- 月线：12个月内出现 DIF 上穿 DEA，且此后 DIF 始终 ≥ DEA（零轴上下均可）
- 周线：26周内出现零轴上方 DIF 上穿 DEA，且此后 DIF 始终 ≥ DEA
- 日线：22日内出现 DIF 上穿 DEA，且此后 DIF 始终 ≥ DEA

### 三、OBV
- 月线 / 周线 / 日线：OBV > MA(OBV, 20)

### 四、DMA（仅月线 + 周线）
- DIF_DMA = MA(close, 10) − MA(close, 50)
- DIFMA = MA(DIF_DMA, 10)
- 条件：DIF_DMA > DIFMA

### 五、AMO 放量（三个条件同时满足）
- 52周内任意一周成交量 > 前一周 3 倍
- 26周内任意一周成交量 > 前一周 1.5 倍
- 22日内任意一日成交量 > 前一日 1.5 倍

### 六、KDJ（三线金叉：J 上穿 K 且 K 上穿 D）
- 月线：24个月内出现
- 周线：26周内出现
- 日线：22日内出现

## 自动运行

GitHub Actions 在每个交易日（周一至周五）北京时间 16:30 自动运行，结果发布到 GitHub Pages。

## 结果页面

[https://Jesse-J-whu.github.io/stock-picker-v3/](https://Jesse-J-whu.github.io/stock-picker-v3/)

## 免责声明

本项目仅为量化策略技术演示，不构成任何投资建议。股市有风险，投资需谨慎。
