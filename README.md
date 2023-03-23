# game

MediaPipe是一款由Google開發並開源的數據流處理機器學習應用開發框架。它是一個基於圖的數據處理管線，用於構建使用了多種形式的數據源，如視頻、音頻、傳感器數據以及任何時間序列數據。


手部追蹤的MediaPipe流程:

![image](https://github.com/LizhuChen/game/blob/main/img/architecture.png)

由兩個子圖組成，一個用於手部偵測，一個用於手部關鍵點（landmark）計算。 MediaPipe提供的一項關鍵優化是手部偵測器僅在必要時運行，從而節省了大量的計算時間。我們通過從當前Frame計算出的手部關鍵點，推斷出後續影像Frame中的手部位置，而無需在每個Frame上運行手部偵測器。為了增強健壯性，手部追蹤模組產出額外的純量數值，這個數值代表畫面中有手出現且合理對齊的置信程度。僅當置信程度降至某個閾值以下時，手部偵測模型才會重新對整個Frame進行偵測。


分別定義剪刀、石頭、布三種手勢，與電腦隨機對戰

Win:

![image](https://github.com/LizhuChen/game/blob/main/img/win.png)

Lose:

![image](https://github.com/LizhuChen/game/blob/main/img/lose.png)

Draw:

![image](https://github.com/LizhuChen/game/blob/main/img/draw.png)
