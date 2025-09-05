🏠 > [프롬프트 엔지니어링](../) > `프롬프트 엔지니어링 방법: ChatGPT 200% 활용 하기 - 입문편`

### INDEX

- []()
- [참고자료](#참고자료) 

---
# 프롬프트 엔지니어링 방법: ChatGPT 200% 활용 하기 - 입문편
프롬프트 엔지니어링이란 무엇일까요? 이는 언어 모델을 효과적으로 활용하기 위해 프롬프트를 개발하고 최적화하는 새로운 분야입니다. 이 글에서는 프롬프트 엔지니어링의 기본 개념과 실제 예시, 그리고 효과적인 프롬프트 작성 팁에 대해 알아보겠습니다.

## 1. 프롬프트 엔지니어링의 기본 개념
프롬프트는 언어 모델에게 전달하는 지시문이나 질문 등의 정보를 포함할 수 있습니다. 예를 들어, 아주 간단한 프롬프트는 다음과 같습니다:

프롬프트
하늘은

출력
"파란색입니다. 맑은 날에는 하늘이 파란색입니다. 흐린 날에는 하늘이 회색이거나 흰색일 수 있습니다."

이 예시에서 언어 모델은 주어진 문맥 "하늘은"에 따라 의미 있는 문자열을 출력합니다. 하지만 이 출력은 우리가 원하는 작업과는 거리가 있을 수 있습니다. 이는 우리가 특정 작업을 수행하고자 할 때 더 많은 문맥이나 지시를 제공해야 함을 보여줍니다.

프롬프트를 개선해 보겠습니다:

프롬프트
다음 문장을 완성하세요: 하늘은

출력
"오늘 너무 아름답습니다."

위에서 보시는것 처럼 모델에게 문장을 완성하라고 지시했기 때문에 결과가 훨씬 나아 보입니다.

프롬프트의 기본 요소는 다음과 같습니다:

프롬프트의 기본 요소

지시문(Instruction): 모델이 수행하길 원하는 특정 작업이나 지시
문맥(Context): 모델이 더 나은 응답을 제공할 수 있도록 돕는 외부 정보나 추가 문맥
입력 데이터(Input Data): 우리가 응답을 찾고자 하는 입력이나 질문
출력 지시자(Output Indicator): 출력의 유형이나 형식을 나타냅니다.

<br/>

[[TOP]](#index)

---
## 2. 프롬프트의 예시
프롬프트 엔지니어링을 더 잘 이해하기 위해 몇 가지 예시를 살펴보겠습니다:

1) 기본 프롬프트:
프롬프트
하늘은

출력
"파란색입니다. 맑은 날에는 하늘이 파란색입니다. 흐린 날에는 하늘이 회색이거나 흰색일 수 있습니다."

2) 지시문을 추가한 프롬프트:
프롬프트
다음 문장을 완성하세요: 하늘은

출력
"오늘 너무 아름답습니다."

3) 특정 작업을 수행하도록 지시하는 프롬프트:
프롬프트
다음 텍스트를 스페인어로 번역하세요: Text: "hello!"

출력
"¡Hola!"

4) 특정 정보를 추출하도록 지시하는 프롬프트:
프롬프트
다음 텍스트에서 장소 이름을 추출하세요.

원하는 형식(Desired format):
Place: 'comma_separated_list_of_company_names'
Input:
Although these developments are encouraging to researchers, much is still a mystery. “We often have a black box between the brain and the effect we see in the periphery,” says Henrique Veiga-Fernandes, a neuroimmunologist at the Champalimaud Centre for the Unknown in Lisbon. “If we want to use it in the therapeutic context, we need to understand the mechanism.

출력
Place: Champalimaud Centre for the Unknown, Lisbon

<br/>

[[TOP]](#index)

---
## 3. 프롬프트 설계 팁
프롬프트를 설계할 때는 다음과 같은 일반적인 팁을 기억해야 합니다.

프롬프트를 설계 팁

간단하게 시작하기. (Start Simple)
지시문을 잘 작성하기. (The Instruction)
구체적으로 작성하기. (Specificity)
불명확함을 피하기. (Avoid Impreciseness)
무엇을 하지 말아야 하는지보다 무엇을 해야 하는지에 집중하기. (To do or not to do?)
<br/>

[[TOP]](#index)

---
## 4. 결론
프롬프트 엔지니어링은 언어 모델을 효과적으로 활용하는 데 중요한 역할을 합니다. 이 기술을 통해 우리는 모델의 출력을 더욱 향상시킬 수 있습니다. 다음 시리즈에서는 프롬프트 엔지니어링의 고급 기법에 대해 알아보겠습니다.

이 글이 프롬프트 엔지니어링에 대한 이해를 돕는데 도움이 되셨으면 좋겠습니다. 다음 시간에는 더 깊이 있는 내용을 다뤄보도록 하겠습니다.

## ** 참고자료 **

https://github.com/dair-ai/Prompt-Engineering-Guide/blob/main/guides/prompts-intro.md

<br/>

[[TOP]](#index)

---