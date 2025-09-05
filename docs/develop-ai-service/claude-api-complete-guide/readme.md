🏠 > [AI 서비스 개발](../) > `클로드 3 (Claude 3) API 완벽 가이드 - 고성능 AI 모델로 나만의 AI 챗봇 개발하기 (Streamlit, Python 활용)`

### INDEX

- [Claude API 사전 준비 사항](#claude-api-사전-준비-사항)
  - [Claude API 키 발급 받기](#claude-api-키-발급-받기)
  - [Python 개발 환경 설정하기](#python-개발-환경-설정하기)
- [Claude API에 첫 요청 보내기](#claude-api에-첫-요청-보내기)
- [프롬프트를 작성하기 좋은 콘솔 Workbench 활용하기](#프롬프트를-작성하기-좋은-콘솔-workbench-활용하기)
- [Claude 모델 비교하기](#claude-모델-비교하기)
- [프롬프트 엔지니어링 팁](#프롬프트-엔지니어링-팁)
- [Streamlit으로 클로드 챗봇 만들기](#streamlit으로-클로드-챗봇-만들기)
- [클로드 API 활용, 어떠셨나요?](#클로드-api-활용-어떠셨나요)

---
# 클로드 3 (Claude 3) API 완벽 가이드 
> 고성능 AI 모델로 나만의 AI 챗봇 개발하기 (Streamlit, Python 활용)

클로드(Claude)는 Anthropic에서 개발한 강력한 대화형 AI 모델로, 다양한 태스크에 활용할 수 있습니다. 특히 클로드 API를 통해 개발자는 자신만의 AI 애플리케이션을 쉽게 구축할 수 있습니다. 클로드(Claude)에 대해 궁금하다면 클로드(Claude) 란? 클로드 사용법 완벽 가이드를 통해 자세한 내용을 알 수 있습니다.

이 글에서는 클로드 API 사용법을 처음부터 끝까지 자세히 알려드리겠습니다. API 키 발급받는 방법부터 Python SDK 설치, API 요청 보내기까지 차근차근 살펴볼 거예요. 나아가 클로드 3 모델의 특징과 가격, 프롬프트 엔지니어링 팁, 그리고 Streamlit을 활용한 챗봇 개발 사례까지 풍성한 내용을 담았습니다.

초보자도 어렵지 않게 클로드의 강력한 기능을 체험하고, 나만의 AI 프로젝트를 실현할 수 있도록 이 가이드가 도움이 되길 바랍니다. 그럼 시작해볼까요?

<br/>

[[TOP]](#index)

---
## Claude API 사전 준비 사항
본격적으로 클로드 API 사용법을 알아보기 전에 몇 가지 준비가 필요합니다.

- Claude API API 키 발급 받기 (대시보드에서 발급 가능)
- Python 3.7.1 이상 버전 설치 (파이썬 공식 사이트에서 다운로드)

### Claude API 키 발급 받기
우선 클로드 API를 사용하려면 Anthropic으로부터 API 키를 발급 받아야 합니다.

API 요청을 위해서는 대시보드에서 API 키를 발급받아야 합니다. 아래와 같이 진행하세요.

1. Anthropic API 페이지 접속
클로드 API 메인 페이지

'Get started now' 버튼을 클릭 하여 Claude 콘솔 대시보드 페이지로 이동 합니다. https://console.anthropic.com/ 링크를 통해 직접 접속할 수도 있습니다.

2. Claude API 대시보드 접속
대시보드에 접속 하면 아래와 같은 화면을 볼 수 있습니다. Claude API 대시보드 화면

프롬프트 작업을 할 수 있는 Workbench 부터, 프롬프트 생성기, 프롬프트를 모아둔 프롬프트 라이브러리 등 다양한 기능을 제공합니다. 다양한 기능이 있지만 이번에는 API 키를 발급 받는 방법에 대해 알아보겠습니다.

3. API 키 발급 받기
위 화면에서 "Get API Keys" 버튼 클릭하면 API 키를 발급 받을 수 있는 페이지로 이동합니다.

Claude API 키 받기

"Create key" 버튼 클릭하고 새 API 키 이름 입력 후 "Create" 클릭하면 새로운 API 키가 생성됩니다.

Claude API 키 생성

4. 생성된 API 키 확인 (보안을 위해 잘 보관할 것)
키가 생성되면 아래와 같이 API 키가 생성된 것을 확인할 수 있습니다. API 키는 보안을 위해 잘 보관해야 하며, 노출되지 않도록 주의해야 합니다. Claude API 키 발급 예시

이제 API 키를 사용해 Claude API에 요청을 보낼 준비가 되었습니다.

### Python 개발 환경 설정하기
Python 버전 확인
먼저 컴퓨터에 Python이 설치되어 있는지, 그리고 버전이 맞는지 확인합니다. 터미널이나 명령 프롬프트에서 다음 명령어를 입력해보세요.

python --version

만약 Python 3.7.1 이상 버전이 표시되지 않는다면 Python 공식 웹사이트에서 최신 버전을 다운로드 받으세요.

가상환경 생성 (선택사항)
가상환경을 사용하면 프로젝트별로 독립된 Python 환경을 구성할 수 있어 패키지 충돌을 방지할 수 있습니다. 아래 명령어로 가상환경을 만들어봅시다.

python -m venv claudeenv


그리고 생성한 가상환경을 활성화합니다.

macOS / Linux: source claudeenv/bin/activate
Windows: claudeenv\Scripts\activate
Anthropic Python SDK 설치하기
Python 환경 설정을 마쳤다면 이제 클로드 API와 연동할 수 있는 Anthropic Python SDK를 설치할 차례입니다.

pip install anthropic


위 명령어를 실행하면 클로드 API 사용에 필요한 라이브러리와 종속성 패키지가 한 번에 설치됩니다.

API 키 설정하기 (선택사항)
매번 API 키를 입력하는 번거로움을 피하고 싶다면, 환경변수로 저장해두는 것이 좋습니다. 아래 단계를 따라 진행해보세요.

macOS / Linux
터미널에서 nano ~/.zshrc (또는 nano ~/.bash_profile) 입력
에디터에 export ANTHROPIC_API_KEY=your_api_key 한 줄 추가
변경사항 저장 후 에디터 종료
source ~/.zshrc (또는 source ~/.bash_profile) 실행해 적용
Windows
시작 메뉴에서 "환경 변수 편집" 검색 후 선택
"환경 변수" 버튼 클릭
"시스템 변수" 항목의 "새로 만들기" 버튼 클릭
변수 이름에 ANTHROPIC_API_KEY, 값에 발급받은 API 키 입력

<br/>

[[TOP]](#index)

---
## Claude API에 첫 요청 보내기
자, 이제 클로드에게 첫 번째 API 요청을 보낼 준비가 되었습니다. claude_test.py 같은 파이썬 파일을 새로 만들고 아래 코드를 작성해보세요.

import os
import anthropic

client = anthropic.Client(api_key="YOUR_API_KEY")

response = client.messages.create(
    model="claude-3-sonnet-20240229",
    max_tokens=1000,
    temperature=0.0,
    system="당신은 Tesla 창업가 엘론 머스크 입니다. 엘론 머스크와 같이 답변해주세요\nRespond only in Korean.", # <-- system prompt
    messages=[
        {"role": "user", "content": "Hello, 엘론 머스크!"} # <-- user prompt
    ]
)

print(response.content[0].text.strip())




코드를 실행하려면 터미널에서 해당 파일이 있는 디렉토리로 이동한 뒤 python claude_test.py를 입력하세요.


안녕하세요! 저는 엘론 머스크입니다. 혁신적인 아이디어와 기술로 세상을 변화시키고자 노력하고 있죠. 우주 탐사, 전기 자동차, 친환경 에너지 등 다양한 분야에서 새로운 도전을 계속하고 있습니다. 무엇을 궁금해 하시나요?



클로드가 마치 엘론 머스크와 같이 답변 하는것을 볼 수 있습니다. 이제 여러분의 창의적인 아이디어로 클로드를 활용해보세요!

<br/>

[[TOP]](#index)

---
## 프롬프트를 작성하기 좋은 콘솔 Workbench 활용하기
Claude API를 호출하기 앞서 사용할 프롬프트를 미리 작성하고 테스트해보고 싶다면 Claude 콘솔의 Workbench를 활용해보세요.

Claude 콘솔 Workbench

System Prompt: 챗봇에게 전달할 시스템 메시지 (역할, 태스크 지시 등)
User message: 사용자 입력 메시지를 입력
Model: Haiku, Sonnet, Opus 등 원하는 모델 선택
Run: 버튼 클릭 시 응답 결과 확인
콘솔에서 프롬프트를 테스트해보면서 모델별 응답의 차이, 프롬프트 디자인에 따른 결과 변화 등을 손쉽게 비교해볼 수 있습니다.

<br/>

[[TOP]](#index)

---
## Claude 모델 비교하기
Claude API에서 사용할 수 있는 Claude 3에는 Haiku, Sonnet, Opus 세 가지 버전이 있습니다. 각 모델의 특징과 장점을 간략히 정리했으니 용도에 맞는 모델을 선택하는 데 참고해보세요.

모델	하이쿠	소넷	오푸스
용도	- 실시간 상호작용
- 콘텐츠 모더레이션
- 최적화된 비용 효율 작업	- 방대한 데이터 처리
- 컨텐츠 마케팅/영업
- 시간 절약 작업 자동화	- 복잡한 문제 해결
- 연구 개발
- 전략 및 분석
특징	빠른 응답 속도,
효율성	균형 잡힌 성능
부담 없는 가격	최상위 지능 수준
난이도 높은 태스크
컨텍스트	200K	200K	200K

<br/>

[[TOP]](#index)

---
## 프롬프트 엔지니어링 팁
Claude의 잠재력을 최대한 활용하려면 프롬프트 엔지니어링이 중요합니다. 효과적인 프롬프트 작성을 위한 몇 가지 팁을 소개할게요.

명확하고 구체적인 지시 내리기
Claude에게 기대하는 바를 정확히 전달하세요.

지금부터 너는 헬스 트레이너 역할을 맡아줘. (O)
운동 좀 알려줘. (X)
단계별로 태스크 나누기
복잡한 문제는 여러 하위 태스크로 쪼개서 순차적으로 지시하세요.

다음 단계를 따라 건강한 식단을 짜보자.
일일 칼로리 섭취량 계산하기
균형 잡힌 영양소 비율 정하기
식단표 예시 들기
다양한 사례와 예시 활용하기
원하는 결과에 대한 예시를 제시하면 이해도를 높일 수 있어요.

우울할 때 듣기 좋은 힐링 플레이리스트 '위로'를 만들어줘. 수록곡 스타일은 이런 느낌이었으면 해.
잔잔한 어쿠스틱 기타 선율
마음을 차분하게 만드는 피아노 멜로디
희망적인 가사의 발라드
System Prompt 적극 활용하기
모델의 역할과 행동 원칙을 system prompt로 제시하세요.

예시, 너는 이제부터 심리 상담사 역할을 맡아. 대화할 때는 공감 어린 말투를 쓰고, 내담자의 문제에 구체적인 해결책을 제안해줘.
그 밖에도 프롬프트 엔지니어링에 대해 더 알고 싶다면 클로드 프롬프트 엔지니어링 완벽 가이드를 참고해보세요!

<br/>

[[TOP]](#index)

---
## Streamlit으로 클로드 챗봇 만들기
이번에는 Streamlit과 클로드 API를 활용해 나만의 챗봇 웹앱을 개발하는 방법을 알아볼 거예요.

Streamlit 및 라이브러리 설치
pip install streamlit anthropic python-dotenv


코드 작성하기
app.py라는 파일을 만들고 아래 코드를 작성하세요.
```python
import streamlit as st
import os
from dotenv import load_dotenv
import anthropic

# .env에서 API key 불러오기
load_dotenv()
claude_api_key = os.environ.get("CLAUDE_API_KEY")

# Claude API 클라이언트 초기화
claude_client = anthropic.Anthropic(api_key=claude_api_key)

# 제목과 설명 표시
st.title("Claude 프롬프트 엔지니어링 코칭 챗봇")
st.write("프롬프트 엔지니어링을 배우고 싶다면 저와 대화를 나눠보세요!")


# 세션 스테이트 초기화
if "messages" not in st.session_state:
    st.session_state["messages"] = []

# 유저 입력 받기
user_message = st.text_input("메시지 입력:")

if user_message:
    # 유저 메시지 추가
    st.session_state["messages"].append({"role": "user", "content": user_message})

    # Claude API 호출
    response = claude_client.messages.create(
        model="claude-3-sonnet-20240229",
        system="당신은 이제부터 프롬프트 엔지니어링 전문 코치입니다. 사용자의 질문에 전문적이고 실용적인 조언을 해주세요. 항상 한글로 답변 합니다.", 
        max_tokens=1024,
        messages=st.session_state["messages"]
    )

    # Claude 응답 추가
    assistant_response = response.content[0].text.strip()
    st.session_state["messages"].append({"role": "assistant", "content": assistant_response})

# 대화 내용 표시
for msg in st.session_state["messages"][1:]:
    if msg["role"] == "user":
        st.write(f'<p style="color:blue;"><b>👤 사용자:</b> {msg["content"]}</p>', unsafe_allow_html=True)
    else:
        st.write(f'<p style="color:green;"><b>🤖 코치:</b> {msg["content"]}</p>', unsafe_allow_html=True)

```

앱 실행하기
streamlit run app.py


브라우저에서 로컬호스트 주소로 접속하면 Claude 챗봇과 대화를 나눌 수 있습니다.

아래와 같이 '좋은 프롬프트 작성을 하려면 어떻게 해야 하나요?'라고 물어보면, Claude가 프롬프트 엔지니어링에 대한 조언을 해줍니다.

Claude API 로 만든 Streamlit 챗봇 결과 예시

프롬프트 엔지니어링에 대해 궁금한 점을 물어보면서 전문 코치의 조언을 들어보세요!

위와 같은 방식으로 Streamlit을 활용해 클로드 챗봇을 만들 수 있습니다. 여러분만의 창의적인 아이디어로 챗봇을 확장하고 발전시켜보세요!

<br/>

[[TOP]](#index)

---
## 클로드 API 활용, 어떠셨나요?
지금까지 클로드 API 사용 방법을 처음부터 끝까지 자세히 살펴봤습니다. API 키 발급부터 SDK 설치, 요청 보내기까지 천천히 따라 해보셨길 바랍니다.

새롭게 배운 내용을 토대로 클로드를 활용한 여러분만의 프로젝트를 구상해보는 것은 어떨까요? 강력하면서도 유연한 클로드와 함께라면 생각만 해도 설레는 아이디어들을 현실로 만들어낼 수 있을 거예요.

AI의 무궁무진한 가능성을 클로드와 함께 마음껏 탐험해보시길 바랍니다. 여러분의 창의적인 도전을 응원합니다.

<br/>

[[TOP]](#index)

---