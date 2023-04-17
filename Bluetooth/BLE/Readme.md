# BLE protocol & software development information

## BLE Protocol detail
  1. Core5.1

  1. Core5.3

## BLE software development (base as nordic52832)

  1. Nordic nRF5 SDK & Softdevice introduction

  * 概要的な説明

      nRF5 SDKはソフト開発を容易するためにNordic社が提供した開発キットです。
    
      Softdeviceは、Nordic社提供したプロトコルスタックです。
    
      基本的に、各SDKはサポートされるSoftdevice含んでおり、そのファイルは **\components\softdevice**フォルダに格納されています。

  * nRf5 SDK各バージョンに関して

     | バージョン | 対応したIC |
     |----------|----------|
     | V9.0~V10  | Only supoort nRF51|
     | V11~V12 | suport nRF51/nRF52 |
     | V13~V17 | only suport nRF52 |
    
      ※1.最新のSDKバージョンを使用することが推奨されています。

      ※2.Nordic社はnRF5 SDK 以外にも特定用途のSDKも提供していますが。ここでは紹介しません。

  * Softdeviceネーミングルール

      Softdeviceには2つプロトコルスタックがあり、BLEとANTです。

      また、BLEはCentral（またはmaster）とPerpheral（またはSlave)の2つロールがあります。
  
      Softdeviceは、上記の区別のためにSxyzの形式の名前を持ちます.
      詳細は以下の通りです。

        x： プロトコルスタックの種類。1：BLE、2：ANT、3:両方
        y:　BLEのロールの種類。1:Perpheral 、2:Central、3：両方
        z： サポートするICの種類。：0：nRF51シリーズ、1:nRF52シリーズ

      ※上位SocのnRF52840向けに、特別の名前S140があります。
      
       52840のFlash容量が大きいため、S140はほぼすべてのプロトコルスタックを含まれています。

    **主に以下の内容を参照すればいいです.** 

    [Nordic nRF5 SDK ＆softdevice \(中国語)](https://www.cnblogs.com/iini/p/9095551.html)

    [Nordic nRF5 SDK & softdevice \(英語)](https://devzone.nordicsemi.com/guides/short-range-guides/b/getting-started/posts/introduction-to-nordic-nrf5-sdk-and-softdevice) 
  2. nRF5 SDKのAPIに関して

     nRF5 SDKは多数の機能を提供していますが、その分APIの構成が複雑で、初心者には非常に混乱する事あります。
    
     個人の経験に基づいた内容ですが、大まかな分類と区別方法を紹介します。
     
  * 分類
    
    - ハードウエアドライバー＆その他機能ライブラリ

      ICのハードウエアドライバーとアプリケーション作成時に簡単使用ため提供したライブラリです。
      
      ※本来Softdevice　APIにも含まれていますが、構成上別ものであり、分けます。
　　　
　　　見分け方法は関数の名前が　**_nrf__**　または **_nrfx__** で始まることです。
    
      但し、例外があります。BLEとANTのプロトコルスタックに関連するライブラリ機能は　**_ble__**　と　**_ant__** で始まります。
      
      BLEとANTのプロトコルスタックに関連する関数はSoftdevice　APIをコールする形になります。以下の図を参照してください。
    　![BLE advertising message sequence](image/BLE_advertising_msg_seq.png)
    
      SDK　APIの詳細は以下のURLを参照してください。

       [nrf5 SDK V17.1.0](https://infocenter.nordicsemi.com/topic/struct_sdk/struct/sdk_nrf5_latest.html) 


    - Softdevice API

      プロトコルスタックのAPIです。

      BLEのプロトコルスタック機能使用する場合、Softdevice　APIをコール必要です。
    
      見分け方法は関数の名前が **_sd__** で始まることです。BLE機能に関連する関数は　**_sd_ble__**で始まります。それ以外Softdevice設定及びSoCライブラリの関数は各自のキーワードが付けます。詳細は下記のURLを参照してください。

       [S132 softdevice V7.31.0 API](https://infocenter.nordicsemi.com/index.jsp?topic=%2Fcom.nordic.infocenter.s132.api.v7.2.0%2Findex.html)


    　
  　
  　
