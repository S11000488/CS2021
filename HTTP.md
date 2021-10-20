# HTTP
## -超文本傳輸協定（英語：HyperText Transfer Protocol，縮寫：HTTP）
- HTTP是一個客戶端（使用者）和伺服器端（網站）之間請求和應答的標準，通常使用TCP協定。
- [超文本傳輸協定](https://zh.wikipedia.org/wiki/%E8%B6%85%E6%96%87%E6%9C%AC%E4%BC%A0%E8%BE%93%E5%8D%8F%E8%AE%AE "link")
- [Hypertext Transfer Protocol](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol"link")
# HTTP 八大方法
| 指令| 輸出結果|
| -------| -------|
| GET| 獲取資源|
| POST| 傳輸實體內容
| DELETE| 刪除資源|
| OPTIONS| 詢問支持的請求方法|
| PUT| 傳輸文件|
| HEAD| 獲取首部|
| TRACE| 路徑追蹤|
| CONNECT| 要求用隧道協議連接代理|
# HTTP 狀態碼
[狀態碼列表](https://zh.wikipedia.org/wiki/HTTP%E7%8A%B6%E6%80%81%E7%A0%81)
| 代碼| 代表|
| --------| -------|
| 1xx| 訊息|
| 2xx| 成功|
| 3xx| 重新導向|
| 4xx| 客戶端錯誤|
| 5xx| 伺服器錯誤|
## 常遇到
- 200 OK
請求已成功，請求所希望的回應頭或資料體將隨此回應返回。實際的回應將取決於所使用的請求方法。在GET請求中，回應將包含與請求的資源相對應的實體。在POST請求中，回應將包含描述或操作結果的實體。
- 301 Moved Permanently
被請求的資源已永久移動到新位置，並且將來任何對此資源的參照都應該使用本回應返回的若干個URI之一。如果可能，擁有連結編輯功能的客戶端應當自動把請求的位址修改為從伺服器回饋回來的位址。
- 302 Found
要求客戶端執行臨時重新導向（原始描述短語為「Moved Temporarily」）。由於這樣的重新導向是臨時的，客戶端應當繼續向原有位址傳送以後的請求。只有在Cache-Control或Expires中進行了指定的情況下，這個回應才是可快取的。
- 304 Not Modified
表示資源在由請求頭中的If-Modified-Since或If-None-Match參數指定的這一版本之後，未曾被修改。在這種情況下，由於客戶端仍然具有以前下載的副本，因此不需要重新傳輸資源。
- 401 Unauthorized 參見：[HTTP基本認證](https://zh.wikipedia.org/wiki/HTTP%E5%9F%BA%E6%9C%AC%E8%AE%A4%E8%AF%81) [HTTP摘要認證](https://zh.wikipedia.org/wiki/HTTP%E6%91%98%E8%A6%81%E8%AE%A4%E8%AF%81)
- 403 Forbidden
伺服器已經理解請求，但是拒絕執行它。與401回應不同的是，身分驗證並不能提供任何幫助，而且這個請求也不應該被重複提交。如果這不是一個HEAD請求，而且伺服器希望能夠講清楚為何請求不能被執行，那麼就應該在實體內描述拒絕的原因。當然伺服器也可以返回一個404回應，假如它不希望讓客戶端獲得任何資訊。
- 404 Not Found
請求失敗，請求所希望得到的資源未被在伺服器上發現，但允許使用者的後續請求。[34]沒有資訊能夠告訴使用者這個狀況到底是暫時的還是永久的。假如伺服器知道情況的話，應當使用410狀態碼來告知舊資源因為某些內部的組態機制問題，已經永久的不可用，而且沒有任何可以跳轉的位址。404這個狀態碼被廣泛應用於當伺服器不想揭示到底為何請求被拒絕或者沒有其他適合的回應可用的情況下。
![image](https://user-images.githubusercontent.com/90757612/138025519-b698da70-20d1-4c0f-ae43-f785c8ac11af.png)

- 418 彩蛋 I'm a teapot
本操作碼是在1998年作為IETF的傳統愚人節笑話, 在RFC 2324超文字咖啡壺控制協定'中定義的，並不需要在真實的HTTP伺服器中定義。當一個控制茶壺的HTCPCP收到BREW或POST指令要求其煮咖啡時應當回傳此錯誤。這個HTTP狀態碼在某些網站（包括Google.com）與項目（如Node.js、ASP.NET和Go語言）中用作彩蛋。
-
