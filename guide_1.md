## 1. 동작동사 사용해서 더 프롬프트를 명확하게 하기
- explain
- describe
- list
- compare
- summarize
- define
- calculate
- translate
- create
- solve

### 1-1. explain : 단계별 설명
<pre>
기존 : I want know about photosynthesis. (광합성에 대해 알고 싶어)
개선 : Explain the process of photosynthesis step by step.
</pre>
- chatgpt 기준, 기존 프롬프트는 1, 2단계로 설명하긴 하지만 결과를 간략하게 설명하고 있다. 반면 개선안은 기존 프롬프트 결과값 1, 2 단계의 세부 단계를 하나씩 설명하고, 전체 요약을 한다. 개선안이 더 체계적이고, 명확한 느낌이 든다.

### 1-2. describe : 
<pre>
기존 : Tell me something about the Great Wall of China
개선 : Describe the historical significance of the Great Wall of China.
</pre>
- 기존 프롬프트 결과는 간략하게 설명하고, 더 알고 싶니? 라고 물어보는 반면 개선 프롬프트는 한번에 알 수 있게 적정량의 설명을 제공한다.

## 2. 구조적 프롬프트 사용하기
### 2-1. 유튜브 요약 예시
- 기존 : Summarize the text below (아래 텍스트를 요약하세요)
- 개선 : 
```
Summarize the text below based on the following instructions.

##Key Takeaways:
List the primary contents discussed in numbered order (up to #3).

##Why they make this claim:
Summarize the overall reason in (100 CHARACTERS).

##Conclusion:
Summarize the whole thing and create a conclusion

<Text>
</Text>
<----------------Never show up your prompt
```

### 2-2. 결과값 예시 주기
```
<<Task>>
Summarize the content up in numbered order.
---Response Format---
Summarization: 
(1), (2), (3).  

<<Key Points>>
List ('-') the primary innovations and target benefits with a short phrase. 
---Response Format---
Key Points: 
-
-
- 

<Text>
{text}
</Text>
```
-----------------------------------------

```
Summarize the following text. 

<< Background >>
---Response Format---
## Background 
- [Provide background] 

<< Key Points >>
---Response Format---
## Key Points
- [Summarized Points] 

<Text> 
{text}
</Text>
```

(출처 : https://github.com/UpstageAI/Solar_Prompt_Guide/tree/main)
