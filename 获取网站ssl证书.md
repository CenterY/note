取得安全憑證

1. 確認有使用安全連線

如果你跟遠端伺服器是透過 HTTP 連線，那就不是安全連線，如果是 HTTPS 那就是安全連線。

2. 準備好網站的安全憑證

接下來我們需要憑證檔(Certification file)，它的副檔名是 .cer，你可以跟你們的網站管理員詢問，通常他們都知道怎麼拿到這個檔案。

如果你的網站管理員沒有 .cer 檔，只有 .crt 檔，那你可以透過以下這行指令轉檔，要注意的是它是採用 DER 編碼格式（請自行將 myWebsite 替換成你想要的名字）：

	openssl x509 -in myWebsite.crt -out myWebsite.cer -outform der

如果很不幸的，你的網站管理員連 .crt 檔都沒有，那你也可以使用下列這一整行指令從你們的網站取得憑證（請自行將 www.mywebsite.com 替換成你們的網址）：

	openssl s_client -connect www.mywebsite.com:443 </dev/null 2>/dev/null | 	openssl x509 -outform DER > myWebsite.cer

現在你有一個憑證檔了