# 机器学习中的数学——矩阵分解(一)

![fb4722319b8b490b7dc8c07725c92324](C:\Users\Administrator\Desktop\fb4722319b8b490b7dc8c07725c92324.jpeg)

[TOC]



## Schmidt正交化

### 不严谨推导

![image-20220523235404347](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220523235404347.png)

### QR分解——Schmidt正交化递推到n

![image-20220523235725929](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220523235725929.png)

<center>
<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220523235800254.png" alt="image-20220523235800254" style="zoom:150%;" />
</center>


## 实对称矩阵的对角化

### 研究原因

![image-20220524000120298](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524000120298.png)

![image-20220524000530225](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524000530225.png)

### 几何理解

![image-20220524000614637](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524000614637.png)

## 谱分解

### Vector形式

![image-20220524001108998](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524001108998.png)

### Matrix形式

**注：**   Vector形式是Matrix形式的分块，这种分块我们还可以在SVD中看到

![image-20220524001214111](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524001214111.png)

<center>
<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524001326748.png" alt="image-20220524001326748" style="zoom:150%;" />
</center>
## 奇异值分解(SVD)

### 提出背景

![image-20220524001653554](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524001653554.png)

### 构造原理

**注： **  构造时，不妨设$m \geq n$

#### 确定V

![image-20220524001933567](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524001933567.png)

![image-20220524002112519](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524002112519.png)

____

**注： **  

1.为什么我们要研究$A^TA$的秩？

因为$A^TA$是对称阵，而对称阵一定可以相似对角化，即$A^TA$与$\Lambda$相似。我们知道，相似的矩阵拥有相同的特征值(因为相似变换是可逆的，可逆的初等变换不改变矩阵的特征多项式/矩阵行列式的值/矩阵的秩)。所以，$A^TA$非零eigenvalue数量=对角化后$\Lambda$的非零eigenvalue数量=对角化后$\Lambda$的秩=$A^TA$的秩。

2.为什么$Rank(A)=r$，有$Rank(A^TA)=r$？

![image-20220524002207206](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524002207206.png)

____

![image-20220524002307778](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524002307778.png)

![image-20220524002344355](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524002344355.png)

#### 确定U

![image-20220524002437364](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524002437364.png)

![image-20220524004833273](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524004833273.png)

**注：**为什么想到这样构造？

![image-20220524004634473](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524004634473.png)

<center>
<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524004651823.png" alt="image-20220524004651823" style="zoom:150%;" />
</center>

**下面就是求整个$U$，即找到$U_2$**

![image-20220524005656671](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524005656671.png)

![image-20220524005749065](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524005749065.png)

![image-20220524005947013](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524005947013.png)

最后进行合并：

![image-20220524010046916](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524010046916.png)

#### 证明前面构造的U,Σ,V是矩阵的SVD

![image-20220524010136117](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524010136117.png)

## 紧奇异值分解和截断奇异值分解

### 紧奇异值分解

![image-20220524010409865](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524010409865.png)

### 截断奇异值分解

![image-20220524010544717](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524010544717.png)

![img](https://img-blog.csdnimg.cn/e05f57f0a0c84dd795160e240aa18ada.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAZGlzYW5kYQ==,size_20,color_FFFFFF,t_70,g_se,x_16)

## SVD的向量分解形式

与谱分解有异曲同工之妙

![image-20220524011037074](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524011037074.png)

## 举个栗子——对一个矩阵进行SVD

<center>
<img src="C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524011059774.png" alt="image-20220524011059774" style="zoom:150%;" />
</center>

![image-20220524011154902](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524011154902.png)

![image-20220524011223386](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524011223386.png)

![image-20220524011240458](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524011240458.png)

![image-20220524011336528](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524011336528.png)

## SVD的主要性质

### 分解结果不唯一

![image-20220524011442310](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524011442310.png)

### U的求法不唯一

可以使用$AA^T$求$U$

![image-20220524011512849](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524011512849.png)

## 对于SVD的几种理解

### 信息压缩

![image-20220524011709904](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524011709904.png)

### 降维

![image-20220524011910541](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524011910541.png)

**小记：**

![image-20220524011955184](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524011955184.png)

### 线性变换的分解(几种变换的复合)

![image-20220524012132534](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524012132534.png)

![img](https://img-blog.csdnimg.cn/ac11270f171648738b2270fe62587a6e.png)

### SVD：从一个优化的观点出发

#### SVD是对原始数据阵D的最优k维近似

![image-20220524012331613](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524012331613.png)

![image-20220524012419229](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524012419229.png)

#### OP1：最大化矩阵U的energy

![image-20220524012521770](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524012521770.png)

![image-20220524012802126](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524012802126.png)

![image-20220524012850435](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524012850435.png)

**A note(How to slove a problem which is the same as OP1):**

![image-20220524012625221](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524012625221.png)

![image-20220524012650536](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220524012650536.png)

#### OP2：最小化近似误差

OP2 (A Minimization Formulation with Residuals):

$$ Minimize_{[U,V]} \quad J =||D-UV^T||_F^2 $$

We can prove that OP2 is equivalent to OP1 after learning matrix calculus.

