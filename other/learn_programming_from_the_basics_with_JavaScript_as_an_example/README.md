# [目錄](../../) >> [雜談篇](../) >> 從基礎學起程式（以 JavaScript 為例）

> 

---

# 從基礎學起程式（以JavaScript為例）

## 前言
「一切都是工程問題，都是要你找一種思考模式去解決問題。」

「數學真的是寫程式的外掛，切記學先好數學。」

### 如何選擇第一門你專研的程式語言
不論你是否已經開始接觸程式，首先你得要先了解一門程式語言，並將其鑽研到透徹，在此也推薦幾個語言適合新手入門的程式語言，如：C#、JavaScript、Python 等...。

至於為什麼我要推薦這些語言，而不是先推薦 C、C++ 呢？其實 C 或是 C++ 在新手階段時對於記憶體操作與管理上得要有計算機架構的基本認知，且一些庫也是要理解其設計目的，才比較容易學習。

### 以下為碎碎念，可以直接跳過：

像是C語言，我得要搞清楚的是這語言被設計的用途就是來做系統(請參照UNIX系統)，而其設計概念都是以方便底層與系統上控制來進行設計，如果你們有幸學了 Verilog 與 VHDL 等硬體描述語言，在看看 C 語言實現電路控制的書籍、作業系統的書籍、Jserv 的影片，你將發現 C 語言中的 Macro 與各指針的用途與設計目的。

而 C++，C++ 11後的標準（C++ 14、C++ 17 等）已經定義了各種神奇功能的實現，當然一般初學者完全用不到的，也許新手可以試到 C++ 的物件導向，但更進階的迭代器控制與設計、匿名模板與進階應用、甚至直接調用 algorithm 庫等，還是要有基本資料結構與物件導向的基礎，最好也是要對於系統架構上有一定的了解。

所以，在此推薦的程式語言都是一些不必刻意思考底層實現，你只需要當作下面的系統是個理想系統，也不容易發生 string to float 型態轉換錯誤等情況，你只需要專注於簡單的學習基礎語法、流程控制以及你要做的功能。

而像是 JavaScript 或是 Python 等直譯語言，相較於 C 與 C++ 編譯式語言而言，在撰寫與 DeBug 上相對容易（除非你踩到的是 JavaScript 神奇的Bug）

##  了解語言的歷史
在了解任何的程式語言時，我們得先了解這個語言是為了做什麼而開發的？我們要從程式語言的設計者角度是切入，了解該語言的設計者設計這語言的目的與設計上的思考方式。

同時我們也得了解這個語言在現階段的應用為何？。

首先我們了解 JavaScript 的程式語言歷史，基本上得要回溯到 Netscape 的那個年代，JavaScript 原本是被設計用於網頁上的輔助語言，

後來再不斷的前端語言廝殺下，JavaScript 因為他的方便撰寫與等特性而活了下來並成為通用的語言，嗯...你說有哪些被殺掉的前端語言...，望向微軟以不支援的 VBscript 與快要被取消支援 Flash 的 ActionScript。

而近幾年來也有人將 JavaScript 搞到後端上，也就是我們在 Server 上常見的 node.js，同時為了讓 node.js 能管理我們使用的函式庫，也有了像是 npm 與 yarn 等套件管理程式。

而套件管理程式就像是，當你想做一個專案時，你會使用一些已經寫好的函式庫，並 call 那些函數來避免重複造輪子。

在當年和 JS
## 安裝程式語言與相對應開發環境與工具
### 1. 說明
首先我們得知道，我們在電腦中所用的程式大多都是已經編譯好的執行檔或是或是打包好的批次檔，而我們現在要做的是寫程式，大部分情況下你的電腦系統都不會預先裝好開發工具，這意謂著這些工具你得要自己安裝。

### 2. 安裝 JavaScript 與 npm
但在此幸運的是 JavaScript 是已經屬於使用者端的瀏覽器的一部分功能，如：Chrome、FireFox等瀏覽器上都能直接執行。

但在此，為了未來想對於 JavaScript 了解更加進步，就可以安裝 node.js 與 npm，到 [此連結](https://nodejs.org/zh-tw/download) 就就可以下載。


當然在此筆者以不客觀的角度，直接推薦你們去使用 Linux 系統（如果你們是 Mac 使用者請繼續使用 Mac），基本上像是 Linux 系統對於開發者比較友善。

像是安裝上，如果你是用 Arch Linux 就直接由軟體庫直接用一行指令安裝：
```bash
sudo pacman -S nodejs ## 同時 npm 相依於 nodejs 上
```

如果是 Debian、Ubuntu、KDE neon、Linux Mint、MX 等系統可參閱 [此文章](https://github.com/nodesource/distributions/blob/master/README.md) 的安裝方式，基本上也很簡單，基本上就把以下指令複製在虛擬終端上執行就行了：
```bash
curl -sL https://deb.nodesource.com/setup_13.x | sudo -E bash - ##首先安下載官方二進位安裝檔 且不保存檔案的方式執行測試
sudo apt install -y nodejs ## 接著由 apt 去安裝

```

其他發行版，請點選 [此連結](https://nodejs.org/zh-tw/download/package-manager) 查看對應安裝指令。

在安裝完成 node.js 後，建議先寫個 hello world 程式來測試你的 node.js 是否安裝成功，而 npm 就直接輸入'npm -v'查看版本，以簡單確認是否已經完成安裝。

### 3. 安裝開發環境 VS Code 
網頁的開發相對簡單，只要有一個記事本或是一個內建的vi就可以進行開發了，但其實各些基本編輯器都還不夠用，在此推薦一個對於網頁開發相對方便的工具 VS Code，VS Code 為微軟開發的開源文字編輯器，有許多外掛能進行擴充，幾乎是一鍵安裝一樣的方便。

在此推薦找有對應你語言的且有 snippet 支援的擴充工具，所謂的 snippet，請參照 [此連結](https://en.wikipedia.org/wiki/Snippet_(programming)) wiki的介紹，簡單來說就是含高亮提示語法或自動提醒語法等功能的擴充功能，此兩類功能皆在開發上能發揮很大的優勢：減少輸入時間與降第打錯字的錯誤，讓整體開發時間更快。

### 4.學習 html 與 css
首先我們已經知道了 JavaScript 是為了輔助網頁而設計的，在此先不談 Node.js，而在應用上基本上和網頁前端的應用為主。

當然建議可以從 w3c 或是一些網頁教學的網站進行學習。

## 學習使用基本工具 DeBug
### 1. 說明
當你在學習一門語言或是使用一門語言進行開發時，得要先了解如何使用工具進行 DeBug，否則會寫程式，確不會 DeBug。

### 2. 使用 Chrome Dev
白話文就是使用 Chrome 或 FireFox 瀏覽器上的開發工具進行 DeBug 的檢查。

你可以透過 Console 上直接輸出 window、document 等方式查詢對應瀏覽器環境狀況，或是直接`console.log(Value)`來輸出你目前的變數。

當然以上都是屬於相對暴力又簡單的方式，如果要好好 DeBug 與分析，建議就由 Source 上監測的執行行數、變數資料變化狀況、一些函數呼叫的堆疊等重要資訊進行分析。

而網頁的 html、CSS 則是以 Element 下查尋 html 標籤與各元件的 CSS 資料、各類型監聽事件等......。

## 實做基本程式
在此階段你可以找一些簡單的問題來解，基本上都是處理數學、字串處理或資料前處理問題。

像是一些題庫的例題，如果真的沒辦法，就自己想一個題目給自己解吧...。

### 1. 數學基本計算解題
* 基本的大小比較
    * [簡單]請設計一個程式，能將輸入 A,B 比較大小將較大的輸出。
    * [進階]輸入 A,B,C,D,E 等多筆數值，如何找出最大或最小值？請設計一個程式能比較任意K個數值，並能找出最大的數與最小的數。
    * [複雜]同進階題，但需妥善處理例外狀況，如：輸入英文、NAN、undefined、bool、Array 等資料型態狀況下等輸入如何處理。

* 基本加減乘除運算取餘數等純計算
    * [簡單]請設計一個程式，能將輸入 A,B 進行運算
    * [進階]請設計一個程式，將應用的計算問題以文字描述，並以該需求定義的輸入輸出進行設計，並確保不會發生例外或 IEEE754 規範精度完全失準。
    * [複雜]以基礎數學理論手刻出大數運算，請設計一個程式，輸入在此限制100位數內的輸入資料，且不使用 IEEE754 規範的實現計算功能，並能正常運行。
    * [極限]請設計一個程式，能讀取至設放好的 4 GB 的數值與運算子資料，並完成計算。
    
* 切線方程程式運算
    * [簡單] 請設計一個程式，限制在 y=ax^3+bx+c 的公式下，以限定 a、b、c，輸入 x 並輸出 y。
    * [進階] 請設計一個程式，能解二元一次聯立方程式。
    * [困難] 請設計一個程式，用高斯-喬丹消去法求基底。
     
* 面積體積運算
    * [基本] 基本面積運算
    * [進階] 多立體面積總和運算
    * [困難] 極複雜體積函數運算
    
* 因數運算
    * [基本] 求 A 與 B 的最大公因數與最小公倍數
    * [進階] 自動分解質因數分解

* 質數運算
    * [基本] 設計一個程式透過
    * [進階] 設計一個程式，判斷輸入是否是質數


* 數列計算
    * [基本] 設計一個程式來計算等差級數第 k 個索引值（像是費氏數列、盧斯卡數列等）
    * [進階] 設計一個程式來找出等比級數的第k位索引值，該輸入的值非常大
    * [困難] 給一個列表，請找出一個能最簡單計算的程式


* ~~微積分~~
    * ~~[基本] 使用積分定義實現函數的面積計算。~~
    * ~~[進階] 使用微分定義進行微分。~~
    * ~~[困難] 實做爬山演算法。~~

### 2. 基本應用

* 使用亂數做一些資料生成與處理
    * [基本] 使用亂數函數產生亂數。
    * [進階] 使用亂數種子+時間產生亂數，並限制與某區間 (a,b] 內。
    * [困難] 使用亂數種子產生身份證號碼。
    * [極限] 設計一個輸入總輸出數，亂數區間，能產生常態分佈。
    
* 讀寫檔案
    * [基本] 使用 node.js 的 FS 進行讀檔與寫檔操作
    * [進階] 使用 node.js 的 FS 進行讀檔與寫檔操作（使用 Ansyc）
    * [困難] 使用 node.js 的 FS 做二進檔的讀寫操作
    
* 輸入一句話查詢有無關鍵字等
    * [基本] 使用 node.js 的 FS 進行讀檔來找出關鍵字
    * [進階] 使用 node.js 的 FS 進行讀檔來建立語法剖析樹
    * [困難] 使用 node.js 的 FS 進行讀檔來進行語意分析
    * [極限] 使用 node.js 的 FS 進行自然語言分析

## 實做基本資料結構應用
當你認為基本的問題已經很簡單的解決後，你會發現你解決問題的方式似乎不怎麼有效率。

這時如果你的信心沒有被完全擊潰，從崩潰到放棄學習的話，你會開始想追尋如何讓你的程式更有效率。


### 1. 結構化資料

首先你會發現，你的程式儲存的資料是如此零散，你就得要找個有效率的方式儲存你的資料結構。

然後你仔細分析後會發現，。

### 2. 最基礎的資料結構特性

* **陣列**：請參照[此連結]( https://zh.wikipedia.org/wiki/%E9%93%BE%E8%A1%A8)
* **串列**：請參照[此連結](http://zh.wikipedia.org/wiki/%E6%95%B0%E7%BB%84)
* **佇列**：請參照[此連結](https://zh.wikipedia.org/wiki/%E9%98%9F%E5%88%97)
* **堆疊**：請參照[此連結](https://zh.wikipedia.org/wiki/%E5%A0%86%E6%A0%88)


### 3.陣列、串列、堆疊在 JavaScript 上實現的列表
在此 JavaScript 上，你可以視為用列表實現了陣列、串列、堆疊，這乍看之下是是很方便的功能，但也因為其本身是基於串列的列表特性，實際上的搜尋處理速度是相對較慢的（當然這也包含了 JavaScript 是跑在 V8 引擎，在此不探討 JavaScript 使用 webassembly 的技術問題）。

其實現方式相對簡單能理解，運用：
* **陣列**：將列表以陣列索引操作的方式進行操作。
* **串列**：因為是基於 [列表](https://zh.wikipedia.org/wiki/%E4%B8%B2%E5%88%97_(%E6%8A%BD%E8%B1%A1%E8%B3%87%E6%96%99%E5%9E%8B%E5%88%A5)) 所以就具有串列相似其特性，而功能上就是建立對應功能成員函數，只要當成串列使用時，就使用串列對應的函數進行呼叫。
* **佇列**：是和串列的功能一樣，也是在功能上就是建立對應功能成員函數，只要當成佇列使用時，就使用佇列對應的函數進行呼叫。
* **堆疊**：也是和串列的功能一樣，也是在功能上就是建立對應功能成員函數，只要當成堆疊使用時，就使用堆疊對應的函數進行呼叫。

就資料儲存上陣列是將資料存於連續的分配空間：
```
 ----------------------------------------------------
 |  [0]  |  [1]  |  [2]  |  [3]  | ........ |  [n]  |
 ----------------------------------------------------
```
再用指標(指針) + 索引值來進行查詢：
```
                            (位址+3*k)       (位址+n*k)   
                   (位址+2*k)  index3         index(n)
                    index2     |                |
          (位址+1*k)   |        |                |
  (位址)    index1     |        |                |
  index0     |        |        |                |
     ↓       ↓        ↓        ↓                ↓
 ----------------------------------------------------
 |  [0]  |  [1]  |  [2]  |  [3]  | ........ |  [n]  |
 ----------------------------------------------------
 ※在此的k為單一資料所使用的儲存空間。
```

而從記憶體抽象位置來看陣列就像是如此：
```
------------------------------------------------
|value1 | Array [1], [2], [3]        | Value2  |
------------------------------------------------
```
串列則是：
```
 -------  -------  ------- -------       -------
 | [0] |  | [1] |  | [2] | | [3] | ..... | [n] | 
 -------  -------  ------- -------       -------
```
你可以看成有無型的線將資料接起來，方便隨意從中插入新變數：
```
 -------  -------  -------  -------           -------
 | [0] |<-| [1] |<-| [2] |<-| [3] | <-..... <-| [n] | 
 -------  -------  -------  -------           -------
```


而列表上在記憶體抽象位置則像是有位子就塞一樣：
```
         (1) ___________________
            |                   |
            |                   V
------------------------------------------------
|valueC | ValueA | Value1 | Value B | Value2  |
-----------------------------------------------
   A                           |
   |                           |
   |____________________________ (2)
```

JavaScript 上實現對於佇列操作對應函數使用範例：
```javascript=
var List1 = [2,3,6,9,11];         //原始資料(當成佇列)
List1.push(4);                    //在堆放入4
console.log(List1);               //在此將輸出：  [2, 3, 6, 9, 11, 4]
var GetShiftData = List1.shift(); //把佇列第一個元素推出去
console.log(GetShiftData);        //在此將輸出：2
console.log(List1);               //在此將輸出： [3, 6, 9, 11, 4]
```

JavaScript 上實現對於堆疊操作對應函數使用範例：
```javascript=
var Stack1 = [2,3,6,9,11];     //原始資料(當成堆疊)
Stack1.push(4);                //在堆放入4
console.log(Stack1);           //在此將輸出： [2, 3, 6, 9, 11, 2]
var GetPopData = Stack1.pop(); //取出最後堆入的資料
console.log(GetPopData);       //在此將輸出：4
console.log(Stack1);           //在此將輸出： [2, 3, 6, 9, 11]
```


### 4. 基礎的資料結構特性
* **樹**：請參照[此連結]( https://zh.wikipedia.org/zh-tw/%E4%BA%8C%E5%8F%89%E6%A0%91)
* **堆**：請參照[此連結]( https://zh.wikipedia.org/wiki/%E9%93%BE%E8%A1%A8)
* **圖**：請參照[此連結]( https://zh.wikipedia.org/wiki/%E5%A0%86%E7%A9%8D)
* **trie**：請參照[此連結]( https://zh.wikipedia.org/wiki/Trie)
* **Hash**：請參照[此連結]( https://zh.wikipedia.org/wiki/%E5%93%88%E5%B8%8C%E8%A1%A8)

### 5. 如何在 JavaScript 實現數樹、堆、圖、Hash
在 C 語言中，而在 JavaScript 中有些實現上有所差別。

* **樹**：可使用傳統陣列形式表示樹狀關係表示，當然這也耗費其空間，而且就效能上，預設函數已經做到有效的優化，不必這麼做，這段只是寫給想練習的人。
 使用陣列儲存樹結構，如 [3,33,12,41,1,NULL,25]
 
 該陣列的描述就是對應於此型態的樹
 ```
          33              index的3代表其使用資料空間為2的3次方
         /  \
       12    41
      / \    / \
     1  25  X   53
      
 ```
 實際使用陣列實現樹狀結構：
 ```
          [1]        ------------ 2的0次方 -> 1
         /  \        
       [2]   [3]     ------------ 2的1次方 -> 2
      /  \   /  \
    [4] [5] [6] [7]  ------------ 2的3次方 -> 4
    / \ / \ / \ / \
    ... ... ... ...  ------------2的深度次方
      
 ```
 而在結構上使用物件儲存資料：
 ```javascript=
var Tree = [];

var Node = {
  Data       : "ABC" , //儲存資料
  LeftNode   : 2     , //該左節點子樹的索引值
  RightNode  : 3     , //該右節點子樹的索引值
 }
 ```
 
* **堆**
    * 堆其實是樹這個資料結構相似，基本上在實現上也是一樣用陣列儲存。
    
* **圖**
    * 這部份也只能像是弄樹的節點一樣，用各索引方式來連接，姑且筆者在打這段時一時半刻想不到其他好的方法。
```javascript=
//在此已有雙向連結的圖為範例：
var Node = {
  Data             : "ABC"        , //該節點儲存資料
  MappingOutNode   : [1,3,4,6]    , //該節點指向的其他節點索引列表
  MappingInNode    : [1,2,3,4,8]  , //指向這個節點的其他節點索引列表
 }
```
* **trie**
    * 該實現方式也與樹的實現類似。
    
* **Hash**
    * 在 Node.js 上就有開源的函式庫，像是 js-sha256 已經幫你打包好相關的函數，但如果考慮要自己手刻，基本上就看著書本上的範例就能做出簡單的 hash function。

### 6. 如何使用好資料結構來做設計
1. 建議好好的分析問題與應用
2. 了解各資料結構的優缺點
3. 實做久的經驗法則

### 7.實現物件導向
好的物件導向設計能讓專案程式碼簡潔且易於擴充，而在 JavaScript 上實現物件導向的概念也滿容易的。

運用將其設定為物件初始化，並運用新增成員方式建立 data 與 function：
```javascript=
var Human = new Object;

Human.data ={
    HP   : 1000   ,
    Name : "None"
}

Human.event ={
    Run:function(){
        //TODO
    },
    Walk:function(){
        //TODO
    },
    Sleep:function(){
        //TODO
    }
}
```

用最基礎的方式達到繼承（非最佳方法）：
```javascript=
var Human = new Object;

Human.data ={
    HP   : 1000   ,
    Name : "None" 
}

Human.event ={
    Run:function(){
        //TODO
    },
    Walk:function(){
        //TODO
    },
    Sleep:function(){
        //TODO
    }
}

var Superman = new Object;

Superman.data = {
    HumanType : Human , //簡單的達到繼承
    Color     : "red" 
}

Superman.event = {
    AtkSkill1:function(){
        //TODO
    },
    AtkSkill2:function(){
        //TODO
    }
}

/* 而在呼叫其父成員的函數時，則直接以成員方式進行呼叫 */
Superman.data.HumanType.event.Run();

```

而整體物件導向的概念能參閱此 [Wiki上的介紹](https://zh.wikipedia.org/zh-tw/%E9%9D%A2%E5%90%91%E5%AF%B9%E8%B1%A1%E7%A8%8B%E5%BA%8F%E8%AE%BE%E8%AE%A1)。

## 實做演算法基本練習

### 何謂演算法？
相信這問題問修過演算法的大學生們都會給出一類的標準答案，這些答案：「可以各種形式/以一個明確清晰的描述/在有效時間內/接受有效的輸入/輸出完成與中止。」


此部份 [引用Wiki](https://zh.wikipedia.org/wiki/%E7%AE%97%E6%B3%95#%E7%89%B9%E5%BE%81) 的內容：
```
以下是高德納在他的著作《電腦程式設計藝術》裡對演算法的特徵歸納：
    1. 輸入：一個演算法必須有零個或以上輸入量。
    2. 輸出：一個演算法應有一個或以上輸出量，輸出量是演算法計算的結果。
    3. 明確性：演算法的描述必須無歧義，以保證演算法的實際執行結果是精確地符合要求或期望，通常要求實際執行結果是確定的。
    4. 有限性：依據圖靈的定義，一個演算法是能夠被任何圖靈完備系統類比的一串運算，而圖靈機只有有限個狀態、有限個輸入符號和有限個轉移函式（指令）。而一些定義更規定演算法必須在有限個步驟內完成任務。
    5. 有效性：又稱可行性。能夠實現，演算法中描述的操作都是可以通過已經實現的基本運算執行有限次來實現。
```

基本上描述都是基於此類的說明，白話點來說就是：「學習演算法，就是嚷你有辦法設計一個能有效解決問題的方法，並且你的方法還得要讓其他人能看懂。」

而學習演算法的重點在於讓你能設計一個演算法，但同時你也得要學習其他人所設計演算法，主要還是學習其他人的方法是如何設計且你也能從現有的演算法中借鑒去設計出更好的演算法。

然而事實上，大部的情況如下：

```
老師：(教授演算法)

學生A ( ; O w O) ：原來程式還能這麼寫，有效率多了

學生B (  O A O)  ：這都有人寫好函數庫了，直接 Call 就行了

學生C (  @ A @)/ ：唯一支持「暴力解」!哈～哈～哈～


學生A !(  O _ O) :......

學生B !(  O _ O) :......


學生A (  O w O)/ ：暴力解!

學生B (  O w O)/ ：暴力解!
```

坦白說，這部份我還真的建議一邊讀一本演算法的書籍，同時參照著計*算機編程藝術*、*演算法導論*等書了解演算法與背後的數學。

就方法而言就有：Brute Force（暴力法）、Divide and Conque（分而至治法）、greedy algorithm（貪婪演算法）、Iteration（迭代法）、Dynamic programming（動態規畫）......。

而在學習到的演算法上就會碰到：排序問題、比較資料大小問題、最小生成樹問題等......。

當然當你了解的更透徹後又會發現在部份的應用上，我們的資料又是動態的，而不是像是演算課本範例中所提題的就只有固定幾個數值讓你排序或是比較，實際應用上資料都是動態的進出系統，就有人提出了對於這類型的動態系統演算法的效能評估方式 Amortized Analysis，有興趣的讀演算法導論到第 17 章就能看到 Amortized Analysis 的介紹。

### 了解 NP、NP-hard、NP-complete
所謂的NP問題在此請參閱 [Wiki 對於 NP 問題的介紹](https://zh.wikipedia.org/wiki/NP_(%E8%A4%87%E9%9B%9C%E5%BA%A6))，若是無法分辨 NP-hard 與 NP-complete 等描述差異則可參閱此 [Wiki對於複雜度的介紹](https://zh.wikipedia.org/wiki/%E8%A4%87%E9%9B%9C%E5%BA%A6%E9%A1%9E%E5%88%97%E8%A1%A8)。

P 與 NP


### 如何解決無法用演算法解題的問題？
如果了解了 NP、NP-hard、NP-complete 等問題後就會發現，其實有些問題我們還沒找到亦或是不存在在有線時間內由我們的電腦上完成有效率的計算或是驗證，像是著名的 [TSP問題](https://zh.wikipedia.org/wiki/%E6%97%85%E8%A1%8C%E6%8E%A8%E9%94%80%E5%91%98%E9%97%AE%E9%A2%98)，但偏偏這些問題我們終究會遇上。

既然不能用傳統的數學理論以無法解決此問題，這問題的最佳解就是一個近乎不可能的事。於是就有科學家想說既然找不到最佳解，那就找個近似的解法，即便有錯不要錯太大就行了，只要絕大多數的結果就是我們要的就行了，這便是現今人工智慧學門的基底之一：軟式計算（soft computing）。

軟式計算亦或稱作軟計算，不同於傳統的硬計算，傳統的計算都像是 "1+1=2"，這種有明確結果的運算，而是採用了容許誤差與錯誤的形式來解決問題，像是 "1+1=0.9" 與 "1+1=1.1" 這種不太明顯的誤差都能接受。

在此建議可以試著用 JavaScript 寫寫看幾個著名的演算法，基本上就是在練習而已，也是試試看將真正的將方法成程式解決，雖然在偉大的神經網路下這已經沒人用了，

### 輪盤法
就像是轉輪盤般的轉輪盤（身為 21 世紀的人，就用現代的比喻：就像是手遊抽卡一樣），1/k 的機會是 A、1/n 的機會是 B，基本上將仰賴隨機機率處理問題，自然這是後序各方法都會用到的方法。

### 集體智慧
有科學家觀測大自然，發現了大自然的一些動物現象而發現它們在生活上的活動狀況正是和我們解函數中，回歸分析類似，進而逼近至最佳解的情況，像是透過模仿蟻群用費落蒙建立最短路徑的演算的**蟻群演算法**，當然也有蜂群演算法與粒子群優化演算法等。

### 基因演算法
有科學家觀測人的細胞到基因，發現基因在進化時，能往越好的方向發展~~然而實際上還是有發展到滅亡的狀況~~，於是就透過**從基因池取出一定量的基因**、固定2組進行基因交換、任意基因突變、**以輪盤法淘汰部份視為過老的基因**等......。

### 模糊理論
基本上就是將問題模糊化，用設定規則將模糊化的問題以規則形式來一致處理，最後在解模糊化。基本上光模糊函數理論的**模糊數學**就能用一年以上的課程時間探討與計算還有研讀論文，且在工程上又有**模糊控制**、**模糊推論**、**模糊標記語言**等...，且在模糊函數的表示上又有 Type1 Fuzzy 與 Type2 Fuzzy 等...，在此建議可以研讀台大張智星教授的 *Neuro Fuzzy and Soft Computing* 一書。

### 神經網路
在此，神經網路的發展史我就懶得講了，簡單來說前面的鋪陳就是為了這個，神經網路基本上就是透過抓整體特徵與分析器來達到分析效果，並透過餵資料找到收斂值並配合神經元各節點上的參數控制調整達到學習效果。

在此不建議手刻神經網路，建議可以用 keras、yolov3 等框架進行遊玩，此外 TensorFlow 有支援 JavaScript，如果想了解可以看看 TensorFlow.js。

當然玩神經網路是要 GPU 的，否則會跑很慢，在此建議買不起 GPU 或是沒有 GPU 的人們，使用 Colaboratory 的免費 GPU/TPU 來進行運算。

至於為什麼 GPU 能做神經網路運算呢？其實本來 GPU 是要給 3D 遊戲算其各物件在螢幕上的顯示的。在 3D 遊戲的畫面計算上都是在算圖上一區塊一區塊的，所以可以各區塊能平行化處理，且此運算的核心可以不用像是 CPU 一樣的精準，所以就用了非常多個只算基本數學運算的核心來處理，這便就是 GPU。而在神經網路上學習驗證收斂值是能平行化運算，所以剛好碰上了 GPU，就是這樣剛好的巧合，讓 GPU 的使用者除了遊戲玩家外，也多了一群 AI 工程師。

在此基本知識，就讀 Google 的 Codelab 的介紹吧，同場加映 Google 整理的 [人工智慧單詞整理](https://developers.google.com/machine-learning/glossary?utm_source=google-ai&utm_medium=card-image&utm_campaign=training-hub&utm_content=ml-glossary#c)。

## 學習軟體工程

軟體工程一學門十分重要建議好好學習，如果不是以PM為目標而是專注於寫程式的人，重點將著重於
* 如何與客戶有良好的互動並獲取正確的需求
* 如何有效的分析
* 如何分配時間
* 如何讓程式好維護
* 如何寫好文件
* **以下繁多不予逐一記載**

在此建議研讀 *Clean Code* 系列、*代碼大全*、*人月神話*、培生出版的**軟體工程** 等著名書籍。

建議基本上要學會：
* 了解敏捷式開發與瀑布流開發的差異
    * 在此建議可以閱讀此Wiki上對於 [敏捷流](https://zh.wikipedia.org/wiki/%E6%95%8F%E6%8D%B7%E8%BD%AF%E4%BB%B6%E5%BC%80%E5%8F%91) 與 [瀑布流](https://zh.wikipedia.org/wiki/%E7%80%91%E5%B8%83%E6%A8%A1%E5%9E%8B) 說明的文章。

* 繪製程式流程圖
    * 在任何無法完全掌握的開發上，使用程式流程圖繪製軟體繪製整體處理控制流程，並依據此流程圖進行開發。
    
* 分析並繪製 UML 模型
    * 對於開發需求進行有效的分析，如果是不涉及建立關聯資料庫設計部份的大多數情況，可以建立 [UML 模型](https://zh.wikipedia.org/wiki/%E7%BB%9F%E4%B8%80%E5%BB%BA%E6%A8%A1%E8%AF%AD%E8%A8%80) 以分析，其優點在於能進行優化分析、資安弱點分析與後續文件撰寫維護。
    
* 落實有效的協定管理
    * 在開發上與需求方建立完善的合約協議，在此合約協議是很重要的，在開發上的各需求增加與更新都需以有協議式的互動，如：傳統瀑布流開發的事前需求的確認與敏捷式開發的每次更新的調整需求，都是要有一定機制的去處理。
 
* 能繪製功能流程與資料流程的分析
    * 基本上若是在建立關聯資料庫設計時，會採用 [ER模型](https://zh.wikipedia.org/zh-tw/ER%E6%A8%A1%E5%9E%8B)，在此的 ER 模型，需要經歷數個步驟產生：
    
```
1. 以需求建立功能的流程
2. 以功能流程推演至資料流程
3. 由資料流程建立 ER 模型
4. 由ER模型建立分析優化結構
5. 最後是情況來決定是否進行正規化
```

* 實現模組化開發
    * 有效的將功能切割，以方便實做與分工。
    
* 落實版本管理
    * 學會使用 git 工具與 GitHub 服務。
    
* 在小組開發時能落實 code review
    * 在多人合作專案時，落實程式碼的相互審核，以有效避免錯誤。
    
* 有好的 code style
    * 在多人開發的大型項目時，不會因為程式錯誤而對於開發進度造成影響，且在維護時不會因為一堆亂七八糟的變數而影響。

* 程式碼能讓人看得懂(包含你自己)
    * 讓程式碼能簡潔明瞭，方便維護。


## 實做進階程式
* 程式方法
    * 平行化計算
    * 同位異步運算
    * 有效落實 OOP
    * 實現 [functional programing](https://llh911001.gitbooks.io/mostly-adequate-guide-chinese/content/)
    * JavaScript 與 DOM 控制
    * 使用正規表達式
    * 了解程式的授權協議
    
* 常用函式庫
    * 使用 [JQuery](https://jquery.com/)
    * 使用 AJAX
    * 使用 [Bootstrap UI](https://getbootstrap.com/) 框架
    
* 數學與文獻
    * 使用 [math.js](https://mathjs.org/) 實現特殊運算
    * 使用 [latex.js](https://latex.js.org/) 實現 latex 公式表示
    
* 圖學與動畫
    * 學習 Canvas 應用
    * 使用 [pixi.js](https://www.pixijs.com/) 實現 2D 動畫設計
    * 使用 [three.js](https://threejs.org/) 實現 3D 操作
    * 使用原生 WebGL 實現 3D 操作
    * 了解 [gltf](https://www.khronos.org/gltf/) 格式並使用 [blender](https://www.blender.org/) 或其他 3D 建模軟體
    
* 統計
    * 使用 [stdlib.js](https://github.com/stdlib-js/stdlib) 實現數值方法
    * 使用 [C3.js](https://c3js.org/) 實現資料視覺化
    * 使用 [D3.js](https://d3js.org/) 實現資料視覺化

* 神經網路
    * 使用 [keras.js](https://github.com/transcranial/keras-js) 用現有模型做練習神經網路
    * 使用 [ml5.js](https://ml5js.org/) 實現神經網路應用
    * 使用 [Brain.js](https://brain.js.org/) 實現神經網路應用
    * 使用 [TensorFlow.js](https://www.tensorflow.org/js/) 實現神經網路應用
    
## 實做個人小型專案
到了這個階段時，你可以真正去嘗試寫一個個人的業餘專案（side-project），基本上可以寫一些小型的專案來進行開發。

當然個人建議，可以以程式碼行數作為基準：500 行、1000 行、3000 行、5000 行、10000 行逐漸往上，在此筆者是高三實踐500行以上、大二實現 5000 行以上、大三實現 10000 行以上、大四實現 30000 行以上，當然相信你們從高一開始就以此教學進行高壓的訓練 ~~，想必能在高三前達到 10000 行以上的~~。

但值得注意的是，當程式碼超過 3000 行以上時就得要注重軟體工程的實踐，否則在維護上會隨著程式碼的增加使得維護上拖累開發進度。

## 了解規格 熟知一切標準
* 了解ECMAScript標準：[請參閱此文件](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-262.pdf)
* 了解Json標準：[請參閱此文件](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-404.pdf)
* 了解Web API規範：[請參閱此文件](https://developer.mozilla.org/en-US/docs/Web/API)
* 了解TypeScript規範：[請參閱此文件](https://www.typescriptlang.org/docs/home.html)

## 架設 Server 與使用 Node.js
建議使用 Linux 弄個 LAMP 或 LEMP，如果是 Windows 上則建議就用 xampp。基本上 Server 服務，是要架網站用的，在此裝版本都是本地端上實現的，若要真正的架站建議可以去看一下 *鳥哥的 Linux 教學* 尤其架站的部份。

### 搞懂什麼是後端？
首先，我們瀏覽器上看到的網頁頁面是**前端**，而我們看不到的網頁服務都是屬於**後端**，常見的後端服務像是：
* 使用者登入系統的驗證
* 操作的資料儲存至後端 Server 上的資料庫
* 處理網頁路徑路由，將不存在的頁面導到 404 頁面上

### 後端語言與環境介紹
* 在此簡單說明個 LAMP、LEMP、XAMPP：
    * LAMP： 
        * 作業系統 **L**inux
        * 服務器 **A**pache
        * 資料庫系統 **M**ySQL
        * 後端語言 **P**HP
    * LEMP：
        * 作業系統 **L**inux
        * N**e**gix
        * 資料庫系統 **M**ySQL
        * 後端語言 **P**HP
    * XAMPP：
        * 作業系統 **X**(可跨平台)
        * 服務器 **A**pache
        * 資料庫系統 **M**ySQL
        * 後端語言 **P**HP
        * 後端語言 **P**erl

* 當然後端語言也非常多種，在此列舉幾個常見的：
    * PHP
        * 一門十分容易入手的語言，但結構上會恨亂
        * 建議學好基本語法後使用 PHP 框架中較為著名的 Laravel 來開發
        
    * Node.js
        * 和前端的 JavaScript 幾乎一樣，但支援使用後端的函式庫
    * Perl
        * 高可寫性，但後續程式碼的可讀性較低
        
    * Python
        * 就是那個常見的 Python
        
    * C
        * 理論上用優化編譯可以跑得很快
        * C 語言是能到達後端語言功能的
        
    * Go
        * C 語言開發者之一的肯湯姆森進行開發的
        * 並由 Google 維護
        * 支援簡易的平行化與引用 C 語言函式
    
    * Rust
        * 安全、並行、實用

* 在此也推薦數個實用的 Node.js 庫：
    * fs
        * 預設，讀寫檔用
    * os
        * 預設，系統操作用
    * express
        * NPM 安裝，Server 服務用
    * koa
        * NPM 安裝，Server 服務用
    * mysql
        * NPM 安裝，資料庫存取控制用
    * parceljs
        * NPM 安裝，打包用
    * electron
        * NPM 安裝，開發桌面程式用
    * nightwatch
        * NPM 安裝，自動化測試用
    * node-telegram-bot-api
        * NPM 安裝，telegram 機器人的 api 庫

* 基本要了解的知識
    * 了解 WebSocket
    * 了解常用的通訊 Port
    * 了解 TCP 與 UDP 的差別
    * 了解 5 層或是 7 層網頁通訊協議
    * 了解 Session 與 cookies 的用途
    * 了解 Linux 系統
    * 了解服務器的用途與設定
    * 了解資料庫操作與設計
    * 了解 DBMS
    
## 基於一些框架下做到簡化設計
* 選取你的御三家：
    * Vue.js
    * React
    * Angular

* 選取你的Server框架：
    * express.js
    * koa.js

* 落實自動化測試：
    * nightwatch.js

## 優化程式碼

* 運算時間優化
    * 以全域變數取代區域變數
    * 降低使用遞迴
    * 降低運行時間
    * 直接展開迴圈
    * 使用 webassembly 技術

* 運算空間優化
    * 降低程式碼行數
    * 最少記憶體儲存資料
    * 降低其記憶體使用

* 避免漏洞發生
    * 落實輸入的資料安全管理
    * 落實資料傳遞時的加密
    * 落實實體資料安全
    * 落實程式碼管理
    * 落實有效的界面管理
    * 落實有效的權限分配
    * 落實 Code review
    * 落實定期更新相依函式庫
    * 落實在更新前進行完善測試
    * 落實有效使用憑證與身份驗證軟體使用
    * 落實密碼管理與更新

## 了解 UI 與 UX
* UI
    * 了解界面設計
    * 如何去設計 icon 或是界面
    * 如何使用原生的 CSS 功能取代圖檔
    
* UX
    * 了解功能需如何設計讓使用者能順利使用
    
* 如何與設計師對話
    * 了解設計師對於設計的要求
    * 了解設計師使用的設計圖界面與解釋
    * 了解在特定無法實現的狀況下要如何妥協 

（切記設計師也算是和工程師一樣熬夜到爆肝的職業，請小心輕放）

## 實做大型專案
實做多人開發的大型專案，並使用 git 進行管理，且落實 Code review 與 ISO 或 CMMI 等工程標準進行開發。

## 理解 直譯器 語法分析器 到 V8 引擎
在了解一門語言的最後，你能對於該語言的編譯器設計與語法剖析的概念有所了解，當你學會了這些後這也意謂著你完全了解這個語言的一切了，同時你有一定的概念來自己設計一門語言了。

**以下省略數萬字......**

## 最後
「祝福看完這篇簡單的學習說明且完全落實的後輩們，能成為未來台灣科技界的中流砥柱，告訴社會大眾未來能撐起台灣的不只有半導體製程，還有我們資訊科技人材與資訊產業。」 --- [Lian0123](https://lian0123.github.io/) 2020.02.21