---
copyright:
  years: 1994, 2017
lastupdated: "2017-11-28"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# SSL 証明書の管理

{{site.data.keyword.BluSoftlayer_full}} では、ポータル内に証明書を保管する手段を提供するようになりました。これは、証明書を管理するためのリポジトリーとして機能するだけでなく、証明書を使用または必要とする可能性があるサービスを使用する際にも必要です。

1. ユーザー固有の資格情報を使用して、[{{site.data.keyword.slportal_full}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://control.softlayer.com/){: new_window} にアクセスします。
2. **「セキュリティー」**メニューで、**「SSL」>「証明書」>「証明書の管理」**を選択します。

現在の証明書のリストが、その状況に関する情報と共に表示されます。

検索、証明書の各部分または PEM 形式バージョンのダウンロード、証明書の有効期限の確認を行うことができます。また、各証明書を現在いくつのサービスが使用しているかを確認することもできます。これにより、証明書の有効期限が近づいたときに、アクションを取る必要があるかどうかを判断できます。

## 証明書の追加

証明書を追加する準備ができたら、サブナビゲーション・メニューで、または「証明書リスト」タイトル内で、「証明書の追加」を選択します。証明書とその秘密鍵を提供するだけで済みます。ただし、発行元が中間証明書を提供しているときにそれを提供しないと、証明書チェーンが中断され、エンド・ユーザーや関連サービスの検証が不適切になる可能性があります。

注: パスフレーズを必要とする秘密鍵は保管できません。

追加されると、以下のフィールドが証明書から直接取り出されます。

* 共通名
* 組織名
* 有効期間


以上です。

## 証明書の編集

証明書の左側の三角をアクティブにすると、証明書の各部分の全体が明らかになります。これにより、証明書の各部分を編集することも可能になります。メモを追加したり、必要であれば、証明書を削除したりできます。また、現在その証明書を使用中のサービスのリストも表示されます。



重要な注記: サービスに関連付けられていない証明書のみ、それぞれの「秘密鍵」、「証明書」、または「中間証明書」の部分を更新できます。証明書を削除できないこともあります。

メモは、いつでも変更できます。

## 証明書の削除

証明書を削除するには、編集の手順に従い、証明書の削除を確認するためのチェック・ボックスを選択して、保存するだけです。

### API

証明書の追加、削除、編集、および検索の機能は、SLAPI sldn.softlayer.com でも使用可能です。いくつかの例が、SLDN 記事 (sldn.softlayer.com/article/SSL-Management-my-SLAPI-Its-more-likely-you-think) に示されています。