# atmacup11

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
