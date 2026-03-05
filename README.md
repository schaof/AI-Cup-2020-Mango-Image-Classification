# AI-Cup-2020-Mango-Image-Classification
深度學習｜🥭 AI Cup 2020：愛文芒果影像辨識——等級分類(Mango image recognition for grade classification)

## ⚙️ Workflow Architecture
```mermaid
graph LR
        A["Raw Microclimate Data"]
        B["Solar Radiation Data (External Data from Central Weather Administration)"]
        A --> C["Data Preprocessing"]
        B --> C
        C --> D["Feature Engineering"]
        D --> E["Model Training and Hyperparameter Tuning"]
        E --> F["Solar Power Prediction"]
        F --> G["Final Submission CSV Generation"]

%% 視覺設定：定義企業級深色主題 (深色背景 + 白字避免無法閱讀)
        classDef premiumBlue fill:#2C356A,stroke:#1F264A,stroke-width:2px,color:#ffffff
        classDef premiumGreen fill:#2D5C4A,stroke:#1F4234,stroke-width:2px,color:#ffffff

        %% 套用配色：主流程使用藍色，最終產出使用綠色
        class C,D,E,F premiumBlue
        class A,B,G premiumGreen
```

## 📂 Repository Structure
```text
AI-Cup-2024-Power-Prediction/
├── competition-guidelines/       # 競賽官方說明文件與範例程式
├── sample-data/
│   ├── L1_Train.csv              # 測站一之微氣候訓練數據（共 17 個觀測站）
│   └── 2024-01全天空日射量.csv     # 一月份全天空日射量（外部資料來自中央氣象署，含 1-10 月）
├── scripts/
│   └── power_prediction.ipynb    # 程式碼：涵蓋探索式資料分析、資料前處理、訓練與生成預測結果
├── reports/                      
│   ├── report_slides.pdf         # 專案簡報
│   └── report.pdf                # 專案完整技術報告
├── checkpoints/                  # 存放訓練完成之模型權重
├── submission-prediction-csvs/   # 最終上傳至 AI CUP 系統之預測 csv 檔
└── README.md
```
