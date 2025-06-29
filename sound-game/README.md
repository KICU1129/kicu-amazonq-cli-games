# 🎵 Enhanced Beat Jumper

音楽に完全同期したリズムアクションゲーム

![Game Screenshot](https://img.shields.io/badge/Game-Enhanced%20Beat%20Jumper-brightgreen)
![HTML5](https://img.shields.io/badge/HTML5-Canvas-orange)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-yellow)
![Web Audio API](https://img.shields.io/badge/Web%20Audio%20API-Dynamic%20Music-blue)

## 🎮 ゲーム概要

**Enhanced Beat Jumper** は、動的に生成される音楽に完全同期したリズムアクションゲームです。プレイヤーは音楽のビートに合わせて変形する床を利用しながら、様々な敵を避けてアイテムを収集し、高スコアを目指します。

### ✨ 主な特徴

- **🎶 動的音楽生成**: Web Audio APIによるリアルタイム音楽生成
- **🌊 音楽連動ステージ**: ビートに合わせて床が波打つように変形
- **🎊 華やかな演出**: レベルアップ時の大迫力アニメーション
- **🎯 多彩なゲーム要素**: 3種類の敵、コンボシステム、ダッシュ機能
- **🎨 美しいビジュアル**: パーティクルエフェクトとグローエフェクト

## 🎵 音楽システム

### 楽曲構成
- **イントロ** → **Aメロ** → **サビ** → **Bメロ** → **アウトロ** → **ループ**
- 各セクション32ビート（8小節 × 4拍）で構成

### 音楽レイヤー
1. **ベースライン** (Sawtooth波) - リズムの基盤
2. **リードメロディー** (Square波) - メインメロディー
3. **パッド** (Triangle波) - 和音・雰囲気作り
4. **アルペジオ** (Sine波) - 装飾的なメロディー

### BPM変化
- 初期BPM: 120
- レベルアップごとに+5 BPM
- 最大BPM: 180

## 🎮 操作方法

### 基本操作
| キー | 動作 |
|------|------|
| ← → または A D | 左右移動 |
| スペース または W | ジャンプ |
| Shift | ダッシュ（クールダウン付き） |

### ゲーム内操作
| ボタン | 動作 |
|--------|------|
| 🎵 音楽付きゲーム開始 | 音楽と共にゲーム開始 |
| 🔇 無音でゲーム開始 | 音楽なしでゲーム開始 |
| 🚪 やめる | メニューに戻る |

## 🎯 ゲームシステム

### プレイヤー
- **HP**: 100（最大100）
- **移動速度**: 通常5、ダッシュ時12
- **ジャンプ力**: -18（重力0.8）
- **無敵時間**: ダメージ後2秒間

### 敵の種類
1. **通常敵** - 一定速度で移動
2. **ジャンプ敵** - 定期的にジャンプ（白い四角マーク）
3. **高速敵** - 1.5倍速で移動（白い線マーク、ピンク色）

### ダメージシステム
- **敵との接触**: 15ダメージ
- **画面下落下**: 50ダメージ
- **ダメージ後**: 2秒間無敵（点滅表示）

### 回復システム
- **アイテム取得**: +5 HP
- **レベルアップ**: +20 HP

### スコアシステム
- **基本スコア**: レベル + コンボ数（毎フレーム）
- **アイテム取得**: (50 + レベル×10) × (1 + コンボ×0.1)
- **コンボ**: アイテム連続取得で増加、敵接触でリセット

## 🌊 音楽連動システム

### 床の変形
- **プラットフォーム**: 音楽に合わせて波打つように上下移動
- **床の波**: ビートごとに色付きの波が画面を流れる
- **変形強度**: ビートの強さとレベルに応じて変化

### ビジュアルエフェクト
- **パーティクル爆発**: ビートに合わせて大量のパーティクル生成
- **画面振動**: 音楽の強さに応じたシェイク効果
- **背景色変化**: 音楽に同期した色相変化
- **グローエフェクト**: 全要素に美しい発光効果

## 🎊 レベルアップ演出

### アニメーション要素
- **中央テキスト**: 「LEVEL UP!」+ 新レベル数字
- **バウンスアニメーション**: 拡大→維持→縮小の3段階
- **回転リング**: 金色の点線リングが回転
- **8つの星**: 周囲を回転する金色の星エフェクト

### パーティクルエフェクト
- **50個の放射パーティクル**: 中央から放射状に飛び散る
- **30個の爆発パーティクル**: 追加の華やかなエフェクト
- **3回の画面振動**: 大迫力のシェイク効果

### タイミング
- **総時間**: 3秒間
- **発生条件**: 64ビート（約16小節）ごと

## 📁 ファイル構成

```
/
├── sound_game.html          # メインゲームファイル（完全版）
└── README.md               # このファイル
```

## 🚀 プレイ方法

1. **ファイルを開く**
   ```bash
   # ブラウザで以下のファイルを開く
   sound_game.html
   ```

2. **ゲーム開始**
   - 「🎵 音楽付きゲーム開始」または「🔇 無音でゲーム開始」を選択
   - 音楽が聞こえない場合は無音モードを選択

3. **プレイ**
   - 音楽のリズムに合わせて床が変形
   - 敵を避けながらアイテムを収集
   - コンボを繋げて高スコアを目指す

4. **終了**
   - 右上の「🚪 やめる」ボタンでメニューに戻る

## 🎨 技術仕様

### 使用技術
- **HTML5 Canvas**: ゲーム描画
- **Web Audio API**: 動的音楽生成
- **JavaScript ES6**: ゲームロジック
- **CSS3**: UI・アニメーション

### 音楽生成
- **オシレーター**: 4つの音楽レイヤー
- **周波数制御**: リアルタイム音程変更
- **音量制御**: セクションごとの音量調整
- **パターン制御**: 楽章ごとの音楽パターン

### パフォーマンス
- **60 FPS**: スムーズなゲームプレイ
- **リアルタイム音楽**: 遅延なしの音楽生成
- **効率的な描画**: Canvas最適化

## 🎯 ゲームのコツ

### 基本戦略
1. **音楽を聞く**: ビートに合わせて床が変形するタイミングを覚える
2. **ダッシュを活用**: 危険な場面ではダッシュで素早く回避
3. **コンボを維持**: アイテムを連続取得してスコア倍率を上げる
4. **敵の種類を覚える**: それぞれの動きパターンを把握

### 高スコアのコツ
- **アイテム優先**: HPが満タンでもアイテムを取ってコンボ維持
- **リスク管理**: HPが少ない時は無理をしない
- **レベルアップ狙い**: 長時間生存してレベルを上げる
- **音楽活用**: サビの部分は特に床の変形が激しいので注意

## 🐛 トラブルシューティング

### 音楽が聞こえない場合
1. **ブラウザの音量確認**: システム音量とブラウザ音量をチェック
2. **無音モード使用**: 「🔇 無音でゲーム開始」を選択
3. **ブラウザ更新**: ページをリロードして再試行

### 動作が重い場合
1. **他のタブを閉じる**: ブラウザのメモリ使用量を減らす
2. **ブラウザ更新**: キャッシュをクリア
3. **Chrome推奨**: 最新のChromeブラウザを使用

### 操作が効かない場合
1. **キーボード確認**: 他のアプリケーションがキーを占有していないか確認
2. **フォーカス確認**: ゲーム画面をクリックしてフォーカスを当てる
3. **代替キー使用**: 矢印キーが効かない場合はWASDキーを使用

## 🎵 音楽について

このゲームの音楽は完全にプログラムによって生成されており、著作権フリーです。Web Audio APIを使用してリアルタイムで作曲・演奏されるため、プレイするたびに微妙に異なる体験を楽しめます。

### 音楽の特徴
- **ジャンル**: エレクトロニック・チップチューン風
- **構成**: 古典的なポップス構成（ABABCB形式）
- **調性**: Cメジャー基調
- **リズム**: 4/4拍子

## 🏆 更新履歴

### v3.0 (最新版 - fixed_game.html)
- ✅ レベルアップ演出の追加
- ✅ 左右移動問題の修正
- ✅ やめるボタンの追加
- ✅ WASD操作の追加
- ✅ ゲームオーバー処理の改善

### v2.0 (enhanced_game.html)
- ✅ 音楽システムの大幅改善
- ✅ HPシステムの修正
- ✅ 床変形システムの実装
- ✅ 3種類の敵の追加
- ✅ ダッシュ機能の追加

### v1.0 (rhythm_action_game.html)
- ✅ 基本ゲームシステム
- ✅ 音楽生成機能
- ✅ パーティクルエフェクト

## 📝 ライセンス

このゲームはオープンソースプロジェクトです。自由に改変・配布していただけます。

---

**🎮 Enhanced Beat Jumper で音楽と共に踊ろう！ 🎵**

*Made with ❤️ and Web Audio API*
