1. 請用簡單的方式敘述以下每一行程式碼：

  ```ruby 
  a = 1
  @a = 2
  @@a = 5
  user = User.new
  user.name
  user.name = "Joe"
  ```
ans:
  ```ruby 
  a = 1  #區域變數a寫入整數1
  @a = 2 #實例變數(instance variable)是綁定物件的資料,寫入整數2
  @@a = 5 #class variable 就是綁定 class 本身的資料,寫入整數5
  user = User.new #創造一個User class的物件user
  user.name  #物件user的實例變數name		
  user.name = "Joe"#物件user的實例變數name寫入"Joe"這個字串
  ```
2. 什麼是 module? 請寫一段程式碼說明一個 class 要如何使用一個 module 裡面的 method?  
   ans:可把 module 想像成工具箱，本身並不是 class
   沒有實例、不可 new，只能被 include 到其他 class 裡面使用
    一個 class 使用模組在 ruby 界是叫做 mixin module
  ```ruby 
  module Knowledge
  def program
    puts "I know how to program"
  end
end

class Person  
  attr_accessor :name, :age

  def initialize(name, age)
    @name = name
    @age = age
  end
end

class Engineer < Person
  include Knowledge # Mixin
end

bob = Engineer.new("Bob", 17)
bob.program
# => I know how to program
	
  ```

3. 請說明 class variable 和 instance variable 之間的差別  

   ans:class variable 就是綁定 class 本身的資料;紀錄在class中  
       instance variable是綁定物件的資料;分別紀錄在class各個實例中 
 
4. 請說明 class method 和 instance method 之間的差別

  ans:class method只能被class呼叫,instance method只能被instance呼叫
```ruby 
class Foo
  def self.bar
    puts 'class method'
  end
  
  def baz
    puts 'instance method'
  end
end

Foo.bar # => "class method"
Foo.baz # => NoMethodError: undefined method ‘baz’ for Foo:Class

Foo.new.baz # => instance method
Foo.new.bar # => NoMethodError: undefined method ‘bar’ for #<Foo:0x1e820>
```
5. 如果今天我為一個叫 User 的 class 產生一個新物件的方式是:
  ```ruby
  User.new("Bob", "male", "Engineer")
  ```
請寫出 User class 的 initialize method
  ```ruby
class User  
  attr_accessor :name, :sex, :occupation

  def initialize(name, sex, occupation)
    @name = name
    @sex = sex
    @occupation=occupation	
  end
end
  ```
6. 在：
  A.  一個 class 裡，method 外面
  B.  一個 class 裡，instance method 裡
  self 分別是指向什麼?  

  ans: A.指向class  
       B.指向instance	
7. attr_accessor 的功能是什麼，它和 attr_reader、attr_writer 之間的差別是什麼？  
  ans: attr_accessor包含getter和setter method;attr_reader只有getter method;  
       attr_writer只有setter method  
 		
8. 請說明 public 和 private method 之間的不同  
  ans:public 就是任何屬於這個 class 的物件都能使用  
      private 是只有在 class 內部才可以存取  


9. 請說明 Inheritance 和 Module 之間的差別，它們分別是用於哪些情況？ 請舉例說明  
  ans:
   1. You can only subclass from one class. But you can mix in as many modules as you'd like.  
   你只能為一個 class 建立子類別，但卻可以 mix 很多 module  

   2. 如果今天你是需要 "是某個..." 的關係，就用 inheritance，如過需要 "擁有某項行為" 就用 module  
      繼承相同的class後,在利用include Module創造有差異的行為  
   Ex. 蝙蝠是屬於一種哺乳動物，就讓 Bat 繼承 Mammal  
       蝙蝠有飛行的能力，但並非所有哺乳動物都會飛，所以讓 Bat include 擁有 fly 這個 method 的 module  
     
   3. Module 不能使用 new，他只能被其他 class 使用  

10. 若今天有一個 class 有 include 一個 module，他的 parent class 和 sub class 是否可以使用該 module 裡的 method?  
  
  ans:sub class可以使用但parent class無法使用該module  
11. 請間單說明什麼是 Relational Database，什麼是 SQL  
  ans:Relational Database關聯式資料庫是將資料間的關係以資料庫表的形式加以表達，並將資料存儲在表格中  
     SQL是一種被設計用來讓使用者可以從Relational Database查詢、操作、傳換資料的語言

