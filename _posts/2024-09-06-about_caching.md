---
title: About Caching 
date: 2024-09-06 09:01:00 +09:00
categories: [CS, WEB]
tags:
  [
    CS,
    File System,
    WEB,
    WAS,
    Security,
    웹 서비스,
    .
    .
    .
  ]
---

# Introduction
```shell
캐시: 접근 시간이 느린 곳의 데이터를 상대적으로 빠른 장소에 임시 보관
```

1. 일반적인 캐시 활용
- 이미지, css, js 등 정적 리소스 대상
- 캐시 기반 장점을 위해서 서버 리소스 변경 시 클라이언트에 실시간 반영이 불가능

- WAS에 Caching Service 파트를 연결시켜서 웹 아키텍처에 포함시킬 수도 있음.

2. 온라인 갤러리를 구현하고자 할 경우
```shell
1. 파일이 변경되지 않는다는 조건을 세운다면 캐시 적용

- I/O 흐름을 고려하는 단계 필요:
+ 데이터 읽기 후 외부 장치로의 전송 흐름과 속도
+ 자주 변하는 것과 변하지 않는 요소를 정의


2. 파일이 변경된다는 조건 존재
- 원본 파일 변경을 리스닝하다가 적용
```


## 로컬 캐시 라이브러리
1. 캐시 항목 만료 정책
2. 캐시 제거 정책 (ex: LFU, LRU)
3. 기타 클러스터 캐시 동기화 및 디스크 저장 기능
