---
title: "My Python Environment on M1 Mac"
slug: "python", "env"
date: 2023-03-04T16:11:47+08:00
draft: false
thumbnailImagePosition: "top"
metaAlignment: center
tags: ['M1',
       'Mac',
       'Python',
       'Environment']
---
> 換了 M1 Mac 之後，一樣遇到一個大魔王就是 Python 環境的問題，這邊不是純粹的指 Python 的安裝，而是管理 Python 環境跟各種 Framework 是不是能正確的再 M1 Mac 上運作，能不能很好的調用硬體的問題，這篇文章記錄一下我在這條路上的愛恨情仇。
<!--more-->

## Python Environment on M1 Mac

### 前情提要
* 因為我會希望我的原生 Python 環境不要因為各種套件或者實驗性的東西而被污染，而且在開發中往往會需要附上 requirements.txt 來讓其他人知道你的環境是怎麼樣的，所以我會希望能夠有一個虛擬環境來管理我的 Python 環境，這樣我就可以在不同的專案中切換不同的環境，而不會互相影響。

### Python Environments
* 為了符合正確的開發流程跟環境管理，我自己嘗試歸納整理了一下，目前我會使用的 Python 環境管理方式，這邊會分成兩個部分，一個是在開發的時候，一個是在部署的時候。

#### Python Virtual Environment
* Python 原生的 virtual environment 在管理套件上可以說是非常方便了，而且由於可以直接輸出 requirements.txt，因此如果是開發的話，我會直接在目錄下創建 `.venv` 來管理我的環境，這樣的好處是 VSCode 在開啟 Python 專案的目錄時，如果有看到 `.venv` 資料夾，會預設直接使用這個環境，而不用再去設定。
* 但這個部分會遇到一個小問題，也就是 `pip install` 下來的 packages 不一定對於 aarm 環境有支援優化，因此在開發的過程中會發現，如果是利用這樣的方式準備的環境，在測試的過程中可以明顯發現很多時候 python 會跑到 rosetta 上去，經過一層 x86 轉譯，對於一些需要高效率的套件來說，效能會大打折扣，因此如果再做實驗的時候，我會希望能確實選擇跟安裝到 aarm 的相關套件，只有在確定要 deploy 的時候，再開始使用 venv 來整理環境並且輸出。
* 這樣的使用想必對不管是在什麼機器上開發 Python Application 的人都是這樣在整理的，所以也就不過多贅述，只是強調一下這樣的 Python Code 不一定能完全發揮 M1 Mac 的效能。

#### Anaconda / Miniconda / Miniforge
* 三者的核心都有 conda 這個工具，其主要用來實現 python 的 `環境 Environment` 和 `套件 Package` 的管理 (其實有包含多種語言，除了 Python，R, Java, C 等等都有支持)。
* Anaconda 跟 Miniconda 是公司的產品，如果商用需要付費，但個人使用是免費的，而 Miniforge 則是由社群維護的。
* Anaconda VS Miniconda
  * 而 Miniconda 跟 Miniforge 都是相較輕量化的版本，相比 Anaconda 中預設 Python + conda + meta package 的肥胖組合，Miniconda 只有 Python + conda。
* Miniconda VS Miniforge
  * 兩者都是 Python + conda，但其 Miniforge 的預設 conda channel 是 `conda-forge`，而 Miniconda 則是預設的 channel 是 `anaconda.org`。
    > conda channels (來源) 是 packages 的儲存位置，目前 `conda-forge` 的維護度是最高的，而 `anaconda.org` 則是 Anaconda 公司的產品，所以如果是要安裝一些比較新的套件，建議使用 `conda-forge`。conda channel 是可以更換的，因此也可以使用 miniconda 但讓 channel 指向 `conda-forge`。
* Miniforge 相比 Miniconda 更早的支援了 Apple M1 Chip，但現在 Miniconda 已經也支援了，但這也側面證明了 Miniforge 的更新維護狀況是非常良好且快速的。
  > PS. 在早期 Tensorflow 的 M1 Installation 教學是推薦 Miniforge 的，但現在因為 Miniconda 已經支援了，所以改推薦 Miniconda 了。

##### 小總結
* Miniforge 由於是社群維護的，開源、更新快速、維護狀況其實也非常良好，如果沒啥意外 M1 Mac 我是推薦的直接安裝 Miniforge 來使用。
* 但也請注意，由於 Miniforge 是由社群維護驗證，穩定性一定還是會略輸 Miniconda 跟 Anaconda，因此如果不追求最快速的更新支援，那麼 Miniconda 或是 Anaconda 也是不錯的選擇。
* Anaconda 太肥胖了，如果只是要用來管理 Python 環境，那麼 Miniconda 或是 Miniforge 就足夠了。

#### Conda VS pip
* conda 的 package source 在前面已經提過了，而 pip 的來源是 PyPI (Python Package Index)。pip 是專門針對 python 打包而成的，屬於 wheels or source distributions，會需要 compiler 來安裝，而 conda 則是 packages are binaries，因此包含例如 C Language 所撰寫的套件，都可以直接安裝，不需要 compiler。
* conda 則會有嚴格的依賴衝突檢查，pip 則沒有。

### 我的使用方式
* 由於是 M1 Mac，為了集結社群之力，盡快取得合適的 Python 環境，我是直接安裝了 Miniforge 來使用。穩定性上我目前沒有特別擔心。
* 雖然一般來說，關於 Python 的 Package 會盡可能建議直接用 pip 來安裝，但由於我希望能夠盡可能的利用 M1 Mac 的效能，因此我會盡可能的使用 conda 來安裝套件，但如果是沒有 conda 的套件，那麼我會直接使用 pip 來安裝。
  > 好處在於 conda 的 binary package 會類似於 source code 的編譯，可以發現其效能是比 pip 來的好的。
