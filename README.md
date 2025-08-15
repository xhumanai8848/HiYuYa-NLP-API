# 宇芽免费NLP交互API / Yuya Free NLP Interactive API

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License">
  <img src="https://img.shields.io/badge/version-1.0.0-green.svg" alt="Version">
  <a href="http://www.hiyuya.com"><img src="https://img.shields.io/badge/website-hiyuya.com-orange.svg" alt="Website"></a>
</p>

[English](README_EN.md) | 中文

## 项目简介

**宇芽免费NLP交互API** 是一个开源项目，为开发者提供免费的自然语言处理(NLP)服务。本项目专注于提供高质量的意图识别和实体提取功能，帮助开发者快速构建智能对话系统。

API接口地址: [https://nlp.hiyuya.com](https://nlp.hiyuya.com)

### 支持的行业领域

- 🏠 **家用智能音箱** - 为家庭场景提供语音交互支持
- 🏨 **酒店智能音箱** - 针对酒店服务场景优化的语音交互
- 📚 **教育智能设备** - 支持教育场景下的语音识别和理解
- 📱 **学习机智能平板** - 为学习机应用提供NLP能力支持

## 功能特性

- ✨ **意图识别** - 精准识别用户输入的意图，支持多场景复杂意图分析
- 🔍 **实体提取** - 从自然语言中提取关键信息实体，如时间、地点、人物等
- 🌐 **多语言支持** - 目前支持中文，未来将扩展到更多语言
- ⚡ **高性能** - 低延迟响应，支持高并发访问
- 🛠️ **易于集成** - 简单的API接口，支持多种编程语言调用

## 快速开始

### 安装

```bash
pip install yuya-nlp-api
```

### 基本使用

```python
from yuya_nlp import YuyaNLP

# 初始化客户端
client = YuyaNLP(industry="home_smart_speaker")

# 调用意图识别
result = client.recognize_intent("帮我把客厅的灯打开")
print(result)
# 输出: {'intent': 'turn_on_light', 'confidence': 0.95, 'entities': {'location': '客厅', 'device': '灯'}}
```

### API示例

#### 意图识别

```python
import requests

url = "https://nlp.hiyuya.com/intent"
data = {
    "text": "明天早上8点提醒我吃药",
    "industry": "home_smart_speaker"
}

response = requests.post(url, json=data)
print(response.json())
```

响应:

```json
{
    "intent": "set_reminder",
    "confidence": 0.92,
    "entities": {
        "time": "明天早上8点",
        "action": "吃药"
    }
}
```

#### 实体提取

```python
import requests

url = "https://nlp.hiyuya.com/entity"
data = {
    "text": "我想查询从北京到上海的机票",
    "industry": "hotel_smart_speaker"
}

response = requests.post(url, json=data)
print(response.json())
```

响应:

```json
{
    "entities": {
        "departure": "北京",
        "destination": "上海",
        "service_type": "机票"
    }
}
```

## 行业适配

宇芽NLP API针对不同行业场景进行了优化，使用时只需指定相应的行业参数:

- `home_smart_speaker`: 家用智能音箱
- `hotel_smart_speaker`: 酒店智能音箱
- `edu_smart_device`: 教育智能设备
- `learning_tablet`: 学习机智能平板

## 本地部署

如需本地部署，请参考以下步骤:

```bash
# 克隆仓库
git clone https://github.com/yuya-nlp/free-nlp-api.git
cd free-nlp-api

# 安装依赖
pip install -r requirements.txt

# 启动服务
python server.py
```

服务将在 `http://localhost:8000` 启动。

## 贡献指南

我们欢迎所有形式的贡献，无论是新功能、文档改进还是bug修复。请查看[贡献指南](CONTRIBUTING.md)了解更多信息。

## 路线图

- [ ] 支持更多行业场景
- [ ] 添加情感分析功能
- [ ] 增加多语言支持
- [ ] 提供更多预训练模型

## 许可证

本项目采用 [MIT 许可证](LICENSE)。

## 联系我们

- 🌐 官网: [www.hiyuya.com](http://www.hiyuya.com)
- 📧 Email: support@hiyuya.com
- 🐞 Issues: [GitHub Issues](https://github.com/yuya-nlp/free-nlp-api/issues)
- 💬 讨论: [GitHub Discussions](https://github.com/yuya-nlp/free-nlp-api/discussions)

---

<p align="center">由宇芽团队 ❤️ 用爱发电</p>
