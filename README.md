# 忘れっぽいエンジニアためのメモ

[JavaScriptエスケープ文字](http://www.tohoho-web.com/js/string.htm)  
とほほのJavaScriptリファレンス

# Solidity勉強   
https://cryptozombies.io/jp/   

# OutSystemsに関する
[Highcharts API Reference](https://api.highcharts.com/highcharts/labels.style)     
内容が多すぎて、ざっと見てから、コードを触りながら、APIを確認したほうがよいと思う	
	
[Highcharts Demo](https://www.highcharts.com/demo)    
サンプルも豊富、パターンも多い、コードを修正しながら、確認できる	
	
[Highcharts Forums](https://www.outsystems.com/forums/25/technology-integration/)     
はまったところがあれば、ここに質問して、すぐ回答してくれる人がいる	

# LINUX(Ubuntu)
# IPアドレスアクセス制限  
'# vi /etc/hosts.deny  
ALL: ALL⇒すべて拒否に設定  
'# vi /etc/hosts.allow  
ALL: 192.168.0.1,153.142.14.1,test.azurewebsites.net  
vsftpd: 192.168.0.  
sshd: 192.168.0.

# LINUX(Ubuntu)
# IPアドレスアクセス制限  
Azure Functionsでは実行時間に注意が必要(https://kumachan.biz/2017/04/03_1611/4722/)  
Timeout value of 00:05:00 was exceeded by function.  


# ポート公開  
状態確認    
$ telnet 192.168.1.1 8081  
$ netstat -anp  
$ lsof -i -nP  
$ sudo iptables -L  
ポート公開  
$ sudo iptables -I INPUT -p tcp -m tcp --dport 8081 -j ACCEPT  
保存  
$ sudo iptables-save | sudo tee /etc/iptables.rules  
再起動する時に、ロードする  
$ cd /etc/network/if-pre-up.d/  
$ sudo vi iptables_start  
⇒⇒⇒iptables_startに貼付け⇒⇒⇒  
#!/bin/sh  
/sbin/iptables-restore < /etc/iptables.rules  
exit 0  
⇒⇒⇒iptables_startに貼付け⇒⇒⇒  
$ sudo chmod a+x /etc/network/if-pre-up.d/iptables_start  
再起動する  
root@test:~#reboot  

#mkcert  
yum install nss-tools  
curl -JLO "https://dl.filippo.io/mkcert/latest?for=linux/amd64"  
chmod +x mkcert-v*-linux-amd64  
cp mkcert-v*-linux-amd64 /usr/local/bin/mkcert  
cd /usr/local/bin/mkcert  
mkcert install   
mkcert localhost  

# その他
[BASIC認証](https://github.com/wangzhijin/memo/blob/master/txt)
