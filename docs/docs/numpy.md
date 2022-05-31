# numpy
## 基本概念 

纬度，秩 ， 轴

ndarray.ndim - 数组的轴（维度）的个数。在Python世界中，维度的数量被称为rank。

举例说明：我们描述一个点的时候，通常使用 x 轴、y 轴，这样就能确定一个点的具体位置了。因此，这里的两个维度，也就跟两个轴对应了起来。如果是立体的三维世界中，我们就会多出一个z轴，以此更加准确的来反映点的位置。所以，我么可以把以上的维度和轴进行等价。

什么是秩(rank)？它是指轴的数量，或者维度的数量，是一个标量

在下面的例子中，有一个数组 [1,2,1]， 它的维度是1，也就是有一个轴，这个轴的长度是3，而它的秩也为1。这些信息，都可以通过NumPy提供的数组属性来获得ndarray.ndim the number of axes (dimensions) of the array秩，数组轴的数量，或者维度的数量

![clipboard.png](.\assets\clip_image200.gif)

### 一维数组：

![clipboard.png](.\assets\clip_image400.gif)

数组a的维度数是1。查看它的shape，返回值为元组(3,) ，从这里也可以反映出这个数组的基本形状，即它是1维的，在这1维的空间中，拥有3个数据。

### 二维数组：

![ip_image002.jpeg](.\assets\clip_image600.jpg)


![clipboard.png](.\assets\clip_image800.gif)


![clipboard.png](.\assets\clip_image100.gif)


数组b，从属性 ndim 中可以知道，它的秩为2，即轴的个数是2，或者维度的数量是2（行和列两个维度）。shape中反映出来的是，它是2行3列的一个矩阵。

当前轴的数量已经上升为2，那么NumPy中是怎么定义这个轴的方向的呢？在二维中，轴0表示了数组的行，轴1表示了数组的列。因此，在该列中轴0的长度是2，轴1的长度是3。

如果我们把轴0上的数进行相加，可以得到一个一维数组，值为[5,7,9]，数组的元素个数为3。

如果我们把轴1上的数进行相加，也可以得到一个一维数组，但值为[6, 15]，数组的元素个数为2。

所以在不同轴上进行数据操作会得到不同的值，数组中的值是由沿轴方向上的数据相加所得。


### 三维数组：

![clipboard.png](.\assets\clip_image120.gif)


![clipboard.png](.\assets\clip_image140.gif)


我们再升级一个维度，使其成为一个3维数组，秩的值已经变为3，它的shape反映出它的轴0长度为2，轴1长度为2，轴2的长度为3。

![clipboard.png](.\assets\clip_image160.gif)

![clipboard.png](.\assets\clip_image180.gif)


参考 ：https://zhuanlan.zhihu.com/p/77974803


**np.where(condition)**

坐标以tuple的形式给出，通常原数组有多少维，输出的tuple中就包含几个数组，分别对应符合条件元素的各维坐标。

\>>> a = np.array([2,4,6,8,10])>>> np.where(a > 5)# 返回索引(array([2, 3, 4]),)>>> a[np.where(a > 5)]# 等价于 a[a>5] array([ 6, 8, 10])