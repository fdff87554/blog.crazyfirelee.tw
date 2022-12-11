---
title: "[AI 求生日誌] About Machine Learning"
slug: "about-machine-learning"
date: 2022-12-12T00:04:42+08:00
draft: false
autoThumbnailImage: true
thumbnailImagePosition: "top"
metaAlignment: center
tags: ['Artificial Intelligence',
       'Machine Learning',
       'Deep Learning']
---
> AI 在長久的發展中載浮載沈，是什麼決定了現在的崛起？在 2022 年的今天，生活中似乎已經慢慢被 AI 給滲透，手機、銀行和政府機構等等，似乎沒有什麼服務已經看不到 AI 的身影，究竟是什麼成就了現在的 AI？
<!--more-->

## What is Machine Learning? / 什麼是機器學習？
* 機器學習 (ML) 是人工智慧 (AI) 的一種，基於計算機可以在沒有人工干預的情況下學習信息的概念。
* 最基本的做法是使用算法解析數據，從中學習，然後對世界上的某事做出決定或預測。
* 因此，機器不是使用一組特定指令手動編碼軟件程序來完成特定任務，而是使用大量數據和算法"訓練"機器，使其能夠學習如何執行任務。

## Why Big Data pushed Machine Learning a hand? / 為什麼大數據推了機器學習一把？
* 剛剛有提到機器學習其實就是從眾多數據中，找到針對特定目標的一種解決方案，那數據的多寡很直觀明顯的決定了 ML 對於數據判斷的精準程度，因為數據 == 可能出現的特徵，因此很多人也會說，正式 21 世紀生活型態，網路雲端等等爆炸性數據的出現，成就了現在的 AI 發展，因為有足夠多的數據，造就了足夠精準跟完善的 AI 辨識結果。
* 大數據的確切定義如下：
	* 種類更多樣化 (variety)、數量不斷增加 (volume) 且產生速度越來越快 (velocity) 的數據。以上三個特徵又稱為「三個 V」。

## How Machine Learning Works? / 機器學習是怎麼運作的？
* 相比一般程式的運作是我們給予問題和解決邏輯，他輸出答案給我們，機器學習剛剛有提過是希望能藉由問題和答案給我們一個解決方案並接著解決沒有答案的問題，所以差異上看起來會長下面這樣
    > ![How Machine Learning Works](https://blog.crazyfirelee.tw/images/how-machine-learning-works.png)
* 那實際上其實對於我們來說，我們是提供機器學習一大堆的可能的 function，並且希望他在這堆可能的 function 中找到能用的最佳的那個。

## The Types of Machine Learning / 機器學習有哪些種類？
* 我們說過機器學習是利用數據跟問題去做學習，選擇一個解法，那究竟是處理什麼問題跟怎麼學習的呢？
* 那這邊我們可以做一些分類，分別是，
    * 依照目標可分成
        * Regression (預測)
        * Classification (分類)
        * Clustering (分群)
    * 依照資料狀況和訓練方式可以分成
        * Supervised Learning (監督式學習)
        * Semi-supervised Learning (半監督式學習)
        * Unsupervised Learning (非監督式學習)
        * Reinforcement Learning (強化學習)

### Tasks of Learning / 學習的任務
* Regression (預測) - 顧名思義是希望藉由之前的狀況預測下一個時間點的狀況，因此我們的模型輸出的是一個數值。
    > ![Task of Regression](https://blog.crazyfirelee.tw/images/task-regression.png)
* Classification (分類) - 顧名思義是希望藉由現在的資料分類現在輸入的數據，因此我們的模型會輸出一個分類的答案。
    > ![Task of Classification](https://blog.crazyfirelee.tw/images/task-classification.png)
* Clustering (分群) - 顧名思義是希望將有關聯性的資料分成一群整理出來，因此我們的模型會出書很多群的資料。
    > ![Task of Clustering](https://blog.crazyfirelee.tw/images/task-clustering.png)

### Types of Learning / 學習的類型
* Supervised Learning (監督式學習) - 我們會給予模型一些答案，讓他去學習，因此我們會有一個答案的資料集，而這個資料集會有一個輸入跟一個輸出，輸入就是我們的特徵，輸出就是我們的答案。
* Semi-supervised Learning (半監督式學習) - 對少部分資料進行「標註」，電腦只要透過有標註的資料找出特徵並對其它的資料進行分類。
* Unsupervised Learning (非監督式學習) - 我們不會給予模型任何答案，而是要求模型想辦法把相似的集合在一起，沒有答案。
* Reinforcement Learning (強化學習) - Training 當下沒有給答案，但是會在事後告訴他他的回答是好的還是不好的，也就是一種混合的概念。

## What is the Differences between Statistics & ML? / 機器學習跟統計學的差異？
* 上面的一切聽完之後，應該會有人疑會那究竟機器學習跟統計到底有什麼差異呢？感覺就是把東西歸類整理完之後，給一個結論而已啊？
* 其實最大的差異就在於能不能面對未知跟未來這兩件事情，什麼意思呢？
* 統計其實就是整理歸納，這件事情在 ML 中也是近似的，但最大的差異在於 ML 會把歸納的東西變成一種判斷模式，新的資料進來 or 問題進來的時候，就算之前完全沒有出現過這個數據，他也會盡可能給你一個相似的答案，意味著 ML 就是在整理歸納的過程中發展出了判斷標準，一個 function 來面對這個問題，他給你的是一個這個問題的答案
* 但統計就是統計，你可以拿來算平均，拿來算標準差看看現況，但他不能告訴你今天突然出現一個 300 公分的人是不是代表他有些問題，不能告訴你明天會不會下雨，他不會給你一個答案，給出判斷的人是看這些統計資料的人，不是電腦。

## References

### Web Site
* [What's the Difference Between Artificial Intelligence, Machine Learning and Deep Learning? - Nvidia](https://blogs.nvidia.com/blog/2016/07/29/whats-difference-artificial-intelligence-machine-learning-deep-learning-ai/)
* https://www.ecloudvalley.com/tw/blog/machine-learning/
* https://www.trendmicro.com/zh_tw/what-is/machine-learning.html

### Book
* 圖解人工智慧 - 神崎洋治 - 碁峰出版
* 機器學習、人工智慧與人類未來 - 吳作樂、吳秉翰 - 五南出版
* 機器學習和深度學習的技術與原理 - 山口達輝、松田洋之 - 碁峰出版
* 從人到人工智慧，破解 AI 革命的 68 個核心概念 - 三宅陽一郎、森川幸人 - 臉譜出版
