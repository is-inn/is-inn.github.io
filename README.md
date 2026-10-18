# is-inn.github.io

zari Lab のユーザーサイト（GitHub Pages）。

## 役割
- `https://is-inn.github.io/` のトップページ
- **`/.well-known/assetlinks.json`**：Android の TWA（Trusted Web Activity）用 Digital Asset Links。
  `is-inn.github.io` ドメインとアプリを紐づけ、アドレスバー非表示のフルスクリーン表示を可能にする。

## assetlinks.json の仕上げ手順（PWABuilder の後）
1. PWABuilder で Android パッケージ（AAB）を生成すると、署名鍵の **SHA-256 フィンガープリント** が発行される。
2. `.well-known/assetlinks.json` の `sha256_cert_fingerprints` の
   `REPLACE_WITH_SHA256_FINGERPRINT_FROM_PWABUILDER` を、その値（`AA:BB:CC:...` 形式）に置き換える。
3. `package_name` が PWABuilder で設定したアプリ ID（既定の想定値：`com.zarilab.zombieface`）と一致しているか確認する。
4. コミット＆プッシュ。数分後に `https://is-inn.github.io/.well-known/assetlinks.json` へ反映される。

関連アプリ：ゾンビフェイス → https://is-inn.github.io/privacy-policy/zombie-face/
