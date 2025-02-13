---
title:       "如何使用git 架站"
subtitle:    ""
description: ""
date:        2025-02-13
author:      "Yuchi"
image:       ""
tags:        ["tag1", "tag2"]
categories:  ["Tech" ]
draft: false
---
# 如何使用git 架站

使用 **GitHub** 來架設網站是一個方便又免費的選擇，特別適合個人作品集、部落格或專案文件。GitHub 提供 **GitHub Pages**，可以將儲存庫中的靜態網頁（如 HTML、CSS、JavaScript）直接部署成一個公開可訪問的網站。

**如何使用 GitHub 架設網站的步驟**



**方法 1：使用 GitHub Pages 部署靜態網站**

這種方法適合單純的靜態網站（HTML、CSS、JavaScript），適合新手使用。

**步驟 1：建立 GitHub 儲存庫**

1\. 登入 [GitHub](https://github.com)。

2\. 點擊「**New Repository**」建立一個新的儲存庫。

3\. 命名儲存庫，例如 my-website，選擇「Public」，並勾選「Add a README file」。

4\. 點擊「Create Repository」。

**步驟 2：上傳或建立網頁文件**

1\. 進入儲存庫，點擊「**Add file → Upload files**」，上傳你的 HTML、CSS、JavaScript 文件，或直接在線上編輯。

2\. 建立一個 index.html 作為網站的首頁，內容範例如下：

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My GitHub Website</title>
</head>
<body>
    <h1>歡迎來到我的 GitHub Pages 網站！</h1>
    <p>這是一個靜態網站示範。</p>
</body>
</html>
```

**步驟 3：啟用 GitHub Pages**

1\. 進入儲存庫，點擊右上角的「**Settings**」。

2\. 在左側選單中找到「**Pages**」選項。

3\. 在「Branch」下拉選單中選擇 main（或 master，依據你的預設分支）。

4\. 點擊「**Save**」，GitHub 會自動部署你的網站。

5\. 你將會看到一個自動產生的網址，例如：

```
https://你的GitHub使用者名稱.github.io/你的儲存庫名稱/
```

**步驟 4：更新網站內容**

• 每次對儲存庫進行推送（git push），GitHub Pages 都會自動更新網站內容。



**方法 2：使用 Jekyll 或 Hugo 建立靜態網站**

如果你想要建立部落格或需要更複雜的網站，GitHub Pages 支援 **Jekyll**（一個靜態網站生成器）。

**快速上手 Jekyll 網站**

1\. 安裝 Ruby 和 Jekyll：

```
gem install jekyll bundler
jekyll new my-blog
cd my-blog
bundle exec jekyll serve
```



2\. 建立網站內容後，將檔案上傳至 GitHub 儲存庫並啟用 GitHub Pages。

3\. 你也可以選擇使用 **Hugo** 或其他靜態網站生成器。



**方法 3：透過 GitHub + CI/CD 部署動態網站**

如果你的網站需要更進階功能（例如後端 API、資料庫），可以使用 **GitHub Actions** 搭配雲端服務（如 Netlify、Vercel）進行 CI/CD 自動部署。

**示範使用 Vercel 自動部署**

1\. 在 [Vercel](https://vercel.com/) 註冊並連接你的 GitHub 儲存庫。

2\. 每當你更新程式碼並推送到 GitHub，Vercel 會自動重新部署你的網站。

**GitHub Pages 的優缺點**

| **優點** | **缺點** | 
|---|---|
| 免費且無廣告 | 只支援靜態網站 | 
| 簡單易用，適合初學者 | 需要綁定網域手動設定 | 
| 可搭配 Jekyll 使用 | 不能直接執行伺服器端程式碼（如 PHP） | 

**額外進階技巧**

1\. **綁定自訂網域：**

在 Settings > Pages 中設定自訂網域，例如 [www.mywebsite.com](www.mywebsite.com)，並在網域服務商設定 DNS 記錄。

2\. **使用 HTTPS 安全加密：**

GitHub Pages 提供免費的 SSL 憑證，保證你的網站透過 https:// 安全存取。

3\. **版本控制與回溯：**

使用 GitHub 的版本控制功能，追蹤網站的變化，必要時回滾至舊版。

如果你有具體的網站需求或想要深入學習，可以告訴我你的目標，我可以幫你選擇最適合的方法！



---

使用 **Hugo** 搭配 **GitHub Pages** 來架設網站是一個高效、免費且靜態的網站解決方案。Hugo 是一個輕量且快速的靜態網站生成器，適合建立部落格、個人網站或文件網站。

**使用 Hugo + GitHub Pages 架站流程**



**步驟 1：安裝 Hugo**



在開始之前，首先需要安裝 Hugo。根據你的作業系統選擇安裝方法：



**Windows：**

1\. 下載 Hugo 安裝程式：[Hugo Releases](https://github.com/gohugoio/hugo/releases)

2\. 解壓後將 hugo.exe 加入系統環境變數。



**macOS：**

```
brew install hugo
```

**Linux：**

```
sudo apt install hugo
```

安裝完成後，驗證安裝：

```
hugo version
```

如果成功，應該會顯示 Hugo 的版本資訊。

**步驟 2：建立新的 Hugo 網站**



開啟終端機（Terminal/Command Prompt），執行以下指令來建立新網站：

```
hugo new site my-hugo-site
cd my-hugo-site
```

這會在本地建立一個基本的 Hugo 網站架構。

**步驟 3：選擇與下載 Hugo 佈景主題**



Hugo 提供多種免費佈景主題，瀏覽 [Hugo Themes](https://themes.gohugo.io/) 選擇一個適合的主題，然後下載到你的專案目錄。



例如，使用 ananke 佈景主題：

```
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
```

在網站的設定檔 config.toml 中啟用主題：

```
theme = "ananke"
baseURL = "https://你的GitHub使用者名稱.github.io/"
title = "My Hugo Website"
languageCode = "en-us"
```

**步驟 4：新增網站內容**



使用以下指令新增文章或頁面：

```
hugo new posts/my-first-post.md
```

進入 content/posts/ 資料夾，編輯 Markdown 文件，例如：

```
---
title: "我的第一篇文章"
date: 2025-01-24
draft: false
---

這是我的第一篇 Hugo 部落格文章，歡迎光臨！
```

**重要提醒：** 將 draft: false 改為 false，否則 Hugo 不會發佈該文章。

**步驟 5：本地測試網站**



在開發過程中，可以在本機測試網站：

```
hugo server -D
```

打開瀏覽器，訪問 <http://localhost:1313> 查看你的網站。

**步驟 6：建置網站**



當你滿意你的內容後，可以使用 Hugo 將網站轉換為靜態 HTML：

```
hugo
```

Hugo 會在 public/ 資料夾中生成靜態網站檔案。

**步驟 7：推送至 GitHub Pages**

1\. 前往 [GitHub](https://github.com)，建立一個新的儲存庫，例如 my-hugo-site。

2\. 在終端機執行以下指令將網站推送到 GitHub：

```
# 進入 Hugo 生成的 public 目錄
cd public

# 初始化 Git 儲存庫
git init
git remote add origin https://github.com/你的GitHub使用者名稱/my-hugo-site.git

# 提交變更
git add .
git commit -m "Initial commit"

# 推送至 GitHub
git branch -M main
git push -u origin main
```

**步驟 8：設定 GitHub Pages**

1\. 進入你的 GitHub 儲存庫，點擊「**Settings > Pages**」。

2\. 在「Branch」選擇 main，資料夾選擇 / (root)，然後按下「Save」。

3\. GitHub 會提供一個網址，例如：

```
https://你的GitHub使用者名稱.github.io/my-hugo-site/
```

**步驟 9：設定 GitHub Actions（自動部署）**



如果你希望自動部署網站（當你修改內容並推送時），可以使用 GitHub Actions 自動化流程。

1\. 在 GitHub 儲存庫中建立 .github/workflows/gh-pages.yml 檔案，並加入以下內容：

```
name: Deploy Hugo site to GitHub Pages

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v2

      - name: Install Hugo
        uses: peaceiris/actions-hugo@v2
        with:
          hugo-version: 'latest'

      - name: Build site
        run: hugo --minify

      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./public
```

2\. 提交這個檔案後，GitHub Actions 會自動執行，並將網站部署到 GitHub Pages。

**步驟 10：設定自訂網域（可選）**



如果你有自己的網域名稱，可以在 GitHub Pages 設定：

1\. 前往 Settings > Pages，在「Custom domain」輸入你的網域，例如 [www.mydomain.com](www.mydomain.com)。

2\. 到你的網域註冊商（如 GoDaddy、Cloudflare），新增 CNAME 記錄指向 [你的GitHub使用者名稱.github.io](你的GitHub使用者名稱.github.io)。

**常見問題解決**

1\. **網站不顯示變更？**

• 檢查 Hugo 文章是否標記為 draft: false。

• 清除瀏覽器快取。

2\. **GitHub Pages 無法找到網站？**

• 確保 GitHub Pages 設定正確，並使用 <https://你的GitHub使用者名稱.github.io/你的儲存庫名稱/> 瀏覽。

3\. **佈景主題未正確載入？**

• 檢查 config.toml 是否正確引用佈景主題，並將佈景主題加入版本控制：

```
git submodule add <theme-url> themes/<theme-name>
```

**總結**

1\. 安裝 Hugo 並建立網站架構。

2\. 選擇佈景主題並新增內容。

3\. 本機測試網站，然後使用 Hugo 生成靜態頁面。

4\. 推送網站到 GitHub 儲存庫並啟用 GitHub Pages。

5\. 設定 GitHub Actions 自動部署（可選）。

6\. 綁定自訂網域（可選）。

希望這個流程對你有幫助！如果你有進一步的問題，請隨時提問。