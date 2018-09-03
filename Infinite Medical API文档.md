# 患者挂号

### 请求参数
|名称 |类型|示例|是否必填|
|:---| ----|:----:|:-----:|
|患者ID|String|0c7de048813d45a68d11877e00b40a59|是|
|医院ID|String|hospitalXieHe|是|
|患者科室|String|ophthalmology|是|
|患者密码|String|123456|是|

### 返回参数
json
```
{"patientKey":"患者本次就诊于区块链中的唯一key"，"info":"备注"}
```


# 患者转院
### 请求参数

|名称 |类型|示例|是否必填|
|:---| ----|:----:|:-----:|
|患者key|String|371****:hospitalxiehe:20180903|是|
|患者密码|String|123456|是|
|即将转诊医院|String|hospitalputian|是|


### 返回数据
```
success
```

# 获取转诊
### 请求参数
|名称 |类型|示例|是否必填|
|:---| ----|:----:|:-----:|
|患者key|String|371****:hospitalxiehe:20180903|是|
|患者密码|String|123456|是| 
|即将转诊医院|String|hospitalputian|是|
|待解密数据|String|https://oss.aliyun.com|是|

### 成功后返回数据
```
{dercData:""｝
```