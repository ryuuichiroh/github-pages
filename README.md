# GitHub Pages Documentation

このリポジトリは、AsciiDocファイルを自動的にHTMLに変換してGitHub Pagesで公開するシステムです。

## 📊 Mermaid図の表示について

### GitHub上での表示
- GitHubで直接AsciiDocファイルを閲覧する場合、以下の記法を使用してください：

```asciidoc
ifdef::env-github[]
[source,mermaid]
endif::[]

ifndef::env-github[]
[mermaid]
endif::[]
....
flowchart TD
    A[開始] --> B[終了]
....
```

### GitHub Pagesでの表示
- GitHub Pagesでは、両方の形式が自動的に図として表示されます
- `[mermaid]` ブロックも `[source,mermaid]` ブロックも対応

## 🚀 使用方法

1. `docs/` ディレクトリに `.adoc` ファイルを配置
2. GitHubにプッシュすると自動的にHTMLに変換
3. GitHub Pagesで公開されます

## 📝 Mermaid記法の例

### AsciiDoc形式（推奨）

```asciidoc
ifdef::env-github[]
[source,mermaid]
endif::[]

ifndef::env-github[]
[mermaid]
endif::[]
....
flowchart TD
    A[開始] --> B{条件}
    B -->|Yes| C[処理A]
    B -->|No| D[処理B]
    C --> E[終了]
    D --> E
....
```

## 🔧 技術詳細

- **変換**: Asciidoctor
- **スタイル**: カスタムCSS (グラスモーフィズムデザイン)
- **Mermaid**: v10 (CDN経由)
- **デプロイ**: GitHub Actions + GitHub Pages
