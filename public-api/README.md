# 快速开始

---

## 接口请求域名

https://pubapis.lan2wan.top

## 接入流程

### 获取密钥

1. 扫码打开小程序

   ![小程序码](./img/mini_program_code.png)

2. 点击底部菜单 密钥 生成或获取密钥

   <img src="./img/secret.png" alt="生成或获取密钥" style="zoom:75%;" />



### 请求接口时在Header中加入密钥参数

| 参数名       | 说明                                                        |
| ------------ | ----------------------------------------------------------- |
| C-SECRET-KEY | 密钥，是一个UUID 类似：3d8f4b99-e850-461a-a8ad-f01546bef9e8 |

---

# 图片处理

---

## OCR-基础验证码图片识别


### 接口地址

**POST** https://[域名](#接口请求域名)/img/ocr/vercode

### 请求参数(Body-json)

| 参数名 | 说明                   |
| ------ | ---------------------- |
| img    | 验证码图片的Base64编码 |

```json
{
    "img": "iVBORw0KGgoAAAANSUhEUgAAAIAAAAAoBAMAAADEX+97AAAAG1BMVEXz+/6NjX+ztq6mqJ7M0c7m7e6Zmo7Z397AxL6uJst4AAAACXBIWXMAAA7EAAAOxAGVKw4bAAABb0lEQVRIie1UPU/DMBS00nx0zKVgGInoD6gRIMZGorAGpDaMGKnqmkogMaaI8rux81xDi0gMSEy5Jc6T3/nu/BLGOvwr7s6rn2zPdws+MHBv9wXOdkorAGPX/kACfPNSlEYAcORKMNO7S1r3MNKPUJdGrgRC765ondG5SyxCJwXeyZBFwKs0hn0jfIVx3yUD5T5hHvZUQ30Pt9ISlB5vbCUsgQNlO2ZpYgwYLxmq8JBdtvX31f5YBRZHmG8TLFFlcbsGAakU9x7KGc8twVgvwgUTa7lJ9jvMsNDhBYppzgpdeb42BFEecTVL9439PpICdXg9Pn2jEJgdCE+JGXyZ8C1k+qrqgU8TsZl8S3DTPopSzw9fm7mlwAKSVNOr221EgBr7dJhREFmCFLzZAJ1b56S/vNN8h0C0TnLw+HJMPiUGkw9WsxItBggSQ5UZLqxY3/5GrloMkAgSPPlUeXI518KXLh9MI6Z/JejQocOv8A6qbDTicu0kOgAAAABJRU5ErkJggg=="
}
```

### 响应数据(json)

| 参数名 | 说明                   |
| ------ | ---------------------- |
| code   | 识别成功后返回的验证码 |

```json
{
    "success": true,
    "code": 0,
    "msg": "",
    "data": {
        "code": "4212"
    }
}
```

---

# 日历相关

---

## 阳历农历互转

### 接口地址

**POST** https://[域名](#接口请求域名)/calendar/lunar

### 请求参数(Body-json)

| 参数名 | 说明                      |
| ------ | ------------------------- |
| type   | 1:阳历转农历 2:农历转阳历 |
| date   | 阳历或农历日期 yyyy-mm-dd |

```json
{
    "type": 1,
    "date": "2024-03-29"
}
```

### 响应数据(json)

| 参数名   | 说明                         |
| -------- | ---------------------------- |
| date     | 阳历日期 yyyy-mm-dd          |
| lunar    | 农历日期 yyyy-mm-dd          |
| lunarcn  | 农历日期 yyyy年mm月dd        |
| lunarcn1 | 农历日期 中文格式 含生肖     |
| lunarcn2 | 农历日期 中文格式拆分 含生肖 |

```json
{
    "success": true,
    "code": 0,
    "msg": "",
    "data": {
        "date": "2024-03-29",
        "lunar": "2024-02-20",
        "lunarcn": "2024年2月20日",
        "lunarcn1": "二零二四年二月二十 甲辰年 (龙年)",
        "lunarcn2": [
            "二零二四年二月二十",
            "甲辰年",
            "龙年"
        ]
    }
}
```

---

