+++
title = "tar (child): gzip: Cannot exec: No such file or directory"
url = "2019-01-21"
date = "2019-01-21"
description = "Guide to emoji usage in Hugo"
tags = [
    "iOS",
]
categories = [
    "themes",
    "syntax",
]
archives = "2019/09"
aliases = ["migrate-from-jekyl"]
+++

<br>
tar コマンドで解答ができずに困りました。

$ tar -zxvf openjdk-11.0.1_linux-x64_bin.tar.gz

tar (child): gzip: Cannot exec: No such file or directory
tar (child): Error is not recoverable: exiting now
tar: Child returned status 2
tar: Error is not recoverable: exiting now

依存パッケージの gzip を入れてあげることで解決しました。

$ yum install gzip