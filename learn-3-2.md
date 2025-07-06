# Learn-3-2: フレックスボックスで横並びレイアウト

## 学習目標

このレッスンでは、フレックスボックスを使って要素を横並びにする方法を学びます：

- `display: flex` の基本
- `justify-content` で水平方向の配置
- `align-items` で垂直方向の配置
- `gap` で要素間の間隔調整

## 前回からの変更点

- ヘッダーにナビゲーションメニューを追加（横並び）
- ヒーローセクションにボタンを追加（横並び）
- ホバー効果を追加

## 重要なCSSの概念

### 1. フレックスボックスの基本

要素を横並びにするには `display: flex` を使います：

```css
.header-content {
  display: flex;
  justify-content: space-between; /* 両端に配置 */
  align-items: center;            /* 垂直方向の中央揃え */
}
```

### 2. フレックスボックスの主要プロパティ

#### justify-content（水平方向の配置）
- `flex-start`: 左端に配置
- `center`: 中央に配置
- `flex-end`: 右端に配置
- `space-between`: 両端に配置、間隔は均等
- `space-around`: 各要素の周りに均等な間隔

#### align-items（垂直方向の配置）
- `stretch`: 高さを揃える（デフォルト）
- `center`: 垂直方向の中央揃え
- `flex-start`: 上端に配置
- `flex-end`: 下端に配置

### 3. gap プロパティ

要素間の間隔を簡単に設定：

```css
.header-nav {
  display: flex;
  gap: 24px; /* 各ナビゲーション項目の間に24pxの間隔 */
}
```

### 4. ホバー効果

ユーザーの操作に反応するインタラクティブな要素：

```css
.nav-item:hover {
  background-color: #e9ecef;
  border-radius: 4px;
}
```

## 実際のレイアウトパターン

### ヘッダーレイアウト
ロゴを左、ナビゲーションを右に配置する典型的なパターン：

```css
.header-content {
  display: flex;
  justify-content: space-between;
}
```

### ボタングループ
複数のボタンを中央に横並びで配置：

```css
.hero-buttons {
  display: flex;
  justify-content: center;
  gap: 16px;
}
```

## 実際に試してみよう

1. `learn-3-2.html` をブラウザで開いてみてください
2. ナビゲーション項目にマウスを重ねてホバー効果を確認してください
3. ブラウザウィンドウのサイズを変更して、フレックスボックスの動作を確認してください
4. CSSの `justify-content` の値を変更して、配置の違いを試してみてください

## 次のステップ

次回（learn-3-3）では、グリッドレイアウトを使って、より複雑な2次元レイアウトを学びます。
