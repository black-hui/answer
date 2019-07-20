# answer

ans1

import numpy as np  #调取矩阵库,并定义np为矩阵

matrixA=[]           #定义list：matrixA

for A in open ("matrixA.txt"):       #定义字符串A为打开的文本
    matrixA.append( [int (i) for i in A.split(",")])    #以'，'作为切分形成list，每一次list及所含元素进行累加

matrixB=[]       #定义list：matrixB 

for B in open ("matrixB.txt"):
    matrixB.append( [int (j) for j in B.split(",")])

matrixA = np.array(matrixA)    #制作成矩阵
matrixB = np.array(matrixB)

ans = matrixA.dot(matrixB)     #矩阵A乘以B
sorted(ans)             #按从大到小顺序排列
np.savetxt("Q1_ans.txt", ans, fmt="%d", delimiter="\r\n")  #将矩阵np保存为txt文本形式


ans2

from PIL import Image

lena = Image.open("lena.png")
lena_modified = Image.open("lena_modified.png")

w, h = lena.size
for j in range(h):
    for i in range(w):
        if lena.getpixel((i, j)) == lena_modified.getpixel((i, j)):
            lena_modified.putpixel((i, j), 255)

lena_modified.show()
lena_modified.save("ans_two.png")
