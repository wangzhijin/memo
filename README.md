# 忘れっぽいエンジニアためのメモ

[JavaScriptエスケープ文字](http://www.tohoho-web.com/js/string.htm)  
とほほのJavaScriptリファレンス

# OutSystemsに関する
[Highcharts API Reference](https://api.highcharts.com/highcharts/labels.style)     
内容が多すぎて、ざっと見てから、コードを触りながら、APIを確認したほうがよいと思う	
	
[Highcharts Demo](https://www.highcharts.com/demo)    
サンプルも豊富、パターンも多い、コードを修正しながら、確認できる	
	
[Highcharts Forums](https://www.outsystems.com/forums/25/technology-integration/)     
はまったところがあれば、ここに質問して、すぐ回答してくれる人がいる	

# LINUX(Ubuntu)
状態確認
$ sudo iptables -L
ポート公開
$ sudo iptables -I INPUT -p tcp -m tcp --dport 8080 -j ACCEPT
$ sudo iptables -I INPUT -p tcp -m tcp --dport 8081 -j ACCEPT
保存
$ sudo iptables-save | sudo tee /etc/iptables.rules
再起動する時に、ロードする
$ cd /etc/network/if-pre-up.d/
$ sudo vi iptables_start
⇒iptables_startに貼付け
========================
#!/bin/sh
/sbin/iptables-restore < /etc/iptables.rules
exit 0
========================
$ sudo chmod a+x /etc/network/if-pre-up.d/iptables_start
再起動する
$ reboot

# その他
[BASIC認証](https://github.com/wangzhijin/memo/blob/master/txt)
