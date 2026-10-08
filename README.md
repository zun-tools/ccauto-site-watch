# ccauto-site-watch

Claude Code のルーチンで、好きなサイトの更新を見張るためのひな形です。
動画「Claude で作る自動化 #1」で使っています（ずんだもんの実験道具箱）。

## 使い方

1. このページ右上の **Use this template** から、自分のリポジトリを作る（非公開でかまいません）
2. 作ったリポジトリを手元に clone し、そのフォルダで Claude Code を開く
3. 次の1文を、見張りたいサイトの URL に替えて送る

```
/schedule https://www.anthropic.com/news を毎朝7時に見て、前回から新しい記事が増えたときだけ、要点3行をスマホに通知して
```

前回見た内容は、このリポジトリのブランチ `claude/watch-state` に残ります。
比べ方・通知の書き方のルールは `CLAUDE.md` に書いてあります。

## 見張りたいサイトが読めないとき

ルーチンが動くクラウドの環境は、既定（**Trusted**）では決められたドメインにしか通信できません。
ほかのサイトを見張るときは、そのドメインを環境に足します（公式: [Configure cloud environments](https://code.claude.com/docs/en/cloud-environments)）。

1. [claude.ai/code](https://claude.ai/code) を開き、入力欄の上にある雲のアイコン（環境の名前）を選ぶ
2. **Cloud** の一覧で、ルーチンが使う環境にカーソルを合わせ、右に出る設定アイコンを選ぶ（新しく作るなら **Add cloud environment**）
3. **Network access** を **Custom** にし、**Allowed domains** に見張りたいドメインを1行に1つ書く（例: `example.com`）
4. 既定の許可も残したいときは **Also include default list of common package managers** にチェックを入れて保存する

ルーチンがどの環境を使うかは、ルーチンの編集画面で選べます。

## 止める・消す

[claude.ai/code/routines](https://claude.ai/code/routines) のルーチン詳細画面で、スイッチで止める・メニューの Delete で消す。
作成時に接続中のコネクタが全部付くので、見張りに要らないものは外しておくと安心です。
