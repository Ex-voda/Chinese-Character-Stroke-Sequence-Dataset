# Chinese-Character-Stroke-Sequence-Dataset
**汉字笔画序列的图片数据集**

#### 数据集来源

​	本项目整合了Liu.等提出的[CCES数据集](https://github.com/lizhaoliu-Lec/CCSE.git)，以及Arphic Technology Co., Ltd.[提出的汉字笔画数据集](https://github.com/chanind/makemeahanzi.git)。感谢以上两个项目的贡献。

#### 数据集说明

​	包含笔画序列信息的汉字数据集非常稀少，Arphic Technology Co., Ltd.为此提供了一个非常棒的优秀工作（makemeahanzi)，按准确的笔画信息绘制了汉字字符；而Liu.等提出的CCES工作进一步使用25个笔画类别为笔画信息进行了标注。

​	本数据集整合了二者的工作，相较于CCES数据集，本数据集借助makemeahanzi的曲线数据（graphics.txt），将其与CCES的标注数据（fort_annotation.json)对齐，通过曲线信息和标注信息，程序直接在本地生成对应的笔画序列图。因此本数据集的在线文件更小，离线文件分辨率更高。

​	本数据集与CCES一样，包含了9523个汉字的标注信息，所有的图片都是1024*1024的二值图。

​	后期会更新叠加笔画程序

#### 使用说明

​	本项目基于python开发，除了常见的库意外，请运行以下命令安装一些必要的库：

```
pip install opencv-python svgwrite cairosvg 
```

​	为了正确使用 cairosvg ，请前往[这里](https://github.com/tschoonj/GTK-for-Windows-Runtime-Environment-Installer.git)下载GTK-3并重启你的计算机（Windows系统）（默认添加环境变量），直接下载链接在[这里](https://github.com/tschoonj/GTK-for-Windows-Runtime-Environment-Installer/releases/download/2022-01-04/gtk3-runtime-3.24.31-2022-01-04-ts-win64.exe)。

​	本项目的部分文件只是为了保留数据集原始来源的参照，您可以移动以下文件到您的任何项目目录中，但请确保其在一个目录下：

```
data(空目录)
run.py
utils.py
data_graphics.json
fort_annotation.json
```

​	最后，执行命令开始生成数据：

```
python run.py
```

​	生成的笔画序列图储存在 data/jpg/ ，data/svg/ 和 data/png/ 可以按需删除。

#### 更新日志

- 更新了多核并发优化
