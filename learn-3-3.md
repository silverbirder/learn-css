# Learn-3-3: グリッドレイアウトで2次元配置

## 学習目標

このレッスンでは、CSSグリッドを使って2次元レイアウトを学びます：

- `display: grid` の基本
- `grid-template-columns` で列の定義
- `gap` でグリッドアイテム間の間隔
- レスポンシブグリッドの作り方

## 前回からの変更点

- 機能紹介セクションを追加
- 機能カードを2×2のグリッドレイアウトで配置
- ホバー効果とトランジションを追加
- 基本的なレスポンシブ対応

## 重要なCSSの概念

### 1. グリッドレイアウトの基本

2次元（縦横）にアイテムを配置するには `display: grid` を使います：

```css
.features-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr); /* 2列、等幅 */
  gap: 24px;                             /* アイテム間の間隔 */
}
```

### 2. グリッドの主要プロパティ

#### grid-template-columns（列の定義）
- `repeat(2, 1fr)`: 2列、等幅で分割
- `300px 1fr`: 最初の列は300px、残りは可変
- `1fr 2fr`: 1:2の比率で分割

#### gap（間隔の設定）
- `gap: 24px`: 行と列の間隔を24pxに設定
- `row-gap: 20px; column-gap: 30px`: 行と列で異なる間隔

### 3. フレックスボックスとグリッドの違い

- **フレックスボックス**: 1次元レイアウト（横並び、縦並び）
- **グリッド**: 2次元レイアウト（行と列の組み合わせ）

### 4. レスポンシブグリッド

画面サイズに応じてグリッドの列数を変更：

```css
/* デスクトップ：2列 */
.features-grid {
  grid-template-columns: repeat(2, 1fr);
}

/* モバイル：1列 */
@media (max-width: 600px) {
  .features-grid {
    grid-template-columns: 1fr;
  }
}
```

### 5. ホバー効果とトランジション

カードにインタラクティブな効果を追加：

```css
.feature-card:hover {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  transform: translateY(-2px);
  transition: all 0.2s ease;
}
```

## 実際のレイアウトパターン

### カードグリッドレイアウト
機能紹介、商品一覧、ブログ記事などでよく使われるパターン：

```css
.features-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 24px;
}
```

### 自動調整グリッド
アイテムの幅に応じて自動的に列数を調整：

```css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 24px;
}
```

## 実際に試してみよう

1. `learn-3-3.html` をブラウザで開いてみてください
2. 機能カードにマウスを重ねてホバー効果を確認してください
3. ブラウザウィンドウのサイズを変更して、レスポンシブ動作を確認してください
4. CSSの `grid-template-columns` の値を変更して、レイアウトの違いを試してみてください

## 次のステップ

次回（learn-3-4）では、スタックパターンを使って縦方向の要素配置とマージン管理を学びます。
