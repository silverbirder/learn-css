# Learn-3-6: 高度なレイアウトパターン

## 学習目標

このレッスンでは、プロフェッショナルなWebサイトで使われる高度なレイアウトパターンを学びます：

- **Cover Pattern**: フルスクリーンセクション
- **Switcher Pattern**: 柔軟な2カラムレイアウト  
- **Reel Pattern**: 横スクロールレイアウト
- **Sidebar Pattern**: メイン+サイドバーレイアウト

## 前回からの変更点

- Cover Patternでヒーローセクションを全面的に改良
- Switcher Patternでデモセクションを実装
- Reel Patternでお客様の声を横スクロール表示
- Sidebar Patternで料金プランとFAQを配置
- グラデーション背景を追加

## 重要なCSSの概念

### 1. Cover Pattern（カバーパターン）

フルスクリーンまたは大きな領域を占めるセクション：

```css
.cover {
  min-height: 60vh;           /* ビューポートの60%の高さ */
  display: flex;
  align-items: center;        /* 垂直方向の中央揃え */
  justify-content: center;    /* 水平方向の中央揃え */
}
```

### 2. Switcher Pattern（スイッチャーパターン）

画面サイズに応じて横並び/縦並びが切り替わるレイアウト：

```css
.switcher {
  display: grid;
  grid-template-columns: 1fr 1fr;  /* デスクトップ: 2列 */
  gap: 40px;
}

@media (max-width: 768px) {
  .switcher {
    grid-template-columns: 1fr;     /* モバイル: 1列 */
  }
}
```

### 3. Reel Pattern（リールパターン）

横スクロールできるカードの列：

```css
.reel {
  display: flex;
  gap: 24px;
  overflow-x: auto;           /* 横スクロールを有効化 */
  padding-bottom: 16px;       /* スクロールバーの余白 */
}

.review-card {
  min-width: 300px;           /* 最小幅を固定 */
  flex-shrink: 0;             /* 縮小を防ぐ */
}
```

### 4. Sidebar Pattern（サイドバーパターン）

メインコンテンツとサイドバーを配置：

```css
.sidebar {
  display: grid;
  grid-template-columns: 2fr 1fr;  /* メイン:サイドバー = 2:1 */
  gap: 40px;
}
```

### 5. グラデーション背景

魅力的な背景効果：

```css
.hero-cover {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
}
```

## 実際のレイアウトパターン

### フルスクリーンヒーロー
インパクトのある最初の印象：

```css
.cover {
  min-height: 60vh;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}
```

### 柔軟な2カラム
コンテンツに応じて最適化：

```css
.switcher {
  grid-template-columns: 1fr 1fr;
}
```

### 横スクロールカード
多くの情報を効率的に表示：

```css
.reel {
  overflow-x: auto;
  flex-shrink: 0;
}
```

### メイン+サイドバー
主要情報と補助情報を分離：

```css
.sidebar {
  grid-template-columns: 2fr 1fr;
}
```

## 高度なレイアウトの利点

1. **ユーザビリティ**: 情報の整理と視覚的階層
2. **スペース効率**: 限られた画面領域の有効活用
3. **モバイル対応**: 自動的なレイアウト調整
4. **プロフェッショナル感**: 洗練された見た目

## レスポンシブ戦略

各パターンは画面サイズに応じて自動調整：

- **Cover**: 高さを調整
- **Switcher**: 2列→1列に変更
- **Reel**: カードサイズを調整
- **Sidebar**: サイドバーを下に移動

## 実際に試してみよう

1. `learn-3-6.html` をブラウザで開いてみてください
2. ヒーローセクションのグラデーション背景を確認してください
3. お客様の声セクションで横スクロールを試してください
4. 料金プランのサイドバーレイアウトを確認してください
5. ブラウザサイズを変更して各パターンの動作を確認してください

## 次のステップ

次回（learn-3-7）では、Position（fixed/sticky）、高度なインタラクション、完成版の仕上げを学びます。
