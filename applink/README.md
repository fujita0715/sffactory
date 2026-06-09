# applink

アプリごとの共通ダウンロード URL を置くためのフォルダです。  
QR コードはこの共通 URL を指すように作成し、アクセス端末に応じて iOS / Android のストアへ誘導します。

## 現在の共通URL

- 麻雀スコア表: `https://www.sffactory.jp/applink/mahjongscoresheet/`
- 麻雀スコア計算: `https://www.sffactory.jp/applink/mahjongscorecalculation/`
- ちんいつナビ: `https://www.sffactory.jp/applink/chinitsunavigator/`

## 新しいアプリを追加する手順

1. `applink/<app-slug>/index.html` を作成する（`<app-slug>` は英小文字 + ハイフン推奨）。
2. ページ内に iOS / Android のストア URL を設定する。
3. User-Agent で端末判定し、iOS は App Store、Android は Google Play へ `location.replace` で遷移させる。
4. `applink/index.html` に対象アプリのリンクを追加する。
5. QR コードは `https://www.sffactory.jp/applink/<app-slug>/` を登録して作成する。

> これでストア URL が将来変わっても、QR コードの差し替えなしで `applink/<app-slug>/index.html` だけ更新すれば運用できます。
