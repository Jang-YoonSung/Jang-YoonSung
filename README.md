<h2 align="center"><b>👋 About Me</b></h2>

<p align="center">
<b>AI 서비스 & MLOps 엔지니어</b> 장윤성입니다.<br>
Docker · FastAPI · Celery 기반 비동기 서버 아키텍처 설계부터<br>
LLM/STT/TTS 모델 파인튜닝, 서빙 인프라 운영까지<br>
기획-개발-배포-운영 전 과정을 실제 기업 서비스에 적용해왔습니다.
<br><br>
오픈소스를 그대로 가져다 쓰기보다 <b>내부 구조를 분석해 필요한 만큼 재설계</b>하는 것을 선호하고,<br>
GPU 공유 환경에서의 리소스 트러블슈팅, 라이브러리 버그 패치 등 <b>인프라 레벨 문제 해결</b>에 강점이 있습니다.
</p>

---

<h2 align="center"><b>🔧 Tech Stack</b></h2>

<p align="center">
<b>AI</b><br>
<img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white"/>
<img src="https://img.shields.io/badge/Transformers-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black"/>
<img src="https://img.shields.io/badge/LangChain-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white"/>
<img src="https://img.shields.io/badge/MCP-005AF0?style=for-the-badge&logo=modelcontextprotocol&logoColor=white"/>
<img src="https://img.shields.io/badge/Agno-6E56CF?style=for-the-badge"/>
<br><br>
<b>SERVING / INFERENCE</b><br>
<img src="https://img.shields.io/badge/vLLM-000000?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Ollama-000000?style=for-the-badge&logo=ollama&logoColor=white"/>
<img src="https://img.shields.io/badge/CTranslate2-4B5563?style=for-the-badge"/>
<img src="https://img.shields.io/badge/Qdrant-DC244C?style=for-the-badge&logo=qdrant&logoColor=white"/>
<br><br>
<b>BACKEND / ASYNC</b><br>
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white"/>
<img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white"/>
<img src="https://img.shields.io/badge/Celery-37814A?style=for-the-badge&logo=Celery&logoColor=white"/>
<img src="https://img.shields.io/badge/RabbitMQ-FF6600?style=for-the-badge&logo=rabbitmq&logoColor=white"/>
<img src="https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white"/>
<img src="https://img.shields.io/badge/WebSocket-010101?style=for-the-badge"/>
<br><br>
<b>MLOPS / INFRA</b><br>
<img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white"/>
<img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black"/>
<img src="https://img.shields.io/badge/CUDA-76B900?style=for-the-badge&logo=nvidia&logoColor=white"/>
<img src="https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white"/>
<img src="https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white"/>
</p>

---

<h2 align="center"><b>💼 Work Experience</b></h2>

### 🏢 보이스오버랩 — <i>AI Engineer</i>
**2025.11 ~ 재직 중**
음성인식, LLM, 회의록 서비스를 제공하는 기업

- STT 학습 자동화 파이프라인 + LLM-as-judge 기반 자동 채점 시스템 설계·구축
- Triton Inference Server + TensorRT-LLM 기반 STT 추론 서버 구축
  * 동시 요청 처리량 최대 2.8배, 단건 처리속도 최대 4.9배 개선
- 개별 LLM 파이프라인 운영 방식을 vLLM 기반 통합 서빙 시스템으로 전환
  * 단일 요청 기준 (500 tokens) 20.7 tok/s(hf_pipeline) 156 tok/s(vllm) **약 7.5배** 향상
  * 동시 요청 4개 기준 (2,000 tokens 합산) 20.5 tok/s(hf_pipeline) 557 tok/s(vllm) **약 27배** 향상
  
### 🏢 솔루게이트 — <i>LLM Engineer</i>
**2024.07 ~ 2025.07**
음성인식, LLM, 회의록 서비스를 제공하는 기업

- 키워드 기반 문장 생성 및 음성 생성 서비스 개발
- 회의록 요약 서비스 고도화, 영한/한영 비동기 번역 서비스 개발
- 사내 고유명사/약어 인식을 위한 데이터셋 구축

<h2 align="center"><b>🚀 Projects</b></h2>

---

### 🎯 AI 면접 자동 채점 시스템 (2026.04 ~ 2026.07)
국내 공공기관 AI 면접 답변을 자동으로 채점하는 End-to-End 시스템. 음성 → STT 전사 → LLM 채점 → 리포트까지 이어지는 파이프라인을 설계·구현.

- MongoDB 기반 학습 데이터 축적 → Whisper LoRA 파인튜닝 → CER/WER 자동 평가까지 무중단 재학습 파이프라인 구축
- RabbitMQ 이벤트 기반 상태 관리로 폴링 없이 "STT 처리 중 → 학습 전환" 타이밍 자동 판단
- vLLM(gemma4 12b it) + guided decoding으로 LLM-as-judge 답변 평가 API 단독 개발, 구조화 출력 신뢰성 확보

**Tech:** `FastAPI` `Celery` `RabbitMQ` `MongoDB` `Whisper` `vLLM` `Docker`

---

### 🎙️ 실시간 STT 파이프라인 분석 및 재설계 (2026.08)
오픈소스 실시간 STT 라이브러리 내부 구조를 소스 레벨에서 분석하고, 재사용 가능한 컴포넌트 단위로 분리해 MVC 구조로 재설계.

- 오디오 청크 → VAD → 증분 디코딩 → 화자분리(diarization)까지 이어지는 스트리밍 파이프라인 구조 분석
- 공유 GPU 환경에서의 OOM/리소스 경합 트러블슈팅
- 오픈소스 라이브러리 내부 버그 직접 진단 및 패치 (라이브러리 소스 레벨 디버깅)

**Tech:** `FastAPI` `WebSocket` `faster-whisper` `Docker`

---

### 🧳 Tripfolio — 여행 카드 수집 플랫폼 (개인 풀스택, 2026.04 ~ 2026.05)
YouTube 영상에서 여행 정보를 AI로 자동 추출해 카드로 만들고 공유하는 개인 풀스택 프로젝트. 기획부터 프론트엔드/백엔드/배포까지 단독 설계·구현.

- Ollama(Qwen3.5) 기반 YouTube 자막 분석 → 여행 정보 구조화 AI 파이프라인
- React + TypeScript 프론트엔드, FastAPI + MongoDB 백엔드, Docker Compose 배포까지 전 과정 단독 수행

**Tech:** `React` `TypeScript` `FastAPI` `MongoDB` `Ollama` `Docker`

---

### ✈️ Trip Agent Project (2025.10 ~ 2025.11)
- 멀티 에이전트 기반 all-in-one 여행 플래너 서비스 (팀 프로젝트)
- Airbnb/Google Flights MCP Custom Tool 개발 담당

**Tech:** `Python` `FastAPI` `AsyncIO` `Docker` `MCP` `SerpApi` `Agno`

---

<h2 align="center"><b>🏆 Awards</b></h2>

- 🥇 **금상 (1위)** — 2022 SW Week Python 경연대회
- 🥈 **은상 (2위)** — 2022 SW Week 오픈소스 SW 경연대회
- 🎖 **7등** — SW중심대학 공동 AI 경진대회 2023 (위성 이미지 건물 영역 분할)

---

<h2 align="center"><b>📌 Activities</b></h2>

- 학부 연구생 — [A.I. Accelerator Computing](https://sites.google.com/site/embeddedsochallymuniv/project) (2022.12 ~ 2023.12)
- 네이버 "소프트웨어야 놀자" 대학생 멘토 (2023.07 ~ 2023.08)
- 한림대 축구동아리 DEFY 회장 (2022, 2023)
