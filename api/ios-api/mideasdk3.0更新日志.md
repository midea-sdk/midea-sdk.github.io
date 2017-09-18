### MideaSDK3.0更新日志



####3.1.49

```objective-c
2017年09月11日-LYQ
1. Update：大屏扫码激活升级
接口变动：
MSmartDeviceManager：
//二维码解密
- (void)decryptSNWithQRCode:(NSString *)qrcode
                completion:(void (^)(NSError *error, NSDictionary *dictionary))completion;

MSmartDeviceManager+Family：
//激活设备 对于大屏设备扫码激活extraDic直接可以传入解析出来的dictionary
- (void)activeDeviceWithDeviceSN:(NSString *)deviceSN
                        familyId:(NSString *)familyId
                        extraDic:(NSDictionary *)extraDic
                      completion:(void (^)(NSError *error))completion;
```



#### 3.1.48

```objective-c
2017年09月01日-MYH
1.修改注释，增加英文注释
2.以下错误码被废弃，详细参见下表：
```

|               SDK错误码                |  枚举值  |         释义         | 云端错误码 |       废弃原因       |
| :---------------------------------: | :---: | :----------------: | :---: | :--------------: |
|    ERROR_ACCESSTOKEN_NOT_EXISTS     | 4003  |   accessToken未知    |       |     SDK中未使用      |
|      ERROR_BIND_PARAMS_INVALID      | 4019  |       绑定参数无效       |       |     SDK中未使用      |
|     ERROR_DEVICE_SN_CHECK_FAULT     | 4043  |       SN校验出错       | 3145  |       云端废弃       |
|   ERROR_DEVICE_SUBTYPE_NOT_EXIST    | 4045  |      设备子类型不存在      | 3160  |       云端废弃       |
|       ERROR_DEVICE_NOT_ONLINE       | 4051  |       设备不在线        |       |     SDK中未使用      |
|         ERROR_FAMILYID_NULL         | 6001  |       家庭ID为空       |       |     SDK中未使用      |
|    ERROR_FAMILY_CANNOT_SET_ROLE     | 6012  |      不能分配此角色       | 3112  |       云端废弃       |
|      MSDevProtocolErrorUartMsg      | 30001 |      Uart包不符       |       |     SDK中未使用      |
|      MSDevProtocolErrorDevice       | 30002 |       设备对象不符       |       |     SDK中未使用      |
|      MSDevProtocolErrorMsgBody      | 30003 |       消息体不符        |       |     SDK中未使用      |
| MSDevProtocolErrorFunctionConflict  | 30004 |        功能冲突        |       |     SDK中未使用      |
|      MSSSKProtocolErrorConfig       | 30005 |        配置错误        |       |     SDK中未使用      |
|   MSSSKProtocolErrorControlFailed   | 30006 |       指令控制失败       |       |     SDK中未使用      |
|    MSSSKProtocolErrorJsonFormat     | 30007 |      Json格式错误      |       |     SDK中未使用      |
|  MSSSKProtocolErrorDeviceIdInvalid  | 30008 | DeviceId无效，列表中无此设备 |       |     SDK中未使用      |
| MSSSKProtocolErrorDeviceTypeInvalid | 30009 |     当前不支持该设备类型     |       |     SDK中未使用      |
| MSDevProtocolErrorParameterInvalid  | 30010 |        参数无效        |       |     SDK中未使用      |
|      MSDevProtocolMsgTypeError      | 30011 |       消息类型不符       |       |     SDK中未使用      |
|        ERROR_LOGIN_REGISTER         | 3009  |        注册失败        |       |     SDK中未使用      |
|       ERROR_EMAIL_SEND_FAILD        | 3018  |       邮件发送失败       | 3125  |       云端废弃       |
|        ERROR_EMAIL_NOT_BIND         | 3019  |       未绑定邮箱        | 3132  |       云端废弃       |
|      ERROR_DEVICE_NOT_REGISTER      | 4021  |     设备没有注册到美居      | 3128  | 现云端3128标识OTA正在升级 |
|     ERROR_LANGUAGE_NOT_SUPPORT      | 1008  |      不支持该区域语言      | 3146  |       云端废弃       |
|         ERROR_APPID_LENGTH          | 2001  |     AppID长度不符      |       |     SDK中未使用      |
|     ERROR_THIRD_SERVER_OVERTIME     | 3025  |      访问第三方云超时      | 3175  |       云端废弃       |

```
2017年09月05日-MYH
1.Update:单用户中修改设备名称bug
```



#### 3.1.47

```objective-c
2017年08月30日-LYQ
1.协商次数改为1次
```

#### 3.1.46 —- (将使用commit前4位)

```objective-c
2017年08月29日-LYQ
1.修改局域网在线判断（新家电在密钥协商成功之后才算局域网在线）
  
2017年08月26日-LYQ
1.局域网sst密钥协商兼容
```

#### 3.1.45

```objective-c
2017年08月21日-LYQ
1.手机号码取消正则
```

#### 3.1.44

```objective-c
2017年08月15日-LYQ
1.Add: 扫码激活需求二维码解密SN
[MSmartDeviceManager decryptSNWithQRCode:completion:]
2.厨电OTA错误码3128处理
  
2017年07月29日—DLB
1.Add:SDK新增获取WiFi模块升级状态、OTA升级功能
MSmartDeviceManager类
//获取WiFi模块升级状态
- (void)queryDeviceOTAState:(NSString *)deviceId
             completion:(void (^)(NSError *error,NSDictionary *deviceInfo))completion;
//OTA升级
- (void)startDeviceOTAState:(NSString *)deviceId
             completion:(void (^)(NSError *error))completion;
```

#### 3.1.43

```objective-c
2017年07月28日—MYH
1.Fix:激活插座成功后获取设备列表时被删除bug
  
2017年07月26日—MYH
1.Fix:添加局域网设备获取子类型有误bug
```

#### 3.1.42

```objective-c
2017年07月12日—MYH
1.Fix:根据sn激活设备返回未知设备bug
2.Add：新增扫码登录相关接口
MSmartUserManager类
（1）根据uuid创建子账号接口
- (void)createSubAccountWithUuid:(NSString *)uuid completion:(void (^)(NSError *error,NSDictionary *dic))completion;
（2）主账号绑定子账号接口
- (void)bindSubAccountWithUuid:(NSString *)uuid subAccout:(NSString *)subAccount completion:(void (^)(NSError *error))completion;
```

#### 3.1.41

```objective-c
2017年07月05日—MYH
1.增加ap隔离在云端通过sn发现设备机制
2.Fix：应用服务器透传失败bug
  
2017年07月04日—MYH
1.增加配网日志上传
  
2017年07月03日—MYH
1.增加登录日志上传
  
2017年06月29日—MYH
1.Fix：修复快连接口（不带回调），一型一码快连接口crash问题
```

#### 3.1.40

```objective-c
2017年06月28日—MYH
1.Update：该接口返回的deviceList以及configDeviceList中每个字典增加 @“ip” 字段
- (void)startScanDeviceInWifi:(void (^)(NSError* error, NSArray* deviceList, NSArray* configDeviceList))completion;
2.Fix：lua脚本下载服务器返回失败本地保存无效文件bug
```

#### 3.1.39

```objective-c
2017年06月26日—MYH
1.Fix：快连配网失败bug

2017年06月23日—MYH
1.废弃接口
- (void)startNewSendMSCWithDeviceType:(NSString *)deviceType
                             homeSSID:(NSString *)homeSSID
                             password:(NSString *)password
                                  tsn:(NSString *)tsn
                                  key:(NSString *)key
                           completion:(void (^)(NSError *err, NSDictionary *dict))completion；
下面接口为该废弃接口的替代
- (void)startNewSendMSCWithDeviceType:(NSString *)deviceType
                             homeSSID:(NSString *)homeSSID
                             password:(NSString *)password
                                  tsn:(NSString *)tsn
                            extension:(NSString *)extension
                                  key:(NSString *)key
                           completion:(void (^)(NSError *err, NSDictionary *dict))completion;
备注：参见MSmartDeviceManager.h
2.修改接口
- (void)requestServerWithoutLogin:(NSString *)api
                       apiVersion:(NSString *)apiVersion
                           params:(NSDictionary *)params
                           isSign:(BOOL)flag
                       completion:(void (^)(NSError *error, NSDictionary *result))completion;
为 - (void)requestMCloudWithoutLoginWithHttpHead:(NSString *)httpHead
                                       domain:(NSString *)domainName
                                         port:(NSString *)domainPort
                                      version:(NSString *)version
                                          api:(NSString *)api
                                      bodyDic:(NSMutableDictionary *)postDic
                                   uploadInfo:(NSDictionary *)uploadInfoDic
                                   completion:(void (^)(NSError *error, NSDictionary *result))completion;
备注：参见MSmartServerManager.h

2017年06月20日—MYH
1.add接口
- (void)requestMCloudWithHttpHead:(NSString *)httpHead
                           domain:(NSString *)domainName
                             port:(NSString *)domainPort
                          version:(NSString *)version
                              api:(NSString *)api
                          bodyDic:(NSMutableDictionary *)postDic
                       uploadInfo:(NSDictionary *)uploadInfoDic
                       completion:(void (^)(NSError *error, NSDictionary *result))completion;
备注：参见MSmartServerManager.h ，该接口用来替代下面的废弃接口
2.废弃接口
- (void)requestForVariableInterfaceWithName:(NSString *)interfaceName
                                     server:(NSString *)server
                                     params:(NSDictionary *)params
                                       post:(BOOL)post
                              versionString:(BOOL)versionString
                                 completion:(void (^)(NSError *error, NSDictionary *result))completion；
备注：参见MSmartServerManager.h

2017年06月19日—MYH
1.update接口
 （1）修改 - (void)activeDeviceWithQRCode:(NSString *)strCode
                    completion:(void (^)(NSError *error))completion；
     为   - (void)activeDeviceWithQRCode:(NSString *)strCode
                      familyId:(NSString *)familyId
                    completion:(void (^)(NSError *error))completion;
     备注：参见 MSmartDeviceManager+Family.h
 （2）修改 - (void)activeDeviceWithDeviceSN:(NSString *)deviceSN
                      completion:(void (^)(NSError *error))completion；
      为  - (void)activeDeviceWithDeviceSN:(NSString *)deviceSN
                        familyId:(NSString *)familyId
                      completion:(void (^)(NSError *error))completion;
     备注：参见 MSmartDeviceManager+Family.h
 （3）修改 - (void)add2GDeviceByQrCode:(NSString *)strCode
                 completion:(void (^)(NSError *error,NSDictionary *deviceInfo))completion;
      为 - (void)add2GDeviceByQrCode:(NSString *)strCode
                   familyId:(NSString *)familyId
                 completion:(void (^)(NSError *error,NSDictionary *deviceInfo))completion;
     备注：参见 MSmartDeviceManager+Family.h
```

#### 3.1.38

```objective-c
2017年06月12日—MYH
1. Add:增加接口 
  （1）MSmartUserManager.h类
- (void) registerWithEmail:(NSString *)email
                  password:(NSString *)password
                  nickName:(NSString *)nickName
                  extraDic:(NSDictionary *)extraDic
                completion:(void (^)(NSError *error))completion;
备注：详情请参见文档
2. 以下接口废弃
- (void) registerWithEmail:(NSString *)email
                  password:(NSString *)password
                  nickName:(NSString *)nickName
                completion:(void (^)(NSError *error))completion；
备注：该废弃接口用新增接口替代
3.Update：海外服务器邮箱重置密码，邮箱注册接口增加多语言功能
```

#### 3.1.37

```objective-c
2017年05月26日—LYQ
Add: 
1. 推送添加RemotePushType_Device_Fault
Fix:
1. https网络请求策略defaultPolicy（当前安全策略）

2017年05月26日——MYH
1、ADD：增加接口
  MSmartUserManager类：
- (void) loginWithAccount:(NSString *)account
                 password:(NSString *)password
                 extraDic:(NSDictionary *)extraDic
               completion:(void (^)(NSError *error, NSDictionary *dict, NSArray *familysOrUsers, NSArray *devices))completion;

2、以下接口废弃：
（1）- (void) loginWithPhoneNum:(NSString*)phoneNum
                  password:(NSString*)password
                completion:(void (^)(NSError* error))completion；
（2）- (void) loginWithEmail:(NSString *)email
               password:(NSString *)password
             completion:(void (^)(NSError *error))completion；
（3）- (void)loginWithAccount:(NSString *)account
            hashPassword:(NSString *)hashPassword
               pushToken:(NSString *)pushToken
              completion:(void (^)(NSError *error))completion；
（4）- (void)loginWithAccount:(NSString *)account
      SHA256HashPassword:(NSString *)SHA256HashPassword
         MD5HashPassword:(NSString *)MD5HashPassword
               pushToken:(NSString *)pushToken
              appInfoDic:(NSDictionary *)appInfoDic
              completion:(void (^)(NSError *error,NSDictionary *userInfo))completion；
（5）- (void)loginWithAccount:(NSString *)account
      SHA256HashPassword:(NSString *)SHA256HashPassword
         MD5HashPassword:(NSString *)MD5HashPassword
               pushToken:(NSString *)pushToken
              appInfoDic:(NSDictionary *)appInfoDic
      completionWithInfo:(void (^)(NSError *error, NSDictionary *dict, NSArray *familysOrUsers, NSArray *devices))completion；
（6）- (void)loginWithAccount:(NSString *)account
            hashPassword:(NSString *)hashPassword
               pushToken:(NSString *)pushToken
              appInfoDic:(NSDictionary *)appInfoDic
              completion:(void (^)(NSError *error,NSDictionary *userInfo))completion；

3、Update：lua脚本增加检测最新版本机制
```

#### 3.1.36

```objective-c
2017年05月08日——MYH
Update：（1）海外测试服域名
```

#### 3.1.35

```objective-c
2017年04月28日——MYH
Fix：(1)配网时闪退问题
```

#### 3.1.34

```objective-c
2017年04月26日——MYH
ADD：(1)增加接口 
   MSmartServerManager类：
   - (void)requestServerWithoutLogin:(NSString *)api
                       apiVersion:(NSString *)apiVersion
                           params:(NSDictionary *)params
                           isSign:(BOOL)flag
                       completion:(void (^)(NSError *error))completion;
```

#### 3.1.33

```objective-c
2017年04月24日——MYH
ADD：(1)增加日志，确定当前局域网扫描设备所在局域网名称
```

#### 3.1.32

```objective-c
2017年04月20日——MYH
Fix：
(1)配网获取周围wifi列表为空
(2)未登录情况下获取loginId为@“0”
```
#### 3.1.31

```objective-c
2017年04月18日——MYH
Update：HTTPS保留本地验证机制，并验证域名
```

#### 3.1.30

```objective-c
2017年04月13日——MYH
FIX：HTTPS取消本地验证机制
```

#### 3.1.29

```objective-c
2017年04月13日——MYH
FIX：净饮机设备类型查询不支持问题
```

#### 3.1.28

```objective-c
2017年04月07日——LYQ
MTK快连扩展
MSRandomNUMObject.h public
```

#### 3.1.27

```objective-c
2017年03月30日——MYH
Fix:DDLog私有化遗漏问题
```

#### 3.1.26

```objective-c
2017年03月22日——LYQ
UPDATE: 通用接口 美居背景图片上传兼容
ADD：新增选择lua脚本是否为密文接口
MSmartSystemManager：
- (void)isLuaScriptCryptograph:(BOOL)flag ;
```

#### 3.1.25

```objective-c
2017年03月22日——LYQ
FIX: MideaMTKConnect extension字符串拼接
FIX：MideaNetLog block判断
```

#### 3.1.23

```objective-c
2017年03月21日——MYH
UPDATE:lua脚本加载明文
UPDATE:查询设备绑定或激活信息接口，返回字典deviceSn使用明文
```

