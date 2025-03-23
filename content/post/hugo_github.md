---
title:       "hugo + github"
subtitle:    ""
description: ""
date:        2025-02-09
author:      "Yuchi"
image:       ""
tags:        ["github", "hugo"]
categories:  ["Tech"]
draft: false
---

1. baseURL 如果打錯會造成裡面的連結錯誤
   1. e.g. xxx.github.io 打成 xxx.io.github

2. 網站修改完upload流程
   1. terminal
      1. $: hugo
         1. 生成新的網頁到/public
   2. 在/my-hugo-site
      1. 把/public中的網頁拉出來到./
   3. git commit + push 拉出來的網頁