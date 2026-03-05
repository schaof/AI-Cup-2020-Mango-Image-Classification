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
AI-Cup-2020-Mango-Image-Classification/
├── competition-guidelines/       # 競賽官方說明文件
├── data/                         
│   ├── sample-images/            # 原始芒果影像樣本，包含 A, B, C 三個等級
│   │   ├── sample_A.jpg          
│   │   ├── sample_B.jpg          
│   │   └── sample_C.jpg          
│   └── processed/                # 經裁剪與去模糊處理之影像樣本
│       ├── sample_A_processed.jpg 
│       ├── sample_B_processed.jpg 
│       └── sample_C_processed.jpg 
├── scripts/
│   ├── crop.ipynb             # 影像裁剪程式碼
│   ├── deblur.ipynb           # 使用 SRN-Deblur 
│   └── mango_training.ipynb   # 主程式碼
├── reports/                      
│   └── report.pdf             # 專案技術報告
└── README.md
```
