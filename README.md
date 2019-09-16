
# postman 
# linebot 
# richmenu
這個專門是給要寫程式去刻rich menu

事前工作：下載Postman

## step1.
首先利用 Post https://api.line.me/v2/bot/richmenu

### Authorization   
Tyoe : Bearer Token
Token 的部分填自己line bot的Token
### Headers
Content-Type : application/json 
### Body raw

    {
     "size": {
      "width": 2500,
      "height": 1686
      },
    "selected": true,
    "name": "圖文選單 1",
    "chatBarText": "下方有更多功能喔",
    "areas": [
    {
      "bounds": {
        "x": 0,
        "y": 0,
        "width": 833,
        "height": 1686
      },
      "action": {
        "type": "postback",
        "text": "台北",
        "data": "action=getOrders"
      }
    },
    {
      "bounds": {
        "x": 834,
        "y": 0,
        "width": 833,
        "height": 1686
      },
      "action": {
        "type": "postback",
        "text": "影片",
        "data": "action=getMemberInfo"
      }
    },
    {
      "bounds": {
        "x": 1667,
        "y": 0,
        "width": 833,
        "height": 1686
      },
      "action": {
        "type": "postback",
        "text": "天氣",
        "data": "action=getProducts"
      }
    }
    ]
    }

send

之後會給你一組ID

## step2.

Post : https://api.line.me/v2/bot/richmenu/richmenu-83c7d096aefbca57480443468686017c/content

注意！！ richmenu-83c7d096aefbca57480443468686017c要替換成你拿到的那組ID

### Authorization   
Tyoe : Bearer Token
Token 的部分填自己line bot的Token
### Headers
Content-Type : image/jpeg

### Body binary
在這邊上傳你要的照片

注意！！
上傳的照片要按照官方的格式比較安全喔！！
本實例為 2500 X 1686解析度

send 

當你回傳得到{}代表成功

## step3.

Post : https://api.line.me/v2/bot/user/all/richmenu/richmenu-83c7d096aefbca57480443468686017c

注意！！ richmenu-83c7d096aefbca57480443468686017c要替換成你拿到的那組ID

send
