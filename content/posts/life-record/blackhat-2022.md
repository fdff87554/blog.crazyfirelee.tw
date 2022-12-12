---
title: "Blackhat 2022 線上遊記"
slug: "blackhat-2022"
date: 2022-12-12T11:31:28+08:00
draft: false
autoThumbnailImage: true
thumbnailImagePosition: "top"
metaAlignment: center
tags: ['Blackhat',
       'Security',
       'Conference']
---
> BlackHat，這個資安圈盛會，也一直是自己學習資安的路上一個嚮往和期待能參與的活動，但對於學生來說，費用相較昂貴而且參與成本較高，尤其是在疫情當頭的 2022 年，能參加更是一種奢侈...，但是！今年感謝 Orange Tsai 願意給我講者的學生推薦票，讓我有機會線上參與這場活動 (因為是役男不能隨便出國 QQ)，所以我就來紀錄一下這次的線上遊記吧！也希望藉由這個簡單的紀錄，讓更多人知道究竟 BlackHat 上會有什麼，跟我藉由這次參與兩天的議程，有什麼收穫跟感想。
<!--more-->

## 前言

* 在大四即將畢業的今年，剛好也是學習資安這條路上的第三年，其實對於未來也有些迷莽，由於自身也有接觸 AI 的相關領域，其實一直希望研究 AI + Security 這條路，但對於這條路上會需要的知識跟技能，還有發展方向都不是很清楚，也不確定世界是不是需要這樣的人，在台灣的很多 Conferences (HITCON、資安大會等等) 其實都有對應的議題議程，但對於正個世界而言，是不是真的有需要，還是只要好好學好資安在跨足把 AI 當工具就好，這些困擾一直在我心頭，也一直希望有機會聽聽看國際議程，更了解世界正在發生著什麼，跟需要怎樣的人。
* 這時剛好看到 Orange 大大願意讓大家爭取他的學生推薦票去參加 BlackHat 2022 USA，抱著試試看的心情填寫了問卷並且表達了自己對於相關議程的興趣之後，Orange 大大願意給我這個機會去看看 BlackHat 這個盛會正在討論著什麼，雖然因為各種原因只能線上參加，但能獲得這個機會實在很難得也很感謝，因此要特別感謝 Orange 大大願意給這個機會，因為這次聽完議程，有更加理解自己能做什麼跟 AI Security 究竟是什麼。
* 由於這次真的太多東西可以分享了，因此我大打算藉此機會寫一系列相關的文章，分別是內部的技術分析跟我自己的理解，因此這篇作為開場會 Summary 關於這次我聽的議程的一些大綱，然後會再 link 到我自己另外想討論的內容～
* 這邊挖了坑但是也要說聲抱歉，很多東西都還在學習中，因此可能會有一些錯誤的地方，如果有任何問題或是想討論的地方，歡迎在下方留言討論～

## 議程

### Day 01

#### [Keynote: Black Hat at 25: Where Do We Go from Here?](https://attend.blackhatevents.virtual.informatech.com/event/black-hat-usa-2022/planning/UGxhbm5pbmdfOTQ5NDUx)
> [time= Aug 10, 2022 09:00 to 10:00]
* Jeff Moss，Black Hat 的聯合創辦人為我們進行了精彩的開場，很榮幸今年是我第一次參加 Black Hat 卻剛剛好是 Black Hat 創辦的地 25 個年頭，Jeff 有特別說到 25 年是一個很重要的里程碑之一，1/4 個世紀以來整個環境有許多改變，很多事情正在慢慢明瞭中，但仍有許多未知的事物等著所有人去理解探索。
* Jeff Moss 在開場提到了一個很重要的事情，那就是網路世界或者說整個世界已經有根本性的改變，Jeff 提到了訊息監管和網路權威等等的資訊跟議題，究竟是更完善完整的訊息才是重點還是適當的資訊限制才對人們有利呢？也提到了現在其實有一股力量，被他稱為 super empovered organization，擁有巨大的影響力，他們有權利有能力跟你的 mail server 的 spam block list 一樣創建一個阻擋清單。Jeff 利用這次的烏俄戰爭作為例子，當人們決定懲罰戰爭罪的時候，當人們覺得政府並不夠積極的時候，發生了什麼事情？ MongoDB 刪除了所有跟俄羅斯有關的項目、數據，公司將以一個超高影響力的角度進駐社群改變生態也都是可能的，而且這件事情會越來越明顯，越來越強勢。Jeff 提到正因為這些事情的發生，讓他提議發起一個監管組織，來制定所謂的 block list，這樣才能更針對性的制裁或者控制影響範圍，例如假設今天有這個監管組織，MongoDB 就不會移出所有俄羅斯的 Database，而是說，我們基於這個 block list 禁止了特定 IP 的訪問，這樣就不會影響那些無法改變任何事情的普通民眾。但這件事情就如一個魔盒，有些事情並不是被期望攤出來說的，我們期望政府監管，但我們也在種種地方看到政府無力影響龐大的公司決策，但 Jeff 也狠狠的說明，當政府無能時，會有人接手填補空白，上述資訊說明了世界的互動已經有了截然不同的改變，很多事情不再如我們預想的一般運行，影響力巨大的世界互動慢慢在改變著世界。
* Chris Krebs 開始了接下來的演說，整個核心主題我認為說明到了現在的狀況和未來其實應該注意的部分，現階段的產品設計或者說公司主軸都還是認為產品的搶先對於市場對於賺錢而言有至高無上的地位，這當然沒錯，但這樣搶快的開發根本性的造就了現在架構上的混亂，當然，這些風氣正在因為越來越嚴重的資安事件跟勒索病毒有所改變但這些改變仍然太慢，公司領導必須放眼到 2~3 年後的世界變化，應該能更加重視接下來 2~3 季可能發生的攻擊、可能發生的國際情勢變化，我們無法忽視各種數據正在加速擴展的事實跟這些資料都是攻擊者的目標，俄羅斯對烏克蘭的攻擊、中國跟台灣的緊張關係都正說明世界的改變其實並沒有依照原設想的劇本走，資訊安全有許多期望跟需要努力的方向，都一一在這個演說中被強調出來。

#### [All Your GNN Models and Data Belong to Me](https://attend.blackhatevents.virtual.informatech.com/event/black-hat-usa-2022/planning/UGxhbm5pbmdfOTQ5MjY4)
> [time= Aug 10, 2022 10:20 to 11:00]

:::info
* Notes
    * Message Passing Technology
    * GNN
        * Graph Converlution Network
        * Graph Isomorphism Network
    * Euclidean space 歐幾里得空間
    * Adversarial Machine Learning 對抗式機器學習
        * The big topic of the security of machine learning themselves
    * Privacy - Graph
        * Link Re-Identification Attack 鏈路重識別攻擊
        * Property Inference Attack 屬性推理攻擊
        * Subgraph Inference Attack 
    * Secure - Model
        * Model Extraction Attack
:::

* 本分享主要在說明一個利用公司提供的 GNN API 就可以針對其中的 Graph & Model 盜取，由於涉及到大量的 GNN 基礎知識，因此這邊預計會寫一篇 GNN 的說明文章，大家可以去閱讀一下，應該會更好理解我這邊說明的部分
* 這邊大致上針對這個 Speach 說明一下幾個核心重點，因為有 Release PPT 因此下面會直接截圖 PPT 內容，完整 PPT 請去官網連結獲取。
* 這次的攻擊主要分成針對 Graph 的 Privary Attack，專注在利用 Link Re-Identification Attack、Property Inference Attach、Subgraph Inference Attack 來做 graph stealing，然後也可以直接利用 Model 的 Secure Attack 則是利用 Model Extraction Attack 例用輸出值做梯度下降來擬合建立的假 model 做目標 model 結構推估，而且可以利用約 1/4 的 network size 做到只有 3~5% 原始 model 的誤差的模型。
* 我聽完這場議程後最大的感想是因為 GNN 的模型特性，如果不做一定程度的輸出混淆，確實真的很容易被利用這樣的方式把 model 的 graph dataset 跟 model structure 給整個偷出來，但是這整個想法真的是非常非常的特別，因為我從來每想到可以利用後接一個 network 作為收斂函式就快速收斂逼近模型結構。那由於議程講者有說他們有提供緩解解法了，因此我現在想到針對這個做法的應用反而可以是公司端利用這個技術來優化縮小 model size，因為有時候 3~5% 的 model acc 誤差是完全可以接受的，但是 model size 只要 1/4 卻是對於硬體設備有極大的優勢跟誘因，因此雖然現在這個可能慢慢不是 security issue 卻仍然可以是一個非常天才非常令人讚嘆的作法，來優化模型結構。

#### [Glitched on Earth by Humans: A Black-Box Security Evaluation of the SpaceX Starlink User Terminal](https://attend.blackhatevents.virtual.informatech.com/event/black-hat-usa-2022/planning/UGxhbm5pbmdfOTQ5Mzk1)
> [time= Aug 10, 2022 11:20 to 12:00]

#### [In Need of 'Pair' Review: Vulnerable Code Contributions by GitHub Copilot](https://attend.blackhatevents.virtual.informatech.com/event/black-hat-usa-2022/planning/UGxhbm5pbmdfOTQ5NDM4)
> [time= Aug 10, 2022 13:30 to 14:10]

#### [Return to Sender - Detecting Kernel Exploits with eBPF](https://attend.blackhatevents.virtual.informatech.com/event/black-hat-usa-2022/planning/UGxhbm5pbmdfOTQ5NTM2)
> [time= Aug 10, 2022 14:30 to 15:10]

#### [Fault-Injection Detection Circuits: Design, Calibration, Validation and Tuning](https://attend.blackhatevents.virtual.informatech.com/event/black-hat-usa-2022/planning/UGxhbm5pbmdfOTQ5Mzg2)
> [time= Aug 10, 2022 15:30 to 16:10]

#### [GPT-3 and Me: How Supercomputer-scale Neural Network Models Apply to Defensive Cybersecurity Problems](https://attend.blackhatevents.virtual.informatech.com/event/black-hat-usa-2022/planning/UGxhbm5pbmdfOTQ5NDA1)
> [time= Aug 10, 2022 16:30 to 17:10]

### Day 02

#### [Keynote: Pre-Stuxnet, Post-Stuxnet: Everything Has Changed, Nothing Has Changed](https://attend.blackhatevents.virtual.informatech.com/event/black-hat-usa-2022/planning/UGxhbm5pbmdfOTY1MDYz)
> [time= Aug 11, 2022 09:00 to 10:00]

#### [Do Not Trust the ASA, Trojans!](https://attend.blackhatevents.virtual.informatech.com/event/black-hat-usa-2022/planning/UGxhbm5pbmdfOTQ5MzYz)
> [time= Aug 11, 2022 10:20 to 11:00]

#### [Oops..! I Glitched It Again! How to Multi-Glitch the Glitching-Protections on ARM TrustZone-M](https://attend.blackhatevents.virtual.informatech.com/event/black-hat-usa-2022/planning/UGxhbm5pbmdfOTQ5NDkz)
> [time= Aug 11, 2022 11:20 to 12:00]

#### [The Battle Against the Billion-Scale Internet Underground Industry: Advertising Fraud Detection and Defense](https://attend.blackhatevents.virtual.informatech.com/event/black-hat-usa-2022/planning/UGxhbm5pbmdfOTQ5NTkw)
> [time= Aug 11, 2022 13:30 to 14:10]

#### [Malware Classification With Machine Learning Enhanced by Windows Kernel Emulation](https://attend.blackhatevents.virtual.informatech.com/event/black-hat-usa-2022/planning/UGxhbm5pbmdfOTQ5NDcw)
> [time= Aug 11, 2022 14:30 to 15:10]

#### [Human or Not: Can You Really Detect the Fake Voices?](https://attend.blackhatevents.virtual.informatech.com/event/black-hat-usa-2022/planning/UGxhbm5pbmdfOTQ5NDI4)
> [time= Aug 11, 2022 15:30 to 16:10]

#### [Locknote: Conclusions and Key Takeaways from Black Hat USA 2022](https://attend.blackhatevents.virtual.informatech.com/event/black-hat-usa-2022/planning/UGxhbm5pbmdfOTY1MDY1)
> [time= Aug 11, 2022 16:30 to 17:10]
