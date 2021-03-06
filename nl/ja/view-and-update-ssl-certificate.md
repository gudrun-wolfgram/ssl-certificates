---
copyright:
  years: 2014, 2018
lastupdated: "2018-02-22"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSL 証明書の表示と更新

SSL 証明書を SSL 証明書画面にインポートした後は、いつでも表示および更新できます。更新作業は[インポート処理](import-ssl-certificate.html)に似ています。インポートの場合と同様に、更新される詳細は、スペーシングや改行を含めて、すべて元の証明書と正確に一致していなければなりません。

SSL 証明書を表示および更新するには、以下の手順を実行します。

1. ユーザー固有の資格情報を使用して、[{{site.data.keyword.slportal_full}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){: new_window} にアクセスします。
2. **「セキュリティー」**メニューで、**「SSL」>「証明書」**を選択します。
2. **「アクション」**ドロップダウン・リストから**「証明書の表示/更新」**を選択します。
3. アプリケーション・テキスト・ボックスの**「SSL 証明書の詳細」**を更新します。

   **注:** **「SSL 証明書のインポート」**ウィンドウに入力される詳細は、スペーシングや改行を含めて、認証局によって指定されたとおり正確に入力する必要があります。そうしないと、エラーが発生します。

| テキスト・ボックス | 項目 |
| -------- | ----- |
|証明書 |認証局によって提供される SSL 証明書の詳細。 これは通常、英数字のテキスト・ブロックです。|
|秘密鍵 | 認証局によって提供される、証明書の秘密鍵の詳細。 これは通常、英数字のテキスト・ブロックです。|
|中間証明書 | 認証局によって提供される中間証明書の詳細。 中間証明書は必須ではありませんが、その SSL 証明書に関する情報が使用可能である場合は、入力する必要があります。|
| 証明書署名要求 | 認証局によって提供される、証明書署名要求 (CSR) の詳細。 CSR の詳細は必須ではありませんが、証明書の一部である場合は、指定する必要があります。 **注:** CSR は絶対に変更しないでください。 公開鍵が CSR に含まれている場合があり、秘密鍵で置き換えてはなりません。|
|メモ | 他のユーザーに役立つ可能性がある、SSL 証明書に関するメモ。SSL 証明書を更新する場合は**「更新」**をクリックし、アクションを取り消す場合は**「キャンセル」**をクリックします。

## 次のステップ

SSL 証明書の詳細を更新した後、その証明書を使用する製品やサービスは、変更による悪影響を受けることはありません。 証明書は、上記の手順を繰り返すことで、いつでも再更新できます。
