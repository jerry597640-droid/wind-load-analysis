# 臺灣建築物風力分析

線上：https://jerry597640-droid.github.io/wind-load-analysis/
整體分析：https://jerry597640-droid.github.io/wind-load-analysis/advanced.html

- 基本模組：普通矩形建物、開放式結構係數輸入、局部構材。
- 整體模組：規則矩形柱體的 G/Gf、順風／橫風／扭轉；三種用途的載重 CSV；同一結構效應組合、模型回填變位及加速度檢核。
- 施工設定：§6.2，回歸期最低 10 年，10/25/50 年風速比 .782/.908/1，分段年數線性內插。月數不直接折減，I 採 1 或依重要性採 1.1，不再疊加 0.9 折減。
- 不提供材料抗力及結構剛度求解；外部設計紀錄需與結構分析報告核對。非規則或超出公式適用範圍需專案／風洞分析。
- 介面內附逐欄說明、可照填範例、120 秒繁體字幕操作影片。
- 「下載離線版」包含影片及本次專案設定，開啟無須網路。各單檔為各自模組；完整離線 ZIP 提供兩個模組互相切換。

## 開發與驗證

`node assemble.cjs` 重建 index.html 及 advanced.html（所有程式與 DOCX 函式庫內嵌）。
`node full/test-engine.cjs` 比對規範表 2.18／2.19 共 1112 點及積分、施工折減、載重組合、加速度等，輸出 verification.json。

依據：https://www.nlma.gov.tw/ch/legislation/regsearch/166
版本：103.6.12，104.1.1 生效，含 103.12.3 §2.4／表 2.21 修正。
