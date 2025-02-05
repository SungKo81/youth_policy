### 청년정책 RAG 학습 모델
- SKN 3번째 단위 프로젝트 제외된 자료를 활용하여 진행한 개인 프로젝트
- 목표: LANGCHANIN을 활용하여 청년정책 자료내에서 대답할수 있도록 프로그래밍

사용 모듈
- langchain

사용 모델
- 임베딩 : text-embedding-3-small
- RAG LLM : gpt-4o-mini
- 벡터스토어 : Chroma
- EVAL LLM : gpt-4o

학습 진행순서 (rag_youth_policy.ipynb)
- 청년법령집.pdf 로드
- RecursiveCharacterTextSplitter를 사용하여 chunk 분할
- 임베딩 후 벡터스토어 저장
- langchain 구성 (retriever -> prompt_template -> model -> parser

평가 진행 순서 (eval_youth_policy.ipynb)
- 평가 데이터로 사용할 context 추출
- Eval 데이터셋 생성 (질문, context, reference)
- 벡터스토어 연결
- 평가 진행
  - LLMContextRecall
  - LLMContextPrecisionReference
  - Faithfulness
  - AnswerRelevancy

결과
- LLMContextRecall : 0.88
- LLMContextPrecisionReference : 0.80
- Faithfulness : 0.92
- AnswerRelevancy : 0.31

결론
- recall, precision, faithfullness는 양호하게 나왔으나 relevancy가 낮아 응답이 적절하게 나오지는 않은것 같다.
