# CLIA Cutoff 建立工具

雙點加權 Cutoff 計算器：`Cutoff = α × Cal1 + β × Cal2`

支援 **多試劑批 × 多儀器 × 多次校正**，跨情境搜尋較穩健的 α、β，並可從 Excel / CSV 匯入資料。

## 線上使用

GitHub Pages 啟用後：

https://aaronlin547.github.io/clia-cutoff-tool/

## 功能

- 雙點加權係數 α、β 與判陽門檻、灰區
- 可選羅氏風格背景校正 `(樣本 − k×Cal1) / Cutoff`
- 多校正情境（Lot / Instrument / CalId + Cal1 / Cal2）
- 檢體掛在對應情境下，即時算 S/CO、判讀與正確率
- 分情境績效：TP / TN / FP / FN、敏感度、特異度、Youden
- 跨情境網格搜尋最佳 α、β（穩健 / 總正確 / 平均 Youden）
- 下載空白 Excel 模板、匯入 xlsx/csv、匯出結果

## 本地開啟

直接用瀏覽器開啟 `index.html` 即可（Excel 匯入需可連線載入 SheetJS CDN）。

## Excel 模板欄位

| 欄位 | 說明 |
|------|------|
| Lot | 試劑批次 |
| Instrument | 儀器 |
| CalId | 校正編號 |
| Cal1 | 陰性校正液 RLU |
| Cal2 | 陽性校正液 RLU |
| SampleId | 檢體編號 |
| RLU | 檢體訊號 |
| Truth | `neg` / `pos` |

相同 `Lot + Instrument + CalId + Cal1 + Cal2` 會合併為同一校正情境。

## 注意

本工具僅供方法理解、內部試算與教學探索。正式產品係數仍需依設計控制與法規要求，以足夠的多批、多機、臨床樣本驗證後鎖定。

## License

MIT
