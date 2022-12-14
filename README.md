# QTS_Knapsack_problem

## Knapsack Problem

##### The knapsack problem is a problem in combinatorial optimization: Given a set of items, each with a weight and a value, determine the number of each item included in a collection so that the total weight is less than or equal to a given limit and the total value is as large as possible.

### Problem Definition

* Given
  * There are ten for each item
  * The maximum capacity of the knapsack is 275
  * | Item    | A   | B   | C   | D   | E   | F   | G   | H   | I   | J   |
    | :-----: |:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
    | Weight  | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  |
    | Value   | 6   | 7   | 8   | 9   | 10  | 11  | 12  | 13  | 14  | 15  |

* Find
  * a set of items

* Best known solution
  * Overall weight equal to 275
  * Overall value (fitness) equal to 620
  * | Item    | A   | B   | C   | D   | E   | F   | G   | H   | I   | J   |
    | :-----: |:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
    | #       | 10  | 10  | 10  | 10  | 10  | 10  | 8   | 0   | 1   | 0   |


---

### Program


Statistic.h & Statistic.cpp: 用於統計執行 QTS 數回合的結果。 


---


### Encoding

每個個體有以下 data：
 * int sol[SEQUENCE_LENGTH];
 * int weight;
 * int value;
 * int fitness;

**SEQUENCE_LENGTH** 為 100 個 bit，其中
 * 每個 bit 之編碼範圍 ∈ **[0,1]**


---


### Argument

##### QTS.h
* **ROUND:** 設定欲跑幾個回合, e.g., 100
* **POPULATION_SIZE:** 設定族群大小, e.g., 4
* **KNAPSACK_SIZE:** 背包大小（275）
* **SEQUENCE_LENGTH:** 序列長度（100）
* **DEBUG_MODE:**
    * 0: 不將執行過程的細節印出
    * 1: 將執行過程的細節印出
    
* **EACH_ROUND_RESULT:** 
    * 0: 不將每個回合的結果印出
    * 1: 將每個回合的結果印出
    


##### Statistic.h
* **STATISTICAL_ROUND:** 設定欲跑幾個回合



---



### Result

相較於 GA ，QTS 反而效率低落，測試了幾次都沒有比較好的解，


幾次的測試結果如下：



```
==================== STATISTIC ====================
Statistical round: 1
Round: 500
Population: 800
+----------+----------+----------+----------+----------+----------+----------+
|Overweight|Overweight| Best case|   Avg.   |   Best   |   Best   | Best case|
|   count  |   rate   |  weight  |   value  |   value  |  fitness |   count  |
+----------+----------+----------+----------+----------+----------+----------+
|        0 |   0.00 % |      275 |   590.00 |      590 |      590 |        0 |
+----------+----------+----------+----------+----------+----------+----------+
1	1	1	1	1	1	0	1	0	1	
1	1	1	0	1	1	1	1	0	1	
1	0	1	1	1	1	1	1	1	0	
1	0	1	1	1	1	1	1	1	1	
0	1	1	0	1	1	1	1	1	0	
1	1	1	1	1	1	1	1	1	1	
1	1	0	1	1	1	1	1	0	1	
1	1	1	0	0	0	1	0	1	0	
0	0	0	0	0	0	0	0	0	0	
0	0	0	0	0	0	0	0	0	0	
A: 8  B: 8  C: 8  D: 9  E: 7  F: 10  G: 8  H: 5  I: 0  J: 0  
Time taken: 418.22 s
```

```
==================== STATISTIC ====================
Statistical round: 1
Round: 500
Population: 300
+----------+----------+----------+----------+----------+----------+----------+
|Overweight|Overweight| Best case|   Avg.   |   Best   |   Best   | Best case|
|   count  |   rate   |  weight  |   value  |   value  |  fitness |   count  |
+----------+----------+----------+----------+----------+----------+----------+
|        0 |   0.00 % |      271 |   586.00 |      586 |      586 |        0 |
+----------+----------+----------+----------+----------+----------+----------+
1	1	0	1	1	1	1	1	1	1	
1	1	1	1	1	1	1	1	1	0	
1	1	0	1	1	1	0	1	1	1	
1	1	1	1	1	1	1	1	0	1	
1	1	1	1	1	0	0	0	1	1	
1	0	0	0	1	1	1	1	1	1	
0	1	1	0	0	0	1	1	1	1	
1	1	0	1	1	0	1	1	0	1	
1	0	0	0	0	0	0	0	0	0	
0	0	0	0	0	0	0	0	0	0	
A: 9  B: 9  C: 8  D: 9  E: 7  F: 7  G: 6  H: 7  I: 1  J: 0  
Time taken: 183.42 s
```

```
==================== STATISTIC ====================
Statistical round: 1
Round: 5000
Population: 50
+----------+----------+----------+----------+----------+----------+----------+
|Overweight|Overweight| Best case|   Avg.   |   Best   |   Best   | Best case|
|   count  |   rate   |  weight  |   value  |   value  |  fitness |   count  |
+----------+----------+----------+----------+----------+----------+----------+
|        0 |   0.00 % |      275 |   585.00 |      585 |      585 |        0 |
+----------+----------+----------+----------+----------+----------+----------+
1	1	1	0	0	1	1	1	1	1	
1	1	0	1	1	1	1	1	1	1	
0	1	1	0	1	1	1	1	1	1	
0	1	1	1	1	1	1	1	1	1	
1	1	0	1	0	1	1	0	1	1	
1	1	0	1	0	0	0	1	0	1	
1	1	0	1	0	1	1	0	1	0	
1	1	1	1	1	1	1	0	0	1	
1	0	1	0	0	0	0	0	0	0	
0	0	0	0	0	0	0	0	0	0	
A: 8  B: 9  C: 8  D: 9  E: 7  F: 5  G: 6  H: 8  I: 2  J: 0  
Time taken: 343.42 s
```

```
==================== STATISTIC ====================
Statistical round: 1
Round: 10000
Population: 50
+----------+----------+----------+----------+----------+----------+----------+
|Overweight|Overweight| Best case|   Avg.   |   Best   |   Best   | Best case|
|   count  |   rate   |  weight  |   value  |   value  |  fitness |   count  |
+----------+----------+----------+----------+----------+----------+----------+
|        0 |   0.00 % |      275 |   575.00 |      575 |      575 |        0 |
+----------+----------+----------+----------+----------+----------+----------+
0	1	0	1	0	0	1	1	1	0	
1	1	1	1	0	1	1	1	0	1	
1	1	1	0	1	1	1	1	1	0	
1	1	1	1	1	1	1	1	1	1	
0	0	1	1	1	0	1	1	0	1	
1	0	1	1	1	0	1	1	1	1	
1	1	0	1	0	1	1	1	1	1	
0	1	0	1	1	1	1	0	1	1	
0	0	0	0	0	0	0	0	0	0	
0	0	0	0	0	0	0	0	0	0	
A: 5  B: 8  C: 8  D: 10  E: 6  F: 8  G: 8  H: 7  I: 0  J: 0  
Time taken: 574.44 s
```

```
==================== STATISTIC ====================
Statistical round: 10
Round: 100
Population: 100
+----------+----------+----------+----------+----------+----------+----------+
|Overweight|Overweight| Best case|   Avg.   |   Best   |   Best   | Best case|
|   count  |   rate   |  weight  |   value  |   value  |  fitness |   count  |
+----------+----------+----------+----------+----------+----------+----------+
|        0 |   0.00 % |      275 |   583.70 |      595 |      595 |        0 |
+----------+----------+----------+----------+----------+----------+----------+
1	1	1	1	1	1	1	1	1	1	
1	1	1	1	0	1	1	1	1	0	
1	1	1	1	1	1	1	1	1	0	
1	1	0	1	1	1	1	1	1	1	
1	1	1	0	0	1	1	0	1	0	
1	1	1	0	0	1	1	0	1	1	
0	1	1	1	1	0	1	1	0	1	
1	0	0	1	1	1	1	1	0	1	
0	1	0	0	0	0	0	0	0	0	
0	0	0	0	0	0	0	0	0	0	
A: 10  B: 8  C: 9  D: 9  E: 6  F: 7  G: 7  H: 7  I: 1  J: 0  
Time taken: 113.66 s
```

```
==================== STATISTIC ====================
Statistical round: 10
Round: 100
Population: 200
+----------+----------+----------+----------+----------+----------+----------+
|Overweight|Overweight| Best case|   Avg.   |   Best   |   Best   | Best case|
|   count  |   rate   |  weight  |   value  |   value  |  fitness |   count  |
+----------+----------+----------+----------+----------+----------+----------+
|        0 |   0.00 % |      275 |   586.60 |      600 |      600 |        0 |
+----------+----------+----------+----------+----------+----------+----------+
1	1	1	1	1	1	1	1	1	1	
1	1	1	1	1	1	0	1	1	1	
1	1	1	1	1	1	1	1	0	1	
1	1	1	0	0	1	1	1	1	1	
1	1	1	0	1	1	1	1	0	1	
0	0	1	0	1	1	1	1	1	1	
1	0	1	0	1	1	0	1	1	0	
1	0	1	1	1	1	1	0	1	1	
0	0	0	0	0	0	0	0	0	0	
0	0	0	0	0	0	0	0	0	0	
A: 10  B: 9  C: 9  D: 8  E: 8  F: 7  G: 6  H: 8  I: 0  J: 0  
Time taken: 206.92 s
```



```
==================== STATISTIC ====================
Statistical round: 1
Round: 500
Population: 300
+----------+----------+----------+----------+----------+----------+----------+
|Overweight|Overweight| Best case|   Avg.   |   Best   |   Best   | Best case|
|   count  |   rate   |  weight  |   value  |   value  |  fitness |   count  |
+----------+----------+----------+----------+----------+----------+----------+
|        0 |   0.00 % |      275 |   615.00 |      615 |      615 |        0 |
+----------+----------+----------+----------+----------+----------+----------+
1	1	1	1	1	1	1	1	1	1	
1	1	1	1	1	1	1	1	1	1	
1	1	1	1	1	1	1	1	1	1	
1	1	1	1	1	1	1	1	1	0	
1	1	1	1	1	1	1	1	1	1	
1	1	1	1	1	1	1	0	1	0	
1	1	1	1	1	0	1	0	0	1	
0	0	1	1	1	0	1	0	0	0	
0	0	0	0	0	0	0	0	0	0	
0	0	0	0	0	0	0	0	0	0	
A: 10  B: 10  C: 10  D: 9  E: 10  F: 8  G: 7  H: 4  I: 0  J: 0  
Time taken: 170.25 s
```
