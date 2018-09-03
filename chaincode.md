# Infinite Medcial 正反转诊解决方案
## 智能合约
### 初始化

需要参数数量：10个

参数对应：方法名，医院1ID，医院1密码，医院1信息，医院2ID，医院2密码，医院2信息，监管机构ID，监管机构密码，监管机构信息

fabric-cli命令举例：

```
FABRIC_CFG_PATH=./sampleconfig peer chaincode instantiate -v 0 -c '{"Args":["init","a","1","h1","b","2","h2","c","3","admin"]}' -o 127.0.0.1:7050 -C test1 -n mycc

```

---

### invoke
#### signin 患者挂号
需要参数数量：5个

参数对应：方法名，患者ID，医院ID，患者科室，患者密码

返回内容：json

```
{"patientKey":"患者于区块链中的密码"，"info":"备注"}
```

fabric-cli命令举例：

```
FABRIC_CFG_PATH=./sampleconfig peer chaincode invoke -v 0 -c '{"Args":["signin","1","h1","y1","u1","p1"]}' -o 127.0.0.1:7050 -C test1 -n mycc
```

#### transform 患者转院
需要参数数量：4个

参数对应：方法名，患者key，患者密码，患者要转院的医院

返回内容：成功或失败

fabric-cli命令举例：

```
 FABRIC_CFG_PATH=./sampleconfig peer chaincode invoke -v 0 -c '{"Args":["transform","1:h1:y1","key","h2"]}' -o 127.0.0.1:7050 -C test1 -n mycc
```

#### getTransform 被转诊医院获取

需要参数数量：5个

参数对应：方法名，患者key，患者密码，医院2的ID,需要解密的数据

返回内容：data


fabric-cli命令举例：

```
 FABRIC_CFG_PATH=./sampleconfig peer chaincode invoke -v 0 -c '{"Args":["transform","1:h1:y1","key","h2"]}' -o 127.0.0.1:7050 -C test1 -n mycc
```

#### 打包chaincode
```
FABRIC_CFG_PATH=./sampleconfig peer chaincode package -n mycc4 -p github.com/hyperledger/fabric/examples/chaincode/go/madical -v 0 -s -S -i "OR ('secMSP.member')" ccpack.out
```