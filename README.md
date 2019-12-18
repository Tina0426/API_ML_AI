# “我是铲屎官” 产品PRD
|发布日期|2019-12-8|
|:---|:---:|
|项目名称|我是铲屎官|
|项目现状|进行中|
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


### 核心价值：（最小可行性产品）
用户通过上传照片找到与自己宠物有相似病症的病历，获取照顾自己宠物的提示。

用户痛点：
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



## 产品规划

### 产品架构图

!(我是铲屎官_产品架构图)[C:\Users\大软爸爸\Desktop\API_期末\我是铲屎官_功能架构图.png]
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


### 


   
