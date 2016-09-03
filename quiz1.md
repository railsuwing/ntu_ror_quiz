1. 請說明 Fixnum (整數) 和 Float (浮點數) 之間的差異   
  ans:Float能表示小數且數值範圍較大

2. 今天有兩個字串：
  ```ruby 
  str1 = "Hallo Welt!" 
  str2 = " NTU Rails 261!"
  ```
請說明以下兩個印出字串的方式的不同處：
  ```ruby
  puts str1 + str2
  puts "#{str1}#{str2}"
  ```
  ans:
  ```ruby 
  put str1+str2#相較會需要多花費暫存的記憶體
  ```
  ```ruby
  put #{str1}#{str2}#為字串內插的連接方式
  ```
3. 請解釋 array 和 hash 的不同處  
 
 ans:array 和 hash內都能存放告種不同型態的資料,array內的每一筆資料在array中的位置是以0 1 2..的順序來表示,但在hash中則是會對應到一個immutable (不能被改變的)的key

     	
4. 請用一行程式碼從 [1, "a string", 3.14, [1,2,3,4]] 這個陣列找出所有非字串的值  
 
 ans:
  ```ruby
   [1, "a string", 3.14, [1,2,3,4]].select{|x| x.class!="".class}
  ```
5. 請用一行程式碼把一個內容為整數 1 到 100 的陣列裡所有的值加上 2  
 
 ans:
  ```ruby
  (1..10).to_a.map!{|x| x+2}
  ```
6. 請寫出以下兩行程式碼迴傳的值，並解釋他們呼叫的方法差別為何：
  ```ruby
  [1, 2, 3, 3].uniq
  [1, 2, 3, 3].uniq!
  ```
  ans:
  ```ruby
  [1, 2, 3, 3].uniq=> [1, 2, 3]

  [1, 2, 3, 3].uniq!=> [1, 2, 3]

  ```
  uniq會列出陣列中不重複的部份,加 ! 的方法代表呼叫該方法的物件最後會被改變

7. 請列出兩種產出亂數的方法  
  
  ans:
  ```ruby
  arr.sample
  arr.shffle
  ```
8. 以下這段程式碼：
  ```ruby
  ((1 > 3)&&(true == true))||(!!!false)
  ```
  會執行出什麼結果？ 請試試不用 irb 算出結果  
  ans:
  ```ruby
  (false && true) || true  =>  true
  ```
9. 請問 binding.pry 是什麼？ 要如何使用它？  
  ans:可以下中斷點來debug
 ```ruby
  require 'pry' # 在程式的最上方寫 require 'pry'

  binding.pry
   # binding.pry 等於在 ruby 的程式碼裡面下斷點，程式執行到此就會停住
  ```
10. 下面的一段程式碼，請嘗試用其他方法把 if...else...end 簡化成一行
  

  ```ruby
  var = 5

  if var >= 5
  	return "var is greater than or equal to 5"
  else
  	return "var is less than 5"
  end
  ```
  ans:
  ```ruby
  if  var >= 5  ? return "var is greater than or equal to 5" :   	return "var is less than 5"
  ```
11. 請列出兩種不同的 hash 寫法  
  ans: 
  ```ruby
  person = { 
             :name => "Bob", 
             :age => 30,
             :occupation => "Engineer"
           }
  # ‘=>' 符號叫做 hashrocket，是 hash 用來 assign 值所使用的符號
  ```

  ```ruby
    person = { 
               name: "Bob", 
               age: 30,
               occupation: "Engineer"
             }
  ```
