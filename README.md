# “我是铲屎官” 产品PRD
- [PPT 20*20 介绍](https://github.com/Tina0426/API_ML_AI/blob/master/%E4%BA%A7%E5%93%81%E4%BB%8B%E7%BB%8D.pptx)  
  
  
|发布日期|2019-12-8|
|:---|:---:|
|项目名称|我是铲屎官|
|项目现状|已完成|
|项目主人|郭沅宜|
|项目设计师|郭沅宜|
|项目开发者|郭沅宜|
|项目测试者|郭沅宜|
## 价值主张设计
### 背景概述
   2018年中国养宠物人数达7355万（含水族），“它经济”（即宠物经济）市场规模达1780亿。表明，中国宠物市场庞大，而且宠物主人为宠物花费的意愿较强。反观中国宠物APP的发展现状：现在中国宠物APP多以购物、上门服务为主；而且宠物APP中，社交性的应用数量少，而且功能尚不完善。此外，宠物APP在应用市场的排名普遍靠后，可以看出中国的宠物应用市场还处于探索期。
   此外，随着今年来宠物博主在社交平台上越来越火热，许多人新手开始加入到饲养宠物的大军中，但是由于缺乏经验，网上饲养宠物的新手教程贴子又未必能够样样具备，当宠物发生异常时，新手主人稍有不慎将有可能加重宠物的病情。

### 加值宣言
- 用户通过上传宠物身体上异常的照片，系统通过相似图片识别，调用检索接口，在自建库中搜索相似图片集，并给出相似度分值，反馈给用户相似的图片和图片所属的贴子，为用户找到有相似病症的宠物主人发布的内容，从而可以获取他人在照顾宠物时的经验、方法。
- 当宠物走时时，上传宠物最具特征的图片至社交圈，系统通过通过其他用户上传的相似图片识别，找出相似度高且打上走失标签图片的图片，缩短用户在大范围内寻找宠物的时间。
- 有的时候我们可能会有幸遇到那些珍稀的动物，但是不幸的是我们并不了解它们，而当时它们又正需要帮助，该怎么办呢？我们可以打开APP，然后拍下它们的照片并上传，我们就能够知道他们到底是什么动物，是否足够稀有，而且恰好需要帮助，那么我们就可以联系有关部门过来保护他们。


### 核心价值：（最小可行性产品）
用户通过上传照片找到与自己宠物有相似病症的病历，获取照顾自己宠物的提示。

#### 用户痛点：
- 痛点一：宠物突然患病，主任没有照顾的经验。
- 痛点二：宠物不见了，但是范围过大，不好寻找。
### 针对用户：
饲养动物的新手、宠物喜欢离家出走的主人、宠物病症特殊的主人

### 需求列表与人工智能API价值
|用户案例|对应API|重要程度|
|:---|:---:|---:|
|用户想找到与自己宠物相类似的病症图片与照顾经验贴子|相似图片识别|非常重要|
|用户的宠物走失了，用户想在网站看看有没有人看到自己宠物并上传至社交圈，以方便缩小寻找难度|相似图片识别|非常重要|
|用户偶然间看到了稀奇的动物但是无法确定物种是保护动物，如果确定为保护动物的话，可以致电有关部门为其寻求帮助|动物识别|普通|

### 应用场景
- 场景一：
    小明在某个深夜发现养的宠物猫咪身上长出了红斑点，但是他是一位新手铲屎官，他一时不知道该怎么处理猫咪身上的斑点。放着不管又担心小猫咪，又怕自己擅自处理小猫咪身上的红斑又怕会加重猫咪的病情。
    于是小明打开了“我是铲屎官”的APP，拍下小猫身上的红色斑点上传到“找病历”的功能中，系统通过识别上传的图片为小明找到了相似的照片及其附带的相关病症的照顾经验贴子。

- 场景二：
  小红家的狗不见了，而且自己的宠物又很能跑，只靠自己去找回宠物非常困难。
  于是小红打开了“我是铲屎官”APP，在“找宠物”的功能里面上传了小狗最有特色的一张图片，于是系统通过识别上传的图片为小红找到了相似的特征小狗的照片及其附带的相关信息，帮助她寻找它的小狗。
  
- 场景三：
小A在路上遇到了一只从来没有见过的野生动物，而且看起来是误闯到了人类生活的区域，扔下不管可能会有危险，但是它不确定是不是真的珍惜的野生动物是否需要特殊处理，于是小A打开了APP，拍下该动物的照片并上传识别，发现是是一只“朱鹮”，于是致电给中国野生动物保护协会来拯救这只朱鹮。

### 人工智能概率性
- 百度API：相似图片搜索：
1. 可自建图库支持亿级图片量上传入库，实现实时检索，单图毫秒级响应。
2. 基于数千万级的训练数据、数万个语义类别进行模型训练及图库积累，使用精准的算法迭代模型不断提高准备度。

   综上可知，用户在社交群中上传越多的照片，图库的量就最大，能够检索出的结果就越多，找到符合用户需求照片（病症）的概率就越大。而且能够实现实时检索，单图能够做到毫秒级响应，能够快速为用户匹配到相似的宠物病症。此外，大量的的语义类别能够帮助用户更加精确地找到有效的病症。同样的，足够大的图库量，能够提升主人找回宠物的可能性。 
   但是仍然有可能将返回不了相似图片或者相似图片返回错误，所以，我们将相似图片API与标签相结合，来较低人工智能的错误率对用户体验产生的影响



## 产品规划

### 产品流程图
![我是铲屎官_产品流程图](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E6%88%91%E6%98%AF%E9%93%B2%E5%B1%8E%E5%AE%98_%E4%BA%A7%E5%93%81%E6%B5%81%E7%A8%8B%E5%9B%BE%20.png)

### 产品功能架构图
![我是铲屎官_功能架构图](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E6%88%91%E6%98%AF%E9%93%B2%E5%B1%8E%E5%AE%98_%E5%8A%9F%E8%83%BD%E6%9E%B6%E6%9E%84%E5%9B%BE.png)


## 产品原型

[原型](http://nfunm017.gitee.io/api_ml_ai)
- 查找病历  
  
![点击查找病历](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E5%AF%BB%E6%89%BE%E7%97%85%E5%8E%86.jpg)  
  
- 编辑病历内容  
  
![编辑病历的内容以及上传图片](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E7%BC%96%E8%BE%91%E7%97%85%E5%8E%86%E5%86%85%E5%AE%B9.jpg)  

- 通过识别找出相似的图片并且返回相应的病历  
  
![找到病历](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E6%89%BE%E5%88%B0%E7%97%85%E5%8E%86.jpg)  
  
- 编辑、分享病历  
  
![编辑内容、分享病历](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E5%88%86%E4%BA%AB%E7%97%85%E5%8E%86.jpg)  
  
- 使用找走失动物的功能  
  
![找宠物功能](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E6%89%BE%E5%AE%A0%E7%89%A9.jpg)  
  
- 编辑自己宠物走失的信息、身上的特征  
  
![通过图片返回相似的宠物图片](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E9%80%9A%E8%BF%87%E5%8C%B9%E9%85%8D%E6%89%BE%E5%88%B0%E5%AE%A0%E7%89%A9.jpg)  


- 发现走失的宠物  
  
  ![发现别人的宠物走失时](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E5%8F%91%E7%8E%B0%E5%88%AB%E4%BA%BA%E7%9A%84%E5%AE%A0%E7%89%A9.jpg)  
  
  
- 将走失的动物照片上传至图库
![上传走失的动物照片](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E4%B8%8A%E4%BC%A0%E5%88%AB%E4%BA%BA%E5%AE%A0%E7%89%A9%E8%B5%B0%E5%A4%B1%E7%9A%84%E7%85%A7%E7%89%87.jpg)  
  
- 识别珍稀动物  

![上传珍稀动物的照片](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E5%8F%91%E7%8E%B0%E5%8A%A8%E7%89%A9.jpg)  
  
- 识别成功返回相关信息    
    
![识别动物成功](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E5%AF%BB%E6%89%BE%E5%8A%A8%E7%89%A9%E6%88%90%E5%8A%9F.jpg)  
  


### API的运用
- 百度API：类似图片搜索
接口描述：  
在自建图库中找到与检索图片语义相似的图片集，并给出相似度打分（综合图片类型、颜色、内容、布局等特征）；适用于各种相似图片查找、相关内容推荐场景。  
接口地址：  
https://aip.baidubce.com/rest/2.0/realtime_search/same_hq/add?access_token=24.f9ba9c5241b67688bb4adbed8bc91dec.2592000.1485570332.282335-8574074  

请求方法：POST  
建立图片库：  

```
from aip import AipImageSearch
""" 你的 APPID AK SK """
APP_ID = '你的id'
API_KEY = 'API key'
SECRET_KEY = 'secret key'
client = AipImageSearch(APP_ID, API_KEY, SECRET_KEY)
""" 读取图片 """
def get_file_content(filePath):
    with open(filePath, 'rb') as fp:
        return fp.read()
url = "https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1576664027723&di=6b8ba1ebac07f21bf9532a42082b829f&imgtype=0&src=http%3A%2F%2Fgss0.baidu.com%2F94o3dSag_xI4khGko9WTAnF6hhy%2Fzhidao%2Fpic%2Fitem%2F279759ee3d6d55fb62af20ec6f224f4a21a4dd8b.jpg"
client.similarAddUrl(url);
""" 如果有可选参数 """
options = {}
options["brief"] = "{\"name\":\"猫藓\", \"id\":\"666\"}"
options["tags"] = "1"
""" 带参数调用相似图片搜索—入库, 图片参数为远程url图片 """
client.similarAddUrl(url, options)
```
搜索照片：  
```
def get_file_content(filePath):
    with open(filePath, 'rb') as fp:
        return fp.read()
url = "https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=2295067928,2583641020&fm=26&gp=0.jpg"
client.similarSearchUrl(url);
options = {}
options["tags"] = "100,11"
client.similarSearchUrl(url, options)
```
结果：  
```
{'has_more': False,
 'log_id': 9124903545715924818,
 'result_num': 1,
 'result': [{'score': 0.70554447174072,
   'brief': '{"name":"猫藓", "id":"666"}',
   'cont_sign': '1570273859,4007812260'}]}
```

- 百度API：动物识别
接口描述：输入一张动物照片，输出动物识别结果  
接口地址：http://https//ai.baidu.com/ai-doc/IMAGERECOGNITION/Zk3bcxdfr  
请求方法：POST

输入代码：  
```
def get_file_content(filePath):
    with open(filePath, 'rb') as fp:
        return fp.read()
image = get_file_content('朱鹮.jpg')
client.animalDetect(image);
options = {}
options["top_num"] = 3
options["baike_num"] = 5
client.animalDetect(image, options)
```
输出：  
```
{
	"log_id": "3739980897571176466",
	"result": [
		{
			"score": "0.971646",
			"name": "朱鹮"
		},
		{
			"score": "0.0217333",
			"name": "秦岭四宝"
		},
		{
			"score": "0.00249143",
			"name": "朱鹭"
		},
		{
			"score": "0.00036921",
			"name": "美洲白鹮"
		},
		{
			"score": "0.000339712",
			"name": "白鹮"
		},
		{
			"score": "0.000238314",
			"name": "琵鹭"
		}
	]
}
```


 

### 百度与阿里之间 相似照片的搜索 比较
- 从图库的容量上，百度图库的容量比阿里云的图库容量大，阿里云的图库容量只能到达10万，百度图库容量可达1000万。
- 从请求参数上，百度的请求参数更多，能够对图片进行标签分类，而阿里的请求参数相对较少，能够选择的空间较少，难以对图库里面的图片进行分类处理。
- 百度的动物识别能够与百度百科连接使用而阿里只能在返回动物的名称。
![百度可请求的参数更加多样化](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E7%99%BE%E5%BA%A6AI%E5%8F%AF%E8%AF%B7%E6%B1%82%E5%8F%82%E6%95%B0.jpg)  
![阿里可请求参数比较少](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E9%98%BF%E9%87%8C%E4%BA%91%E5%8F%AF%E8%AF%B7%E6%B1%82%E5%8F%82%E6%95%B0.jpg)  

## 后风险报告
#### 相似图片搜索API定价
- 图库定价  
![百度图库定价](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E7%99%BE%E5%BA%A6%E5%9B%BE%E5%BA%93%E5%AE%9A%E4%BB%B7.jpg)  

- 调用量定价  
![调用量定价](https://github.com/Tina0426/API_ML_AI/blob/master/image/%E7%99%BE%E5%BA%A6%E8%B0%83%E7%94%A8%E9%87%8F%E5%AE%9A%E4%BB%B7.jpg)  
  
  
#### 输入限制
该接口实现单张图片入库，入库时需要同步提交图片及可关联至本地图库的摘要信息（具体变量为brief，具体可传入图片在本地标记id、图片url、图片名称等）；同时可提交分类维度信息（具体变量为tags，最多可传入2个tag），方便对图库中的图片进行管理、分类检索。
请求图片需经过base64编码：图片的base64编码指将一副图片数据编码成一串字符串，使用该字符串代替图像地址。您可以首先得到图片的二进制，然后用Base64格式编码即可。
注意：图片的base64编码是不包含图片头的，如（data:image/jpg;base64,）


## 产品可行性
- 从目前的宠物APP市场上看，这种查找宠物病历、寻找宠物的社交性APP比较少，而且现在中国越来越多的人选择饲养宠物，有一定的市场需求量。
- 该产品能够帮助饲养新手找到比价合适的饲养宠物的经验，此外还能够帮助宠物走失的主任找到他们的宠物
- 动物识别功能能够帮助人们认识在偶然间发现的珍稀动物，如果这种珍稀动物在被发现时刚好处于危险的状态中，我们能够联系有关的部门来帮助它们。


## 结果预期
该APP是一个社交型的APP，图库的来源取决于用户是否上传了足够多的图片与经验，如果没有用户上传的相似图片，在前期的API调用上失败率非常高，通常的情况下就是找不到相似的宠物图片和宠物病症图片，在这种情况下，应该给予分享病历的用户与帮忙寻找宠物的用户相应的奖励。增大我们的图库里的图库量。



   
