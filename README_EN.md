# Yuya Free NLP Interactive API

<p align="center">
  <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License">
  <img src="https://img.shields.io/badge/version-1.0.0-green.svg" alt="Version">
  <a href="http://www.hiyuya.com"><img src="https://img.shields.io/badge/website-hiyuya.com-orange.svg" alt="Website"></a>
</p>

[中文](README.md) | English

## Project Introduction

**Yuya Free NLP Interactive API** is an open-source project providing free Natural Language Processing (NLP) services to developers. This project focuses on delivering high-quality intent recognition and entity extraction capabilities to help developers quickly build intelligent dialogue systems.

API Endpoint: [https://nlp.hiyuya.com](https://nlp.hiyuya.com)

### Supported Industries

- 🏠 **Home Smart Speakers** - Voice interaction support for home scenarios
- 🏨 **Hotel Smart Speakers** - Voice interaction optimized for hotel service scenarios
- 📚 **Educational Smart Devices** - Support for speech recognition and understanding in educational settings
- 📱 **Learning Tablets** - NLP capabilities for learning tablet applications

## Features

- ✨ **Intent Recognition** - Accurately identify user intentions with support for complex intent analysis across multiple scenarios
- 🔍 **Entity Extraction** - Extract key information entities from natural language, such as time, location, people, etc.
- 🌐 **Multilingual Support** - Currently supports Chinese, with plans to expand to more languages
- ⚡ **High Performance** - Low-latency responses, supporting high-concurrency access
- 🛠️ **Easy Integration** - Simple API interface, supporting calls from multiple programming languages

## Quick Start

### Installation

```bash
pip install yuya-nlp-api
```

### Basic Usage

```python
from yuya_nlp import YuyaNLP

# Initialize client
client = YuyaNLP(industry="home_smart_speaker")

# Call intent recognition
result = client.recognize_intent("Turn on the living room light")
print(result)
# Output: {'intent': 'turn_on_light', 'confidence': 0.95, 'entities': {'location': 'living room', 'device': 'light'}}
```

### API Examples

#### Intent Recognition

```python
import requests

url = "https://nlp.hiyuya.com/intent"
data = {
    "text": "Remind me to take medicine tomorrow at 8 AM",
    "industry": "home_smart_speaker"
}

response = requests.post(url, json=data)
print(response.json())
```

Response:

```json
{
    "intent": "set_reminder",
    "confidence": 0.92,
    "entities": {
        "time": "tomorrow at 8 AM",
        "action": "take medicine"
    }
}
```

#### Entity Extraction

```python
import requests

url = "https://nlp.hiyuya.com/entity"
data = {
    "text": "I want to check flights from Beijing to Shanghai",
    "industry": "hotel_smart_speaker"
}

response = requests.post(url, json=data)
print(response.json())
```

Response:

```json
{
    "entities": {
        "departure": "Beijing",
        "destination": "Shanghai",
        "service_type": "flights"
    }
}
```

## Industry Adaptation

Yuya NLP API has been optimized for different industry scenarios. Simply specify the appropriate industry parameter when using:

- `home_smart_speaker`: Home Smart Speakers
- `hotel_smart_speaker`: Hotel Smart Speakers
- `edu_smart_device`: Educational Smart Devices
- `learning_tablet`: Learning Tablets

## Local Deployment

For local deployment, please follow these steps:

```bash
# Clone repository
git clone https://github.com/yuya-nlp/free-nlp-api.git
cd free-nlp-api

# Install dependencies
pip install -r requirements.txt

# Start service
python server.py
```

The service will start at `http://localhost:8000`.

## Contribution Guidelines

We welcome all forms of contribution, whether it's new features, documentation improvements, or bug fixes. Please check the [Contribution Guidelines](CONTRIBUTING.md) for more information.

## Roadmap

- [ ] Support for more industry scenarios
- [ ] Add sentiment analysis functionality
- [ ] Increase multilingual support
- [ ] Provide more pre-trained models

## License

This project is licensed under the [MIT License](LICENSE).

## Contact Us

- 🌐 Website: [www.hiyuya.com](http://www.hiyuya.com)
- 📧 Email: support@hiyuya.com
- 🐞 Issues: [GitHub Issues](https://github.com/yuya-nlp/free-nlp-api/issues)
- 💬 Discussions: [GitHub Discussions](https://github.com/yuya-nlp/free-nlp-api/discussions)

---

<p align="center">Made with ❤️ by the Yuya Team</p>
