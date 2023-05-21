
<h1>交通标志检测系统</h1>

![img_14.png](img_14.png)

---
<h3>1.获取项目</h3>
<h7>在新建的文件夹下进入命令窗口</h7>

![img_8.png](img_8.png)

<h7>输入命令行获取GITHUB上的项目TSD
```bash
$ git clone https://github.com/Lynch-lam/TSD.git
```
![img_7.png](img_7.png)

---

<h3>2.数据集下载</h3>

<h6> 链接：https://pan.baidu.com/s/1zaaoar7GVd-eip8GiQ3JpA   提取码：6666</h6>

<h6> 放在项目的同级目录data中（不是子目录下），如下图所示</h6>

![img_9.png](img_9.png)

---

<h3>3.添加国内镜像源

<h6>在Anaconda prompt中，添加国内源加速后续需要第三方库的下载

```bash
conda config --remove-key channels
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/main/
conda config --add channels https://mirrors.ustc.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.bfsu.edu.cn/anaconda/cloud/pytorch/
conda config --set show_channel_urls yes
pip config set global.index-url https://mirrors.ustc.edu.cn/pypi/web/simple
```

---

<h3>4.创建虚拟环境</h3>

```bash
conda create -n TSD python==3.8.5
conda activate TSD
```

---

<h3>5.Pytorch安装</h3>



<h7>对于30系的显卡，我们的cuda不能小于11，对于10和20系的显卡，一般使用的是cuda10.2。下面给出了30系显卡、30系以下显卡和cpu的安装指令，根据自己的电脑配置自行下载。

```bash
conda install pytorch==1.10.0 torchvision torchaudio cudatoolkit=11.3 # 30系列以上显卡gpu版本pytorch安装指令
conda install pytorch==1.8.0 torchvision torchaudio cudatoolkit=10.2 # 10系和20系以及mx系列的执行这条
conda install pytorch==1.8.0 torchvision==0.9.0 torchaudio==0.8.0 cpuonly # CPU的直接执行这条命令
```

<h7>检查GPU是否可用

![img_12.png](img_12.png)

---

<h3>6.其余库安装

```bash
pip install -r requirements.txt
```

---

<h3>7.Pycharm中运行</h3>

1. 添加解释器；
2. 选择刚才创建的虚拟环境；

![img_4.png](img_4.png)


3. 右键执行main_window.py；

![img_13.png](img_13.png)


---
<h3>8.训练模型</h3>

1. 将数据集文件中**my_data.yaml**中的数据路径替换成本地的路径；
![img_10.png](img_10.png)
2. 执行go_train.py训练（可变更参数）；
![img_11.png](img_11.png)
3. 训练结果（以exps为例子）

![img.png](img.png)


<h3>9.测试模型</h3>

1. 修改weight的路径
![img_3.png](img_3.png)
2. 执行go_test.py测试


<h3>10.补充</h3>

1. 自动装包的时候，numpy版本可能会过高（如运行时候报错），降低版本即可