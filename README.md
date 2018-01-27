# 本文基于tensorflow、keras/pytorch实现对自然场景的文字检测及端到端的OCR中文文字识别

# 实现功能

- [x] 文字方向检测：fine-tune VGG
- [x] 文本检测：CTPN
- [x] 不定长OCR识别：CRNN

## 环境部署
``` Bash
sh setup.sh
```

# 模型训练

## 训练keras版本的crnn   

``` Bash
cd train & sh train-keras.sh   
```

## 训练pytorch版本的crnn   

``` Bash
cd train & sh train-pytorch.sh   
```

# 文字方向检测
在VGG16模型的基础上进行迁移学习，训练文字方向检测（0、90、180、270度）分类模型，详细代码参考angle/predict.py文件，训练图片8000张，准确率88.23%。

模型下载地址：[百度云](https://pan.baidu.com/s/1pM2ha5P)

# 文字检测
支持CPU、GPU环境，一键部署，文本检测训练参考：[https://github.com/eragonruan/text-detection-ctpn](https://github.com/eragonruan/text-detection-ctpn)

# OCR端到端识别
## 采用GRU+CTC端到到识别技术，实现不分隔识别不定长文字
提供keras与pytorch版本的训练代码，在理解keras的基础上，可以切换到pytorch版本，此版本更稳定   

# 识别结果展示
## 文字检测及OCR识别结果
<div>
<img width="420" height="420" src="https://github.com/chineseocr/chinses-ocr/blob/master/img/tmp.jpg"/>
<img width="420" height="420" src="https://github.com/chineseocr/chinses-ocr/blob/master/img/tmp.png"/>
</div>

### 倾斜文字 

<div>
<img width="420" height="420" src="https://github.com/chineseocr/chinses-ocr/blob/master/img/tmp1.jpg"/>
<img width="420" height="180" src="https://github.com/chineseocr/chinses-ocr/blob/master/img/tmp1.png"/>
</div>

## 参考

1. crnn：https://github.com/meijieru/crnn.pytorch

2. keras-crnn：https://www.zhihu.com/question/59645822 

3. ctpn：https://github.com/eragonruan/text-detection-ctpn, https://github.com/tianzhi0549/CTPN 


