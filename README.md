环境搭建
===================================

Windows7（8.1）  Python，Numpy，matpltlib安装教程 
----------------------------------------------
### 1.安装python
        在官网下载，并加入系统环境变量内,可在命令台输入python进行测试。

### 2.安装networkx-1.11-py2.7.egg
        NetworkX是一个用Python语言开发的图论与复杂网络建模工具，内置了常用的图与复杂网络分析算法，可以方便的进行复杂网络数据
        分析、仿真建模等工作。启动DOS控制台（在“运行”里输入cmd），
        输入D:\Android\python\Lib\site-packages\easy_install.py D:\networkx-1.11-py2.7.egg，回车后
        会自动执行安装。注意我是把networkx-1.11-py2.7.egg放到了D盘根目录，读者在安装时应该具体根据情况修改路径。
        在命令台测试

        C:\Users\zcr>python                   
        Python 2.7.9 (default, Dec 10 2014, 12:28:03) [MSC v.1500 64 bit (AMD64)] on win
        32
        Type "help", "copyright", "credits" or "license" for more information.
        >>> import networkx as nx
        >>> print nx
        <module 'networkx' from 'D:\Android\Python\lib\site-packages\networkx-1.11-py2.7
        .egg\networkx\__init__.pyc'>

        可正确输出<module 'networkx' from 'D:\Android\Python\lib\site-packages\networkx-1.11-py2.7.egg\networkx\__init__.pyc'>，
        配置正确。

###3.（此处与步骤5冲突，可忽略此步）安装Matplotlib
        Matplotlib是一个Python的图形框架，类似于MATLAB和R语言。[点击这里你可以链接到www.google.com](http://www.google.com)<br /> Matplotlib的官网地址是 [http://matplotlib.org/](http://matplotlib.org/)<br /> ，下载地址为
        http://matplotlib.org/downloads.html 选择对应的版本即可安装，我选择的版本为 matplotlib-1.3.1.win32-py2.7.exe
        下载链接
        https://downloads.sourceforge.net/project/matplotlib/matplotlib/matplotlib-1.3.1/matplotlib-1.3.1.win32-py2.7.exe
        下载成功，直接运行即可。

###4.安装numpy
        本人使用的是numpy-MKL-1.8.0.win-amd64-py2.7.exe，可百度下载。需要选对版本，一路next。

###5.安装 matplotlib-1.5.3-cp27-cp27m-win_amd64.whl
        http://www.lfd.uci.edu/~gohlke/pythonlibs/#matplotlib  这个网址下面包含了非常多的python第三方库文件。
        使用浏览器搜索matplotlib即可定位到这里： 
        matplotlib‑1.5.0‑cp27‑none‑win32.whl 支持python2.7 
        matplotlib‑1.5.0‑cp27‑none‑win_amd64.whl 支持python2.7 64位系统    √ 本人选择的此版本
        matplotlib‑1.5.0‑cp33‑none‑win32.whl 支持python3.3 
        matplotlib‑1.5.0‑cp33‑none‑win_amd64.whl 支持python3.3 64位系统 
        matplotlib‑1.5.0‑cp34‑none‑win32.whl 支持python3.4 
        matplotlib‑1.5.0‑cp34‑none‑win_amd64.whl 支持python3.4 64位系统 
        matplotlib‑1.5.0‑cp35‑none‑win32.whl 支持python3.5 
        matplotlib‑1.5.0‑cp35‑none‑win_amd64.whl 支持python3.5 64位系统 
        matplotlib‑1.x‑windows‑link‑libraries.zip 需要依赖的其他的库文件压缩包 
        matplotlib_tests‑1.5.0‑py2.py3‑none‑any.whl 重要文件，可以下载没有的库文件

        在命令行中输入命令：pip install 下载目录\matplotlib‑1.5.0‑cp27‑none‑win_amd64.whl  即可。 
        如: pip install D:\matplotlib‑1.5.0‑cp27‑none‑win_amd64.whl
        安装成功，可在python环境输入以下命令看是否有误。

        import matplotlib.pyplot as plt
        import networkx as nx 

###6.搭建成功
        新建test.py,内容如下
        
        #--This is a test
        import numpy as np
        import matplotlib.pyplot as plt
        N = 5
        menMeans = (20, 35, 30, 35, 27)
        menStd =   (2, 3, 4, 1, 2)
        ind = np.arange(N)  # the x locations for the groups
        width = 0.35       # the width of the bars
        fig, ax = plt.subplots()
        rects1 = ax.bar(ind, menMeans, width, color='r', yerr=menStd)
        womenMeans = (25, 32, 34, 20, 25)
        womenStd =   (3, 5, 2, 3, 3)
        rects2 = ax.bar(ind+width, womenMeans, width, color='y', yerr=womenStd)
        # add some
        ax.set_ylabel('Scores')
        ax.set_title('Scores by group and gender')
        ax.set_xticks(ind+width)
        ax.set_xticklabels( ('G1', 'G2', 'G3', 'G4', 'G5') )
        ax.legend( (rects1[0], rects2[0]), ('Men', 'Women') )
        def autolabel(rects):
            # attach some text labels
            for rect in rects:
                height = rect.get_height()
                ax.text(rect.get_x()+rect.get_width()/2., 1.05*height, '%d'%int(height),
                        ha='center', va='bottom')
        autolabel(rects1)
        autolabel(rects2)
        plt.show()
        #--This is a test

        在python GUI窗口运行test.py，运行成功，可成功绘制图


###第一次写教程###
本文多摘抄自互联网，参考了如下教程。

        http://blog.sina.com.cn/s/blog_720448d301018px7.html
        http://blog.csdn.net/moodytong/article/details/7282008
        http://blog.csdn.net/u010156024/article/details/50056855
        http://www.open-open.com/lib/view/open1393488232380.html
        http://wenku.baidu.com/linkurl=gQvP5Am3v0OYsOhMkK_ShGQylgakrkAg6ArLalSK1VMO5UIBzBANQZhsBasrTAsQe44TeevqF61rXQ4qHjBuWqUIvz6M2dNFvzxnAc6nKfq

