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

### :small_blue_diamond: **從MarketData的資料中，取所有客戶的三個欄位: Age、Annual Income、Spending Score 進行客戶分群，使用K-means分群法，當K = 3時，列出每一群的中心點。3個中心點的列表根據中心點的Age數值升冪排序。**
- 
    1. 選取所有客戶的資料
    2. 使用K-means進行分群，K=3，根據中心點的Age數值升冪排序<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age</th>
      <th>Annual Income (k$)</th>
      <th>Spending Score (1-100)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>32.692308</td>
      <td>86.538462</td>
      <td>82.128205</td>
    </tr>
    <tr>
      <th>1</th>
      <td>40.325203</td>
      <td>44.154472</td>
      <td>49.829268</td>
    </tr>
    <tr>
      <th>2</th>
      <td>40.394737</td>
      <td>87.000000</td>
      <td>18.631579</td>
    </tr>
  </tbody>
</table>
</div>

### :small_blue_diamond: **利用Elbow方法找出K應該設置多少**
- 
    1. 初始化KMeans模型，嘗試不同的K值，並繪製Elbow圖![](https://github.com/jaifenny/MarketData_mining/blob/main/picture/2.png)

    2. 計算相鄰點之間的SSE差異，k = 6之後的SSE下降幅度變得較緩慢，K 應該設置為6，肘部的確定可能有一些主觀性，因此可能需要根據實際應用情境來進行調整。![](https://github.com/jaifenny/MarketData_mining/blob/main/picture/3.png)

### :small_blue_diamond: **承上，K值設置，假設現在有一個行銷活動，透過K-means分群結果進行篩選，選擇一群目標客群，列出此群的中心點。**
- 
    1. 選取所有客戶的資料，使用K-means進行分群，K=6
<div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Age</th>
      <th>Annual Income (k$)</th>
      <th>Spending Score (1-100)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>27.00</td>
      <td>56.66</td>
      <td>49.13</td>
    </tr>
    <tr>
      <th>1</th>
      <td>41.69</td>
      <td>88.23</td>
      <td>17.29</td>
    </tr>
    <tr>
      <th>2</th>
      <td>32.69</td>
      <td>86.54</td>
      <td>82.13</td>
    </tr>
    <tr>
      <th>3</th>
      <td>56.16</td>
      <td>53.38</td>
      <td>49.09</td>
    </tr>
    <tr>
      <th>4</th>
      <td>44.14</td>
      <td>25.14</td>
      <td>19.52</td>
    </tr>
    <tr>
      <th>5</th>
      <td>25.27</td>
      <td>25.73</td>
      <td>79.36</td>
    </tr>
  </tbody>
</table>
</div>

- 群 0: 年輕中產階級
    - 潛在市場策略：這群客戶可能是年輕中產階級，收入中等，且對消費有一定的需求。可以考慮推出吸引年輕人的產品或服務，以及定期的促銷活動。
- 群 1: 高收入低消費
    - 潛在市場策略：高收入但低消費分數可能表示這群客戶對於某些類型的產品或服務不太感興趣。可以著重於了解他們的購物偏好，並通過精心設計的行銷活動來吸引他們。
- 群 2: 年輕高消費群
    - 潛在市場策略：這群客戶可能是年輕且具有高度的消費能力。可以推出高價值、時尚的產品或服務，以及提供獨特體驗的促銷活動。
- 群 3: 中老年群體
    - 潛在市場策略：這群客戶可能需要注重價值的產品或服務，並可能對促銷和優惠感興趣。可以提供老年人常用的商品或服務，同時考慮價格敏感度。
- 群 4: 低收入低消費
    - 潛在市場策略：這群客戶可能是價格敏感型，可以提供具有價值的商品或服務，以及吸引他們的促銷活動。
- 群 5: 年輕高消費群
    - 潛在市場策略：雖然收入較低，但這群客戶有著高度的消費能力。可以提供價格相對較低，但有吸引力的商品或服務，以及針對他們的消費習慣制定促銷計畫。


- 
    2. 這些中心點提供了每個群在年齡、年收入和消費分數上的平均值，透過這些資訊，理解每個群體的特徵，例如，群 2 的中心點顯示年收入相對較高，且消費分數也相對較高，可能代表這是一個較為高價值的客戶群。相反地，群 1 的中心點顯示年收入較高，但消費分數較低，可能需要進一步的分析來理解他們的消費行為。這樣的分析可以幫助定義行銷策略，針對不同群體制定不同的行銷活動。
    3. 實際上，可能需要進一步的市場調查和消費者行為分析，以制定更精細和有效的行銷策略。
 

