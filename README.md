## 环境不可控场景下拍照文档地址文字识别  

这个是 2018年 Deecamp 25组 的OCR项目，非常非常感谢每一位队友！  

此fork具体介绍检测部分的工作内容。
  
我的贡献：CTPN检测部分 + 微信小程序
  
Our Demo: https://www.bilibili.com/video/av30081208  
Our Wechat Program (微信小程序)： OCRdeecamp （因服务器回收，功能暂不可用）  
<img src="https://github.com/Walleclipse/ChineseAddress_OCR/raw/master/demo/demo.png" width="600" >  
Reference Paper: Detecting Text in Natural Image with Connectionist Text Proposal Network https://arxiv.org/pdf/1609.03605.pdf  
Reference Code: https://github.com/YCG09/chinese_ocr (Thanks Yang Chenguang)  


## Method 
Text Detection : CTPN (https://arxiv.org/pdf/1609.03605.pdf)  
Text Recognition: CTC+DenseNet  
Address Judgment: Light GBM or textgrocery (https://github.com/2shou/TextGrocery)  
Address Correction: Fuzzy matching based on address library   

<div style="float:center;border:solid 1px 000;margin:2px;"><img src="https://github.com/Walleclipse/ChineseAddress_OCR/raw/master/demo/method.png"  width="700" ></div>  
  
## About Code
demo_final.py  
You can simply use demo_final.py for inference. Input a picture and output the Chinese address string.   
run_flask.py  
Communicate between server and wechat program using flask  
ocr_whole.py  
Text detection using CTPN, then text recognition using Densenet  
stupid_addrs_rev.py  
Address correction using fuzyy-matching based on address library  
ctpn  
If you want to know more details about CTPN codes, please check https://github.com/eragonruan/text-detection-ctpn  
wechat_program  
Some files of wechat program (微信小程序的一些文件)

## Results
In our dataset, the accuracy of exactly correct is 83%, accuracy of edit distance less than 3 is 97%.   
Our program has a high accuracy at identifying very fuzzy multi-line addresses. 

<div style="float:left;border:solid 1px 000;margin:2px;"><img src="https://github.com/Walleclipse/ChineseAddress_OCR/raw/master/demo/result2.png" width="750" ></div>   
