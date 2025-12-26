# 🎓 學生社團管理系統 Student Club Management System
## 📌 前言（Introduction）
 本專案旨在設計一套方便學生及社團幹部使用的 學生社團管理系統，透過數位化方式整合社團資訊、活動報名與成員管理，提升校園社團運作效率，並改善傳統紙本或分散管理所造成的不便。

## 🖥️ 系統概述（System Overview）
本系統為一套以 Web 為基礎的學生社團管理平台，主要使用對象包含：
- 一般學生（社團成員
- 社團幹部
- 系統管理員
使用者可透過系統進行：
- 查詢社團資訊
- 參與及報名社團活動
- 管理社團事務

系統採模組化設計，讓不同角色依權限使用不同功能，確保資料安全並提升系統維護性。

<img width="5200" height="3363" alt="功能需求分析-2025-12-22-034816" src="https://github.com/user-attachments/assets/d97e7e24-66c4-4c77-9a21-16bcf5e44bb6" />

## ⚙️ 功能需求分析（Functional Requirements）
### 👤 使用者功能
- 使用者註冊與登入
- 瀏覽社團列表與詳細資訊
- 申請加入社團
- 報名參加社團活動
- 查詢個人參與紀錄

### ⭐ 社團幹部功能
- 審核加入申請、管理成員
- 發布社團公告
- 建立與管理活動
- 查看活動報名名單

### 🔐 系統管理員功能
- 管理所有使用者
- 管理社團
- 進行權限設定與系統

### 🧩 系統設計（System Design）
本系統採用 前後端分離架構：
🔹 前端
HTML / CSS / JavaScript  
🔹 後端（擇一）
- Node.js
- PHP
- Python  
🔹 資料庫
MySQL 或 PostgreSQL
系統使用 RESTful API 進行資料交換，提升系統延展性與維護性。

<img width="358" height="699" alt="螢幕擷取畫面 2025-12-24 125423" src="https://github.com/user-attachments/assets/be3aa646-b1a7-4bba-a412-cf53e3ec35c6" />

## 🗃️ 資料庫設計（Database Design）

### 📍 Users（使用者）
| 欄位名稱     | 說明                 |
| -------- | ------------------ |
| user_id  | 使用者編號（Primary Key） |
| name     | 姓名                 |
| email    | 電子郵件（登入帳號）         |
| password | 密碼（加密儲存）           |
| role     | 角色（學生 / 幹部 / 管理員）  |

### 📍 Clubs（社團)
| 欄位名稱        | 說明                |
| ----------- | ----------------- |
| club_id     | 社團編號（Primary Key） |
| club_name   | 社團名稱              |
| description | 社團介紹與宗旨           |
| leader_id   | 幹部編號（對應 Users）    |

### 📍 Club_Members（社團成員）
| 欄位名稱      | 說明                |
| --------- | ----------------- |
| id        | 資料編號（Primary Key） |
| club_id   | 所屬社團編號（FK）        |
| user_id   | 成員編號（FK）          |
| join_date | 加入日期              |

### 📍 Activities（活動）
| 欄位名稱        | 說明                |
| ----------- | ----------------- |
| activity_id | 活動編號（Primary Key） |
| club_id     | 主辦社團編號（FK）        |
| title       | 活動名稱              |
| date        | 活動日期              |
| description | 活動內容說明            |

<img width="480" height="650" alt="螢幕擷取畫面 2025-12-24 125441" src="https://github.com/user-attachments/assets/8b294a66-585d-4a8f-900c-dbd839b7a4bd" />

## 🖌️ 介面設計（UI Mockup）
- 系統介面設計原則為:簡潔,直覺,易操作
- 主要頁面:登入/註冊頁,社團列表頁,社團詳細資訊頁,活動管理頁,個人資料頁
整體風格以校園科技感為設計方向。

## ⭐ 系統特色
- 集中管理社團與活動資訊
- 明確角色與權限分級
- 提升行政運作效率
- 支援多社團、多活動
- 系統架構可持續擴充

## 🔮 結論與未來擴充（Conclusion & Future Work）
本系統能有效改善校園社團管理流程，提升資訊透明度，並讓學生與幹部能更方便地進行社團運作。
### 未來可擴充功能:
- 支援行動裝置 App
- 活動 QR Code 簽到
- 即時通知與推播
- 串接學校帳號系統
