---
title: doc2vec based on gensim library
date: 2024-09-24 10:20:00 +09:00
categories: [Project, 논문]
tags:
  [
    Project,
    WEB,
    DATA,
    Hadoop,
    웹 서비스,
    분산처리,
    파이썬,
    LLM,
    AI Engineering,
    Edge Computing,
    온디바이스 AI,
    생성형 AI,
    AI,
    .
    .
    .
  ]
---

# 패키지 설치
```shell
# 0. 만약 윈도우라면 conda 환경 변수 추가
source ~/.bashrc

# 1. 콘다 환경 사용
conda create -n doc2vec python=3.12.3 -y
conda activate doc2vec

pip install torch faiss-cpu
pip install pandas numpy scikit-learn tqdm
pip install gensim
pip install konlpy

```

# 형태소 분석기
[gpters, 참고 링크](https://www.gpters.org/dev/post/rag-creation-strategy-6SW9xPXYOpEcsJv)

[형태소분석기 okt 오류 참고 링크](https://github.com/konlpy/konlpy/issues/81?fbclid=IwY2xjawFfHhJleHRuA2FlbQIxMAABHVheP5iRRmBIQkTjckMjj2Is239J3QvzVCVEFLZFYOob0M6ZuLB7qj7gRA_aem_bpmw8yxh34aIkqcCopA2Mg)


```shell
- 연구 논문
- 유형 : 학술논문, 연구 보고서
- 청크 크기: 500
- 오버랩: 125
- include_prev_next_rel: True (연구 논문에서 각 섹션 간의 논리적 연결이 매우 중요)
- tokenizer: KoNLPy의 Okt (다양한 문장 구조와 자연스러운 텍스트 처리가 중요)
```

```shell
from konlpy import jvm
jvm.init_jvm()

```
