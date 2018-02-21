---
copyright:
  years: 1994, 2017
lastupdated: "2017-11-17"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 規劃 SSL

開始使用 SSL 需要進行一些規劃。請完成下列必要條件。

1. 決定憑證的取得位置
2. 瞭解憑證類型、金鑰長度及持續時間
3. 選擇通用名稱
4. 瞭解 Socket 規則
5. 產生 CSR

## 決定憑證的取得位置

SSL 憑證可在組織內部取得，或從「憑證管理中心」取得，例如 VeriSign、RapidSSL、Thawte 及其他單位。  

對於控制架構中的小型群組（例如使用內部網路網站的員工），您可以取得自簽憑證，讓每個員工安裝在其瀏覽器中。您也可以設定自己的本端憑證管理中心，以產生在您組織使用的憑證。

對較大型、多樣化的群組而言，使用來自標準來源的 SSL 憑證，可以在沒有特殊化配置的情況下容許存取。現代的 Web 瀏覽器已配置為信任由憑證管理中心所發出的 SSL 憑證。

## 瞭解憑證類型、金鑰長度及持續時間

在決定要取得憑證的位置之後，請檢閱下列的憑證類型選項及其對應的可用性、金鑰長度和持續時間。

|              憑證類型|  可用性|  金鑰長度|  持續時間|
| --------------------------------------- | --------------------------------- | -------------------------- | -------------------------- |
|網域驗證 (DV)| 快速可用| 1024 位元或 2048 位元| 1 或 2 年|
|組織驗證 (OV)             | 2-3 天，最多一週| 1024 位元或 2048 位元| 1 或 2 年|
|延伸驗證 (EV)| 2-3 天，最多一週| 僅限 2048 位元| 1 或 2 年|
{: caption="表 1. 憑證類型" caption-side="top"}   


## 選擇通用名稱

憑證中使用的通用名稱是網站的主機名稱。主機名稱和憑證的通用名稱必須相符，否則瀏覽器會發出警告。如果您的網站是 web1.mydomain.com，則請用它作為您的通用名稱。如果您也使用 images.mydomain.com，您需要萬用字元憑證（無法從 {{site.data.keyword.cloud}} 取得），或是需要設定多個憑證。如果您選擇錯誤的通用名稱，則可以採取一些步驟來修正憑證訂單，或撤銷並重新發出正確的通用名稱。  

## 瞭解 Socket 規則

每個 Socket 被限制為只能有一個憑證。Socket 是 IP 位址和埠的組合，例如 1.2.3.4:443。1.2.3.4:444 會是不同的 Socket。對於像是 SMTP/POP3 或 FTP 之類的應用程式而言，這並不重要。不過，這對於 HTTP 很重要，因為牽涉到虛擬主機作業。

虛擬主機作業是用來在一個 IP 位址上管理 20、30、100 個網站的方法。這種方式可以運作是因為現代瀏覽器會傳遞一個稱為主機讀取器的欄位，作為其要求的一部分。此欄位類似於 "Host: web1.mydomain.com"，並告知 Web 伺服器您嘗試存取的網站。如果是 HTTPS (HTTP over SSL)，在看到主機標頭之前，Web 伺服器必須先選取要傳送給用戶端的 SSL 憑證，這就是為何給定的 Socket 只能有一個憑證。

您可以將每一個啟用 SSL 的網站指派給它自己的 Socket。您可以透過改變 IP 位址或改變埠來達成此目的。請記住，如果您將埠從 443/tcp 變更為其他值，使用者將需要在其 URL 中包含埠號，例如 https://web1.mydomain.com:444。

## 產生 CSR

您可以在 Web 伺服器上使用軟體，來產生「憑證簽署要求」。若為 UNIX 系統，請使用 OpenSSL 套件。若為 Windows，可以從 IIS Manager 中網站內容的「目錄安全」標籤，存取一個精靈。如果您是使用控制台，請參閱該控制台的特定資訊。

產生 CSR 時，您將建立私密金鑰。請勿遺失、刪除或分享私密金鑰。它將在 Web 伺服器上保持私密。部分 CSR 產生公用程式也可讓您建立私密金鑰的通行詞組。除非您打算每當重新啟動 Web 伺服器軟體時便登入伺服器，否則請勿執行此動作。此外，也請勿將盤查詞組套用至 CSR。
