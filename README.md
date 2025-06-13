# ICM-Project
This repository contains materials related to the course **Introduction to Computational Mathematics** at NTU.

* ICM_Project.ipynb: the final project for the course
* Project Idea.pdf: the file came from https://github.com/tobydriscoll/fnc-extras/blob/master/projects/rbf/rbf.pdf

Note: the programming language is Python, and the environment is Google Colab.

## Project Background：
由於這是計算數學導論的Project，所以我所嘗試去做的主題也是希望和上課內容有所相關。根據老師在課程網站上提供的網頁，我瀏覽了一番後決定做RBF插值，因為它需要用到第二章的知識（解線性方程組），實際做了這個Project之後，感覺也跟第五章的知識（插值）有所呼應。除此之外，RBF插值在應用
層面上也有不少用途，像是往高維度去做推廣，可以應用於電腦影像、機器學習或微分方程。

## Project Objectives with Importance and Novelty
### What are you trying to do? Articulate your objectives using absolutely no jargon.
將RBF方法應用於地理數據（𝑓(𝑥𝑖,𝑦𝑖)=𝑧𝑖，X & Y 代表平面上的位置，Z 代表高度），構造出合理的內插模型，並且生成看起來合理的結果


### How is it done today, and what are the limits of current practice?
大部分都還不錯，不過如果輸入的點數據過少或分佈不均，生成的等高線可能缺乏細節，無法準確反映實際情況

### What's new in your approach, and why do you think it will be successful?
有關函數的建構以及一些像是收斂相關的部分，都類似於計算數學導論上課的想法。比較新穎（這裡指的新穎是指就我的背景知識來做對比）的部分就是應用的部分，不過也是使用現有的函式庫來輔助。主要Project還是圍繞在理解一個插值法的建構、收斂，與其應用。成功的原因如上所述，大眾可以更容易親進大數據

### Who cares?
想對大數據資料作分析的人，一般民眾也可以透過數據生成的圖像觀察地理、氣候變化

### If you're successful, what difference will it make?
人們針對大數據可以不需要每一筆資料都瀏覽過，就可以一窺資料的樣貌（資料生成圖像），也與這門課所追求的估計（approximation）有所呼應

### What are the risks and the payoffs?
風險：可能別人有更好的想法，甚至是已經公開的資訊，是我不知道的
報酬：得到學分、認識多一種之前不認識的插值法並應用Python圖像化


## Project Deliverable
### List the expected outputs, e.g. an algorithm, a dataset, app, white paper etc?  
（Script 1 ~ Script 3 與In the octopus’ garden要求前三項相同）
* Script 1 ：先將 𝑦 固定住，探討一維input的情況。利用土法煉鋼的方式觀察 𝑢𝑖(𝑥,𝑦) for distinct 𝑖 的樣貌，並且觀察原始函數和插值函數的誤差
* Script 2 ：探討二維input的情況。也是利用土法煉鋼的方式生成一張表，資訊包含不同的n (取點數量)在不同的點原始函數和插值函數的誤差，以及條件數(condition number)的變化
* Script 3 ：與Script 2的流程相同，只是換成另一個shape function
* RBF interpolation 函數建構：將參考資料提及的RBF interpolation模型轉換成Python Code
* Application - higher dimensions：  
First Block：使用現成的scipy.interpolate.Rbf函數以及隨機生成(x, y)資料來生成一張等高線圖  
Second Block：利用自己寫的RBF函數以及隨機生成(x, y)資料來生成一張等高線圖

## Project Approach
### Describe the steps you would take for the project.

1. 根據參考資料，構造（應用於特定問題的）RBF interpolation，並且觀察些許點上原始函數和RBF插值的值與誤差
2. 增加n（=number of nodes）的數值至 100 ~ 1000 量級，同樣地，觀察些許點上原始函數和RBF插值的值與誤差
3. 更換不同的形狀函數（shape function），重複第二點觀察有何變化
4. 熟練和觀察此插值法後，做一個程式版本的通式
5. 往應用層面做推展，手上沒有資料，就用NumPy中的隨機函數生成data，並且生成等高線圖

## Project Challenges
### 資料稀疏性與分佈問題
當輸入的數據點稀疏或分佈不均時，生成的等高線可能缺乏細節，難以準確地反映真實情況

## Reference
* Textbook: [Fundamentals of Numerical Computation (online version)](https://tobydriscoll.net/fnc-julia/home.html)
* Idea of Project: [In the octopus’ garden](https://github.com/tobydriscoll/fnc-extras/blob/master/projects/rbf/rbf.pdf)



