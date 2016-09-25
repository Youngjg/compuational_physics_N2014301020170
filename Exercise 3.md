EX 3

## 一、摘要 ##
作业L1 在屏幕上让你的英文名字水平移动起来
作业L2 在80*80点阵上用字符拼出你想画的东西，并让它旋转起来，希望脑洞大开！（比如字符、火柴人、火箭等等）
## 二、背景介绍 ##
可以使用如下语句把屏幕清理干净
```python
import os
i = os.system('cls')
```
字符移动可以用在每行前面增加空格的方法实现
```python
print("      ###")
print("     #   ")
print("     #   ")
print("     #   ")
print("      ###")
```
字符串变成列表
```python
a = "test"
l = list(a)
```
列表变成字符串
```python
a = "".join(l)
```
## 三正文 ##
```python
import os
import math
import time
def alphabet_combine(string,length):
    pa =(('   #    '),(' #   #  '),('#     # '),('# ### # '),('#     # '),('#     # '),('#     # '))
    pb =((' #####  '),('#     # '),('#     # '),('######  '),('#     # '),('#     # '),(' #####  '))
    pc =((' #####  '),('#     # '),('#       '),('#       '),('#       '),('#     # '),(' #####  '))
    pd =(('######  '),('#     # '),('#     # '),('#     # '),('#     # '),('#     # '),('######  '))
    pe =(('####### '),('#       '),('#       '),('######  '),('#       '),('#       '),('####### ')) 
    pf =(('####### '),('#       '),('#       '),('#####   '),('#       '),('#       '),('#       '))
    pg =((' #####  '),('#       '),('#       '),('#   ### '),('#     # '),('#    ## '),(' #### # '))
    ph =(('#     # '),('#     # '),('#     # '),('####### '),('#     # '),('#     # '),('#     # '))
    pi =((' #####  '),('   #    '),('   #    '),('   #    '),('   #    '),('   #    '),(' #####  '))
    pj =(('  ##### '),('     #  '),('     #  '),('     #  '),('     #  '),(' #   #  '),('  ###   '))
    pk =(('#     # '),('#    #  '),('#   #   '),('####    '),('#   #   '),('#    #  '),('#     # '))
    pl =((' #      '),(' #      '),(' #      '),(' #      '),(' #      '),(' #      '),(' #####  '))
    pm =(('#     # '),('##   ## '),('# # # # '),('#  #  # '),('#     # '),('#     # '),('#     # ')) 
    pn =(('#     # '),('##    # '),('# #   # '),('#  #  # '),('#   # # '),('#    ## '),('#     # ')) 
    po =((' #####  '),('#     # '),('#     # '),('#     # '),('#     # '),('#     # '),(' #####  ')) 
    pp =(('######  '),('#     # '),('#     # '),('######  '),('#       '),('#       '),('#       ')) 
    pq =((' #####  '),('#     # '),('#     # '),('#     # '),('#   # # '),('#    #  '),(' #### # ')) 
    pr =(('######  '),('#     # '),('#     # '),('######  '),('#   #   '),('#    #  '),('#     # ')) 
    ps =((' ###### '),('#       '),('#       '),(' #####  '),('      # '),('      # '),('######  '))
    pt =(('####### '),('   #    '),('   #    '),('   #    '),('   #    '),('   #    '),('   #    ')) 
    pu =(('#     # '),('#     # '),('#     # '),('#     # '),('#     # '),('#     # '),(' #####  '))
    pv =(('#     # '),('#     # '),('#     # '),(' #   #  '),(' #   #  '),('  # #   '),('   #    '))
    pw =(('#     # '),('#     # '),('#  #  # '),('#  #  # '),('#  #  # '),('# # # # '),(' #   #  ')) 
    px =(('#     # '),(' #   #  '),('  # #   '),('   #    '),('  # #   '),(' #   #  '),('#     # ')) 
    py =(('#     # '),('#     # '),(' #   #  '),('  # #   '),('   #    '),('   #    '),('   #    '))
    pz =(('####### '),('     #  '),('    #   '),('   #    '),('  #     '),(' #      '),('####### '))
    p_ =(('        '),('        '),('        '),('        '),('        '),('        '),('        '))
    dictionary = {' ':p_,'a':pa,'b':pb,'c':pc,'d':pd,'e':pe,'f':pf,'g':pg,'h':ph,'i':pi,'j':pj,'k':pk,'l':pl,'m':pm,'n':pn,'o':po,'p':pp,'q':pq,'r':pr,'s':ps,'t':pt,'u':pu,'v':pv,'w':pw,'x':px,'y':py,'z':pz}
    screen =[' ']*7 
    move = [' ']
    for k in range(20):
        for j in range(7):
            for i in range(length):
                screen[j]=move[0]*k+screen[j]+dictionary[string[i]][j] 
            print screen[j]
            screen = [' ']*7
        time.sleep(0.2)
        os.system('cls')
    return screen
def main():
    name = raw_input('please input your name:')
    length = len(name)
    name = name.lower()       
    alphabet_combine(name,length)
main()
```
以上是作业L1，而作业L2只需将
```python
for k in range(20):
        for j in range(7):
            for i in range(length):
                screen[j]=move[0]*k+screen[j]+dictionary[string[i]][j] 
            print screen[j]
            screen = [' ']*7
        time.sleep(0.2)
        os.system('cls')
    return screen
```
替换为
```python
 for k in range(20):
        for j in range(7):
            for i in range(length):
                screen[j]=move[0]*int(math.cos(k)*10+40-2*k)+screen[j]+dictionary[string[i]][j]
            print screen[j]
            screen = [' ']*7
        time.sleep(0.2)
        os.system('cls')
        print ('\n')*int(math.sin(k)*10+15-k)
    return screen
```
## 四、结论 ##
这个程序让我们能够在屏幕上展现一些有意思的东西，在写程序的时候开始出了很多错误，虽然这些还都是基础，但慢慢改完了之后发现自己进步了不少。
## 五、致谢 ##
### [13级学长chenfeng](https://github.com/chenfeng2013301020145/computational-physics_N2013301020145/blob/master/Exercise/1st%20assignment.md)
### [How to Think Like a Computer Scientist: Interactive Edition](http://interactivepython.org/runestone/static/thinkcspy/index.html)
