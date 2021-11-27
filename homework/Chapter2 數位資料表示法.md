## 目錄
[2-1 資料型態]  
[2-2 二進位表示法]  
[2-3 各種進位表示法的轉換]  
[2-4 整數表示法]  
[2-5 浮點數表示法]  
[2-6 ASCII 與 Unicode]  
[課堂練習題目]  

## 2-1 資料型態
1. 數位是什麼?
* 電學上是指不連續變化的數量表示法
* 何謂不連續變化？  
   * **實數**是連續變化的數量表示法，任兩數之間還可以找到第三個數介於它們之間，直到沒有空隙。  
   * **整數**是不連續變化的數量表示法，例如整數1和整數2之間，找不到任何整數是介於它們之間的。  

2. 介紹位元: 位元(binary digit；bit)  
* 位元是數位資訊的基本粒子  
* 電腦儲存或傳遞資料的最小單位  
* 電腦會採用位元的原因 → 電子元件的穩定狀態有兩種 (開=1，關=0)  
* 8個位元稱為**位元組(byte)**  

3. 資料容量的單位 (「B」代表的是Byte(位元組)，不是Bit(位元) )  
![image](https://user-images.githubusercontent.com/91866985/143687366-246a3608-07ab-457c-ad24-97ca0d1a9ae1.png)


## 2-2 二進位表示法
1. 六十進位: 每分鐘六十秒及每小時六十分。

2. 十進位: 現今公制。

3. 二進位: 
* 0 / 1  
* 目前通行電腦用二進位符號來儲存資料  

## 2-3 各種進位表示法的轉換
* 一個位元組有八個位元，可切成兩個十六進位數  
* 十六進位系統的數字0到15，分別以阿拉伯數字的 0-9 及 A-F 表示  
![image](https://user-images.githubusercontent.com/91866985/143687540-76dc17ba-7049-4b23-b59a-e461e6b28508.png)

* 例題:  
![image](https://user-images.githubusercontent.com/91866985/143687565-9b8ac787-c11c-40d2-bb8f-81ed08b16763.png)


## 2-4 整數表示法
1. 無正負符號的整數  
*  只表示非負的整數  
*  使用8個位元，可表示0～28-1間的所有整數，也就是從0~255的所有整數  
![image](https://user-images.githubusercontent.com/91866985/143687775-131bd9ed-59be-4b07-a000-5ccf3435c69e.png)


2. 帶正負符號大小表示法  
*  同時表示正數和負數  
*  最左邊位元當作符號位元(0為正數；1為負數)  
*  剩下的n-1個位元用來表示數的大小，共可表示-(27-1)～27-1 間的所有整數(-127～127) 
 
*【面臨的問題】:*  
   * 有兩個0，+0(000...00)和-0(100...00)
   * 正數和負數的運算(例如加和減)並不直接
![image](https://user-images.githubusercontent.com/91866985/143687898-f2a148c5-cd62-44f4-a44f-001a4192cab1.png)



3. 補數表示法
* 補數的概念是指要補多少才滿，例如: 793元還差207元就可「補」成1000元。

4. 一補數表示法
* 最左邊的位元當作符號位元(0為正數；1為負數)；其餘的n-1個位元則用來表示正負符號外的數值大小。
* 正數表示方式與「帶正負符號大小表示法」相同，但負數不同。
![image](https://user-images.githubusercontent.com/91866985/143687981-b26902b6-2a5f-440e-b054-cf53fdf2a98c.png)

例題(一):  
![image](https://user-images.githubusercontent.com/91866985/143688008-fc5c5dc1-845a-4a1c-88d4-a32459a82714.png)

例題(二):  
![image](https://user-images.githubusercontent.com/91866985/143688030-9711c4cb-bbbc-4a61-80bb-dc91c9bf3b9c.png)

*【面臨的問題】:*  
   * 有兩個0，00000000和11111111都是0
   * 正數和負數的運算(例如加和減)並不直接

5. 二補數表示法
* 最左邊的位元當作符號位元(0為正數；1為負數)；其餘的n-1個位元則用來表示正負符號外的數值大小。
* 正數表示方式與「帶正負符號大小表示法」相同，但負數不同。
![image](https://user-images.githubusercontent.com/91866985/143688070-a793549a-9769-420c-8b52-6cbdae669ab0.png)

例題(一):  
![image](https://user-images.githubusercontent.com/91866985/143688091-28c75555-d37e-469e-8fe1-8b9b5fa0fd30.png)

例題(二):  
![image](https://user-images.githubusercontent.com/91866985/143688099-9ebf79d1-0c4c-4cee-8de1-50b59f78bdcd.png)


6. 二補數的加法
   1. 將所加的兩個數之二補數位元對齊
   2. 從最右邊的位元開始加起，若相對位置的位元相加為二或以上，則有進位。
   3. 若有進位，則往左邊傳遞；若最左邊位元相加有進位，則忽略這個進位。
   4. 兩正數相加後，若最左邊符號位元為1，則有**溢位(overflow)**；兩負數相加後，若最左邊符號位元為0，則有**溢位(overflow)**

例題(一):  
![image](https://user-images.githubusercontent.com/91866985/143688164-2494c9ad-b1f3-4788-9f21-66885e968ee1.png)

例題(二):  
![image](https://user-images.githubusercontent.com/91866985/143688174-f9f2f62f-f273-4d0e-a885-29816ba5b287.png)


## 2-5 浮點數表示法
* 浮點數表示法是電腦表示實數最常用的方式
* **浮動小數點:** 「536.87」表示成科學記號為「5.3687×102」
* 在有限位元數的情況下，浮動小數點所能表示的數值範圍比固定小數點位置的方式大許多
* 1.0110100011 × 2(4次方) = 小數點右邊的0110100011稱為**尾數(mantissa)**，而**指數(exponent)**為4
* 浮點數表示法以**IEEE 754標準**為主
* 單倍/雙倍精準數:
   * 單倍精準數：以1個位元表示符號；8個位元表示指數；23個位元表示尾數部分。
   * 雙倍精準數：以1個位元表示符號；11個位元表示指數；52個位元表示尾數部分。
![image](https://user-images.githubusercontent.com/91866985/143688274-7e5ff31c-4979-4ca4-ba1b-a0df6145f9d4.png)



## 2-6 ASCII 與 Unicode
![alt 文字](https://upload.wikimedia.org/wikipedia/commons/c/cf/USASCII_code_chart.png "Wiki: ACIIcode")

## 課堂練習題目:  
![計算機概論-11 (1)](https://user-images.githubusercontent.com/91866985/143688363-ee611ed6-9fa3-445a-961e-e5d9ee9b186d.jpg)
![計算機概論-10](https://user-images.githubusercontent.com/91866985/143688372-ab760706-aa41-488f-97bb-98e049707031.jpg)



