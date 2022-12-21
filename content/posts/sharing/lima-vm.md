---
title: "Lima - M1 Mac 跑 x84 的好朋友"
slug: "lima"
date: 2022-12-21T11:08:23+08:00
draft: false
thumbnailImagePosition: "top"
metaAlignment: center
tags: ['M1',
       'Mac',
       'Lima',
       'Tools']
---
> 換了 M1 Mac 之後，發現其實還有大量工具只能跑在 x86_64 的環境，這就超級無敵痛苦了，因為不是所有東西都可以利用 Rosetta 2 來轉換，每天崩潰的使用 RDP 來連回家裡的 Windows 再開 VM 來解決問題也實在煩躁，直到喵喵推薦了 Lima 這個屌炸天的 Linux VM 工具，讓我可以在 M1 Mac 上跑 x86_64 的 Linux VM，真的是太感謝了，這篇文章就來介紹一下 Lima 這個工具吧！
<!--more-->

## Lima-VM

* [lima-vm/lima](https://github.com/lima-vm/lima)
* Lima 是一個超級扯蛋的 Linux Virtual Machine，並且可以說是為了 macOS 而努力的存在，而且是 Containerd 的 Linux VM，並可以在 aarm64 上運行 x84_64 的 Linux VM。(而且還可以在上面再啟動其他 container，包含 docker container)
* Lima 是透過 QEMU 進行執行的，並嚴格說起來是一種虛擬機。
> 致謝: 感謝喵喵推薦這好用的酷東西，他也寫了 [blog](https://blog.stevenyu.tw/2022/08/21/%E5%88%A9%E7%94%A8-lima-%E5%9C%A8-m1-%E5%9F%B7%E8%A1%8C-x86-%E7%9A%84-ubuntu/) 介紹大家可以去~~按讚分享小鈴鐺~~

### Install & Config Prepare

* 如果有 homebrew 的話，可以直接透過 homebrew 進行安裝。
    ```bash=
    brew install lima
    ```
* 使用上 Lima-VM 官方有準備很多很多的 config 可以直接做使用，可以直接參考 [lima-vm/lima/examples](https://github.com/lima-vm/lima/tree/master/examples) 這邊的範例。那我們就直接使用官方的範例來進行操作。
    ```yaml=
    # if using specific environment, add `arch` here to specify the architecture
    arch: "x86_64"

    # ubuntu-22.04.yaml example from lima official (here is all the same as the official example)
    images:
    # Try to use release-yyyyMMdd image if available. Note that release-yyyyMMdd will be removed after several months.
    - location: "https://cloud-images.ubuntu.com/releases/22.04/release-20221214/ubuntu-22.04-server-cloudimg-amd64.img"
    arch: "x86_64"
    digest: "sha256:b9a5a216901c34742ffe662b691db114269aaa25c90eb77f3ef4dd4f818e78a3"
    - location: "https://cloud-images.ubuntu.com/releases/22.04/release-20221214/ubuntu-22.04-server-cloudimg-arm64.img"
    arch: "aarch64"
    digest: "sha256:b27163374c834c770e8db023fb21205529cea494257bf5ba866b8b1ae5969164"
    # Fallback to the latest release image.
    # Hint: run `limactl prune` to invalidate the cache
    - location: "https://cloud-images.ubuntu.com/releases/22.04/release/ubuntu-22.04-server-cloudimg-amd64.img"
    arch: "x86_64"
    - location: "https://cloud-images.ubuntu.com/releases/22.04/release/ubuntu-22.04-server-cloudimg-arm64.img"
    arch: "aarch64"

    # mount the host's $HOME directory to the guest's /home/ubuntu
    # if need writable, add `writable: true` under the mount
    mounts:
    - location: "~"
    - location: "/tmp/lima"
      writable: true
    ```
    * 關於 `arch` 的部分，可以參考 [lima-vm/lima#arch](https://github.com/lima-vm/lima/blob/master/docs/multi-arch.md) 這邊的說明。

#### Issue Summary

* 這邊自己有遇到一個問題，就是 mounts 的目錄指定問題，假設今天我們希望 `~` 家目錄底下的所有目錄都是 readonly 但其中的 `~/Works` 這個目錄是 `writable` 的話，會遇到 [issue 873](https://github.com/lima-vm/lima/issues/873) 的父目錄 readonly 阻止了子目錄 writeable 的問題，目前還在 tracking 中，所以這邊我們就直接把 `~/Works` 這個目錄指定到 `mounts` 裡面就好了。

### Start Lima-VM

* 這邊使用剛剛建立的 config (`ubuntu-22_04.yaml`) 來進行啟動，並且使用 `--name` 來命名我們的環境。
    ```bash=
    limactl start ubuntu-22_04.yaml --name ubuntu-22_04-amd64
    ```
* 這時會顯示選項，選擇 `Proceed with the current configuration`，等到看到 `INFO[xxxx] READY. Run lima to open the shell` 就完成了。

### Usage

```bash=
# 進入 shell
limactl shell ubuntu-22_04-amd64
# 關閉 VM
limactl stop ubuntu-22_04-amd64
# 刪除 VM
limactl delete ubuntu-22_04-amd64
```

### More information

* 官方文件寫得很不錯，可以直接去看官方說明歐～
