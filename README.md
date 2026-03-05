# AI-Cup-2020-Mango-Image-Classification
深度學習｜🥭 AI Cup 2020：愛文芒果影像辨識——等級分類(Mango image recognition for grade classification)

## ⚙️ Workflow Architecture
```mermaid
graph LR
    A["Raw Mango Images"] --> B["Image Cropping (crop.ipynb)"]
    B --> C["Image Deblurring (deblur.ipynb)"]
    
    subgraph Training_Phase["Model Training & Optimization"]
        C --> D["Feature Extraction (Backbones)"]
        D --> E["ResNet50 / DenseNet201"]
        D --> F["ResNeSt26d / SeresNext26d"]
        E --> G["Mish Activation & Ranger Optimizer"]
        F --> G
        G --> H["FP16 Mixed Precision Training"]
    end

    subgraph Inference_Phase["Inference & Ensemble"]
        H --> I["Test Time Augmentation (TTA)"]
        I --> J["Majority Voting (Ensemble)"]
    end
    
    J --> K(["Final Classification Result"])

    %% 視覺設定：定義企業級深色主題
    classDef premiumBlue fill:#2C356A,stroke:#1F264A,stroke-width:2px,color:#ffffff
    classDef premiumGreen fill:#2D5C4A,stroke:#1F4234,stroke-width:2px,color:#ffffff

    %% 套用配色
    class B,C,D,E,F,G,H,I,J premiumBlue
    class A,K premiumGreen
```

## 📂 Repository Structure
```text
AI-Cup-2020-Mango-Image-Classification/
├── competition-guidelines/        # 競賽官方說明文件
├── data/                          
│   ├── sample-images/             # 原始芒果影像樣本，包含 A, B, C 三個等級
│   │   ├── sample_A.jpg           
│   │   ├── sample_B.jpg           
│   │   └── sample_C.jpg           
│   └── processed/                 # 經裁剪與去模糊處理之影像樣本
│       ├── sample_A_processed.jpg 
│       ├── sample_B_processed.jpg 
│       └── sample_C_processed.jpg 
├── scripts/
│   ├── crop.ipynb                 # 影像裁剪程式碼
│   ├── deblur.ipynb               # 影像去模糊處理程式碼
│   └── mango.ipynb                # 主程式碼
├── report.pdf                     # 專案技術報告
├── submission-prediction-csvs/    # 最終上傳至 AI CUP 系統之預測 csv 檔     
└── README.md
```
