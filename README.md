![ChatterBot: Machine learning in Python](https://i.imgur.com/b3SCmGT.png)

# 채터봇(ChatterBot)

채터봇은 머신러닝 기반 파이썬 의사소통 엔진으로, 학습된 대화를 기반으로 답변을 생성할 
수 있습니다. 채터봇은 언어 독립적으로 디자인 되었기 때문에 어떤 언어를 사용하더라고 
채팅 서비스를 이용할 수 있습니다.

[![Package Version](https://img.shields.io/pypi/v/chatterbot.svg)](https://pypi.python.org/pypi/chatterbot/)
[![Python 3.6](https://img.shields.io/badge/python-3.6-blue.svg)](https://www.python.org/downloads/release/python-360/)
[![Django 2.0](https://img.shields.io/badge/Django-2.0-blue.svg)](https://docs.djangoproject.com/en/2.1/releases/2.0/)
[![Requirements Status](https://requires.io/github/gunthercox/ChatterBot/requirements.svg?branch=master)](https://requires.io/github/gunthercox/ChatterBot/requirements/?branch=master)
[![Build Status](https://travis-ci.org/gunthercox/ChatterBot.svg?branch=master)](https://travis-ci.org/gunthercox/ChatterBot)
[![Documentation Status](https://readthedocs.org/projects/chatterbot/badge/?version=stable)](http://chatterbot.readthedocs.io/en/stable/?badge=stable)
[![Coverage Status](https://img.shields.io/coveralls/gunthercox/ChatterBot.svg)](https://coveralls.io/r/gunthercox/ChatterBot)
[![Code Climate](https://codeclimate.com/github/gunthercox/ChatterBot/badges/gpa.svg)](https://codeclimate.com/github/gunthercox/ChatterBot)
[![Join the chat at https://gitter.im/chatterbot/Lobby](https://badges.gitter.im/chatterbot/Lobby.svg)](https://gitter.im/chatterbot/Lobby?utm_source=badge&utm_medium=badge&utm_content=badge)

채팅을 입력하는 과정은 다음과 같습니다:

> **user:** Good morning! How are you doing?  
> **bot:**  I am doing very well, thank you for asking.  
> **user:** You're welcome.  
> **bot:** Do you like hats?  

## 작동 원리

학습되지 않은 채터봇은 학습 지식이 없으므로 의사소통을 할 수 없습니다. 매번 사용자가 문장을 입력할 때마다, 라이브러리는 해당 문장과 답변으로 도출된 문장을 동시에 저장합니다.
채터봇이 더 많은 대화를 저장할 때마다 답변할 수 있는 문장의 수와 정확도는 올라가게 됩니다. 채터봇은 답변을 선택할 때 가능성 있는 문장 중 가장 가장 정확도가 높은 문장을 검색해 선택합니다. 또한 유저에게서 답변이 돌아오는 빈도를 바탕으로 가장 높은 답변을 판단합니다.

## 설치 방법

[PyPi](https://pypi.python.org/pypi/ChatterBot) 채터봇 패키지는 아래의 코드를 실행시켜 다운로드 가능합니다:

```
pip install chatterbot
```

## 기본 사용법

```
from chatterbot import ChatBot
from chatterbot.trainers import ChatterBotCorpusTrainer

chatbot = ChatBot('Ron Obvious')

# 챗봇 학습모델 생성
trainer = ChatterBotCorpusTrainer(chatbot)

# 내장된 영어 말뭉치를 사용해 챗봇 학습
trainer.train("chatterbot.corpus.english")

# 문장을 입력해 답변 출력하기
chatbot.get_response("Hello, how are you today?")
```

# 학습 데이터

채터봇은 학습에 필요한 데이터 유틸리티 모듈이 내장되어 있습니다. 현재는 총 22개의 언어가
학습 데이터에 내장되어 있습니다. 이를 제외한 언어 데이터 추가 혹은 학습 데이터 개선활동은
크게 장려됩니다. 다음 주소에서 학습 데이터의 상세한 정보를 확인 할 수 있습니다.
[chatterbot-corpus](https://github.com/gunthercox/chatterbot-corpus)

```
from chatterbot.trainers import ChatterBotCorpusTrainer

# 챗봇 학습모델 생성
trainer = ChatterBotCorpusTrainer(chatbot)

# 내장된 영어 말뭉치를 사용해 챗봇 학습
trainer.train("chatterbot.corpus.english")

# 내장된 영어 인삿말 학습
trainer.train("chatterbot.corpus.english.greetings")

# 내장된 영어 의사소통 학습
trainer.train("chatterbot.corpus.english.conversations")
```

**학습 데이터 기여할동은 크게 장려됩니다! Pull request부탁합니다.**

# [Documentation](https://chatterbot.readthedocs.io/)

원본 문서 [documentation](https://chatterbot.readthedocs.io/)
혹은 [한글문서](https://simplistic-aphid-cce.notion.site/ChatterBot-7b8719bd0a1f449eab45556248c6ebd6)
를 참고해주세요.

직접 문서를 작성하고 싶다면 [Sphinx](http://www.sphinx-doc.org/), 다음의 코드를 실행하세요:

```
sphinx-build -b html docs/ build/
```

# 예제

예제를 보기 위해서는 [examples](https://github.com/gunthercox/ChatterBot/tree/master/examples)
해당 깃 링크를 클릭하세요.

위의 예시뿐만 아니라 [Django project using ChatterBot](https://github.com/gunthercox/ChatterBot/tree/master/examples), [Flask project using ChatterBot](https://github.com/chamkank/flask-chatterbot) 2개의 다른 예제또한 존재합니다.

# 업데이트 기록

패키지 릴리즈 문서를 보기 위해서 다음 링크를 클릭하세요. https://github.com/gunthercox/ChatterBot/releases

# 오픈소스 기여 패턴

1. [메인 repository](https://github.com/gunthercox/ChatterBot)를 [fork하기](https://help.github.com/articles/fork-a-repo/)
2. `master`를 제외한 다른 branch name으로 branch를 생성하세요, 예시)`my-pull-request`.
3. [Pull request하기](https://help.github.com/articles/creating-a-pull-request/).
4. 다음 링크의 방식을 따라야 합니다 [Python style guide for PEP-8](https://www.python.org/dev/peps/pep-0008/).
5. 작성한 코드의 에러여부는 [built-in automated testing](https://chatterbot.readthedocs.io/en/latest/testing.html) 이 주소를 사용해 확인해주세요.
  

# 라이센스

채터봇의 라이센스는 다음과 같습니다. [BSD 3-clause license](https://opensource.org/licenses/BSD-3-Clause).
