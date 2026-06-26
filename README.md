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
| **English Title** | A Study on Virtual Community Interactions and Knowledge Co-construction Using Social
Network Analysis and Epistemic Network Analysis |
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
├──github-upload/
│
├── 📊 analysis/                              # 統計分析結果
│   ├── H2指標計算明細.xlsx                   # 各成員主題多元性與 K-K 配對數計算
│   ├── SNA與KK配對數之Spearman相關.xlsx      # 表格 8：SNA 中心性 × K-K 配對 相關分析
│   ├── SNA與主題多元性之Spearman相關.xlsx    # 表格 9：SNA 中心性 × 主題多元性 相關分析
│   ├── 論文SNA分析-Edges節點.xlsx            # SNA 邊（互動）資料
│   └── 論文SNA分析-Nodes節點.xlsx            # SNA 節點中心性指標（Gephi 輸出）
│
├── 📂 data/                                  # 去識別化研究資料
│   ├── 22x22矩陣(SNA).xlsx                   # 22 位成員互動矩陣 + 對話人工編碼
│   ├── K1-K8編碼(ENA).xlsx                   # ENA 用編碼資料（K1-K8 + 主/次要編碼）
│   └── SNA相關資料.xlsx                      # SNA 補充資料
│
├── 📄 docs/                                  # 補充文件
│   ├── consent_form_template.pdf             # 知情同意書空白範本
│   ├── ENA編碼準則.docx                      # K1-K8 操作型定義與編碼規則
│   └── SNA互動次數計算準則.docx              # SNA 互動矩陣建構規則
│
└── 🖼️ Pictures/                              # 論文圖表
    ├── SNA圖.png                             # 圖表 10：22 位成員 SNA 網路結構圖
    ├── 圖表8_K1-K8編碼類別分布.png           # K1-K8 編碼類別分布
    ├── 圖表9_各成員發言次數分布.png          # 22 位成員發言次數
    ├── 圖表11.png                            # 發言次數與度中心性散布圖
    ├── 圖12原圖.png                          # 圖表 12：ENA 二維空間分布
    ├── comparison.png                        # 三類成員 ENA 對照圖
    ├── comparison(標註版-有SVD).jpg          # 含 SVD 軸標註版本
    ├── P15.png / P4.png / P5.png / P10.png   # 圖表 14-17：代表性成員 ENA 個別網路
    ├── P18.png / P18放大.png                 # P18 個別 ENA 網路
    ├── R1.png                                # 圖表 18：R1 個案 ENA 網路
    └── P4 SNA.png                            # 補充：P4 SNA 局部圖

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

### 🔄 重現分析步驟 / Reproducing the Analysis

本研究之分析以 **Excel + Gephi + ENA Webtool** 完成，無需程式環境。  
請依下列步驟重現本研究結果：

#### 1️⃣ 取得原始資料
- 開啟 `data/K1-K8編碼(ENA).xlsx`：含 4,571 筆對話之 K1-K8 編碼結果
- 開啟 `data/22x22矩陣(SNA).xlsx`：22 位成員之互動矩陣

#### 2️⃣ SNA 中心性計算（使用 Gephi）
- 將 `analysis/論文SNA分析-Edges節點.xlsx` 與 `analysis/論文SNA分析-Nodes節點.xlsx` 匯入 Gephi
- 計算五項中心性指標：度中心性、加權度、中介中心性、接近中心性、特徵向量中心性
- 詳細操作流程：請參閱 `docs/SNA互動次數計算準則.docx`

#### 3️⃣ ENA 認知網路分析（使用 ENA Webtool）
- 前往 [ENA Webtool](https://www.epistemicnetwork.org/)
- 上傳 `data/K1-K8編碼(ENA).xlsx`
- 參數設定：Units = `user`、Conversations = `convo_id`、Stanza Window = 5
- 編碼準則詳見 `docs/ENA編碼準則.docx`

#### 4️⃣ SNA × ENA 整合相關分析
- 開啟 `analysis/H2指標計算明細.xlsx` 檢視各成員主題多元性與 K-K 配對數
- 開啟 `analysis/SNA與KK配對數之Spearman相關.xlsx`（H2 檢驗 — 表格 8）
- 開啟 `analysis/SNA與主題多元性之Spearman相關.xlsx`（H2 檢驗 — 表格 9）

#### 5️⃣ 圖表對照
所有論文圖表之原始檔皆存放於 `Pictures/` 資料夾，檔名對應論文章節編號。

---

> 💡 **無需安裝任何程式環境**：本研究所有分析均使用 Excel、Gephi（免費下載）  
> 與 ENA Webtool（線上工具）完成，僅需開啟對應檔案即可重現結果。

---

## 📊 資料說明 / Data Description

### 資料來源

本研究資料蒐集自一個 Discord 遊戲公會於 **2026 年 1 月**之文字對話紀錄。經研究倫理規範之知情同意程序後取得，並經系統性去識別化處理。

### 樣本規模

| 項目 | 數量 |
|---|---|
| 參與成員 | 22 位（含研究者本人 R1）|
| 蒐集期間 | 1 個月 |
| 對話總數（篩選後） | 4,571 筆 |

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

- **Email**：[unknown20020504@gmail.com]

---

## 🔖 版本紀錄 / Changelog

| 版本 | 日期 | 說明 |
|---|---|---|
| v1.0 | 2026-06-03 | 論文口試提交版本（凍結版本） |
| v1.1 | 2026-06-26 | 口試後修正版本|


---

## 🙏 致謝 / Acknowledgments

感謝該 Discord 遊戲公會所有參與本研究之成員，謝謝你們願意以資料貢獻於本研究之進行。

亦感謝指導教授 廖慶榮 教授於研究過程中之指導與啟發。

---

*Last updated: 2026-XX-XX*
