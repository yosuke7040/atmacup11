# atmacup11

# 振り返り  
 - 今回はエポック50とかでやってたけど500とかくらいまで回した方がよかったらしい
 - imageNet(Vit,eff-b3,などなど)で予測したのをLightGBMでスタッキングしたらよかった
 - 予測値を0~3丸め込むのやってなかったな・・・

https://www.guruguru.science/competitions/17/

## todo
 - batch sizeは大きい方が精度いいから、ResNetでサイズでかくするのか、efficientnet-b3でぎりぎりまで攻めるのかどっちがいいんだろう
  - 2つの使い分けは何？
 - BERTする?
  - testdataにpenとかないから後回しでええかな
 - cv値として判断するのはtrainの最終epochでええんかな？ 
 - [Supervised Contrastive Learning (：SupContrast)](https://www.guruguru.science/competitions/17/discussions/1775e171-2e66-4823-a3de-943381339fd4/)
 - resnet18, resnet34, efficientnet-b0, b3~
 - [simsiam](https://www.guruguru.science/competitions/17/discussions/a39d588e-aff2-4728-8323-b07f15563552/)

## notebook
|name|content|cv|LB|
|----|-------|----|----|
|nb001|講座1のシンプルバージョンそのまま|0.9483|0.9328|
|nb002|nb001をベースにモデルをefficientnet-b3||0.9365|
|nb003|google colabでefficientnet-b3||0.8519|
|nb004|EDA写経|||
|nb005|初心者講座2回目|0.8345||
|nb006|nb003をそのままモデルだけresnet18||0.9693|
|nb007|SimSiam|||
|nb008|初心者講座2回目のでKFoldからStatifiedGroupKFold|0.4705||
|nb009|nb001のをKFoldからStatifiedGroupKFoldに|0.9410|0.9514|
|nb010|講座1_シンプルバージョンにsimsiamで事前学習|0.9359|0.9075|
|nb011|nb010をベースにTTAしてみる|||
|nb012|nb003をベースにSimSiamとTTA|0.8797|0.8963|
|nb013|nb003をベースにepoch増やす|0.8933|0.8486|
|nb014|nb003をベースにepoch増やす,Data Augmentationなくす|0.|0.|
|nb015|nb014をベースにeff-B0|0.9370|0.8613|

## Log
### 20210710
 - とりあえず初心者講座から受講中
 - 画像は初めてやるけど、なんとか頑張るぞ
 - 休日出勤疲れる

### 20210714
 - ### nb001 
  - 講座1のシンプルバージョンそのまま[url](https://www.guruguru.science/competitions/17/discussions/a7161489-cb5a-4254-bf17-7c66aa53d334/)
 - ### nb002 
  - nb001をベースにモデルをefficientnet-b3にしてみた
  - LBは下がりました
 - ### nb003
  - ResNet34と同じbatch sizeでやるとメモリに乗りきらないのでgoogle colabでやってみた。nb002とbatch size以外は一緒
  - num_workers=2にしたせいか、学習時間半端ねえ
  - めちゃくちゃスコアに影響出るやん
 - ### nb004
  - EDA写経
 - ### nb005
  - 初心者講座2回目の写経
 - ### nb006
  - nb003をそのままモデルだけresnet18でしてみた。eff-b3よりbatchサイズでかくした
  - resnet18dがうまく使えない
 - ### nb007
  - SimSiamの写経

### 20210720
 - ### nb008
  - KFoldからStatifiedGroupKFoldにしたが、CV下がりすぎてリークしてます？
 - ### nb009
  - nb001のをKFoldからStatifiedGroupKFoldに
  - CVは上がったがLBは下がった
 - ### nb010
  - SimSiamで事前学習させたのを読み込んで予測
  - model:resnet18, batch_size:256, epochs:50
