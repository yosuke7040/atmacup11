# atmacup11

https://www.guruguru.science/competitions/17/

## todo
 - batch sizeは大きい方が精度いいから、ResNetでサイズでかくするのか、efficientnet-b3でぎりぎりまで攻めるのかどっちがいいんだろう
  - 2つの使い分けは何？
 - BERTする?
  - testdataにpenとかないから後回しでええかな
 - cv値として判断するのはtrainの最終epochでええんかな？ 

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
