---
title: "A short story about Windows python environment conflict"
slug: "windows-python-env"
date: 2023-04-06T20:50:42+08:00
draft: false
categories:
  - 技術分享
tags:
  - Windows
  - Python
  - Environment
---
> 許久沒有用 Windows 做開發，這幾天剛好在幫我老弟安裝 Python 跟 C++ 的開發環境，結果遇到了一個關於 python 跟 mingw64 的環境衝突的問題，在嘗試解決的過程中，因為沒有查到太多資料，所以就想說記錄一下，以免之後再次遇到相同的問題。
<!--more-->

## Python Environment and Mingw64

### 前情提要
* 由於咱小老弟純粹是為了學校的課程使用到 C++ 跟 Python，所以安裝上原本就希望一切從簡，對於環境的設定也沒有太多的要求，只求能夠正常使用就好。
* 也因此，我決定使用 mingw64 來提供 gcc 跟 g++ 的編譯器，因為這個編譯器的安裝過程相對簡單，而且也不需要太多的設定。而 Python 的部分，我也是直接使用官方提供的安裝程式來安裝，並且沒有特別的設定。
* 由於 Python 非常貼心的在 Windows Installer 的過程中，會自動的將 Python 的安裝路徑加入到系統的環境變數中，所以在安裝完 Python 後，我就可以直接在命令提示字元中使用 python 來執行 Python 的程式了。
* 但是，這邊我遇到了一個很神奇的問題，也就是我在使用 `pip` 來安裝 python 的 packages 的時候，我的 python 竟然吃不到！也因此展開了後續的故事。

### `--version` 的小故事
* 一般來說，我們在安裝好 Python 後，都會使用 `python --version` 來確認 Python 的版本，順便可以確認 python 的安裝狀況跟 windows 的 path 是否正確。
* 好玩的事情是，我的 `python --version` 有正確顯示我安裝的版本 `3.10.9`，而 `pip --version` 則是顯示了 `pip 22.3.1 from the\path\of\AppData\Local\Programs\Python\Python310\lib\site-packages\pip (python 3.10)`，也就是說，我的 pip 是正確的，而且看起來也是確實安裝在 python 3.10 底下的，太好了對吧～
* 開開心心地用 `pip install numpy` 等等把環境裝好之後，`import numpy as np` 的時候，`No module named 'numpy'`...，奇怪，問題出在哪？我有 pip 也有 python 啊，版本也都是對的啊，為什麼會出現這樣的問題呢？
* 這時候我決定多檢查一個部分，所以我使用了 `python -m pip --version`，結果發現，我的 pip 竟然吃不到！顯示了 `path\of\msys64\mingw64\bin\python.exe: No module named pip`！我的 python 竟然是 msys64 底下的 python，而不是我安裝的 python！神奇的 msys64 竟然有 python！
* 好的，環境衝突出現了，我們先來看看上面的不同的 `--version` 其實分別代表什麼意思。

### Different `--version`
* `python --version` 會顯示 python 的版本，也就是說，這個指令會去找到 python 的執行檔，並且執行它，然後顯示出版本，這個部分沒什麼問題。
* `pip --version` 也會顯示 pip 的版本，也就是說，這個指令會去找到 pip 的執行檔，並且執行它，然後顯示出版本，這個部分沒什麼問題。
* 只是上面兩個指令其實都是做一件事情，就是檢查 path，也就是系統路徑中，有記錄的執行檔的位置，然後去找到對應的執行檔，並且執行它，然後顯示出版本，這時候的 python 跟 pip 並沒有任何相依性的檢查，代表的就是 path 中的 python 跟 path 中的 pip，僅此而已，而也只說明了我們的環境中有 python 跟 pip 這兩個東西，但是並沒有說明 python 跟 pip 之間有什麼關係。
* 而 `python -m pip --version` 則是現在這個 python 的 pip 會去找到 python 的執行檔，並且執行它，然後去執行 python 的 pip，也就是說，他的 pip 是 python 的 pip，而不是系統路徑中的 pip，這時候的 python 跟 pip 就會有相依性的檢查。
* 上面的 error message 可以發現，我們現在的 python 是 msys64 底下的 python，而不是我安裝的 python，所以當我們使用 `python -m pip --version` 的時候，python 會去找到 msys64 底下的 python，然後去執行它，而 msys64 底下的 python 並沒有 pip，所以就會出現上面的 error message。

### 環境衝突的原因跟解決辦法
* 簡單來說這個問題就是我的系統中現在有兩個 python 環境，而現在 python 預設執行到了 msys64 底下的 python，而不是我安裝的 python，而這個 python 並沒有 pip，所以就會出現上面的問題。
* 那我們要怎麼解決，其實就是讓系統預設執行的 python 是我安裝的 python，而不是 msys64 底下的 python，這樣就可以解決這個問題了。
* 那由於 python 在安裝時的 path 是自動加入 windows 的 users path 中，而 msys64 則是手動加入在 system 的 path 中，那 Windows 預設 system path 的 priority 會比較高，所以就會出現上面的問題。
* 那我們要怎麼解決，其實就是把 python 的 path 從 users path 中複製一份送到 system path 中，而且要放在 msys64 的前面，這樣就可以解決這個問題了。

### 小結論
* 這次的衝突算是開發過程中第一次遇到，不確定是不是之前安裝 c++ 的時候的安裝方式跟現在新的安裝法不同，所以現在才第一次遇到。
* 那藉由這個衝突，其實讓我對於 python 在系統上的調用跟指令上的差異，以前其實不是很清楚為什麼網路上對於 pip 指令的安裝中，會有 `python -m pip install` 這樣的指令，現在就比較清楚了，因為這樣的指令可以確保我們的 pip 是跟 python 有相依性的，而不是系統路徑中的 pip，所以才會有這樣的指令。
* 那以上就是這次簡單的紀錄了～希望對於有踢到一樣問題的人可以有所幫助～
