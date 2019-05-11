# python-
#coding=utf-8
# wirtten by xh, 2018-4-1
#导入模块
import os
#获取输入路径
#path=input('/home/ubtu/VOC_GJ/tomato/1/') 
path='/home/ubtu/VOC_GJ/tomato/2/'          
#获取该目录下所有文件，存入列表中
f=os.listdir(path)
#对获取的文件名进行排序,否则是乱序修改
f.sort()
n=0
s=str(n+1) #将int转换为string，从1开始
s = s.zfill(6) #字符串长度设置，不足左补零
#遍历修改每一个文件名
for i in f:
    #获取旧文件名（就是路径+文件名）
    oldname=path+f[n]
    #设置新文件名，根据自己的文件名和类型修改
    newname=path+s+'.xml'     ###无论是什么文件，图片或者xml文件，只要改后缀就行
    #调用rename()重命名函数
    os.rename(oldname,newname)
    #打印修改结果
    print(oldname,'------------>',newname)
    #更新字符串
    n+=1
    s = str(n+1)
    s = s.zfill(6)
