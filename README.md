# 作業說明（README）

> 本作業以**預測電信客戶流失 (Customer Churn Prediction)**為主題。請從 `sample_code.ipynb` 起步，熟悉資料與評估流程，依規則完成 baseline 與模型改進，並撰寫報告。

---

## 1) 作業介紹

- **任務**：利用客戶的個人資料、合約資訊與服務使用狀況，預測該客戶是否會流失 **Churn**（二元分類問題）。
- **評估指標**：**ROC-AUC Score**。AUC 越接近 1 代表模型效果越好。所有分數均以評測平台的結果為準。
- **實作重點**
  1. 讀取並理解資料；處理髒資料（如 `TotalCharges` 中的空白字串）
  2. 進行特徵工程（如 K-Means 分群特徵）與解決資料不平衡（Imbalanced）問題
  3. 建立並訓練分類模型（如 XGBoost），產出正確格式的提交檔
  Kaggle網址：https://www.kaggle.com/t/1c9b5182f97f499387eb559797215bc0
- **起始範例**：`sample_code.ipynb` 提供最小可行流程。你需要在此基礎上自行改進。

## 2) 資料集與特徵

資料集包含客戶個人屬性、合約資訊以及最終的流失標籤。
  ```
  data/
    ├─ train.csv      # 訓練資料（含 Churn ）
    └─ test.csv       # 測試資料（不含 Churn ）
  sample_code.ipynb
  ```

| 欄位 | 說明 |
| :--- | :--- |
| **Contract** | 合約類型 (Month-to-month, One year...) |
| **InternetService** | 網路服務類型 (DSL, Fiber optic...)
| **tenure** | 入網月數 |
| **MonthlyCharges** | 每月費用 |
| **TotalCharges** | 總費用 (注意：原始資料含有空白字串，需處理) |
| **Churn** | **[預測目標]** 客戶是否流失 |
| ...(其他個人屬性)... | |

## 3) 評分規則（總分 12 分）

1. **Simple Baseline（3 分）**  
   - 可以嘗試處理髒資料 (TotalCharges)並嘗試特徵工程 (如 K-Means) 。

2. **Medium Baseline（3 分）**  
   - 可以嘗試解決「資料不平衡」的問題，並嘗試更強的模型 (如 XGBoost)。

3. **報告（6 分）**  
  - 第一部分：準確度分數 (Accuracy Scores) (1分)  
  - 第二部分：我的實驗記錄 (My Experiment Log) (3分)  
  - 第三部分：總結與心得 (Conclusion & Reflection) (2分)  
  （請參考`sample_code.ipynb`的報告部分）