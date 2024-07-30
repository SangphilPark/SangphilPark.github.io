---
title: Stable Diffusion 개발 시
date: 2024-07-30 11:02:07 +09:00
categories: [AI, CV]
tags:
  [
    LLM,
    SDXL,
    Stable Diffusion,
    스테이블 디튜전,
    LoRA,
    스케쥴러,
    .
    .
    .
  ]
---

# 🛠️ Stable Diffusion 엔지니어링 일지

### 1. Stable Diffusion 허깅페이스
- [공식 Docs 사용](https://huggingface.co/docs/diffusers/v0.13.0/en/stable_diffusion): Stable Diffusion에 대한 기본적인 설명과 사용 방법이 포함되어 있습니다.

### 2. 스케쥴러
- [스케쥴러 종류와 튜닝 가이드](https://huggingface.co/docs/diffusers/main/en/api/schedulers/overview): 다양한 스케쥴러 종류와 그 특징에 대해 설명합니다.
  - 스케쥴러 종류에 따라 Num Inference 수 튜닝 필요
  - Config 적용 스킬 필요

### 3. 그리드 이미지 배치
- [메모리 효율화 참고](https://huggingface.co/docs/diffusers/v0.13.0/en/stable_diffusion#memory-optimization): 이미지 프로세싱의 스킬로 메모리를 효율적으로 사용합니다.
  - 그리드로 이미지 처리
  - 전, 후, 시드 값, 하이퍼 파라미터 값 등의 차이에 따른 시각적 비교 가능
  - 향후 애니메이션 화 할 때 프레임 분할로 활용 가능성 있음

### 4. Negative Prompt의 필요성
- [Negative Prompt의 중요성](https://minimaxir.com/2022/11/stable-diffusion-negative-prompt/): SD 2.1부터 부정 프롬프트의 필요성이 강조됩니다.
  - 부정 프롬프트를 사용해 원치 않는 요소를 제거
  - 프롬프트 엔지니어링을 통해 결과물의 품질 향상 가능

### 5. Diffusers Most Trend
- [허깅페이스 모스트 트렌드 링크](https://huggingface.co/models?library=diffusers): 최신 트렌드와 인기 모델들을 확인할 수 있습니다.

### 6. Switching out the latent decoder - VAE
- [이미지 퀄리티 개선](https://huggingface.co/docs/diffusers/v0.13.0/en/stable_diffusion#quality-improvements): 이미지 퀄리티를 미세하게 조정합니다.
  - VAE(Variational Autoencoder)를 통해 이미지의 세부 조정 가능
  - 광도 및 채도의 조절이 가능
  - KLEncoder 등 익숙한 파이프라인 내 파트

---

## 참고 사항
- 📘 [포스팅 블로그](https://huggingface.co/blog/stable_diffusion): Stable Diffusion과 관련된 다양한 블로그 포스트가 포함되어 있습니다.
- ⚙️ [xFormer 효율성](https://huggingface.co/docs/diffusers/optimization/xformers): xFormer 라이브러리를 활용한 최적화 방법
- 🏗️ [Dream Booth / LLM PEFT](https://huggingface.co/docs/diffusers/training/dreambooth): DreamBooth와 LLM PEFT(파라미터 효율적 미세조정)에 대한 가이드
- 🚀 [SD 파이프라인](https://huggingface.co/docs/diffusers/main/en/api/pipelines/stable_diffusion/overview): Stable Diffusion 파이프라인의 전반적인 개요와 사용법

---

## 추가로 포함하면 좋을만한 정보
- 🧠 **프롬프트 라이브러리**: 커뮤니티에서 공유하는 다양한 프롬프트 모음
  - 예시: "sunset over a mountain range"와 같은 프롬프트
- 🌐 **인터넷 검색 팁**: 효과적인 프롬프트를 찾기 위한 검색 방법
  - 키워드 조합, 예제 프롬프트 활용 등
- 📊 **성능 벤치마크**: 다양한 설정과 스케쥴러에 따른 성능 비교 데이터
  - 스케쥴러별 처리 속도, 메모리 사용량 등
- 🔧 **툴링 및 플러그인**: 개발에 유용한 다양한 도구와 플러그인 정보
  - Visual Studio Code 플러그인, Jupyter 노트북 등
- 🎨 **시각적 튜토리얼**: 이미지 퀄리티 향상을 위한 시각적 가이드 및 튜토리얼
  - 단계별 스크린샷과 설명 포함

---

✨ 꾸준한 업데이트와 학습으로 최신 트렌드와 기술을 유지하세요!
