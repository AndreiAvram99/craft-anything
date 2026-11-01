<p align="center">
  <a href="https://getartcraft.com/">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="docs/brand/artcraft-logo-white.svg">
      <img alt="ArtCraft" src="docs/brand/artcraft-logo.svg" width="200">
    </picture>
  </a>
</p>

<p align="center">
  <img src="assets/app-icon/hicolor/256x256/apps/ai.storyteller.craft-anything.png" width="128" height="128" alt="Craft Anything のアイコン: 青いタイルに刻まれたカラス">
</p>

<h1 align="center">Craft Anything</h1>

<p align="center">
  <a href="README.md">English</a> · <b>日本語</b>
</p>

<p align="center">
  <b>あらゆる Web サイト、アプリ、ゲームがどう動いているかを見て、あなた自身の版を AI に作らせる。純粋な Rust で書かれた、オープンソースのクリーンルーム・エンジン。</b><br>
  対象を指定して、欲しいものを伝えるだけ。本物の調査ツールで元のソフトを調べ、<br>
  コーディングエージェントに新しいプロジェクトを作らせ、結果を元のソフトと比較して磨き上げます。
</p>

<p align="center">
  <img alt="Rust 100%" src="https://img.shields.io/badge/100%25-Rust-b7410e?style=flat-square&logo=rust">
  <img alt="macOS · Windows · Linux · FreeBSD · Web" src="https://img.shields.io/badge/macOS%20%C2%B7%20Windows%20%C2%B7%20Linux%20%C2%B7%20FreeBSD%20%C2%B7%20Web-native-2d81ff?style=flat-square">
  <img alt="ライセンス: MIT OR Apache-2.0" src="https://img.shields.io/badge/license-MIT%20%2F%20Apache--2.0-3a3a3a?style=flat-square">
  <img alt="ステータス: アーリーアルファ" src="https://img.shields.io/badge/status-early%20alpha-d69e2e?style=flat-square">
</p>

<p align="center">
  <a href="https://discord.gg/artcraft"><img alt="ArtCraft コミュニティの Discord に参加する" src="https://img.shields.io/badge/Join%20us%20on%20Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" height="40"></a>
</p>

<p align="center">
  <a href="#downloads"><b>Craft Anything をダウンロード</b></a> ·
  <a href="https://getartcraft.com/">ArtCraft</a> ·
  <a href="https://getartcraft.com/apps">すべての Crafting Apps</a>
</p>

<br>

<p align="center">
  <img src="docs/images/project-website.png" alt="Craft Anything の Web サイトプロジェクト: チェックがまだ一致していない点と各ページの類似度を示し、ビルダーは自分の版の準備ができたと告げ、承認カードはコマンド実行の前に確認を求め、プランは 4 ステップのうち 2 つが完了していることを示している" width="100%">
  <br>
  <sub>Web サイトプロジェクト: 各チェックがビルドの類似度を示し、ルール外の操作はあなたが承認し、プランは残りの作業を示します。</sub>
</p>

> [!NOTE]
> **ArtCraft は、あらゆる分野の作り手が集まるコミュニティです。** 画家、写真家、映像作家、
> イラストレーター、デザイナー、アニメーター、趣味の人、先週ペンを持ったばかりの人。
> 何かを作っているなら、あなたも仲間です。**[Discord で気軽に声をかけてください](https://discord.gg/artcraft)。**

<p align="center">
  <a href="#how-it-works">仕組み</a> ·
  <a href="#two-ways-to-use-it">2 つの使い方</a> ·
  <a href="#ai">AI</a> ·
  <a href="#built-for-agents">エージェント向け</a> ·
  <a href="#under-the-hood">内部の仕組み</a> ·
  <a href="#get-started">はじめかた</a> ·
  <a href="#status">ステータス</a> ·
  <a href="#downloads">ダウンロード</a> ·
  <a href="https://discord.gg/artcraft">Discord</a>
</p>

<br>

<table>
  <tr>
    <td width="25%" valign="top">
      <h3>🔍 なんでも調べる</h3>
      Web サイト、デスクトップアプリ、スマホアプリ、ゲーム、ファイル。本物の調査ツールが、それらがどう作られ何をするのかを突き止め、答えの裏づけとなるエビデンスも添えます。
    </td>
    <td width="25%" valign="top">
      <h3>🛠️ 自分の版を作る</h3>
      「このサイトを再現して」「このゲームの遊びを Rust で再現して」と伝えれば、コーディングエージェントが指定した技術スタックで新しいプロジェクトを作ります。
    </td>
    <td width="25%" valign="top">
      <h3>✅ 推測ではなく検証</h3>
      すべてのビルドは元のソフトと比較され(3 つの画面幅でのページ、ゲーム自身のセルフテスト、アプリの実行)、十分近づくまで磨かれます。
    </td>
    <td width="25%" valign="top">
      <h3>🤖 エージェント対応</h3>
      284 のツールはそれぞれ CLI コマンドであり MCP ツール。どのエージェントでも、アプリが使うのと同じエンジンを動かせます。調査に AI は要りません。
    </td>
  </tr>
</table>

<br>

<a name="how-it-works"></a>

## 仕組み

Craft Anything に対象を指定し、欲しいものを伝えて「Start」を押すだけ。4 つのステップで進み、
判断が必要なときは平易な言葉で尋ねてきます:

1. **調べる:** 元のソフトを調査します。あらゆる幅でのページ、コード、ファイル、動作のしかた。
2. **作る:** コーディングエージェントが新しいプロジェクトを作ります。言語、フレームワーク、
   エンジンはリクエストで指定したもの(指定がなければ妥当な既定値)を使います。
3. **確認する:** ビルドを元のソフトと比較し、まだ一致していない点を一覧にします。
4. **完成:** 結果を開く、遊ぶ、プレビューする。変更を頼めば磨き直します。

<table>
  <tr>
    <td width="50%" valign="top">
      <img src="docs/images/make.png" alt="Make 画面: 再現する Web サイト、アプリ、ゲームを選び、アドレスを入力し、クリーンルームかディープかを選び、欲しいものを伝えて Start を押す" width="100%"><br>
      <sub><b>Make:</b> 何を再現するかを選び、欲しいものを伝え、Start を押します。</sub>
    </td>
    <td width="50%" valign="top">
      <img src="docs/images/project-game.png" alt="完成したスネークゲームのプロジェクト。すべてのステップが完了し、「ゲームで遊ぶ」ボタンがある" width="100%"><br>
      <sub><b>Ready:</b> ゲームで遊ぶ。変更は下の欄から頼めます。</sub>
    </td>
  </tr>
</table>

<a name="two-ways-to-use-it"></a>

## 2 つの使い方

- **シンプル**(既定): 「What do you want to make?」Web サイト、アプリ、ゲームから選び、説明して
  Start を押します。プロジェクトページには 4 つのステップ(調べる → 作る → 確認する → 完成)、
  エージェントが今何をしているかの平易な説明、質問と承認のカード、結果がどれくらい似ているか、
  結果やそのフォルダを開くボタンが並びます。変更は下の入力欄から頼めます。
  「Just look inside」は、何も作らずに対象へ質問できます(ディープモード時)。
- **アドバンスド**: フル機能のワークベンチ。すべてのツール(Ctrl/Cmd+K)、関数、文字列、疑似 C、
  逆アセンブル、16 進、コールグラフ、エビデンス、未知の点、ジョブ、ログ、エージェントコンソール。

どちらのモードも同じエンジンを動かします。

## クリーンルームかディープモードか

- **クリーンルーム**(既定): 元のソフトの中身は一切読みません。コードも、ファイルも、ページの
  ソースも。Craft Anything は見えるものだけから作業します。追加した画像、訪問者から見た
  Web サイト(スクリーンショット、見えているテキスト、計測したレイアウト、色、フォント、余白、
  開いたメニュー)、許可した場合はアプリのウィンドウの画像。中を覗こうとするツールは拒否され、
  ディープモードの有効化方法を案内します。
- **ディープ**: すべてのツールを使います。私的利用のためのモードです。プログラムのコードとファイルは
  内蔵エンジン(インストールされていれば Ghidra も)で読み、Web サイトの JavaScript を読み、開始
  ページを監視します。ビルダーもそれらすべてを使えます。

タイトルバーか Settings で切り替えられます。`settings_set deep_mode true`、CLI の 1 回限りなら
`--deep`(または `--clean-room`)です。

<p align="center">
  <img src="docs/images/workbench.png" alt="アドバンスドのワークベンチ: 関数一覧、選択した関数の疑似 C、ツール呼び出しで質問に答えるエージェント、エビデンスの台帳" width="100%">
  <br>
  <sub><b>アドバンスド:</b> 関数、疑似 C、エージェント、そしてあらゆる答えの裏にあるエビデンス。</sub>
</p>

<a name="ai"></a>

## AI

ビルドには、お使いのコンピュータ上のコーディングエージェントが必要です。まず **Claude Code**
に対応しています。Craft Anything はあなた自身の、改変されていない `claude` プログラムを実行し、
それはあなた自身のサインインを使います。Craft Anything がアカウントを見たり扱ったりすることは
ありません。利用は Anthropic とのあなた自身の契約に従います。方法と理由は
[docs/claude-code.md](docs/claude-code.md) を参照してください。Codex アダプターもありますが、
実環境での検証はまだです。質問と分析には、Anthropic、OpenAI、OpenRouter、ローカルの
OpenAI 互換サーバーが使えます(Settings → AI)。

<a name="built-for-agents"></a>

## エージェントのために

すべてのツールは CLI サブコマンドでも MCP ツールでもあるので、エージェントはアプリなしで対象を
調べたり、再構築を丸ごと実行したりできます:

```sh
craft-anything-cli commands                                   # every tool, by toolset
craft-anything-cli mcp                                        # serve them to any MCP client
craft-anything-cli rebuild https://example.com "Recreate this website"
```

結果は、信頼度・カバレッジ・制限を備えたエビデンス記録です。大きな結果はまず要約として返り、
`core_evidence_browse` でページ送りできます。`craft-anything-cli setup` は Craft Anything を
コーディングエージェントのアプリにつなぎます。

<a name="under-the-hood"></a>

## 内部の仕組み

ネイティブプログラム、.NET、Java、Android、Apple、Electron/JavaScript、Web サイト、ファームウェア、
パケットキャプチャ、データベース、ゲームファイル向けの 284 ツール(エンジン内が 271、残りは AI と
セットアップの層)を備えた、純 Rust のリバースエンジニアリングエンジンです。独自のデコーダ、
逆アセンブラ、逆コンパイラは外部プログラムなしで動きます。ディープモードではそれらすべてを使い、
Ghidra がインストールされていれば Ghidra も使います。これがデスクトップアプリ(egui)、CLI、
MCP サーバーを支え、一部は WebAssembly としてブラウザでも動きます。
全リストは [docs/tools.md](docs/tools.md) にあります。

<a name="get-started"></a>

## はじめかた

Rust **1.97 以降**が必要です(依存関係が要求します。`rustup update`)。Debian か Ubuntu では、
デスクトップアプリに次も必要です:

```sh
sudo apt-get install libxkbcommon-dev libwayland-dev libx11-dev libxrandr-dev libxi-dev libgl1-mesa-dev libgtk-3-dev
```

そして:

```sh
git clone https://github.com/storytold/craft-anything && cd craft-anything
cargo run --release -p craft-anything                # the desktop app
cargo install --path apps/craft-anything-cli         # the CLI, as `craft-anything-cli`
craft-anything-cli doctor                            # checks the install, coding agents and engines
```

ビルドには、コンピュータ上でサインイン済みのコーディングエージェントが必要です([AI](#ai) 参照)。
足りないものは `doctor` が教えてくれます。コマンドラインからの再構築(質問はターミナルで尋ねられます):

```sh
craft-anything-cli rebuild https://example.com "Recreate this website"
craft-anything-cli rebuild - "A snake game in Rust" --rounds 1
craft-anything-cli rebuild https://example.com "Make the header blue" --continue-in "<project folder>"
craft-anything-cli rebuild - "Add a contact form" --project-folder "<your folder>" --existing edit
```

新しいプロジェクトは `Documents/Craft Anything` に作られます(Settings → General で変更できます)。
各プロジェクトフォルダには `craft.json`(リクエスト、対象、状態、履歴)、`capture/`(対象から記録した
もの)、`app/`(生成されたプロジェクト)、`checks/`(元との比較ごと)、`investigation.cany/`
(エビデンス)、`inbox/`(未回答の質問)が入ります。

プロジェクトは、選んだフォルダから始めることもできます(Start の下の "Choose a folder…"、または
`--project-folder`)。すでにファイルがある場合は、それが何かを答えます。アプリ本体で、ビルダーが
その場で編集するのか、そこから始める素材で、アプリは隣の `app/` に作られるのか(Settings → General
で答えを記憶できます)。Settings → General では、複数のフォルダのプロジェクトも一覧できます。
一覧から外しても、フォルダが削除されるわけではありません。

<a name="status"></a>

## ステータス

> [!IMPORTANT]
> **ステータス:** Craft Anything はアーリーアルファです。今日動くもの、一部だけのもの、次に来るもの:
>
> - **今日動くもの:** デスクトップアプリ(シンプルとアドバンスド)、CLI、MCP サーバー。Claude Code
>   をビルダーとして、Web サイト・アプリ・ゲームを「調べる → 作る → 確認する → 磨く」の順に進める
>   ワークフロー。3 つの画面幅での Web サイト確認。Unity、Unreal、Godot でのゲーム再構築。Ghidra を
>   使うディープモード。生成画像と 3D モデル(オプトイン、自分の fal.ai キー)。プラグイン(MCP
>   サーバー、および `wasm-plugins` オプション付きビルドでの WASM コンポーネント)。
> - **一部だけ:** API キーや他のコーディングエージェントでのビルド(実装済み、実環境では未実行)、
>   アプリとゲームの挙動チェック、代役に対してのみテストした一部のエンジンツール。
> - **次:** 最初の公開リリース(Windows、macOS、Linux、FreeBSD 向けインストーラとブラウザ
>   ビューアは CI に用意済み)、その後マネージド版。
>
> [docs/STATUS.md](docs/STATUS.md) に詳細と各部位の検証方法、
> [docs/tool-status.md](docs/tool-status.md) にツールごとのチェックリスト、
> [docs/ROADMAP.md](docs/ROADMAP.md) に計画の項目別一覧があります。issue を立てるか、
> [Discord](https://discord.gg/artcraft) で壊れたところを教えてください。

**責任ある使い方。** 所有しているか、調べる許可があるソフトに使ってください。DRM、ログイン、
アンチチートを回避することは決してありません。再構築は、エビデンスに基づいてレイアウト・スタイル・
挙動を再現します。エージェントには、あなたが所有しているか許可を得ていると確認しない限り、ロゴ、
写真、テキストをコピーしないよう指示しています。

<a name="downloads"></a>

## ダウンロード

GitHub の[最新リリース](https://github.com/storytold/craft-anything/releases/latest)には以下に挙げる
すべてのビルドが、[すべてのリリース](https://github.com/storytold/craft-anything/releases)には過去の
バージョンとそのリリースノートがあります。ファイル名の `<ver>` はバージョン番号で、
`SHA256SUMS.txt` に各ファイルのチェックサムが載っています。

### Windows

| ビルド | インストーラ | ポータブル |
|---|---|---|
| x64(64 ビット Intel/AMD) | `craft-anything-<ver>-windows-x64.msi` | `craft-anything-<ver>-windows-x64-portable.zip` |
| arm64(Snapdragon などの ARM PC) | `craft-anything-<ver>-windows-arm64.msi` | `craft-anything-<ver>-windows-arm64-portable.zip` |
| x86(32 ビット) | `craft-anything-<ver>-windows-x86.msi` | `craft-anything-<ver>-windows-x86-portable.zip` |

インストーラと実行ファイルはコード署名済みです。ポータブルの zip は設定をアプリの隣に保存します。

### macOS

| ビルド | ファイル | 備考 |
|---|---|---|
| アプリ、ユニバーサル(Apple silicon + Intel) | `craft-anything-<ver>-macos-universal.dmg` | 署名・公証済み |
| コマンドラインツール、ユニバーサル | `craft-anything-cli-<ver>-macos-universal.zip` | 署名・公証済み |

### Linux

| 形式 | x86_64 | aarch64 (ARM64) | 備考 |
|---|---|---|---|
| AppImage | `craft-anything-<ver>-linux-x86_64.AppImage` | `craft-anything-<ver>-linux-aarch64.AppImage` | どこでも動きます。[AppImageUpdate](https://github.com/AppImageCommunity/AppImageUpdate) で自己更新します(`.zsync` ファイル) |
| Flatpak | `craft-anything-<ver>-linux-x86_64.flatpak` | `craft-anything-<ver>-linux-aarch64.flatpak` | サンドボックス化。`flatpak install --user <file>` |
| Debian/Ubuntu | `craft-anything-<ver>-linux-x86_64.deb` | `craft-anything-<ver>-linux-aarch64.deb` | |
| Fedora/RHEL/openSUSE | `craft-anything-<ver>-linux-x86_64.rpm` | `craft-anything-<ver>-linux-aarch64.rpm` | |
| 圧縮アーカイブ | `craft-anything-<ver>-linux-x86_64.tar.gz` | `craft-anything-<ver>-linux-aarch64.tar.gz` | どこにでも展開できます |

RISC-V (riscv64): `craft-anything-<ver>-linux-riscv64.tar.gz`、アーカイブのみです。

### FreeBSD

| ビルド | ファイル |
|---|---|
| x86_64 | `craft-anything-<ver>-freebsd-x86_64.tar.gz` |

### Web(WebAssembly)

| ビルド | ファイル | 備考 |
|---|---|---|
| ブラウザビューア | `craft-anything-web-<ver>.zip` | ファイルの正体をブラウザ上で判定します(ファイルはブラウザから出ません)。フォルダを任意の静的 Web サーバーで公開してください([packaging/web/README.md](packaging/web/README.md)) |

<br>

<p align="center">
  <a href="https://discord.gg/artcraft"><img alt="ArtCraft コミュニティの Discord に参加する" src="https://img.shields.io/badge/Join%20us%20on%20Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" height="40"></a>
</p>

<h3 align="center">一緒にものづくりを</h3>

<p align="center">
  私たちの Discord は、あらゆる種類の作り手が集まる場所です。絵を描く人、写真を撮る人、
  デッサンする人、映像を編集する人、文字を組む人、そしてまだ自分が何を作りたいのか
  模索している人。いま取り組んでいることを共有したり、助けを求めたり、壊れているものを
  教えたり、こうだったらいいのにと思うことを話したりしてください。
  どんな媒体を使っていても、始めてからの年数がどれほどでも、ここでは歓迎します。
</p>

<p align="center">
  <a href="https://discord.gg/artcraft"><b>discord.gg/artcraft</b></a> ·
  <a href="https://getartcraft.com/">getartcraft.com</a> ·
  <a href="https://getartcraft.com/apps">The Crafting Apps</a> ·
  <a href="https://github.com/storytold/craft-anything">Craft Anything</a>
</p>

---

## ライセンスとクレジット

Craft Anything は [MIT](LICENSE-MIT) または [Apache-2.0](LICENSE-APACHE) のデュアルライセンスです
(どちらかお選びください)。Copyright (c) 2026 ArtCraft Team and the Craft Anything contributors.
必要な通知は [NOTICE](NOTICE) にあります。

同梱のフォント、アイコン、画像、その他のアセットは、それぞれ独自のオープンライセンスを保ちます。
それぞれの作者、出典、ライセンスは [ATTRIBUTION.md](ATTRIBUTION.md) に記載しています。

スクリーンショットに写っているのは、そのために作られたサンプルプロジェクトです: example.com、
スネークゲーム、小さな電卓プログラム。

[`docs/brand/`](docs/brand/) にある ArtCraft の名称、ワードマーク、ロゴは ArtCraft Team の商標で、
このライセンスの対象外です。無改変のまま、このリポジトリと Craft Anything の一部としてのみ、
[`docs/brand/LICENSE-brand.txt`](docs/brand/LICENSE-brand.txt) に従って使用できます。
フォークや改変版では、これらを削除しなければなりません。

<p align="center">
  <a href="https://getartcraft.com/"><img alt="ArtCraft" src="docs/brand/artcraft-mark.svg" width="28"></a><br>
  <sub>ArtCraft チームとコミュニティによる制作。</sub>
</p>

---

<sub>このページは [README.md](README.md) の日本語訳です。内容に食い違いがある場合は英語版が優先されます。</sub>
