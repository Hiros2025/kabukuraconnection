# 株クラ Connection — セットアップガイド

## ファイル構成
```
kabukura/
├── index.html          ← メインサイト（これだけでも動く）
├── data/
│   ├── articles.json   ← 記事データ
│   ├── ranking.json    ← ランキングデータ
│   └── people.json     ← 人物データ
└── README.md
```

## すぐ使う方法
`index.html` をブラウザで開くだけで動作します。

## 記事を追加・編集する方法
サイト右上の ⊞ アイコンをクリック → 管理画面から操作できます。
- 記事の追加
- 記事の削除
- ランキングの更新

## Vercelで無料公開する手順
1. https://github.com でアカウントを作る
2. 新しいリポジトリを作成し、このフォルダをアップロード
3. https://vercel.com でGitHubアカウントでログイン
4. 「New Project」→ GitHubリポジトリを選択 → Deploy
5. 数分で公開完了！URLが発行されます

## コメント機能をDisqusで強化する（任意）
1. https://disqus.com でアカウント作成
2. サイト名を登録してshortname を取得
3. index.html の末尾スクリプトに以下を追加：
```javascript
var disqus_config = function () {
  this.page.url = window.location.href;
  this.page.identifier = currentArticleId;
};
(function() {
  var d = document, s = d.createElement('script');
  s.src = 'https://あなたのshortname.disqus.com/embed.js';
  s.setAttribute('data-timestamp', +new Date());
  (d.head || d.body).appendChild(s);
})();
```

## ドメインを取得する（任意）
- お名前.com や Xserver Domain で .com ドメインが年1,000〜2,000円で取得できます
- Vercelの設定画面でドメインを紐付けできます

## 費用まとめ
| 項目 | 費用 |
|------|------|
| GitHub | 無料 |
| Vercel ホスティング | 無料 |
| Disqus コメント | 無料（広告あり） |
| ドメイン（任意） | 年1,000〜2,000円 |
| **合計** | **ほぼ無料〜年2,000円** |
