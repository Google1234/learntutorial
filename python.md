python命令行中获取用户输入：
    import sys
    usrargv = sys.argv
    print usrargv
    print usrargv[0] #第一个参数为文件名
    print usrargv[1] #第一个用户输入的参数 变量字符串型
python命令行中交互获取用户输入：
      下面的函数只在python 2.X被支持
      raw_input()函数：
      
          print "input:" , raw_input("please input :")
      1
          print "input:" , raw_input("please input :")
      
       
      下面的函数只在python 3.X中才是要表达获取用户输入的意思
      在python3.x中，raw_input函数被改名为input() ：
      
          input = str (input("Enter your name:"))
          print ("your name is",input)
      1
      2
          input = str (input("Enter your name:"))
          print ("your name is",input)
      
       
      ======================
      是不是让你想起了python2.x中的input()函数？但是千万要注意这两者的区别差很大。
      在python2.x中，input()函数不是将用户的输入作为字符串读入，而是对用户的输入进行处理，识别，把它当作python表达式，如果符合语法规则，是会直接执行的 。
      加上我C盘下有个s.txt文件，则：
      
          #!usr/bin/env python
          #coding:utf-8
          import sys
          import pprint
          import os
          input("input:") #输入：os.remove("C:\s.txt")
      1
      2
      3
      4
      5
      6
          #!usr/bin/env python
          #coding:utf-8
          import sys
          import pprint
          import os
          input("input:") #输入：os.remove("C:\s.txt")
      
       
      结果会看到，C:\s.txt 文件被删除了。可见，python2.x中input()不是直接把用户的输入当字符串，而是会进行特定的处理，看看是否符合语法规则，是的话就执行。
      见下面：
      
      list = input("input:")   #键盘输入: [1,2]
      print type(list)
      for i in list:
      	print i
      list2 = raw_input("input:")   #键盘输入: [1,2]
      print type(list2)
      for i in list2:
      	print i
      # output
      # input:[1,2]
      # <type 'list'>
      # 1
      # 2
      # input:[1,2]
      # <type 'str'>
      # [
      # 1
      # ,
      # 2
      # ]
      1
      2
      3
      4
      5
      6
      7
      8
      9
      10
      11
      12
      13
      14
      15
      16
      17
      18
      19
      20
      list = input("input:")   #键盘输入: [1,2]
      print type(list)
      for i in list:
      	print i
      list2 = raw_input("input:")   #键盘输入: [1,2]
      print type(list2)
      for i in list2:
      	print i
      # output
      # input:[1,2]
      # <type 'list'>
      # 1
      # 2
      # input:[1,2]
      # <type 'str'>
      # [
      # 1
      # ,
      # 2
      # ]
      
       
      上面input()和raw_input()对同样的输入，结果变量的类型一个是列表，一个是字符串。当我们使用input()函数来获取输入的内容时候，而我们输入的刚好是个列表的形式，则python会认为我们输入的是列表，不是字符串。同理，如果输入132，则会认为我们输入的int类型。
      当我们随便输入内容，而这段内容又不是可执行的代码的时候，则会报错，见下面这个例子：
      list = input("input:") #键盘输入: sfwerwrwe
      当我们输入  sfwerwrwe  后，程序报错：
      
          Traceback (most recent call last):
          File "E:/pyworkspace/jisuan.py", line 43, in <module>
          list = input("input:") #键盘输入: sfwerwrwe
          File "<string>", line 1, in <module>
          NameError: name 'sfwerwrwe' is not defined
      1
      2
      3
      4
      5
          Traceback (most recent call last):
          File "E:/pyworkspace/jisuan.py", line 43, in <module>
          list = input("input:") #键盘输入: sfwerwrwe
          File "<string>", line 1, in <module>
          NameError: name 'sfwerwrwe' is not defined
      
       
      这是因为  sfwerwrwe 不是一段可以执行的python代码，所以，提示无法识别，出现报错。    
    
