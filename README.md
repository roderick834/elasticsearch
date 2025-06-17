# Elastic Stack with Docker Compose + Telegram Alerts

[中文版本請往下滑 / For English version, please scroll up]

---

## 🇺🇸 English Version

### Introduction

This project extends the original [Getting started with the Elastic Stack and Docker-Compose](https://www.elastic.co/blog/getting-started-with-the-elastic-stack-and-docker-compose).

An additional service `versus-incident` is integrated:
- This allows Kibana to send alerts to a Telegram Bot via Webhook Connector.

Sample screenshots:

![Connector Configuration](https://github.com/user-attachments/assets/a03f9f79-d313-4e79-b94d-8f44995e91a9)
<img width="1480" alt="Screenshot" src="https://github.com/user-attachments/assets/940ab8ee-d48e-414a-a55a-0b2745fe537e" />
![Alert Result](https://github.com/user-attachments/assets/519cfb81-4310-47d2-a498-fed72d66b996)

### Services

| Service | Description |
|---|---|
| setup | Initialize Elastic Stack |
| es01 | Elasticsearch Service |
| kibana | Kibana Service |
| logstash01 | Logstash for processing and forwarding logs to ES |
| versus-incident | Centralized webhook receiver that forwards alerts to Telegram |

More about `versus-incident`:  
https://github.com/versuscontrol/versus-incident/pkgs/container/versus-incident

### Environment Configuration

Please update `.env` file before starting:

| Variable | Description |
|---|---|
| TG_TK | Telegram Bot Token |
| TG_CI | Telegram Chat ID |

Pull Requests and Issues are welcome 🙌

---

## 🇹🇼 中文版本

### 專案簡介

本專案基於 [Elastic 官方部落格範例](https://www.elastic.co/blog/getting-started-with-the-elastic-stack-and-docker-compose) 進行擴充，整合了 `versus-incident` 服務：

- 讓 Kibana 可以透過 Webhook Connector 發送告警到 Telegram Bot。

範例畫面：

![Connector Configuration](https://github.com/user-attachments/assets/a03f9f79-d313-4e79-b94d-8f44995e91a9)
<img width="1480" alt="截圖" src="https://github.com/user-attachments/assets/940ab8ee-d48e-414a-a55a-0b2745fe537e" />
![Alert Result](https://github.com/user-attachments/assets/519cfb81-4310-47d2-a498-fed72d66b996)

### 服務說明

| 服務 | 功能說明 |
|---|---|
| setup | Elastic Stack 初始化 |
| es01 | Elasticsearch 服務 |
| kibana | Kibana 服務 |
| logstash01 | 負責處理並轉發 log 到 ES |
| versus-incident | Webhook 統一接收，負責轉發告警至 Telegram |

`versus-incident` 詳細設定文件：  
https://github.com/versuscontrol/versus-incident/pkgs/container/versus-incident

### 環境變數設定

請在啟動前修改 `.env` 檔案：

| 變數 | 說明 |
|---|---|
| TG_TK | Telegram Bot Token |
| TG_CI | Telegram Chat ID |

歡迎 PR 或提問 Issue 🙌
