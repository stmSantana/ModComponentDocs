# Mod作成自分用メモ

## GEAR作成
- ModComponentのアイテム作成時、PrefabをUnity editorでレイヤーを17（GEAR用）にする事。
- 子オブジェクトを持つ場合、親オブジェクトにColliderを設定する。
その際、レイヤーを0(Default)から17(Gear)に変更しないとロード後にプレイヤーとコライダーが衝突するようになる。レイヤー17にしておけばロード後もGEARとしてすり抜けてくれる。衝突させたい場合、親子のレイヤーをDefaultにして、親子ともにコライダーを追加しておく。
- （Modメモ） 子レイヤーを持つ場合、子レイヤーからはコライダーを削除しておく。子にコライダーが残っている場合、「shelter ModのChangeLayerGameObj」の動作後（レイヤー18（Container）などにした後）、マウスで検出できない。このためにDLLを作成して、子オブジェクトのレイヤーをDefault(0)に変更すること。
- 親（レイヤー00 Default　、Collider有り）、子（レイヤー00 Default 、Collider有り）……　プレイヤーと衝突する
- 親（レイヤー17 Gear　 　、Collider有り）、子（レイヤー17 Gear　 　、Colliderなし）……　プレイヤーがすり抜ける
- 親（レイヤー18 Container、Collider有り）、子（レイヤー00 Default 、Collider有り）……　プレイヤーと衝突する
