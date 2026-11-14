# courrierreader-links

CourrierReader のカスタムディープリンクを Discord などの HTTPS リンクから開くための、
静的ページです。アプリ本体のソースは含みません。

## 使い方

```text
https://yamazakiyusuke.github.io/courrierreader-links/?id=465385
```

1. Discord などで URL をタップ
2. ページ内の「CourrierReader で開く」をタップ
3. CourrierReader が起動し、記事を新しいタブで開く

記事 ID は正の整数のみ受け付けます。不正な ID ではエラー表示のみで、
ディープリンクは生成されません。

## 仕組み

`index.html` の JavaScript が `?id=` を読み取り、次のリンクを生成します。

- `courrierreader://article/<id>`
- `intent://article/<id>#Intent;scheme=courrierreader;package=com.example.courrierreader;end`
- `https://courrier.jp/news/archives/<id>/`

GitHub Pages の静的ホスティングのみで動作し、サーバーやDBはありません。
アプリのインストールが必要です。Discord のアプリ内ブラウザからの遷移に対応します。
