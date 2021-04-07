<<<<<<< HEAD
# okex-quantization
欧易网格交易脚本
=======
特别鸣谢：https://github.com/hengxuZ/binance-quantization
主体逻辑来自以上项目，将交易所换成了okex

其中只使用到了交易所的3个api接口。
1. 获取某个交易对的当前价格
2. 限价挂买单 （不用市价，防止滑点）
3. 限价挂卖单 

### 优势：🎉
1. 简单易上手
2. 安全(不用将api_secret告诉他人)


### 如何启动

1. 修改app目录下的authorization文件

```
api_key='你的key'
api_secret='你的secret'

dingding_token = '申请钉钉群助手的token'   # 强烈建议您使用 （若不会申请，请加我个人微信）
```

如果你还没有欧易账号：[注册页面](https://www.okex.win/join/4801149)



2. 修改data/data.json配置文件  根据
```
{
    "runBet": {
        "next_buy_price": 350,      <- 下次开仓价   （你下一仓位买入价）
      
        "grid_sell_price": 375      <- 当前止盈价  （你的当前仓位卖出价）
        "step":0                    <- 当前仓位  （0:仓位为空）
    },
    "config": {
        "profit_ratio": 5,         <- 止盈比率      （卖出价调整比率。如：设置为5，当前买入价为100，那么下次卖出价为105）
        "double_throw_ratio": 5,   <- 补仓比率      （买入价调整比率。如：设置为5，当前买入价为100，那么下次买入价为95）
        "cointype": "ETHUSDT",     <- 交易对        （你要进行交易的交易对，请参考币安现货。如：BTC 填入 BTC/USDT）
        "quantity": [1,2,3]        <- 交易数量       (第一手买入1,第二手买入2...超过第三手以后的仓位均按照最后一位数量(3)买入)
        
    }
}

```
3. 安装依赖包
'''
pip install request time json 
'''
4. 运行主文件
```
# python okex-run.py 这是带有钉钉通知的主文件
```


### 注意事项（一定要看）

   
### 钉钉预警

如果您想使用钉钉通知，那么你需要创建一个钉钉群，然后加入自定义机器人。最后将机器人的token粘贴到authorization文件中的dingding_token
关键词输入：报警

#### 钉钉通知交易截图

![钉钉交易信息](https://s3.ax1x.com/2021/02/01/yZSi1x.jpg)


麻烦备注来自github
### 钉钉设置教程
![钉钉设置教程](https://s3.ax1x.com/2021/01/08/suMVIK.png)


### 免责申明
本项目不构成投资建议，投资者应独立决策并自行承担风险
币圈有风险，入圈须谨慎。

> 🚫风险提示：防范以“虚拟货币”“区块链”名义进行非法集资的风险。
>>>>>>> e4107e5... [feat]:网格机器人
