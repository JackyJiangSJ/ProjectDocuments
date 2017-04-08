# 获取附近群组基本资料

## 请求参数
字段|数据类型|示例值|说明|备注
:----:|:----:|:----:|:----:|:----:
sessionID|string|1491246487334|会话ID|
userID|string|100001|用户ID|
lat|string|39.11111111|纬度|
lng|string|118.11111111|经度|
distance|string|1000|搜索范围|
action|string|nearbyGroup|动作类型|定值

## 响应参数
字段|数据类型|示例值|说明|备注
:----:|:----:|:----:|:----:|:----:
status|int|0|状态码<br>0表成功,-1表失败|
groups|NSArray/List|[{key:value}]|数组内每个元素是一个NSDictionary/Map，客户端可以解析为对象

## group键值对
字段|数据类型|示例值|说明|备注
:----:|:----:|:----:|:----:|:----:
groupName|string|中安盛业大厦|群组名称|
groupID|string|200001|群组ID|
groupImageURL|string|http://www.doudou.com/1.png|群组头像地址
announcement|string|德才兼备，知行合一|群组公告|
groupMemberNumber|int|500|群组成员数|
distance|string|1.62km|群组距离|
groupLocation|string|北苑路与大屯路交界|群组地点|
groupOwnerID|string|100001|群主用户ID|
groupOwnerName|string|豆豆|群主昵称|
ifOfficial|BOOL/bool|YES/true|群组是否是官方群组|和下一条互斥
isMine|BOOL/bool|NO/false|我是否是群主|和上一条互斥
haveJoined|BOOL/bool|NO/false|是否已经加入该群组|理论上附近群组该值全部为false，“我的群组”时全部为true
