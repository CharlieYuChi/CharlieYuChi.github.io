---
title:       "[LCS] Longest Common Subsequence演算法"
subtitle:    ""
description: ""
date:        2025-03-05
author:      "Yuchi"
image:       ""
tags:        ["algo."]
categories:  ["Tech"]
draft: false
---

# \[LCS\] Longest Common Subsequence演算法

給定兩個字串s1和s2，這個演算法可以幫助我們找到兩個字串的最長共同子序列。

如果我們想要判斷兩個字串的最長的共同子序列，可以按照這樣下去思考。

我們從s1和s2的最右端開始去思考

假設s1的長度為m，s2的長度為n

現在判斷s1\[m - 1\]和s2\[n - 1\]是否不一樣

如果一樣我們可以判定s1\[m - 1\]和s2\[n - 1\]屬於共同子序列的一員，這時候共同子序列總長度可以加一。

那如果不一樣，就要考慮三個情況：

第一個是把s1最後一個字去掉然後和s2去找最長共同子序列。

第二個是把s2最後一個字去掉然後去跟s1找最長共同子序列。

第三個是把s1最後一個字去掉和s2最後一個字去掉去找最長共同子序列。

不過其實只要考慮前兩個情況就好了，因為長度越長的字串越有可能出現越長的共同子序列。

所以現在已經處理完兩個字串的判斷邏輯了，最後就要來處理我們字串的判斷的終止條件是什麼？

停止的條件很簡單就是當其中一個字串已經是空的了，那當然就不會有共同子序列了，這時最長共同子序列的長度就是0。



以下是python的實作，@lru_cache是python中的快取機制，作用就像是memo一樣，只要我們call lcs時傳入的參數是一樣的就會直接回傳一樣的結果，可以用來節省時間。

```python
@lru_cache(maxsize=None)
def lcs(w1, w2, i, j):
    if i == 0 or j == 0:
        return 0

    if w1[i - 1] == w2[j - 1]:
        return lcs(w1, w2, i - 1, j - 1) + 1
    else:
        return max(lcs(w1, w2, i - 1, j), lcs(w1, w2, i, j - 1))
```