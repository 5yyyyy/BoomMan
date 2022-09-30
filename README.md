# BoomMan
## 该说明仅针对此项目 此项目为手机游戏
### Unity版本 2022.1.12  

### 关于素材处理  
使用的素材作者为Pixel Frog 已上传文件Pirate Bomb.zip 特此感谢
Tile-Sets中的瓦片地图配置需要更改 Sprite Mode改为Multiple多个图片可以切割 Pixels Per Unit改为对应像素64 Filter Mode改为Point调整比例时不会变糊 Compression改为None不压缩会更清晰 之后按照64*64来切割素材即可 在切割后可以选中单独瓦片进行名字的更改 方便查看

### 关于地图绘制
使用2D Tilemap绘制 按住shift快速删除图画过的模块 按B绘制Tilemap 右键2D Object创建Tilemap 需要创建Window-->2D-->Tile Palette画板使用 创建好画板新建画板存储位置 将切好的瓦片地图导入后也需要新建瓦片的存储位置后即可绘制地图 需要注意在Grid下图层的排列 可新建多个Tilemap来管理不同的图层 需要注意渲染层级的遮挡问题 可以新建图层分类或者更改Order in Layer中的数字

### 关于2D Tilemap Extra
使用2D Tilemap Extra插件快速绘制地图信息 2022版本自带此插件 以下版本需要自行下载此插件 导入插件后右键Create-->2D-->Tiles-->Rule Tile创建一个规则瓦片 拖拽一个基本信息瓦片后点击下方加号可以增加绘制规则 规则为以该瓦片为中心 可以连接其他瓦片的位置左键单击出现绿色箭头 不需要连接的地方左键双击出现红色叉 若需要按照相同规则时随机生成几个瓦片中的其中一个更改Single-->Random后设置需要生成的数量Size后把需要生成的瓦片拖入即可随机生成其中之一 将定好规则的Rule Tile放入Tile Palette中即可按照拟定规则绘制 本项目仅制作背景和平台

