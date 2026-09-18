This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## 構成
- src/lib/db.ts — pg.Pool（.env の PGHOST/PGPORT/PGUSER/PGPASSWORD/PGDATABASE を使用、Next.js が自動読込）
- src/app/api/todos/route.ts — 一覧取得(GET) / 作成(POST)
- src/app/api/todos/[id]/route.ts — 1件取得(GET) / 更新(PUT) / 削除(DELETE)
- src/app/page.tsx — 追加・完了トグル・編集・削除ができるUI（Tailwind）
- db/schema.sql — todos テーブルDDL
- .env / .env.example — 接続情報（.gitignore で除外済み）
- npm run db:init — .env を読み込んで psql でスキーマ適用

## 動作確認
- npm run build 成功（型エラーなし）
- ローカルDB next_crud_example を作成し npm run db:init でテーブル作成
- npm run dev を起動し、POST/GET/PUT(done)/PUT(title)/DELETE を curl で一通り実行

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.
