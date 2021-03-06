# Digital-Collection-Autocomplete
協助文化部「數位典藏完備計畫」之文物計畫填寫自動化

[![](https://i.imgur.com/siK8VRC.jpg)](https://cryolitez.github.io/Digital-Collection-Autocomplete/)
## Project goal
本服務協助歷史博物館的研究人員，免除手動填寫複製文字到Excel的麻煩

網站不收集也不儲存任何研究人員的成果，僅做重新排序與整合

網站: [Digital-Collection-Autocomplete](https://cryolitez.github.io/Digital-Collection-Autocomplete/)

支援 Chrome, Firefox, IE11

若不想使用網站，可使用[Python script](script_big5.py)於local完成

## How to use the script

1. 首先將文物描述等資訊按照下列格式編寫
```
[文物編號] 文物內容...
31922 胡念祖(1927- )湖南省益陽人，字心原...
31923 胡念祖(1927- )湖南省益陽人，字心原...
...
```
並存成純文字檔，編碼使用 big5。有鑑於公家機關的研究人員多使用Windows和Word填寫資訊，故script預設使用big5讀寫檔案。

2. 將文物資料的excel檔另存成csv

csv結果示意圖

![](https://i.imgur.com/lPL2y9E.png)
```
典藏編號,舊典藏編號,入藏單號,入藏日期,中文品名,英文品名,舊的品名,作者,朝代,件數,來源,原所有人,尺寸,文物類別,說明與詮釋,材質,色彩,表現形式,作品內容,款識,鈐印,裝潢尺寸,裝潢式樣,文物描述,"參考資料（僅限本館出版品）
○○○，《書名》，臺北巿：國立歷史博物館，年代。",GIS資訊（物）　　　（臺灣＋地區名）,,,,GIS資訊（人）,,"備註１(品名建議更改, 需要審查者)",備註２(前面欄位無法填寫原因),負責人
,,,,,,,,,,,,,,,,,,,,,,,,,製作地,出土地,遷徙經過地點,描述內容出現地點,創作者相關地點,收藏者相關地點,,,
31806,,(63)博入字第011號,1974.05.15,燈籠花,,,王濟遠,民國,1,受贈,王濟遠,縱58 橫35.5,國畫,,,,,,,,,,,,,,,,,,,,王曉明
31807,,(63)博入字第011號,1974.05.15,瓜果,,,王濟遠,民國,1,受贈,王濟遠,縱40 橫56.5,國畫,,,,,,,,,,,,,,,,,,,,曉明
```


3. 執行script
```
python script_big5.py [info_path] [csv_path] [result_path]
```

範例如下`python script_big5.py my_content.txt data.csv result.csv `

my_content.csv 為研究員撰寫的文物內容說明的純文字路徑

data.csv  為文物資料的excel轉成csv(步驟2)檔案的路徑

result.csv 為結果輸出路徑

執行完畢後會將文物說明按照文物編號寫入到正確的欄位

4. 複製結果到原文物資料的excel

result.csv
![](https://i.imgur.com/pt3eXJD.png)

將以上結果全選複製貼上到原文物資料excel即可

## Credits
Website designed by html5up.net | @ajlkn
