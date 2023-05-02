# AutoEncoder
大学3年生の時に作成した，画像処理用のAutoEncoderモデル及び，Unetのモデル．

# 概要
写真における映り込みを消去するために作ったモデルです.256×256の画像を入力し，出力します．
コードは以下の二つから構成されます．

- オートエンコーダ
- U-net

オートエンコーダーについては，エンコーダ部が4層，デコーダー部が4層で構成される．
エンコーダー部のチャンネル数は3,16,32,64,128と増やし，逆にデコーダー部ではその順で減らす．

U-netについては，差分を学習するためのモデルである．今回，入力画像と出力画像は類似している．そのため，
差分を学習するU-netは有効になると考えた．

学習用データについては，シミュレーションによって映り込みのある画像を作成した．
具体的には，明るさ調整をしたうえで，ガウシアンフィルタをかけたものを，映り込み画像としたうえで，別の画像に足し合わせることで学習が可能．

# 学習例
左から順に，
- 映り込み画像
- モデルの出力
- 正解(映り込みなし画像)
## Auto Encoder
![Autoencoder1](https://user-images.githubusercontent.com/64346532/235559334-c47cadda-7a4b-4e2c-b863-1c5a8ef8f76a.png)

## U-net
![Unet1](https://user-images.githubusercontent.com/64346532/235559352-40c6a567-7d30-4fcd-9479-b291e02d1dd5.png)
