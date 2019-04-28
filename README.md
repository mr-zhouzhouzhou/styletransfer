**图像风格融合与快速迁移**<br>
训练过程：
    1156轮<br>
 ![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/1156.jpg)<br>
    4500轮<br>
 ![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/4500.jpg)<br>
    6000轮<br>
 ![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/6000.jpg)<br>
    10000轮<br>
 ![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/10000.jpg)<br>
    20000轮<br>
 ![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/20000.jpg)<br>
    31000轮<br>
 ![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/31000.jpg)<br>
    41000轮<br>
 ![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/41000.jpg)<br>
    45000轮<br>
 ![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/45000.jpg)<br>
 
 **app展示**<br>
1：项目的首页
 ![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/79816200bc261c4abe08f43bf4d7768.png)<br>
2：选择4种不同的风格
 ![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/030a3982d446a76518c181971820914.png)<br>
 3：选择图片或者进行拍照
 ![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/7475358d9e96425d5900009124271aa.png)<br>
 4：选择图片
 ![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/27cfc33d68e417f54406839be0b2631.png)<br>
 5：加载
 ![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/d898b88d583673a50280386365b8083.png)<br> 
 6：结果
 ![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/4fffdca44807702c0328c2057e8826a.png)<br>
 7：相册
 ![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/22c5fc7949726b5cb2cd196e6a6884f.png)<br>

**结果展示**<br>
![image](https://github.com/mr-zhouzhouzhou/styletransfer/blob/master/img/result25.jpg)<br>
 **项目核心代码**<br>
generateds：生成tfrecords训练集<br>
forward：前向传播过程，包括图像生成网络、损失函数网络和loss的计算<br>
backward：主要训练过程<br>
test：测试部分<br>
app：展示接口，做外部接口调用


 **准备部分**<br>
一、运行环境<br>
python3.6.7<br>
二、coco数据集<br>
http://images.cocodataset.org/zips/train2014.zip <br>
放在 ./core/MSCOCO/ 文件夹中<br>
三、下载vgg16预训练模型
百度网盘：https://pan.baidu.com/s/1gg9jLw3  密码:umce，<br>
放在 ./core/vggnet 文件夹中<br>
四、制作coco数据集tfRecords<br>
执行generateds.py<br>

**训练模型**
```
执行backward.py
```
1、提供断点续训功能<br>
2、提供训练好的模型<br>
3、在训练过程中，每500轮将会保存一张训练图片在./core/save_training_imgs/中，可从中查看训练效果<br>

**测试部分**
1、将测试图片放在./core/test_imgs/中<br>
2、在test.py中，修改测试文件路径PATH_IMG<br>
3、在test.py中，修改风格编号LABEL_1至LABEL_4
4、生成图片存储在./core/results/文件夹中
```
    执行test.py
```


**展示部分**
```
    执行main.py
```
1、在浏览器中打开host地址：127.0.0.1:5000<br>
2、在网页上完成可视化操作<br>

