# ImageJ マクロ集 - 植物画像解析

このリポジトリには、植物画像の解析に使用するImageJマクロが含まれています。

**📖 English version: [README.md](README.md)**

## 概要

このリポジトリには以下の2つのImageJマクロが含まれています：

1. **AreaCalculationExG.txt** - 緑色の葉面積を測定するマクロ
2. **AreaCalculationUsingBOfLabForStem.txt** - 黄色い茎の面積を測定するマクロ

## 必要なソフトウェア

- [ImageJ](https://imagej.nih.gov/ij/) または [Fiji](https://fiji.sc/)

## マクロの使い方

### 準備作業

#### 1. ImageJのインストール
1. [ImageJ公式サイト](https://imagej.nih.gov/ij/)からImageJをダウンロード
2. ダウンロードしたファイルを実行してインストール
3. ImageJを起動

#### 2. マクロファイルのダウンロード
1. このリポジトリからマクロファイルをダウンロード：
   - このリポジトリの`macros`フォルダをクリック
   - `AreaCalculationExG.txt`（緑色葉面積測定用）をダウンロード
   - `AreaCalculationUsingBOfLabForStem.txt`（黄色茎面積測定用）をダウンロード
2. これらのファイルをPCの見つけやすい場所に保存

#### 3. マクロのインストール
1. ImageJを起動する
2. **Plugins** → **Macros** → **Install**をクリック
3. 保存したマクロファイル（`AreaCalculationExG.txt`または`AreaCalculationUsingBOfLabForStem.txt`）を選択
4. マクロがインストールされる

#### 4. 画像の準備
- 解析したい画像を`LeavesImages`（葉用）または`StemsImages`（茎用）フォルダに保存
- 画像には10cmの定規やスケールバーが含まれていることを確認

### 緑色葉面積測定マクロの使用方法

#### 1. マクロの起動
1. **Plugins** → **Macros**をクリック
2. インストールしたマクロ（`AreaCalculationExG`）をクリック
3. マクロが起動する

#### 2. フォルダの選択
1. マクロが起動すると、フォルダ選択ダイアログが表示される
2. 自分のPCに保存した`LeavesImages`フォルダを選択して開く
3. **OK**をクリック

#### 3. 画像処理の実行
フォルダ内の画像がすべて処理されるまで以下の手順を繰り返します：

##### 3-1. 画像の拡大縮小
- フォルダ内の画像が開く
- **Ctrl**を押しながらマウスのホイールを回して画像を拡大縮小する
- 定規の10cmの部分が見やすい大きさになるまで調整

##### 3-2. スケール設定
1. 定規の10cmの部分を見つける
2. 左クリック→ドラッグ＆リリースで10cmの線を引く
3. **OK**をクリックするとスケールが設定される

##### 3-3. ROI（関心領域）の選択
1. 測定対象の葉がすべて入るようなポリゴンを描く
2. 左クリックで頂点を複数作成していく
3. 最初の頂点上で左クリックをしてポリゴンを閉じる
4. **OK**をクリックする

##### 3-4. 閾値調整
1. 自動で閾値が設定され、選択された範囲が赤色になる
2. **Threshold**のスライダーを左右に動かして、葉がなるべく正確に含まれるように閾値を設定する
3. **OK**をクリックする

#### 4. 結果の保存
- `LeavesImages`フォルダ内に測定結果が記録された`green_leaf_area_ExG.csv`ファイルが保存される

### 黄色茎面積測定マクロの使用方法

#### 1. マクロの起動
1. **Plugins** → **Macros**をクリック
2. インストールしたマクロ（`AreaCalculationUsingBOfLabForStem`）をクリック
3. マクロが起動する

#### 2. フォルダの選択
1. マクロが起動すると、フォルダ選択ダイアログが表示される
2. 自分のPCに保存した`StemsImages`フォルダを選択して開く
3. **OK**をクリック

#### 3. 画像処理の実行
フォルダ内の画像がすべて処理されるまで以下の手順を繰り返します：

##### 3-1. 画像の拡大縮小
- フォルダ内の画像が開く
- **Ctrl**を押しながらマウスのホイールを回して画像を拡大縮小する
- 定規の10cmの部分が見やすい大きさになるまで調整

##### 3-2. スケール設定
1. 定規の10cmの部分を見つける
2. 左クリック→ドラッグ＆リリースで10cmの線を引く
3. **OK**をクリックするとスケールが設定される

##### 3-3. ROI（関心領域）の選択
1. 測定対象の茎がすべて入るようなポリゴンを描く
2. 左クリックで頂点を複数作成していく
3. 最初の頂点上で左クリックをしてポリゴンを閉じる
4. **OK**をクリックする

##### 3-4. 閾値調整
1. 自動で閾値が設定され、選択された範囲が赤色になる
2. **Threshold**のスライダーを左右に動かして、茎がなるべく正確に含まれるように閾値を設定する
3. **OK**をクリックする

#### 4. 結果の保存
- `StemsImages`フォルダ内に測定結果が記録された`yellow_area_lab_b.csv`ファイルが保存される

## マクロの特徴

### ExGマクロの特徴
- **ExG指数**: 2G - R - B の計算式を使用
- **緑色検出**: 植物の緑色部分を効率的に検出
- **手動調整**: 閾値を手動で調整可能

### Lab bチャンネルマクロの特徴
- **Lab色空間**: より正確な色分離が可能
- **bチャンネル**: 黄色-青色軸での色分離
- **茎検出**: 黄色い茎部分の検出に特化

## 使用上の注意点

1. **スケール設定**: 必ず10cmの基準線を正確に描画してください
2. **ROI選択**: 解析したい領域のみを選択し、背景を除外してください
3. **閾値調整**: 自動閾値が適切でない場合は、手動で調整してください
4. **ファイル形式**: 対応している画像形式のみ処理可能です

## トラブルシューティング

### よくある問題と解決方法

1. **マクロが実行されない**
   - マクロファイルが正しくインストールされているか確認してください

2. **結果が正しくない**
   - スケール設定が正しく行われているか確認してください
   - ROI選択が適切か確認してください
   - 閾値調整を再確認してください

3. **ファイルが保存されない**
   - 出力フォルダの書き込み権限を確認してください
   - ファイル名に特殊文字が含まれていないか確認してください

## ライセンス

このプロジェクトはMITライセンスの下で公開されています。

## 貢献

バグ報告や機能改善の提案は、IssuesまたはPull Requestsでお願いします。

## 更新履歴

- v1.0.0: 初期バージョン
  - ExGマクロ追加
  - Lab bチャンネルマクロ追加 