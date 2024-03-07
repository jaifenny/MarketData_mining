# MarketData mining
由顧客資料(marketData)，瞭解客戶，顧客資料包含 : CustomerID、 Age、 Gender、Annual Income、 Spending Score Spending Score: 根據顧客行為和購買物品所設
定。
### :small_blue_diamond: **從MarketData的資料中，取女性客戶的兩個欄位: Age、Spending Score 進行客戶分群，使用K-means 分群法，當K = 2 時，列出每一群的中心點。2 個中心點的列表根據中心點的Age數值升冪排序。**
- 
    1. 選取女性客戶的資料
    2. 使用K-means進行分群，K=2，根據中心點的Age數值升冪排序
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age</th>
      <th>Spending Score (1-100)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>29.076923</td>
      <td>78.179487</td>
    </tr>
    <tr>
      <th>1</th>
      <td>42.917808</td>
      <td>37.287671</td>
    </tr>
  </tbody>
</table>
</div>

### :small_blue_diamond: **利用Elbow方法找出K應該設置多少？**
- 
    1. 初始化KMeans模型，嘗試不同的K值，並繪製Elbow圖![](https://github.com/jaifenny/MarketData_mining/blob/main/picture/1.png)

    2. 計算相鄰點之間的SSE差異，k = 4之後的SSE下降幅度變得較緩慢，K 應該設置為4，肘部的確定可能有一些主觀性，因此可能需要根據實際應用情境來進行調整。
     ![](https://github.com/jaifenny/MarketData_mining/blob/main/picture/4.png)

