# 获取用户资料

获取个人资料或他人资料均可
当传入的userID和searchID相同时，是获取个人资料；不同时，是获取他人资料。

## 请求参数
字段|数据类型|示例值|说明|备注
:----:|:----:|:----:|:----:|:----:
sessionID|string|1491246487334|会话ID|
userID|string|100001|用户ID|
searchID|string|100001|要搜索的用户ID|
action|string|search|动作类型|定值

## 响应参数
字段|数据类型|示例值|说明|备注
:----:|:----:|:----:|:----:|:----:
status|int|0|状态码<br>0表成功,-1表失败|
user|NSDictionary/Map|{key:value}|客户端解析为对象

## user键值对
字段|数据类型|示例值|说明|备注
:----:|:----:|:----:|:----:|:----:
userName|string|小明|用户昵称|
userID|string|100001|用户ID|
imageURL|string|http://www.doudou.com/1.png|用户头像地址
sign|string|德才兼备，知行合一|用户签名|
stars|int|5|用户星级|
wechatBind|BOOL/bool|YES/true|是否绑定微信|
phoneBind|BOOL/bool|YES/true|是否绑定手机|
relation|int|1|关系（详见下方枚举）|
babyName|string|豆豆|宝贝昵称|
babyGender|int|1|宝贝性别（详见下方枚举）|
babyBirthday|string|2015-08-13|宝贝出生年月日|
babyConstellation|int|8|宝贝星座（详见下方枚举）|

当请求自己个人资料时，还应含有以下字段：

字段|数据类型|示例值|说明|备注
:----:|:----:|:----:|:----:|:----:
phoneNumber|string|138****1111|用户手机号，中段加密|
groupCount|int|4|已加入的群组数|服务器可以考虑在登录时直接下发所有群组详情代替群组数
friendCount|int|23|好友数（相互关注）|同上
followedCount|int|53|关注数|同上
fansCount|int|101|粉丝数|同上

## 接口枚举值
### 用户关系枚举

enum RelationType {<br>
    RelationTypeStranger       = 0,  //default，陌生人<br>
    RelationTypeFans           = 1,  //粉丝（她是我的粉丝）<br>
    RelationTypeFollowed       = 2,  //关注（我关注了她）<br>
    RelationTypeFriends        = 3,  //好友（两人互相关注，包含上面两种关系）<br>
    RelationTypeBlackList      = 4,  //黑名单（她在我的黑名单里）<br>
    RelationTypeSelf           = 100,//自己（预留）<br>
};

### 宝贝性别枚举

enum GenderType {<br>
    GenderTypeUnknown          = 0,  //default，未填写，理论请求成功时不会出现<br>
    GenderTypeFemale           = 1,  //女<br>
    GenderTypeMale             = 2,  //男<br>
}

### 宝贝星座枚举

enum ConstellationType {<br>
    ConstellationTypeUnknow      = 0, //未知，理论请求成功时不会出现<br>
    ConstellationTypeAries       = 1, //白羊座<br>
    ConstellationTypeTaurus      = 2, //金牛座<br>
    ConstellationTypeGemini      = 3, //双子座<br>
    ConstellationTypeCancer      = 4, //巨蟹座<br>
    ConstellationTypeLeo         = 5, //狮子座<br>
    ConstellationTypeVirgo       = 6, //处女座<br>
    ConstellationTypeLibra       = 7, //天秤座<br>
    ConstellationTypeScorpio     = 8, //天蝎座<br>
    ConstellationTypeSagittarius = 9, //射手座<br>
    ConstellationTypeCapricorn   = 10,//山羊座<br>
    ConstellationTypeAquarius    = 11,//水瓶座<br>
    ConstellationTypePisces      = 12,//双鱼座<br>
}
