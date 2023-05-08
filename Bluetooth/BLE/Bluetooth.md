# Bluetooth 技術概要

## Bluetoothの歴史

 Bluetoothは、デジタル機器用の近距離通信規格の１つである。

 Bluetooth BR/EDR/HS(通称Bluetooth　classic)とBLEから構成される。

 1998年　エリクソン、インテル、IBM、ノキア、東芝の5社でBluetooth SIGを設立し、その後以下の様にBluetooth各バージョン仕様書を発表。

 現在(2023年4月)の最新バージョンは5.4です。

 BLE (Bluetooth Low Energy)はバージョン4.0で追加されました。

 **■沿革**

 | バージョン | 発表時間    |内容概要 | 分類|
 |:-----------|-------------|----------|--------|
 | 1.0       | 1999年7月   |最初のバージョン| Bluetooth Classic(BR/EDR/HS)|
 | 1.1       | 2001年2月   |Bluetoothリリース後、最初に普及したバージョン|^|
 | 1.2       | 2003年11月  |2.4Ghz帯域の無線LAN(WIFI：IEEE 802.11/b/g)などとの干渉対策|^  |
 | 2.0       | 2004年11月  |最大速度3Mbpsに切り替えるEDR(Enhanced Data　Rate)を追加|^  |
 | 2.1       | 2007年3月　 |ペアリングが簡略化され、近距離無線通信の Near Field Communication (NFC) に対応した。マウスやキーボードなどのスリープ時間が多い機器のバッテリーを最大で5倍延長できる「Sniff Subrating」機能を加えた。| ^  |
 | 3.0       | 2009年4月　 |Protocol Adaptation Layer (PAL) とGeneric Alternate MAC/PHY (AMP) によって無線LAN規格IEEE 802.11のMAC/PHY層の利用が可能となり、最大通信速度が24 Mbpsとなる High Speed (HS) がオプションで追加できるようになった。また、電力管理機能を強化して省電力性を向上させた。|^  |
 | 4.0       |　2010年6月　|従来のBLuetooth classic(BR/EDR/HS)に加えて、BLE追加|Bluetooth Classic(BR/EDR/HS) + BLE|
 | 4.1       | 2013年12月|Bluetooth Low Energy にモバイル端末向け通信サービスの電波との干渉を抑える技術、データ転送の効率化、自動の再接続機能、直接インターネット接続できる機能、ホストとクライアント同時になれる機能が追加された|^|
 |　4.2　|　2014年12月|Bluetooth Low Energy に Data Packet Length Extension を追加し、通信速度（アプリケーションスループット）が260 kbpsから650 kbps[20]に2.5倍高速化。Bluetooth Low Energy が IPv6/6LoWPAN でインターネット接続できるようになる|^|
 | 5.0 | 2016年12月|Bluetooth Low Energy のデータレートが2 Mbps, 1 Mbps, 500 kbps, 125 kbpsになり、2 Mbpsおよび1 Mbpsは従来通り到達距離が100 m、125 kbpsは到達距離が400 mとなった|^|
 |5.1 | 2019年1月 |ペアリングされているBluetooth機器の方向を探知する機能が追加された。|^|
 |5.2 |2020年1月 |LE Audio規格の追加を含む複数の改良。|^|
 |5.3 |2021年7月 |消費電流改善|^|
 |5.4 |2023年1月31日|PAwR/PAB/ESL追加|^|

**■ プロファイル**

|プロファイル　　|説明|
|------|-----|
|***A2DP(Advanced Audio Distribution Profile)***|音声をレシーバー付きヘッドフォン（またはワイヤレススピーカー）に伝送するためのプロファイル。（HSP/HFP異なり、ステレオ音声・高音質となる）
|AVRCP(Audio/Video Remote Control Profile)|AV危機のリモコン機能を実現するためのプロファイル|
|BIP(Basic Imaging Profile)|静止画像を転送するためのプロファイル|
|BBP(Basic Print Profile)|プリンタへ転送・印刷するためのプロファイル|
|DUN(Dial-Up　Networking Profile)|携帯電話・PHSを介してインターネットにダイヤルアップ接続するためのプロファイル|
|FTP(File Transfer Profile)|パソコン同士でデータ転送を行うためのプロファイル。コンピューターネットワークなどで用いられるファイル転送プロトコルのFTPは無関係|
|GAP(Generic Access Profile)|機器の接続/認証/暗号化を行うためのプロファイル。|
|HCRP(Hardcopy Cable Replacement Profile)|プリンターへの出力を無線化するためのプロファイル。|
|HDP(Health Device Profile)|健康管理機器同士を接続するためのプロファイル。|
|***HFP(Hands-Free Profile)***|車内やヘッドセットでハンズフリー通話を実現するためのプロファイル。HSPの機能に加え、通信の発信・着信機能を持つ。|
|HID(Human Interface Device Profile)|マウスやキーボードなどの入力危機を無線化するためのプロファイル|
|***HSP(Headset Profile)***|Bluetooth搭載ヘッドセットと通信するためのプロファイル。モノラル音声の受信だけではなく、マイクで双方向通信する｜
|OBEX(Object Exchange)|オブジェクト交換（OPP、BIP、FTP、SYNC）用いる認証方式の一つ。データ転送プロファイルの人で、実装しているとデータ送受信時にOBEX認証パスキーの入力を接続相手に要求する|
|OPP (Object Push Profile)|名刺データの交換などを行うためのプロファイル。|
|PAN (Personal Area Network Profile)|小規模ネットワークを実現するためのプロファイル。|
|PBAP (Phone Book Access Profile)|電話帳のデータを転送するためのプロファイル。|
|SDAP (Service Discovery Application Profile)|他のBluetooth機器が提供する機能を調べるためのプロファイル。|
|SPP (Serial Port Profile)|Bluetooth機器を仮想シリアルポート化するためのプロファイル。|
|SYNC (Synchronization Profile)|携帯電話・PHSやPDAと、PCとの間で、スケジュール帳や電話帳のデータ転送を行い、自動的にアップデートするためのプロファイル。|


これらプロファイルのうち、DUN/FTP/HID/OPP/HSP/HFP/A2DP/AVRCPなどの使用頻度が高い。GAPやSDAPのような下位層のものは実装されていても意識されないことが多い。また、プロファイルによっては実装されていてもほとんど使われていないものもある。

■他の注意事項

・BluetoothはBR/EDR(通称Bluetooth　classic)だけではなく、BLEも含まれている。
　特にBluetooth4.0以降、BLEのみになる事はなく、BR/EDRからBLEを追加である。

・Bluetooth BR/EDR(通称Bluetooth　classic)とBLEはPHY Layerが違うため、お互いに通信できない。但し、一部ICメーカーはdual mode(Bluetooth classic とBLE両方対応)モジュール開発されています。

  ※Dual modeはBluetooth　classicとBLEの通信はできないですが、モジュール内でBluetooth　classicデータとBLEの間でデータ転送など処理できます。時間分けてclassic通信とBLE通信で利用できます。よくある例はスマートフォンです。

・カーオーディオなどよく利用されているはBluetooth Classic(A2DP/HFP/HSP)になります。（2023年4月時点、これから技術発展により変化する可能性もある）



