---
title:       "Docker 超入門介紹"
subtitle:    ""
description: ""
date:        2025-02-24
author:      Yuchi
image:       ""
tags:        ["docker"]
categories:  ["Tech"]
draft: false
---

## Docker情境介紹

想想今天我們在自己的Linux電腦上面開發了一個python寫的AI 程式，為了把這個python程式run起來，我們費盡心力弄好了環境，才讓它能順利的運作。在你終於能夠鬆一口氣後，主管跟你說，另一台電腦也想要用一樣AI程式，你會心想天啊，同樣的環境設定地獄又要再來一次！

這時候就要介紹Docker出場了，Docker 是一種**容器技術**，可以讓你的應用程式和其環境（包含程式碼、依賴、設定等）一起打包，確保它能夠在不同的平台上運行，而不受環境變化影響。

Docker就是我的環境設定超人！

介紹完Docker功用的背景，接著簡單介紹我目前學到的三個最基礎的必備名詞以及它們的關係。

這三個名詞分別是**Dockerfile**、**Image**和**Container**。

## **Dockerfile 是什麼？**

### **Dockerfile 是一個文字檔**，包含了一系列指令，告訴 Docker **如何構建一個 Image**。

### **Dockerfile 與 Image 的關係**

- Dockerfile 是 Image 的「食譜」

- Image 是根據 Dockerfile「烹飪」出來的結果

- Docker 會根據 Dockerfile 的指令，逐步創建一個 **Image**。

## Image 是什麼？

### 可以看作是程式的安裝檔案，安裝檔案裡面要裝什麼都已經定義好了是不能改變的，可以看成就是一個.exe檔或.dmg。

- Docker **Image** 是 **一個不可變的模版**，包含應用程式及其運行環境

   - 運行環境包含以下

      - 作業系統（Linux）

      - 應用程式（Python, Node.js, etc.）

      - 依賴（套件、函式庫）

      - 環境變數

- 它**不能直接運行**，但可以用來啟動**容器（Container）**。

## Container是什麼？

### 可以看成是正在運行的程式，程式內容就是照著Image內定義好的內容下去跑，就像是程序管理員中一個在跑的程序一樣。

- Docker **Container（容器）** 是 **從 Image 啟動的執行實例**，它包含了運行應用所需的一切環境。

- 你可以**創建、運行、停止、刪除**容器，但容器本身是可變的（可以寫入資料）。

- 你可以從同一個 Image 啟動多個 Container，就像你可以打開多個相同的應用程式視窗一樣。

## 小結

我們可以這樣看Dockerfile、Image與Container，如果以寫程式來比喻的話，Dockerfile就是我們的原始碼，Image就是編譯完變成一包的執行檔，Container就是電腦正在執行中的執行檔。
拉回到我們最初的目標就是希望我們寫的那個AI程式能夠跟著設定好的環境順利運作，這個部分就能與上面的例子對應就是把環境與程式都透過Dockerfile設定好，編譯成一個Image，最後我們只要運作一個裝著這個Image的Container就能成功跑起我們的AI程式了！