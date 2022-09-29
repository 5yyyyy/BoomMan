# BoomMan
## 该说明仅针对此项目 此项目为手机游戏
### Unity版本 2022.1.12  

### 关于素材处理  
使用的素材作者为Pixel Frog 已上传文件Pirate Bomb.zip 特此感谢
Tile-Sets中的瓦片地图配置需要更改 Sprite Mode改为Multiple多个图片可以切割 Pixels Per Unit改为对应像素64 Filter Mode改为Point调整比例时不会变糊 Compression改为None不压缩会更清晰 之后按照64*64来切割素材即可

### 关于地图绘制
使用2D Tilemap绘制 按住shift快速删除图画过的模块 按B绘制Tilemap 右键2D Object创建Tilemap 需要创建Window-->2D-->Tile Palette画板使用 创建好画板新建画板存储位置 将切好的瓦片地图导入后也需要新建瓦片的存储位置后即可绘制地图 需要注意在Grid下图层的排列 可新建多个Tilemap来管理不同的图层
