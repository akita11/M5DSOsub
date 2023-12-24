# M5DSOsub

<img src="https://github.com/akita11/M5DSOsub/blob/main/M5DSOsub.jpg" width="320px">

<img src="https://github.com/akita11/M5DSOsub/blob/main/M5DSOsub_usage.jpg" width="320px">

M5StackBasicを簡易的なオシロにするアダプタです。M5Stackを簡易オシロにするソフトウエアはいくつかります（例えば[M5Stack-ESP32-Oscilloscope](https://github.com/botofancalin/M5Stack-ESP32-Oscilloscope)や[M5Stackオシロスコープ](https://goji2100.com/blog/?p=967)など）。いずれもM5StackのBOTTOM（底板）に出ているアナログ入力(GPIO36/35)を入力として使っています。

M5StackBasicのBOTTOMコネクタにこのアダプタを差し込むことで、これらのソフトウエアを使って、簡易オシロにすることができます。入力保護回路つきで、ショートピン切り替えで1/10アッテネータを使用できます。

※これらの2つのソフトウエアは、ArduinoIDEで使えるバージョンのESP32用ライブラリ(ESP-IDF)では再起動を繰り返す挙動があるようです。[M5Stack-ESP32-Oscilloscopeのほうは、Issueに上がっている修正](https://github.com/botofancalin/M5Stack-ESP32-Oscilloscope/issues/2)を行うことで、この問題を回避できます。


## 使い方

<img src="https://github.com/akita11/M5DSOsub/blob/main/M5DSOsub_attach.jpg" width="320px">

M5StackBasicのBOTTOMのコネクタに、このように接続します。

<img src="https://github.com/akita11/M5DSOsub/blob/main/M5DSOsub_config.jpg" width="320px">

2つのメスソケットがCh1, Ch2の入力端子（と基準電圧のGND）です。ジャンパワイヤ等で測定対象の回路に接続します。

またその横のピン（x10と表記）にショートピンをはめると、各チャンネルの入力信号が10倍に増幅されてM5Stackに与えられます。つまり1/10倍の微小な信号電圧を扱うことができます。

### パルス出力

信号チェック等に使える2つの出力波形がOut1, Out2の２つのピンソケットに出力されています。Out1はGPIO2、Out2はGPIO5（またはJP1のハンダジャンパを切り替えることでGPIO26）に接続されています。


## Author

Junichi Akita (akita@ifdl.jp, @akita11)
