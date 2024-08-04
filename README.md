# Lightning-Alert
使用したパーツ  
・AS3935:雷センサーモジュール　　参考）秋月電子さんの販売コード 108685  
・M5Stamp Pico:センサーと接続するマイコンです。今回はESP32マイコン搭載のM5Stamp Picoを使用。  
・ユニバーサル基板:使用する筐体に適したサイズの基板を使用します。今回は配線も少ないためユニバーサル基板を使用。  
・パッシブブザー:警告音を鳴らすために使用。  
・配線:各部品間を接続する配線です。エナメル線などの適当なものを準備。  
・電解コンデンサ:セラミックコンデンサ：電源ノイズの除去用に使用。  
・筐体：ハンディサイズでデザインも良く使いやすいタカチ製のハンドタイププラスチックケース LC135-M3-W を使用。  
・単4電池:M5Stampへの入力電圧は1.5V×3本の4.5Vとしました。  

動作シーケンス  
・雷センサーとM5stamp picoはI2Cで通信します。  
・レジスタの設定が完了後、M5stamp picoは”light sleep mode”に入ります。  
・センサーが雷を検知するとセンサーのIRQ端子がHighになり、M5stamp picoをGPIO33経由で起こしにいきます。  
・GPIO25を使用して、雷までの距離に従って、3種類のブザー音を鳴らします。  
・ブザー終了後、再度 light sleep mode に入ります。  

![image](https://github.com/user-attachments/assets/a6ec59df-30e4-43bb-b85f-1564e31756dc)

