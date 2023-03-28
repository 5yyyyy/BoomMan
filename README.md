# BoomMan
## 该说明仅针对此项目 此项目为手机游戏
### Unity版本 2022.1.12  

### 关于素材处理  
使用的素材作者为Pixel Frog 已上传文件Pirate Bomb.zip 特此感谢
Tile-Sets中的瓦片地图配置需要更改 Sprite Mode改为Multiple多个图片可以切割 Pixels Per Unit改为对应像素64*64 Filter Mode改为Point调整比例时不会变糊 Compression改为None不压缩会更清晰 之后按照64*64来切割素材即可 在切割后可以选中单独瓦片进行名字的更改 方便查看

### 关于地图绘制
使用2D Tilemap绘制 按住shift快速删除图画过的模块 按B绘制Tilemap 右键2D Object创建Tilemap 需要创建Window-->2D-->Tile Palette画板使用 创建好画板新建画板存储位置 将切好的瓦片地图导入后也需要新建瓦片的存储位置后即可绘制地图 需要注意在Grid下图层的排列 可新建多个Tilemap来管理不同的图层 需要注意渲染层级的遮挡问题 可以新建图层分类或者更改Order in Layer中的数字

### 关于2D Tilemap Extra -- Rule Tile
使用2D Tilemap Extra插件快速绘制地图信息 2022版本自带此插件 以下版本需要自行下载此插件 导入插件后右键Create-->2D-->Tiles-->Rule Tile创建一个规则瓦片 拖拽一个基本信息瓦片后点击下方加号可以增加绘制规则 规则为以该瓦片为中心 可以连接其他瓦片的位置左键单击出现绿色箭头 不需要连接的地方左键双击出现红色叉 若需要按照相同规则时随机生成几个瓦片中的其中一个更改OutPut的Single-->Random后设置需要生成的数量Size后把需要生成的瓦片拖入即可随机生成其中之一 将定好规则的Rule Tile放入Tile Palette中即可按照拟定规则绘制 本项目仅制作背景和平台 Game窗口有裂缝问题需要更改Grid的Cell Size X和Y的值都需要改成0.99

### 关于地图平台碰撞体
在平台中添加Tilemap Collider 2D碰撞体后再添加Composite Collider 2D让所有地图碰撞体连接成一个整体 否则会按照单独碰撞体作为判定 Unity会自动添加一个Rigidbody 2D刚体组件 将Body Type改为Static静止即可 否则会有物理反馈 添加后Tilemap Collider 2D勾选Used By Composite即可

### 关于物品碰撞
为所有物体添加了Polygon Collider 2D和RigidBody 2D来进行碰撞 可以更改RigidBody 2D中的Mess参数 调整物体质量 在物体进行碰撞时会根据质量的不同进行不同的物理反馈 更改Collision Detection为Countinues可以持续检测碰撞 所有物体的默认Layer标签是为Default 在Edit-->Project Settings->Physics 2D-->Layer Collision Matrix下可以更改物体标签的碰撞 左侧为当前物体的标签 上方是可以与该标签碰撞的标签 将所有物体作为预制体

### 关于人物素材处理
人物素材像素调整为32 其他更改和素材处理相同 需要改为Point和None 添加人物层级与背景层级区分 同时添加人物碰撞层级更改Layer Collision Matrix与场景物品不进行碰撞 同时为了保证人物不会旋转需要勾选Rigidbody 2D-->Constraints-->Freeze Rotation-->Z锁定人物Z轴旋转

### 关于人物控制
通过PlayerController控制 跳跃时会改变人物重力 人物渲染图层为NPC 碰撞图层为Player 需要注意图层问题 人物方向反转问题可以使用Scale改变也可以使用Rotation以及Flip 需要注意Flip物体下子集的碰撞体等不会随物体反转而反转

### 关于人物动画处理
使用Animation处理动画 统一20帧 通过PlayerAnimation管理人物动画 JumpFX管理人物跳跃落地特效 移动和跳跃使用float控制 落下和在地上使用bool控制 需要注意特效图层问题

### 关于炸弹
使用计时器来判定炸弹时间 动画事件切换炸弹动画控制 使用方法模拟爆炸效果 人物放置炸弹同样使用计时器控制放置炸弹cd 需要注意炸弹图层问题

### 关于敌人
敌人使用FSM有限状态机控制 抽象类继承控制敌人状态
