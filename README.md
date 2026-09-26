# Structure Planner（Windows版）

Minecraftの建築ファイル（.litematic / .mcstructure / .nbt）を読み込んで、必要な素材の一覧・3D表示・編集・地上絵づくりができる非公式ツール。

**NOT AN OFFICIAL MINECRAFT PRODUCT. NOT APPROVED BY OR ASSOCIATED WITH MOJANG OR MICROSOFT.**

- インストール不要のWeb版: https://structure-planner.maxwellailab.com
- このリポジトリはWindows版の配布専用。ダウンロードは右の **Releases** から。

## ダウンロード

[最新版のページ](https://github.com/maxwellailab/structure-planner/releases/latest) から `StructurePlanner_<版>_x64-setup.exe` をダウンロードする。各リリースに SHA-256 を載せている。

壊れていないか・すり替わっていないかは、PowerShellで確かめられる。

```powershell
Get-FileHash "$env:USERPROFILE\Downloads\StructurePlanner_*_x64-setup.exe"
```

表示された Hash がリリースの SHA-256 と一致すればOK。一致しないときは実行せず、削除して取り直してほしい。

## 「WindowsによってPCが保護されました」と出たとき

このインストーラーにはコード署名（有料の発行元証明書）を付けていない。そのため初回は Microsoft Defender SmartScreen の青い画面が出ることがある。

1. SHA-256 が一致することを先に確かめる。
2. 青い画面の「詳細情報」を押す。
3. 発行元が「不明な発行元」、アプリ名が `StructurePlanner_<版>_x64-setup.exe` であることを確認して「実行」を押す。

このリポジトリ以外から入手したファイルは実行しないでほしい。

## 動作環境

- Windows 10 / 11（64bit）
- Microsoft Edge WebView2 ランタイム。Windows 11 には最初から入っている。入っていないPCでは、インストール中にMicrosoftから自動で取得する（このときだけインターネット接続が必要）。

## インストール

- 管理者権限は不要。自分のユーザーだけにインストールされる。
- `.litematic` `.mcstructure` `.nbt` `.mcplan2` をダブルクリックで開けるように関連付ける。すでに別のアプリを「常にこのアプリで開く」に選んでいる場合は、その設定が優先される。アンインストールすると元の関連付けに戻す。
- 起動中に別のファイルをダブルクリックすると、同じウィンドウで開く。

## 初回起動

このアプリにはブロックやアイテムの画像（テクスチャ）を同梱していない。最初に次のどれかを選ぶ。

- **このPCのMinecraft Java版を使う**：インストール済みのゲームから画像を読み込む。許可したときだけ読む。
- **自分でパックを読み込む**：リソースパック（zip / jar / mcpack）を選ぶ。
- **画像なしで使う**：形と色の簡易表示。

あとから「建築」の表示パネルの「テクスチャを選び直す」で変えられる。

## 更新・アンインストール

- 自動更新はない。新しい版はこのリポジトリの Releases に載せるので、同じ手順でインストーラーを実行すれば上書きで更新できる。自動保存・保存スロット・覚えさせたパックは引き継がれる。
- アンインストールは「設定」→「アプリ」→「インストールされているアプリ」→ Structure Planner。「アプリのデータを削除」にチェックを入れると、自動保存や保存スロットも消える。
- エラーで落ちたときの記録は `%LOCALAPPDATA%\StructurePlanner\crash.log` に残る。

## プライバシー

読み込んだファイルはPCの中だけで処理し、どこにも送らない。アカウント、アクセス解析、広告はない。詳しくはアプリの「設定」→「このアプリについて」。

## 問い合わせ・権利表記

- 作者: MaxwellAILab
- 不具合・要望: [問い合わせフォーム](https://docs.google.com/forms/d/e/1FAIpQLSfBgUUTMsFtgh1S7Q5zAbY37YyOEGc9XmRhF6HVuTmtqOAUmQ/viewform)。Mojang・Microsoftへは問い合わせないでほしい。
- 使っているフォント・ライブラリ・データのライセンスは、アプリの「設定」→「このアプリについて」→「第三者の権利表記・ライセンスを見る」で確認できる。

---

## English (short)

Structure Planner is a free, unofficial Minecraft building and materials planner for Windows. It opens .litematic, .mcstructure and .nbt files, shows them in 3D, lists materials, and edits and saves them. Download the installer from **Releases** and check its SHA-256 (listed on each release) with `Get-FileHash`. The installer is not code-signed, so Windows SmartScreen may warn on first run: choose "More info" → "Run anyway" only if the hash matches. No textures are bundled; the app uses your installed Minecraft Java edition (with your permission) or a resource pack you choose. Files never leave your PC. Web version: https://structure-planner.maxwellailab.com
