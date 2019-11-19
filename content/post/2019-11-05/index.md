+++
title =  "p12ファイルから証明書と秘密鍵を取り出す"
url = "2019-11-05"
date = "2019-11-05"
description = "p12ファイルから証明書と秘密鍵を取り出す"
tags = [
    "iOS",
]
categories = [
    "iOS",
]
archives = "2019/11"
aliases = ["migrate-from-jekyl"]
+++

<br>
.p12 ファイルから証明書と秘密鍵を取り出す方法です。  
AWS SNS を Terraform で書くときに必要でした。  

{{< highlight html >}}
$ openssl pkcs12 -in xxxx.p12 -nodes -nokeys -out certificate.pem
$ openssl pkcs12 -in xxxx.p12 -nodes -nocerts -out privatekey.oem
{{< /highlight >}}


<!-- for swiswiswift.com responsive -->
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-5587141252700968"
     data-ad-slot="1697863134"
     data-ad-format="auto"
     data-adtest="on"
     data-full-width-responsive="true"></ins>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>
<!-- for swiswiswift.com responsive -->


ただ、この方法では、ファイルの先頭に NoArgument から始まるテキストが入ってしまいます。  
NoArgument が入っても悪さはしないのですが、気になったので消そうとしました。
以下のコマンドを実行すると秘密鍵は NoArgument 無しで変換できました。  
証明書はそのテキストを消す方法が見つから無かったのでいったん諦めました。  
もし分かりましたら追記します。

{{< highlight html >}}
$ openssl pkcs12 -in xxxx.p12 -nodes -nocerts | openssl rsa -out privatekey.pem
{{< /highlight >}}


参考: [Push通知の証明書、p12 -> pem変換について](http://ryokwkm2.hatenadiary.jp/entry/2016/08/10/095840)