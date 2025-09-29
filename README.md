# 最背面に配置 AviUtl ExEdit2 スクリプト

下のレイヤーにあるオブジェクトでも，フレームの最背面に配置する AviUtl ExEdit2 スクリプトです．

[ダウンロードはこちら．](https://github.com/sigma-axis/aviutl2_script_Layback/releases)

<img width="580" height="180" alt="フレームの最背面にテキストオブジェクトを置く例" src="https://github.com/user-attachments/assets/369b88f6-bfbe-447e-89a6-24d37b836a6c" />

##  動作要件

- AviUtl ExEdit2

  http://spring-fragrance.mints.ne.jp/aviutl

  - `beta13` で動作確認済み．

## 導入方法

以下のフォルダのいずれかに `最背面に配置.anm2` をコピーしてください．

1.  スクリプトフォルダ
    - AviUtl2 のメニューの「その他」 :arrow_right: 「アプリケーションデータ」 :arrow_right: 「スクリプトフォルダ」で表示されます．
1.  (1) のフォルダにある任意の名前のフォルダ

初期状態だと「フィルタ効果を追加」メニューの「配置」に追加されています．
- 「オブジェクト追加メニューの設定」の「ラベル」項目で分類を変更できます．

##  使い方

下のレイヤーにあるけどフレームの最背面に置きたいオブジェクトに，「最背面に配置」のフィルタ効果を追加してください．

他のフィルタ効果との順序は影響しないことが多いですが，一部のフィルタ効果は影響します．そういったフィルタ効果よりも ***前に*** 「最背面に配置」がかかるようにしてください．

- 影響するフィルタ効果は，直接フレームバッファに描画したり，スクリプトで引数なしの `obj.effect()` を呼ぶものなどです．

  「ランダム配置」や「粒子化」などが当てはまります．

一部の条件下ではこのスクリプトが適用できなかったり，正しい描画・動作にならないことがあります．[\[詳細\]](#既知の問題)

##  パラメタの説明

ありません．

##  既知の問題

1.  1つのオブジェクトに対してこのフィルタ効果を複数回適用すると，元の背景画像が消えてしまい正しい描画になりません．グループ制御なども含めて複数回かけてしてしまわないように注意してください．

1.  カメラ制御下のオブジェクトにはこのスクリプトは使えません．

1.  一部のカスタムオブジェクト (`.obj2` ファイルのスクリプトによるオブジェクト) には適用しても効果がないか，正しい描画になりません．

    標準スクリプトだと，次のカスタムオブジェクトには不適です:
    - 走査線
    - レンズフレア
    - 雲
    - 星
    - 雪
    - 雨
    - ランダム小物配置(カメラ制御)
    - ライン(移動軌跡)
    - フレア
    - 水面

    内部的にはこれらのカスタムオブジェクトは，直接フレームバッファに描画したり，スクリプトで引数なしの `obj.effect()` を呼んでいます．

1.  このスクリプトの後続のフィルタ効果に，個別オブジェクト化するものが含まれている場合など，一定の条件下でプレビュー画面のフォーカス枠の表示が消えることもあります (正確な条件は不明).

## 改版履歴

- **v1.00 (for beta13)** (2025-09-29)

  - 初版．


## ライセンス

このプログラムの利用・改変・再頒布等に関しては Unlicense ライセンスに従うものとします．

---

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors
of this software dedicate any and all copyright interest in the
software to the public domain. We make this dedication for the benefit
of the public at large and to the detriment of our heirs and
successors. We intend this dedication to be an overt act of
relinquishment in perpetuity of all present and future rights to this
software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to <https://unlicense.org>


#  連絡・バグ報告

- GitHub: https://github.com/sigma-axis
- Twitter: https://x.com/sigma_axis
- nicovideo: https://www.nicovideo.jp/user/51492481
- Misskey.io: https://misskey.io/@sigma_axis
- Bluesky: https://bsky.app/profile/sigma-axis.bsky.social
