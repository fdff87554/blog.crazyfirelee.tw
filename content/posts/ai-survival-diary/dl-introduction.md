---
title: "[AI 求生日誌] About Deep Learning"
slug: "about-deep-learning"
date: 2022-12-12T12:51:21+08:00
draft: false
categories:
  - AI 求生日誌
tags:
  - Artificial Intelligence
  - Machine Learning
  - Deep Learning
---
> Machine Learning 的概念已經存在數十年，為何於近期才又有一場新的反擊的號角？Deep Learning 的概念為什麼可以跟 Artificial Intelligence 一起被提起變成必駕齊驅的 Keywords？這篇文章將會介紹 Deep Learning 的基本概念，以及為什麼 Deep Learning 會讓 Machine Learning 有了新的生命力。
<!--more-->

## What is Deep Learning? / 什麼是深度學習？

* 深度學習是機器學習領域中的一種作法。
* 主要利用類神經網路的概念，模仿人類神經網路的運作，來判斷資料特徵，達到辨別資料的效果。

### What is Artificial Neural Network? / 什麼是人工神經網絡？

* Artificial Neural Network 是一種藉由模仿人體神經元，來模仿人類思考更新資料的方式的一種概念
* Biological Neuron
    > ![Biological Neuron](https://blog.crazyfirelee.tw/images/biological-neuron.png)
* Artificial Neuron
    > ![Artificial Neuron](https://blog.crazyfirelee.tw/images/artificial-neuron.png)
    > 天主教輔仁大學 深度學習課程 黃貞瑛老師 教材截圖
* 我們可以發現在圖片對照上
    * Dendrites（樹突） = Input Signals（$x_i$）
    * Synapses（突觸） = Weights（$w_i$）
    * Cell Body（細胞體） = Cell Body（$n, f(n)$）
    * Axon（軸突） = Output Signal（$a$）
* 我們來理解一下到底是什麼意思，我們回到我們的機器學習概念，我們希望機器幫我們由資料判斷一個答案，但是這些資料，也就是對這個答案判斷"特徵"一定有好有壞，例如說之前提過的貓咪判斷，我們對於貓咪這個生物有沒有毛，一定不是唯一的判斷標準，但是也會出現在決策的因素裡面，那這邊我們會有很多很多的輸入，就是跟上面提到的 Input Signals 一樣，會有很多個，而這些輸入，有好有壞，因此 weights 這東西就是調控這些資料輸入時的"份量"，Cell body 基於這些 input 的運算了，而後，依照目標，輸出答案

### Relation of Deep Learning and Neuron 深度學習跟神經元的關係

* 深度學習就是一個大量人工神經網路合併的過程，利用模仿大腦神經元的結構，層層傳遞，達到運算等等的效果
* 深度學習的**深度**一詞，就是在說整體神經網路結構到底有多複雜，整個神經元的層數有多**深**
> ![Neural Network Structure](https://blog.crazyfirelee.tw/images/all-kinds-of-neural-networks.png)
* 上圖的詳細初始來源我已經不確定了，但是這張圖完美的呈現了各種神經網路的結構
* 從上圖我們可以發現一件事情，就是每個神經元（就是圖片中的球球）他們都會與下一層的所有神經元座連接，並且一層一層的往下傳遞，因此我們才會用 Layer 的層數來說明這個神經網路有多複雜
* 那這邊有幾個小觀念要順便釐清
    * input layer 不會被算在神經元深度內
    * 除了 input layer 跟 output layer 以外的 layer 我們通稱 hidden layer
    * 當我們定義一個 Network structure，就等於定義了一個 function set
