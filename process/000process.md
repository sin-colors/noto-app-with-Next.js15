1. `npx create-next-app@latest .`でプロジェクトのひな型を作成。

- TypeScript--Yes, ESLint--Yes, TailwindCSS--Yes, src/--Yes, App Router--Yes, import alias--No
- react v19.0.0, next v15.1.7, tailwindcss v3.4.1

1. global.css で、不要なスタイル(上 3 行以外)を削除。page.tsx で、JSX をすべて削除して、`<div>Home Page</div>`のみとする。
1. TailwindCSS のクラスを自動で並べ替える設定を追加。

- ライブラリのインストール `npm install -D prettier prettier-plugin-tailwindcss`
- 設定ファイルの追加

```:.prettierrc
{
"plugins": ["prettier-plugin-tailwindcss"]
}
```

1. Githubのリポジトリを作成。リポジトリ名: note-app-with-Next.js15
1. プロジェクトのルートディレクトリで、gitの初期設定を実行。

- `git init`
- `git add .`
- `git commit -m 'first commit'`
- `git branch -M main`
- アクセストークンの取得
  - Githubにログインして、右上のユーザーアイコン➝settings
  - 左側のサイドバーから、<> Developer settings
  - Personal access tokensのプルダウン(v) ➝ Tokens(classic)
  - Noteの入力欄に適当な名前を記入。Expiration(期限のこと)を30days(30daysじゃなくても大丈夫)。
  - Select scoresで、repo Full control of ・・・にチェックを入れる。➝ Generate token
  - 生成されたトークンをコピー
- `git remote add origin https://ユーザー名:アクセストークン@github.com/ユーザー名/リポジトリ名.git`
- `git push -u origin main`

:::note info
remote: Invalid username or password というエラーが出た場合、remoteのURLの設定が間違っているので、
`git remote set-url origin https://ユーザー名:アクセストークン@github.com/ユーザー名/リポジトリ名.git`としてremoteのURLを設定し直した後、`git push -u origin main`を実行する。
:::

1. git-flow の初期設定。`git flow init -d`
