---
title: "[AI 求生日誌] About Artificial Intelligence"
slug: "about-artificial-intelligence"
date: 2022-12-11T18:59:42+08:00
draft: false
categories:
  - AI 求生日誌
tags:
  - Artificial Intelligence
  - Machine Learning
  - Deep Learning
---
> 1940 年電腦正式誕生之後，1950 年 Alan Turing 就發表論文 計算機與智能（Computing Machinery and Intelligence） 探討機器所能產生的智慧，並提出有名的 圖靈測試（Turing Test），人工智慧的發展可能比你我想像的都更早，且其歷史是更加的值得反思。
<!--more-->

> 在學習任何的領域，都應該先認識一下究竟這個東西是什麼跟其發展的歷史發生了什麼，因為唯有如此我們才能知道這個領域已經發生過什麼問題，而之後的發展跟研究可以避免什麼問題。

## What is Artificial Intelligence? / 什麼是人工智慧？
* 人工智慧（Artificial Intelligence, AI）其實是計算機科學（Computer Science）的一個分支，通常是指由「人」製造出來的機器所表現出來的「智慧」。
* 一般來說就是指電腦模擬人類思維過程以模仿人類能力或行為的能力，強調模擬人類智能。

## The History of Artificial Intelligence / 人工智慧的歷史
> 詳細時間線可以參考 [Introduction of Artificial Intelligence — Builtin](https://builtin.com/artificial-intelligence)，條列的非常的清楚。
> ![History of AI](https://blog.crazyfirelee.tw/images/history-of-ai.png)
* 自 1940 年電腦正式誕生以後，人類對於資訊處理和計算進入了全新的紀元，許多傳統密碼學中一直依賴的人工計算問題被大量的算力所突破，對人類的發展有了新的提升。
* 而到了 1950 年，Alan Turing 就已經設想了機器是否會發展出人類智能的問題，而發表了 Computing Machinery and Intelligence（計算機與智能）一論文，並發表了辨識人和機器的著名測試 Turing Test（圖靈測試），在這時人們其實就已經開始思考各種機器產生人類智慧的可能性和期待了。
* 而 1956 年，達特茅斯會議提出 Artificial Intelligence 一詞，並正式宣告人工智慧在計算機科學這個領域的發展。
* 從上述時間我們可以看到，自 1950 年 ~ 1974 年，是第一次 AI Algorithm 的發展盛期，期間**第一台神經網絡計算機 (1950 年)**、**機器學習 Machine Learning 一詞的出現 (1956 年)**、**第一台成功的專家系統 Expert System (1969 年)** 等等各種嘗試將人類導入機器的實驗跟發展一一出現。
* 但由於人們對人工智慧過度樂觀的預測跟實際電腦發展的軟硬體限制，人工「智慧」一直沒有顯現於機器中，於 1974 年 ~ 1980 年引發了這個研究領域的大量撤資，迎來了**第一次的 AI 寒冬**。
    > 此階段的 AI 發展仍然嘗試在電腦中放入**人類的知識**、**思考方式**，但由於人類其實也不是很確定人類是如何思考的（生物學跟行為學的發展尚未如現在成熟），因此很難正確的把人寫入電腦中，AI 也因此無法擁有**理解 ／決策能力**。
* 到了 1980 年 ~ 1987 年，軟/硬體有了新的突破，也允許了新的發展，如 **1980 年第一個成功的商業專家系統問世**，也開啟了專家系統的大量發展；到了 1982 年，**日本則開啟了第五代計算機系統計畫**，其目標是發展超級計算機 and 人工智能開發平台；到了 1985 年，Lisp 機器（專門的專家系統計算機）的發展巔峰，各公司平均每年投入超過 10 億美金在專家系統的維護上。
* 可惜的是在感覺又有好的發展前景的狀況之下，由於日本的超級計算機計畫失敗，Lisp 機器的市場崩盤等等，AI 發展於 1987 年 ~ 1993 年再次邁入寒冬，進入**第二次 AI 寒冬時期**。
    > 此階段的 AI 發展主要是利用大量人類定義好的規則做決策，卻忘記了人無法定義出一個問題的所有規則，因此只能一直解決**簡單 / 數據小**的問題。
* 又到了 2000 年，軟 / 硬體再次有了新的突破，AI 也再次有了新的進展。
* 2012 年，因**硬體的重大進展**跟 **Deep Learning** 的發展，Google 成功在沒有 Define 貓咪的狀況下，成功利用影片 Train 一個判斷貓咪的模型，也因此 AI 的發展重回了顛峰。
* 而 2016 年，AlphaGo 打敗了世界圍棋冠軍，正式宣告 AI 突破了新的領域，打敗了人類堅守的領域。
    > 此階段的 AI 發展已經理解到人們無法建構人到電腦中，也無法利用人發展出所有的規則，因此改變了 AI 的演算法，要求 AI 自己找到一個答案，而不是變成人類（或者說把人類寫進電腦）。

### 名詞解釋
* **機器學習 (Machine Learning)** - 機器利用給予問題跟結果，嘗試找出一個判斷這些問題的解題思路，並在往後的問題中給予答案的方法。
* **專家系統 (Expert System)** - 在特定領域內具有專家水平的解決問題能力的程式系統，其運作方式就是建構大量的 if aaa, then bbb, else ccc，可以說是一個**收集了大量專家知識的問答系統**。
    * 那究竟有沒有存在的意義？其實是有的，因為可以 **快速**、**大量** 的進行問題的 **分析** / **校正** / **回答**。
    * 但仍然存在很多問題，就是當然不可能回答沒有答案的問題（沒有統計過 or 紀錄過的）。
    * 但現在名詞上已經有些差異了，其實現在的 AI 應用都可以說是一種專家系統，因為會如專家一般在給予我們問題的答案，現在的 AI 會嘗試給予我們沒有面對過的問題一個他可能屬於的答案。

## Weak and Strong Artificial Intelligence / 弱跟強人工智慧
* 弱人工智慧 == 只執行一項特定工作的系統，也就是能解決一個特定任務，也稱為**狹義人工智慧 (ANI)**，是現在正在發展中的各種 AI 應用的種類，目前大多數的 AI 系統皆屬於這個類別，例如 **自駕車**、**自動調貨系統**、**語音助理**...
* 強人工智慧 == 能跟人一樣解決問題的人工智慧，是執行被認為類似於人類的任務的系統，能解決超過一種任務，也稱為**通用人工智慧 (AGI)**，是一種理想中跟人無差別的人工智慧。

## The Type of AI / 人工智慧的種類
* **Reactive Machines / 反應式機器**
    * 這些人工智慧系統沒有記憶並且是特定於任務的。這種 AI 很單純且目標明確，就是解決現在的問題，有名的例子是 IBM 的 DeepBlue 象棋 AI，他可以判斷當前的局面並選擇一個最好的走法來下棋，但是每一次的判斷都跟前一步驟沒有任何關係。
* **Limited memory / 有限記憶**
    * 這些人工智慧系統具有記憶力，因此它們可以利用過去的經驗來為未來的決策提供信息。記憶有限的 AI 能夠在收集信息和權衡潛在決策時存儲先前的數據和預測 — 本質上是回顧過去以尋找接下來可能發生的事情的線索。
    * 其必須遵循六個步驟：

        * 必須創建訓練數據
        * 必須創建 ML 模型
        * 模型必須能夠做出預測
        * 模型必須能夠接收人類或環境反饋
        * 反饋必須作為數據存儲
        
        並且這些步驟必須作為一個循環重複。
* **Theory of mind / 心智理論**
    * 心理理論是一個心理學術語。當應用於人工智慧時，這意味著該系統將具有理解情緒的社會智能。理論上這類型的 AI 我們還沒達到，因為其必須可以通過自我反思和決心來理解人類、動物和其他機器的感受並做出決定，然後利用這些信息做出自己的決定。
* **Self-awareness / 自我意識**
    * 在這一類中，人工智慧系統具有自我意識，這賦予了它們意識。

## Summary
* Artificial Intelligence 的發展涉及到硬體發展、軟體發展和人類對於期望是否明確這件事情，只有人類真的知道硬體的極限、軟體的對硬體調度的成熟度跟究竟「智慧」為何物，我們才能更好的推動發展。

## References

### Web Sites
* [Introduction of Artificial Intelligence - Builtin](https://builtin.com/artificial-intelligence)
* [Artificial intelligence - Britannica](https://www.britannica.com/technology/artificial-intelligence)
* [The History of Artificial Intelligence - Harvard University](https://sitn.hms.harvard.edu/flash/2017/history-artificial-intelligence/)
* [Expert System - 臺灣人工智慧行動網](https://ai.iias.sinica.edu.tw/glossary/expert-system/)
* [Expert System - Wiki](https://zh.wikipedia.org/zh-tw/%E4%B8%93%E5%AE%B6%E7%B3%BB%E7%BB%9F)
* [Expert System - MIT 智庫](https://wiki.mbalib.com/zh-tw/%E4%B8%93%E5%AE%B6%E7%B3%BB%E7%BB%9F)

### Book
* 圖解人工智慧 - 神崎洋治 - 碁峰出版
* 機器學習、人工智慧與人類未來 - 吳作樂、吳秉翰 - 五南出版
* 機器學習和深度學習的技術與原理 - 山口達輝、松田洋之 - 碁峰出版
* 從人到人工智慧，破解 AI 革命的 68 個核心概念 - 三宅陽一郎、森川幸人 - 臉譜出版

