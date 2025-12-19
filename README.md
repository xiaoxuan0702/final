# 學生社團管理系統（Student Club Management System）

## 目錄
- 前言（Introduction）
- 系統概述（System Overview）
- 功能需求分析（Functional Requirements）
- 系統設計（System Design）
- 資料庫設計（Database Design）
- 介面設計（UI Mockup）
- 系統特色
- 結論與未來擴充

# 學生社團管理系統（Student Club Management System）

## 📌 專案簡介（Introduction）
隨著校園社團數量逐年增加，傳統以紙本或通訊軟體進行社團管理的方式，已無法有效應付成員管理、活動紀錄與資訊整合的需求。本專題旨在開發一套「學生社團管理系統」，透過 Web 平台協助社團幹部與成員進行更有效率的管理，提升社團運作的便利性與透明度。

---

## 🖥️ 系統概述（System Overview）
本系統為一套以 Web 為基礎的學生社團管理平台，主要使用對象包含：
- 一般學生（社團成員）
- 社團幹部
- 系統管理員  

使用者可透過系統瀏覽社團資訊、參與活動及管理社團事務。

---

## ⚙️ 功能需求分析（Functional Requirements）

### 使用者功能
- 使用者註冊與登入
- 瀏覽社團列表與社團詳細資訊
- 申請加入社團
- 報名社團活動
- 查詢個人參與紀錄

### 社團幹部功能
- 管理社團成員（審核加入、移除成員）
- 發布社團公告
- 建立與管理社團活動
- 查看活動報名名單

### 系統管理員功能
- 管理使用者帳號
- 管理社團資料
- 系統權限控管與維護

---

## 🧩 系統設計（System Design）
本系統採用前後端分離架構：
- **前端**：HTML、CSS、JavaScript
- **後端**：Node.js / PHP / Python（擇一）
- **資料庫**：MySQL / PostgreSQL  

系統透過 RESTful API 進行資料交換，確保系統具備良好的維護性與擴充性。

---

## 🗄️ 資料庫設計（Database Design）

### Users（使用者）
- user_id
- name
- email
- password
- role

### Clubs（社團）
- club_id
- club_name
- description
- leader_id

### Club_Members（社團成員）
- id
- club_id
- user_id
- join_date

### Activities（活動）
- activity_id
- club_id
- title
- date
- description

---

## 🎨 介面設計（UI Mockup）
系統介面設計以「簡潔、直覺、易操作」為原則，主要頁面包含：
- 登入 / 註冊頁面
- 社團列表頁
- 社團詳細頁
- 活動管理頁
- 個人資料頁  

整體風格以校園科技感為主，提升使用體驗。

---

## ⭐ 系統特色
- 集中管理社團與活動資訊
- 明確的角色與權限區分
- 提升社團行政管理效率
- 支援多社團與多活動管理
- 架構具備良好擴充性

---

## 🚀 結論與未來擴充（Conclusion & Future Work）
本學生社團管理系統能有效改善社團管理流程，使學生與社團幹部皆能更便利地進行資訊管理。  
未來可擴充功能包含：
- 行動裝置 App 支援
- 活動簽到系統
- 即時通知與推播
- 與學校帳號系統整合

---

## 👤 作者
- Yue Xuan Xiao

## 📄 授權
本專案僅供學術與學習用途。

