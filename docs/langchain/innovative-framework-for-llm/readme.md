🏠 > [랭체인](../) > `랭체인 (LangChain) 이란? LLM 서비스 개발을 위한 혁신적인 프레임워크`

### INDEX

- [랭체인 (LangChain) 이란?](#랭체인-langchain-이란)
- [LangChain의 주요 구성 요소](#langchain-을-활용한-간단한-llm-애플리케이션-구축)
  - [랭체인 코어 (langchain-core)](#랭체인-코어-langchain-core)
  - [랭체인 커뮤니티 (langchain-community)](#랭체인-커뮤니티-langchain-community)
  - [LangChain](#langchain)
  - [LangGraph](#langgraph)
  - [LangServe](#langserve)
  - [LangSmith](#langsmith)
- [개발 단계별 지원 요소](#개발-단계별-지원-요소)
  - []()
  - []()
  - []()
- [LangChain 을 활용한 간단한 LLM 애플리케이션 구축](#langchain-을-활용한-간단한-llm-애플리케이션-구축)
  - []()
  - []()
  - []()
  - []()
  - []()
  - []()
  - []()
  - []()
- [결론](#결론)

---
# 랭체인 (LangChain) 이란? LLM 서비스 개발을 위한 혁신적인 프레임워크
인공지능 기술의 급속한 발전으로 대규모 언어 모델(Large Language Models, LLM)을 활용한 서비스 개발이 IT 업계의 핫 토픽으로 떠오르고 있습니다. 그러나 LLM을 실제 서비스에 효과적으로 적용하는 것은 여전히 많은 도전과 복잡성을 수반합니다. 이러한 상황에서 등장한 것이 바로 랭체인(LangChain) 입니다. LangChain은 LLM 기반 애플리케이션 개발을 위한 혁신적인 프레임워크로, 개발자들에게 새로운 가능성을 열어주고 있습니다. 이 글에서는 LangChain의 개념, 주요 특징, 그리고 이를 활용한 개발 방법에 대해 자세히 알아보겠습니다.

## 랭체인 (LangChain) 이란?
랭체인 (LangChain)은 대규모 언어 모델(LLMs)을 이용한 애플리케이션 개발을 위한 종합적인 프레임워크입니다. 이 프레임워크는 LLM 애플리케이션의 전체 생명주기를 간소화하고 최적화하는 것을 목표로 합니다. 개발에서부터 프로덕션 단계, 그리고 최종 배포까지 LLM 기반 서비스 구축의 모든 단계를 지원합니다.

<br/>

[[TOP]](#index)

---
## LangChain의 주요 구성 요소
LangChain 프레임워크는 다음과 같은 핵심 라이브러리로 구성되어 있습니다:

### 랭체인 코어 (langchain-core)
기본 추상화: LangChain 프레임워크의 기초를 형성하는 기본 구성 요소들을 제공합니다. 이는 체인, 에이전트, 데이터 변환기 등을 포함합니다.

랭체인 코어 구성 요소

LangChain 표현 언어(LCEL:LangChain Expression Language): LCEL은 복잡한 작업을 정의하고 실행할 수 있는 고유한 언어입니다. 주요 기능으로는 병렬화, 폴백, 추적, 배칭, 스트리밍, 비동기 처리, 구성 등이 있습니다.

병렬화 (Parallelization): 여러 작업을 동시에 처리하여 성능을 최적화합니다.
폴백 (Fallbacks): 실패 시 대체 경로를 제공하여 안정성을 높입니다.
추적 (Tracing): 작업의 흐름을 모니터링하고 디버깅할 수 있게 합니다.
배칭 (Batching): 여러 작업을 하나로 묶어 처리 효율성을 증대시킵니다.
스트리밍 (Streaming): 실시간 데이터 처리를 지원합니다.
비동기 처리 (Async): 비동기 작업을 통해 응답성을 향상시킵니다.
구성 (Composition): 복잡한 작업을 단순하게 결합하여 처리합니다.

### 랭체인 커뮤니티 (langchain-community)
서드파티 통합: 다양한 외부 라이브러리와 도구를 통합하여 LangChain의 기능을 확장합니다.

랭체인 커뮤니티 구성 요소

모델 I/O (Model I/O): 모델, 프롬프트, 예제 선택기, 출력 파서 등의 I/O 작업을 지원합니다.
검색 (Retrieval): 데이터 검색 및 로딩, 벡터 저장소, 텍스트 분할기, 임베딩 모델 등을 포함합니다.
에이전트 도구 (Agent Tooling): 도구 및 툴킷을 제공하여 에이전트의 기능을 강화합니다.

### LangChain
인지 아키텍처: LangChain 애플리케이션의 인지 아키텍처를 구성하는 주요 구성 요소들을 포함합니다.

LangChain 구성 요소

체인 (Chains): 작업의 순차적 흐름을 정의합니다.
에이전트 (Agents): 특정 작업을 수행하는 독립적인 엔티티입니다.
검색 전략 (Retrieval Strategies): 필요한 데이터를 효율적으로 검색하는 방법을 정의합니다.

### LangGraph
그래프 구조: 복잡한 다중 액터 애플리케이션을 그래프 구조로 구축할 수 있게 지원합니다. 이는 여러 에이전트 간의 상호작용을 명확하게 시각화하고 관리할 수 있게 합니다.

### LangServe
REST API 배포: LangChain 체인을 REST API로 배포하여 다른 애플리케이션과의 연동을 용이하게 합니다. 이는 체인의 기능을 웹 서비스로 제공할 수 있게 합니다.

### LangSmith
개발자 플랫폼: LLM 애플리케이션의 디버깅, 테스트, 평가, 모니터링을 지원하는 종합적인 개발자 도구를 제공합니다.
디버깅 (Debugging): 코드의 오류를 찾아 수정할 수 있는 도구를 제공합니다.
테스트 (Testing): 애플리케이션의 기능을 검증할 수 있는 테스트 환경을 제공합니다.
평가 (Evaluation): 애플리케이션의 성능을 평가하고 개선할 수 있는 지표를 제공합니다.
모니터링 (Monitoring): 애플리케이션의 실시간 상태를 모니터링하고 문제를 조기에 감지할 수 있게 합니다.
이러한 구성 요소들이 유기적으로 결합되어 LLM 애플리케이션 개발의 전 과정을 지원합니다. 각 구성 요소는 독립적으로 동작하면서도, 전체 시스템의 일관성과 효율성을 보장하기 위해 상호작용합니다.

이러한 구성 요소들이 유기적으로 결합되어 LLM 애플리케이션 개발의 전 과정을 지원합니다.

<br/>

[[TOP]](#index)

---
## 개발 단계별 지원 요소

### 1. 개발 (Development) 단계 지원
LangChain은 개발자들이 LLM 기반 애플리케이션을 쉽고 빠르게 구축할 수 있도록 다양한 도구를 제공합니다:

오픈소스 빌딩 블록: LangChain은 다양한 오픈소스 컴포넌트를 제공하여 개발자가 필요한 기능을 쉽게 조합하고 확장할 수 있습니다.
서드파티 통합: 다양한 외부 서비스와의 통합을 지원하여 개발 과정을 더욱 효율적으로 만듭니다.
템플릿: 미리 정의된 템플릿을 통해 개발자는 빠르게 프로젝트를 시작할 수 있습니다.

### 2. 프로덕션 (Production) 단계 지원
LangSmith를 통해 개발된 애플리케이션의 품질을 지속적으로 개선할 수 있습니다:

검사 및 모니터링: 애플리케이션의 동작을 실시간으로 모니터링하고 분석할 수 있습니다.
평가: 다양한 메트릭을 통해 애플리케이션의 성능을 평가할 수 있습니다.
최적화: 수집된 데이터를 바탕으로 지속적인 최적화가 가능합니다.

### 3. 배포 (Devloyment) 단계 지원
LangServe를 통해 개발된 LangChain 결과물을 쉽게 API로 배포할 수 있습니다:

REST API 변환: 복잡한 LLM 체인을 간단한 REST API로 변환할 수 있습니다.
확장성: 클라우드 환경에서의 확장성을 고려한 설계를 제공합니다.


<br/>

[[TOP]](#index)

---
## LangChain 을 활용한 간단한 LLM 애플리케이션 구축
랭체인을 사용하여 간단한 LLM 애플리케이션을 구축하는 과정을 상세히 살펴보겠습니다. 이 예제에서는 한국어 텍스트를 다른 언어로 번역하는 애플리케이션을 만들어보겠습니다.

1. 필요한 라이브러리 설치
먼저 필요한 라이브러리들을 설치 합니다.


pip install langchain_core langchain_openai python-dotenv


2. OpenAI API 키 설정
그리고 OpenAI API 키를 설정하기 위해 .env 파일을 생성하고 API 키를 설정합니다.


OPENAI_API_KEY=your_api_key_here


API 키 발급 방법이 궁금하다면 ChatGPT API 사용 방법 중 API 키 발급 방법에서 확인 할 수 있습니다.

3. 필요한 라이브러리 임포트
먼저 필요한 라이브러리들을 임포트합니다.

import os
from langchain_core.prompts import ChatPromptTemplate
from langchain_core.output_parsers import StrOutputParser
from langchain_openai import ChatOpenAI


2. 언어 모델 초기화
OpenAI의 GPT 모델을 사용하기 위해 OpenAI 클래스를 초기화합니다. 여기서 temperature 파라미터는 모델의 창의성을 조절합니다. 0에 가까울수록 더 일관된 출력을, 1에 가까울수록 더 다양하고 창의적인 출력을 생성합니다.

model = ChatOpenAI(temperature=0.7)

3. 프롬프트 템플릿 정의
번역을 위한 프롬프트 템플릿을 정의합니다. 이 템플릿은 두 개의 입력 변수를 가집니다: 번역할 언어와 번역할 한국어 텍스트입니다.

system_template = "다음 한국어 텍스트를 {language}로 번역하세요:"
prompt_template = ChatPromptTemplate.from_messages([
    ('system', system_template),
    ('user', '{text}')
])


4. 출력 파서 정의
LLM의 출력을 단순 문자열로 파싱하기 위해 StrOutputParser를 사용합니다.

output_parser = StrOutputParser()

5. 전체 파이프라인 구성
이제 프롬프트 템플릿, LLM 체인, 출력 파서를 하나의 파이프라인으로 연결합니다.

translation_chain = prompt_template | model | parser

7. 번역 애플리케이션 실행
이제 우리의 번역 애플리케이션을 실행해볼 수 있습니다.

result = translation_chain.invoke({"language": "영어", "text": "안녕하세요, 오늘 기분이 어떠신가요?"})
print(result)

이 코드를 실행하면 "안녕하세요, 오늘 기분이 어떠신가요?"라는 한국어 텍스트가 영어로 번역되어 출력됩니다.

8. 전체 코드 실행
지금까지 작성한 코드를 하나로 합쳐보겠습니다.

```python
import os
from dotenv import load_dotenv
from langchain_core.prompts import ChatPromptTemplate
from langchain_core.output_parsers import StrOutputParser
from langchain_openai import ChatOpenAI

# .env 파일에서 환경 변수 로드
load_dotenv()

# OpenAI API 키 설정
os.environ["OPENAI_API_KEY"] = os.getenv("OPENAI_API_KEY")

def create_translation_chain():
    # 언어 모델 초기화
        
    # 1. Create prompt template
    system_template = "Translate the following into {language}:"
    prompt_template = ChatPromptTemplate.from_messages([
        ('system', system_template),
        ('user', '{text}')
    ])

    # 2. Create model
    # model = ChatOpenAI()
    model = ChatOpenAI(temperature=0.7)

    # 3. Create parser
    parser = StrOutputParser()

    # 4. Create chain
    chain = prompt_template | model | parser
    return chain

def main():
    # 번역 체인 생성
    print("번역 어플리케이션!")
    translation_chain = create_translation_chain()

    # 사용자 입력 받기
    text = input("번역할 한국어 텍스트를 입력하세요: ")
    language = input("어떤 언어로 번역할까요? ")

    # 번역 실행
    try:
        result = translation_chain.invoke({"language": language, "text": text})
        # 결과 출력
        print(f"\n번역 결과: {result}")
    except ValueError as e:
        print(f"Error: {e}")

if __name__ == "__main__":
    main()

```
이제 위 코드를 실행하면 한국어 텍스트를 다른 언어로 번역하는 간단한 애플리케이션이 실행됩니다.

python translate.py

아래와 같이 번역할 한국어 텍스트와 번역할 언어를 입력하면 번역 결과가 출력됩니다.

랭체인 번역 어플리케이션 결과 예시

상세 설명
언어 모델 (LLM) 초기화:

ChatOpenAI 클래스를 사용하여 GPT 모델을 초기화합니다.
temperature 값을 0.7로 설정하여 적당한 수준의 창의성을 유지합니다.
프롬프트 템플릿:

ChatPromptTemplate을 사용하여 LLM에 전달할 프롬프트의 구조를 정의합니다.
이 템플릿은 "language"와 "text"라는 두 개의 입력 변수를 가집니다.
번역을 위한 프롬프트를 사용하여 모델에게 번역 작업을 지시합니다.
출력 파서:

StrOutputParser는 LLM의 출력을 단순 문자열로 변환합니다.
이는 LLM의 출력을 애플리케이션에서 쉽게 사용할 수 있는 형태로 만듭니다.
LLM 체인 파이프라인 구성:

| 연산자를 사용하여 각 컴포넌트를 연결합니다.
이는 입력이 프롬프트 템플릿을 통과하고, 그 결과가 LLM 체인으로 전달되며, 최종적으로 출력 파서를 통과하는 흐름을 만듭니다.
실행:

invoke 메서드를 사용하여 파이프라인을 실행합니다.
필요한 입력(언어와 텍스트)을 딕셔너리 형태로 제공합니다.
이 간단한 예제는 LangChain의 핵심 개념들을 보여줍니다:

모듈성: 각 컴포넌트(LLM, 프롬프트 템플릿, 체인, 파서)는 독립적으로 정의되고 쉽게 교체 가능합니다.
유연성: 다양한 유형의 LLM, 프롬프트, 출력 처리 방식을 쉽게 통합할 수 있습니다.
파이프라인 구성: 여러 컴포넌트를 연결하여 복잡한 작업 흐름을 만들 수 있습니다.
확장 가능성
이 기본 구조를 바탕으로 다양한 방식으로 애플리케이션을 확장할 수 있습니다:

다중 언어 지원: 한국어를 여러 다른 언어로 번역할 수 있도록 확장할 수 있습니다.
컨텍스트 추가: 번역 시 특정 분야(예: 의료, 법률)나 스타일(예: 공식적, 비격식적)을 고려하도록 프롬프트를 수정할 수 있습니다.
에러 처리: LLM의 출력을 검증하고 필요시 재시도하는 로직을 추가할 수 있습니다.
캐싱: 자주 요청되는 번역 결과를 캐싱하여 성능을 향상시킬 수 있습니다.
사용자 인터페이스: 웹 또는 모바일 앱을 통해 사용자 친화적인 한국어 인터페이스를 제공할 수 있습니다.
이러한 간단한 LLM 애플리케이션 구축 예제를 통해 LangChain의 강력함과 유연성을 확인할 수 있습니다. LangChain은 복잡한 LLM 기반 애플리케이션을 쉽게 구축할 수 있는 도구를 제공하며, 개발자가 LLM의 잠재력을 최대한 활용할 수 있도록 돕습니다.

<br/>

[[TOP]](#index)

---
## 결론
LangChain은 LLM 기반 애플리케이션 개발을 위한 강력하고 유연한 프레임워크입니다. 개발에서 배포까지 전체 생명주기를 지원하며, 다양한 기능과 통합을 통해 개발자의 생산성을 크게 향상시킵니다. AI 기술이 빠르게 발전하는 현재, LangChain은 개발자들이 이러한 기술을 효과적으로 활용할 수 있게 해주는 중요한 도구가 될 것입니다.

LangChain을 사용하여 여러분만의 혁신적인 AI 애플리케이션을 개발해보세요. 더 자세한 정보와 시작 가이드는 LangChain 공식 문서에서 확인할 수 있습니다.

<br/>

[[TOP]](#index)

---