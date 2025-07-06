# Learn-3-5: レスポンシブデザインとモバイル対応

## 学習目標

このレッスンでは、レスポンシブデザインとモバイル対応について学びます：

- メディアクエリの基本
- ハンバーガーメニューの実装
- レスポンシブグリッドの活用
- モバイルファーストの考え方

## 前回からの変更点

- ハンバーガーメニューを追加
- デモセクションを追加（グリッドレイアウト）
- 3段階のメディアクエリを実装（デスクトップ/タブレット/モバイル）
- レスポンシブグリッドを改善
- ボタンのモバイル対応

## 重要なCSSの概念

### 1. メディアクエリの基本

画面サイズに応じてスタイルを変更：

```css
/* タブレット用 */
@media (max-width: 768px) {
  .header-nav {
    display: none;
  }
}

/* モバイル用 */
@media (max-width: 480px) {
  .container {
    padding: 0 16px;
  }
}
```

### 2. ハンバーガーメニュー

モバイルでのナビゲーション表示：

```css
.mobile-menu-toggle {
  display: none;
  flex-direction: column;
  cursor: pointer;
}

@media (max-width: 768px) {
  .header-nav {
    display: none;
  }
  
  .mobile-menu-toggle {
    display: flex;
  }
}
```

### 3. レスポンシブグリッド

自動調整されるグリッドレイアウト：

```css
.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 24px;
}
```

### 4. フレックスボックスのラップ

ボタンが画面幅に応じて折り返し：

```css
.hero-buttons {
  display: flex;
  justify-content: center;
  gap: 16px;
  flex-wrap: wrap;
}
```

### 5. アスペクト比の維持

動画プレースホルダーの比率維持：

```css
.video-placeholder {
  aspect-ratio: 16 / 9;
}
```

## レスポンシブデザインのポイント

### ブレークポイントの設計
- **モバイル**: 480px以下
- **タブレット**: 768px以下
- **デスクトップ**: 769px以上

### コンテンツの優先順位
1. 最重要コンテンツを最初に表示
2. ナビゲーションは省略可能
3. 画像やデモは簡略化

### インタラクションの配慮
- タップしやすいボタンサイズ
- 十分な間隔
- 読みやすいフォントサイズ

## 実際のレイアウトパターン

### ハンバーガーメニュー
モバイルでのナビゲーション：

```css
.mobile-menu-toggle {
  display: none;
}

@media (max-width: 768px) {
  .mobile-menu-toggle {
    display: flex;
  }
}
```

### レスポンシブボタン
モバイルで全幅表示：

```css
@media (max-width: 480px) {
  .hero-buttons {
    flex-direction: column;
    align-items: center;
  }
  
  .btn {
    width: 100%;
    max-width: 280px;
  }
}
```

### 段階的なグリッド
画面サイズに応じた列数調整：

```css
/* デスクトップ: 自動調整 */
.features-grid {
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
}

/* モバイル: 強制的に1列 */
@media (max-width: 480px) {
  .features-grid {
    grid-template-columns: 1fr;
  }
}
```

## レスポンシブデザインのベストプラクティス

1. **モバイルファースト**: 小さい画面から設計
2. **パフォーマンス**: 必要最小限のCSS
3. **アクセシビリティ**: タップしやすいサイズ
4. **一貫性**: デバイス間での統一感

## 実際に試してみよう

1. `learn-3-5.html` をブラウザで開いてみてください
2. ブラウザウィンドウのサイズを段階的に変更してください
3. モバイルサイズでハンバーガーメニューが表示されることを確認してください
4. ボタンがモバイルで全幅になることを確認してください
5. デベロッパーツールでモバイルデバイスの表示を確認してください

## 次のステップ

次回（learn-3-6）では、より高度なレイアウトパターン（Switcher、Sidebar、Reel、Cover）を学びます。
