# Virtual Community Interaction & Knowledge Co-construction — Research Data and Code

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX)

本儲存庫存放賴鈺昀（2026）碩士論文《以社會網路和認知網路分析虛擬社群互動與知識共構之研究》之研究資料、編碼結果與分析程式碼，作為論文附錄之一部分，供後續研究者參考與檢驗。

> This repository contains the de-identified research data, coding results, and analysis scripts for the master's thesis *"A Study on the Relationship between Virtual Community Interaction and Knowledge Co-construction Using Social Network Analysis and Epistemic Network Analysis"* by Yu-Yun Lai (2026).

---

## 📖 論文資訊 / Thesis Information

| 項目 | 內容 |
|---|---|
| **論文題目** | 以社會網路和認知網路分析虛擬社群互動與知識共構之研究 |
| **English Title** | A Study on the Relationship between Virtual Community Interaction and Knowledge Co-construction Using Social Network Analysis and Epistemic Network Analysis |
| **作者 / Author** | 賴鈺昀（Yu-Yun Lai） |
| **指導教授 / Advisor** | 廖慶榮 教授 |
| **學校 / Institution** | 中原大學資訊管理學系 / Chung Yuan Christian University, Department of Information Management |
| **學位 / Degree** | 碩士學位論文 / Master's Thesis |
| **完成日期 / Date** | 2026 年 6 月 / June 2026 |

---

## 🎯 研究概要 / Research Overview

本研究結合**社會網路分析（Social Network Analysis, SNA）**與**認知網路分析（Epistemic Network Analysis, ENA）**，以一個 Discord 遊戲公會為研究場域，探討虛擬社群成員之互動參與行為如何影響其在社群結構中的位置，以及其於知識共構歷程中所展現的語意參與特徵。

### 研究問題

- **H1**：互動頻率較高的參與者，是否更容易成為社群中的核心節點？
- **H2**：參與討論主題較多元的使用者，是否在討論內容中形成較廣泛的概念連結？

### 主要發現

- H1 與 H2 均獲得實證支持
- 整合分析揭示「互動結構」與「知識共構結構」之間具有高度共變對應
- 核心成員與邊緣成員之知識共構結構存在質性差異（非僅量之差異）

---

## 📂 儲存庫結構 / Repository Structure

```
.
├── README.md                          # 本說明檔
├── LICENSE                            # 授權條款（CC BY 4.0）
├── CITATION.cff                       # 引用格式
├── ETHICS.md                          # 研究倫理聲明
│
├── data/                              # 去識別化研究資料
│   ├── 01_raw_anonymized/             # 原始對話資料（已去識別化）
│   │   └── discord_messages_anon.csv
│   ├── 02_coded/                      # K1-K8 編碼結果
│   │   ├── coding_results.csv
│   │   └── coding_scheme.md
│   └── 03_processed/                  # 分析所需之處理後資料
│       ├── interaction_matrix_22x22.csv
│       ├── sna_centrality_results.csv
│       └── ena_metrics.csv
│
├── scripts/                           # 分析程式碼
│   ├── 01_preprocessing/              # 資料前處理
│   │   ├── anonymization.py
│   │   └── data_filtering.py
│   ├── 02_sna_analysis/               # SNA 分析
│   │   ├── build_interaction_matrix.py
│   │   └── centrality_calculation.md  # Gephi 操作說明
│   ├── 03_ena_analysis/               # ENA 分析
│   │   ├── ena_webtool_input.csv
│   │   └── ena_analysis_steps.md      # ENA Webtool 操作說明
│   └── 04_correlation_analysis/       # SNA × ENA 整合分析
│       └── spearman_correlation.xlsx
│
├── figures/                           # 論文圖表原始檔
│   ├── figure_10_sna_network.svg
│   ├── figure_12_ena_space.png
│   └── ...
│
└── docs/                              # 補充文件
    ├── coding_protocol.md             # 編碼操作型定義
    ├── reliability_checks.md          # 編碼信度檢驗詳細結果
    └── changelog.md                   # 版本變更紀錄
```

> ⚠️ 實際檔名與結構可依你的最終整理結果調整，建議保持「資料、程式、文件」三層架構。

---

## 🔧 使用方法 / How to Use

### 環境需求 / Requirements

```
Python >= 3.9
pandas >= 1.5
numpy >= 1.23
scipy >= 1.10
openpyxl >= 3.1
```

外部分析工具：
- **Gephi 0.11**（SNA 中心性計算與視覺化）
- **ENA Webtool**（https://www.epistemicnetwork.org/）

### 重現分析步驟 / Reproducing the Analysis

```bash
# 1. 安裝套件
pip install -r requirements.txt

# 2. 資料前處理（如使用原始資料）
python scripts/01_preprocessing/data_filtering.py

# 3. 建構互動矩陣
python scripts/02_sna_analysis/build_interaction_matrix.py

# 4. SNA 中心性計算 → 匯入 Gephi（詳見 02_sna_analysis/centrality_calculation.md）

# 5. ENA 分析 → 上傳至 ENA Webtool（詳見 03_ena_analysis/ena_analysis_steps.md）

# 6. SNA × ENA 整合相關分析
# 直接開啟 scripts/04_correlation_analysis/spearman_correlation.xlsx
```

---

## 📊 資料說明 / Data Description

### 資料來源

本研究資料蒐集自一個 Discord 遊戲公會於 **2026 年 1 月**之文字對話紀錄。經研究倫理規範之知情同意程序後取得，並經系統性去識別化處理。

### 樣本規模

| 項目 | 數量 |
|---|---|
| 參與成員 | 22 位（含研究者本人 R1）|
| 蒐集期間 | 1 個月 |
| 對話總數（篩選後） | 4,603 筆 |

### 編碼架構（K1-K8）

| 代碼 | 類別 | 中文 |
|---|---|---|
| K1 | Knowledge Request | 知識請求 |
| K2 | Knowledge Provision | 知識提供 |
| K3 | Collaborative Action | 協作行動 |
| K4 | Experience Sharing | 經驗分享 |
| K5 | Knowledge Negotiation | 知識修正／協商 |
| K6 | Emotional Response | 情感反應 |
| K7 | Social Maintenance | 社交維繫 |
| K8 | Playful Interaction | 玩笑互動 |

詳細操作型定義請參見 [`docs/coding_protocol.md`](docs/coding_protocol.md)。

---

## 🔒 研究倫理 / Research Ethics

本研究嚴格遵守學術倫理規範：

1. **知情同意**：所有參與者於資料蒐集前均已知悉研究目的、流程與資料使用方式，並簽署同意書
2. **去識別化處理**：
   - 所有成員以代號 P1–P21、R1 表示
   - 對話內容中之第三方姓名、Discord 帳號、遊戲角色名等個人識別資訊均已替換或移除
   - 伺服器名稱與公會名稱未於本資料集中揭露
3. **資料用途限制**：本資料集僅供學術研究用途，不得用於商業或其他非學術目的
4. **研究者雙重身份**：研究者本人為該公會長期成員，於論文 4.4.4 節已對此雙重身份進行反身性檢視

完整倫理聲明請見 [`ETHICS.md`](ETHICS.md)。

---

## 📝 引用方式 / How to Cite

如果您於學術工作中使用本研究之資料或程式碼，請依下列格式引用：

### APA 7th 格式

```
賴鈺昀（2026）。以社會網路和認知網路分析虛擬社群互動與知識共構之研究
〔未出版之碩士論文〕。中原大學資訊管理學系。

Lai, Y.-Y. (2026). A Study on the Relationship between Virtual Community
Interaction and Knowledge Co-construction Using Social Network Analysis
and Epistemic Network Analysis [Unpublished master's thesis].
Chung Yuan Christian University.
```

### Dataset 引用（Zenodo DOI）

```
Lai, Y.-Y. (2026). Virtual Community Interaction & Knowledge Co-construction
— Research Data and Code (v1.0) [Data set]. Zenodo.
https://doi.org/10.5281/zenodo.XXXXXXX
```

### BibTeX

```bibtex
@mastersthesis{lai2026virtual,
  title  = {A Study on the Relationship between Virtual Community Interaction
            and Knowledge Co-construction Using Social Network Analysis
            and Epistemic Network Analysis},
  author = {Lai, Yu-Yun},
  year   = {2026},
  school = {Chung Yuan Christian University},
  type   = {Master's thesis}
}

@dataset{lai2026dataset,
  title     = {Virtual Community Interaction \& Knowledge Co-construction
               — Research Data and Code},
  author    = {Lai, Yu-Yun},
  year      = {2026},
  publisher = {Zenodo},
  version   = {v1.0},
  doi       = {10.5281/zenodo.XXXXXXX}
}
```

---

## 📄 授權 / License

本儲存庫採用 **MIT License** 授權釋出。引用本研究資料時請依下方「引用方式」段落之格式註明出處。 

您可以自由地：
- **使用**：在個人、學術或商業用途中使用本素材
- **修改**：重混、轉換本素材，及依本素材建立新作品
- **散布**：以任何媒介或格式重製及散布本素材

惟須遵守下列條件：
- **保留授權聲明**：散布本素材或衍生作品時，須保留 MIT License 條款及原始版權聲明
- **學術引用**：若於學術研究中使用本資料或程式碼，請依下方「引用方式」段落正確引用

完整授權條款請見 [LICENSE](LICENSE) 或 https://opensource.org/licenses/MIT

---

## 📬 聯絡資訊 / Contact

如對本研究有任何疑問或希望進一步合作，歡迎透過下列方式聯繫：

- **GitHub Issues**：[此 repo 之 Issues 頁面]
- **Email**：[unknown20020504@gmail.com]

> 💡 *請使用個人長期信箱，避免使用學校信箱（畢業後可能停用）*

---

## 🔖 版本紀錄 / Changelog

| 版本 | 日期 | 說明 |
|---|---|---|
| v1.0 | 2026-06-XX | 論文口試提交版本（凍結版本） |
| v1.1 | 2026-XX-XX | 口試後修正版本（如有）|

完整變更紀錄請見 [`docs/changelog.md`](docs/changelog.md)。

---

## 🙏 致謝 / Acknowledgments

感謝該 Discord 遊戲公會所有參與本研究之成員，謝謝你們願意以資料貢獻於本研究之進行。

亦感謝指導教授 廖慶榮 教授於研究過程中之指導與啟發。

---

*Last updated: 2026-XX-XX*
