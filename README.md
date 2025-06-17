# Getting started with the Elastic Stack and Docker-Compose

This repo is in reference to the blog [Getting started with the Elastic Stack and Docker-Compose](https://www.elastic.co/blog/getting-started-with-the-elastic-stack-and-docker-compose).

Please feel free to ask any questions via issues [here](https://github.com/elkninja/elastic-stack-docker-part-one/issues), our [Community Slack](https://ela.st/slack), or over in our [Discuss Forums](https://discuss.elastic.co/).

Pull Requests welcome :)

---

## 專案簡介

本專案整合了額外的 service：**versus-incident**  
> [versus-incident container](https://github.com/versuscontrol/versus-incident/pkgs/container/versus-incident)

透過整合，Kibana 可於 Stack Management → Connectors 中建立 Webhook 連接器，  
進而將告警 (Alert) 透過 Telegram Bot 發送通知。

範例畫面：

![Connector Configuration](https://github.com/user-attachments/assets/a03f9f79-d313-4e79-b94d-8f44995e91a9)
<img width="1480" alt="截圖 2025-06-17 14 59 54" src="https://github.com/user-attachments/assets/940ab8ee-d48e-414a-a55a-0b2745fe537e" />
![Alert Result](https://github.com/user-attachments/assets/519cfb81-4310-47d2-a498-fed72d66b996)

---

## 服務說明

| Service | 說明 |
|---|---|
| **setup** | 初始化 Elastic Stack 環境 |
| **es01** | Elasticsearch Service |
| **kibana** | Kibana Service |
| **logstash01** | Logstash (負責 log 加工與輸送至 ES) |
| **versus-incident** | 統一接收 Webhook，負責將告警訊息轉發至 Telegram Bot  |

> 詳細 `versus-incident` 配置說明可參考官方文件：  
> https://github.com/versuscontrol/versus-incident/pkgs/container/versus-incident

---

## ⚠ 初次使用注意事項

請務必修改 `.env` 檔案內以下兩個變數：

| 變數 | 說明 |
|---|---|
| `TG_TK` | Telegram Bot Token |
| `TG_CI` | Telegram Chat ID |

設定正確後，即可透過 Kibana Alert 將告警推送至 Telegram。

---

Pull Request 與 Issue 回報非常歡迎 🙌
