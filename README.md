# 🎓 學生社團管理系統 (Student Club Management System)

## 📑 一、 需求說明書 (Requirements Specification)

### 1.1 系統目標
旨在解決校園社團行政作業繁瑣問題，透過數位化平台整合「社團資訊」、「活動報名」與「成員管理」，提升行政效率與資訊透明度。

### 1.2 系統角色與功能
本系統定義了三種主要角色 (Actors)：

* **一般學生 (Student)**
    * 瀏覽與查詢各社團詳細資訊。
    * 申請加入社團。
    * 報名校園活動並查詢參與歷史紀錄。
* **社團幹部 (Officer)**
    * 審核入社申請、管理社團成員名單。
    * 發布與編輯社團公告。
    * 建立活動、設定報名限額、查看報名統計。
* **系統管理員 (Admin)**
    * 管理所有使用者帳號與權限。
    * 審核新社團成立與停辦。



---

## 🏗️ 二、 概要設計說明書 (High-Level Design)

### 2.1 系統架構
本專案採用 **MVC (Model-View-Controller)** 軟體設計模式，並實作前後端分離：
* **View (表現層)**：HTML, CSS, JavaScript (負責介面呈現)。
* **Controller (邏輯層)**：Node.js / PHP / Python (負責 RESTful API 邏輯與權限驗證)。
* **Model (資料層)**：MySQL / PostgreSQL (負責資料持久化儲存)。

### 2.2 系統架構圖
<img width="728" height="692" alt="螢幕擷取畫面 2025-12-29 100724" src="https://github.com/user-attachments/assets/e7c2c6a7-b42e-41ea-a451-ba5317c348b4" />


---

## 🛠️ 三、 詳細設計說明書 (Detailed Design)

### 3.1 資料庫實體關係圖 (ER-Diagram)
<img width="519" height="764" alt="螢幕擷取畫面 2025-12-29 100858" src="https://github.com/user-attachments/assets/9271f673-522b-47a1-9ed9-3c2732e08bfd" />


### 3.2 資料字典 (Data Dictionary)

#### **Table: Users (使用者)**
| 欄位名稱 | 資料型態 | 鍵值 | 說明 |
| :--- | :--- | :--- | :--- |
| `user_id` | INT | PK | 使用者唯一編號 |
| `name` | VARCHAR | - | 真實姓名 |
| `role` | ENUM | - | 角色: Student, Officer, Admin |
| `password`| VARCHAR | - | 雜湊加密後的密碼 |

#### **Table: Activities (活動)**
| 欄位名稱 | 資料型態 | 鍵值 | 說明 |
| :--- | :--- | :--- | :--- |
| `activity_id`| INT | PK | 活動編號 |
| `club_id` | INT | FK | 主辦社團編號 (Ref: Clubs) |
| `max_limit` | INT | - | 報名人數上限 |

### 3.3 關鍵流程邏輯 (Business Logic)
* **報名活動邏輯**：
    1. 系統檢查 `current_date` 是否在活動報名期間內。
    2. 檢查 `Activities.max_limit` 是否已達上限。
    3. 若檢查通過，於 `Registrations` 表新增紀錄。

---

## 🧪 四、 測試計畫 (Testing Plan)

### 4.1 測試範疇
* **單元測試 (Unit Test)**：驗證 API 路由（如 `POST /join_club`）是否正確接收參數。
* **整合測試 (Integration Test)**：模擬學生從註冊、搜尋社團到成功報名活動的完整流程。

### 4.2 測試案例 (Test Cases)
| ID | 測試場景 | 輸入數據 | 預期結果 |
| :--- | :--- | :--- | :--- |
| TC01 | 使用者登入 | 正確的 Email / 密碼 | 系統成功核發 JWT Token 並轉向首頁 |
| TC02 | 重複報名活動 | 已報名的 `user_id` | 系統攔截並顯示「您已報名此活動」 |
| TC03 | 幹部權限檢查 | 一般學生帳號點擊刪除公告 | 系統彈出「權限不足 (403)」 |

---

## 🔮 五、 結論與未來擴充
1.  **即時推播**：整合 Firebase Cloud Messaging (FCM) 提醒學生報名結果。
2.  **QR Code 簽到**：活動現場掃描自動更新出席狀態。
