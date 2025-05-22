# forsure_ai

# 🔮 FOR SURE - 사주팔자 AI 보험 추천 서비스

---

## 1. 프로젝트 개요

사주팔자와 음양오행 이론을 AI 기술로 분석하여 개인의 사고수, 건강운, 신체 취약 부위를 예측하고, 이를 바탕으로 맞춤형 보험 상품을 추천하는 혁신적인 InsurTech 서비스 **FOR SURE**입니다. 전통 명리학의 지혜와 현대 AI 기술을 결합하여 개인별 리스크를 사전에 예측하고 최적의 보험 포트폴리오를 제안합니다.

---

## 2. 핵심 기능 상세

### 2-1. 사주팔자 분석 엔진 (Core Analysis Engine)

#### 사주 데이터 처리 및 벡터화
* **PDF 사주 데이터 처리**: 
  - 전통 사주 서적, 명리학 논문, 사주 해석서 등을 PDF로 수집
  - LangChain Document Loader로 PDF 텍스트 추출 및 청킹
  - 사주 구성요소별 의미적 임베딩 생성 (Pinecone 저장)

* **사주팔자 자동 산출**:
  - 생년월일시 → 천간지지 자동 변환 알고리즘
  - 십간십이지, 오행(금목수화토), 육신 자동 분석
  - 신살(神殺) 및 격국 판정 시스템

#### 음양오행 분석 시스템
* **오행 균형 분석**: 개인 사주 내 금목수화토 비율 및 상생상극 관계 분석
* **용신 찾기**: 사주 내 가장 필요한 오행 원소 식별
* **희신/기신 판별**: 도움이 되는 오행과 해로운 오행 구분
* **계절별 영향**: 출생 계절에 따른 오행 영향 분석

### 2-2. 건강 및 리스크 예측 모듈

#### 사고수 예측 (Accident Proneness Analysis)
* **화(火) 과다**: 화재, 교통사고, 화상 위험도 증가
* **금(金) 불균형**: 수술, 외상, 금속 관련 사고 위험
* **수(水) 과다**: 익수, 중독, 신장 관련 질환
* **토(土) 부족**: 소화기 질환, 비장 관련 문제
* **목(木) 손상**: 간 질환, 근골격계 부상

#### 건강운 분석 (Health Fortune Prediction)
* **체질 분석**: 사주 기반 선천적 체질 및 건강 성향
* **취약 장기 예측**: 오행별 해당 장기의 건강 상태 예측
* **생체 리듬**: 계절별, 시간대별 건강 상태 변화 예측
* **면역력 지수**: 사주 기반 면역 체계 강약 판단

#### 신체 부위별 상세 분석
```
오행별 신체 부위 매핑:
- 목(木): 간, 담낭, 눈, 근육, 손발톱
- 화(火): 심장, 소장, 혀, 혈관계
- 토(土): 비장, 위, 입, 소화기계
- 금(金): 폐, 대장, 코, 호흡기계
- 수(水): 신장, 방광, 귀, 생식기계
```

### 2-3. RAG 기반 보험 상품 매칭 시스템

#### 보험 상품 데이터베이스 구축
* **상품 정보 벡터화**: 보험 상품의 보장 내용, 특약, 조건을 벡터로 변환
* **리스크-보장 매핑**: 예측된 건강 리스크와 보험 보장 항목 자동 매칭
* **실시간 상품 업데이트**: 보험사별 신상품 정보 자동 수집 및 반영

#### 맞춤형 추천 알고리즘
* **개인 리스크 프로파일 생성**: 사주 분석 결과 기반 개인별 위험도 수치화
* **보험 필요도 스코어링**: 예상 리스크 대비 보험 상품별 필요도 점수
* **포트폴리오 최적화**: 예산 대비 최적의 보험 조합 추천

### 2-4. LLM 기반 상담 및 리포트 생성

#### GPT-4.1-nano 활용 서비스
* **사주 해석 서비스**: 복잡한 사주 용어를 일반인이 이해하기 쉽게 설명
* **건강 조언**: 사주 기반 건강 관리 방법 및 주의사항 제안
* **보험 상담**: 추천 근거와 상품별 특징을 자연스러운 대화로 설명
* **질의응답**: 사주, 건강, 보험 관련 실시간 Q&A

#### 개인화된 리포트 생성
* **종합 사주 분석서**: 개인의 사주팔자 전체 해석
* **건강 리스크 리포트**: 예상 질병 및 사고 위험도 상세 분석
* **맞춤 보험 추천서**: 추천 근거와 함께 최적 보험 포트폴리오 제안
* **예방 관리 가이드**: 리스크 예방을 위한 생활 습관 개선 방안

---

## 3. 기술 아키텍처

### 3-1. 핵심 기술 스택

| 구분 | 기술/툴 | 활용 목적 |
|------|---------|-----------|
| **문서 처리** | LangChain Document Loader | PDF 사주 데이터 추출 및 청킹 |
| **벡터 데이터베이스** | Pinecone | 사주 지식 및 보험 상품 임베딩 저장 |
| **검색 엔진** | Meilisearch | 빠른 키워드 검색 (보험사, 상품명 등) |
| **LLM** | OpenAI GPT-4.1-nano | 사주 해석 및 자연어 상담 |
| **RAG 프레임워크** | LangChain | 지식 검색 및 응답 생성 파이프라인 |
| **API 서버** | FastAPI | RESTful API 및 실시간 서비스 |
| **임베딩 모델** | OpenAI text-embedding-3-large | 텍스트 벡터화 |

### 3-2. 데이터 파이프라인

```
[PDF 사주 서적] 
    ↓ (LangChain Document Loader)
[텍스트 추출 및 청킹]
    ↓ (OpenAI Embedding)
[벡터 임베딩 생성]
    ↓ (Pinecone)
[벡터 데이터베이스 저장]
    ↓ (RAG Pipeline)
[사용자 질의 시 관련 지식 검색]
    ↓ (GPT-4.1-nano)
[맞춤형 분석 및 추천 생성]
```

### 3-3. 시스템 구조도

```
[사용자 입력: 생년월일시]
         │
    [사주팔자 산출 엔진]
         │
    [음양오행 분석 모듈]
         │
    ┌────┴────┐
    │         │
[건강 리스크 예측]  [PDF 사주 지식 RAG 검색]
    │         │
    └────┬────┘
         │
   [보험 상품 매칭 AI]
         │
   [GPT-4.1 리포트 생성]
         │
  [맞춤형 추천 리포트]
```

---

## 4. 데이터 구조 설계

### 4-1. 사주 지식 데이터베이스 (PDF 벡터화)

```
saju_knowledge_base/
├── classical_texts/          # 고전 사주 서적
│   ├── myeongnidaejeon.pdf   # 명리대전
│   ├── sajujeongjeong.pdf    # 사주정전
│   └── ohaengnon.pdf         # 오행론
├── modern_analysis/          # 현대 사주 분석서
│   ├── health_correlation.pdf # 사주-건강 상관관계 연구
│   ├── accident_patterns.pdf  # 사고수 패턴 분석
│   └── body_parts_mapping.pdf # 신체 부위별 오행 매핑
├── medical_studies/          # 의학 연구 자료
│   ├── traditional_medicine.pdf # 한의학 체질론
│   ├── constitutional_types.pdf # 체질별 질병 패턴
│   └── preventive_care.pdf    # 예방 의학 가이드
└── insurance_knowledge/      # 보험 상품 지식
    ├── product_descriptions.pdf # 상품 설명서
    ├── coverage_details.pdf    # 보장 내용 상세
    └── claim_statistics.pdf    # 보험금 지급 통계
```

### 4-2. 보험 상품 데이터베이스

```json
{
  "insurance_products": [
    {
      "product_id": "LIFE_001",
      "company": "삼성생명",
      "product_name": "건강플러스보험",
      "coverage_types": ["질병", "상해", "수술"],
      "target_risks": ["심장질환", "간질환", "교통사고"],
      "ohang_compatibility": ["화", "목"],
      "body_parts": ["심장", "간", "전신"],
      "premium_range": [50000, 200000],
      "age_limit": [20, 65],
      "vector_embedding": [0.1, 0.2, ..., 0.9]
    }
  ]
}
```

### 4-3. 사주 분석 결과 스키마

```json
{
  "personal_info": {
    "birth_datetime": "1990-03-15T14:30:00",
    "gender": "M"
  },
  "saju_analysis": {
    "chungan_jiji": {
      "year": "경오",
      "month": "기묘",
      "day": "신해",
      "hour": "을미"
    },
    "ohang_balance": {
      "wood": 2,
      "fire": 3,
      "earth": 1,
      "metal": 1,
      "water": 1
    },
    "yongsin": "수",
    "weakness": ["토"],
    "strength": ["화"]
  },
  "health_prediction": {
    "accident_risk_score": 7.2,
    "vulnerable_organs": ["간", "심장"],
    "constitutional_type": "소양인",
    "health_warnings": [
      "간 기능 주의",
      "심혈관 질환 예방 필요",
      "교통사고 주의"
    ]
  },
  "insurance_recommendations": [
    {
      "product_id": "LIFE_001",
      "necessity_score": 8.5,
      "reasoning": "화 과다로 인한 심혈관 질환 위험이 높아 해당 보험 가입 강력 권장"
    }
  ]
}
```

---

## 5. 개발 로드맵

### Phase 1: 사주 분석 엔진 개발 (3주)
**주요 개발 항목:**
- 사주팔자 자동 산출 알고리즘 구현
- 음양오행 분석 로직 개발
- PDF 사주 서적 데이터 수집 및 전처리
- LangChain을 이용한 PDF 문서 벡터화
- Pinecone 벡터 데이터베이스 구축

**기술적 구현:**
```python
# 핵심 개발 파일
services/saju_analysis.py      # 사주 산출 및 분석
utils/pdf_processor.py         # PDF 처리 및 벡터화
utils/ohang_calculator.py      # 오행 균형 계산
config/saju_rules.py          # 사주 해석 규칙
```

### Phase 2: 건강 리스크 예측 모델 (2주)
**주요 개발 항목:**
- 오행별 신체 부위 매핑 시스템
- 사고수 예측 알고리즘
- 건강운 분석 모델
- 체질별 질병 예측 로직

**기술적 구현:**
```python
# 건강 예측 관련 파일
services/health_predictor.py   # 건강 리스크 예측
utils/risk_calculator.py      # 위험도 계산
models/health_schema.py       # 건강 데이터 모델
```

### Phase 3: RAG 기반 보험 추천 시스템 (3주)
**주요 개발 항목:**
- 보험 상품 데이터 수집 및 벡터화
- 리스크-보험 매칭 알고리즘
- Meilisearch 검색 엔진 연동
- 추천 점수 계산 시스템

**기술적 구현:**
```python
# 보험 추천 관련 파일
services/insurance_recommender.py  # 보험 추천 엔진
utils/product_matcher.py          # 상품 매칭 로직
utils/meilisearch_client.py       # 검색 엔진 연동
```

### Phase 4: LLM 상담 및 리포트 생성 (2주)
**주요 개발 항목:**
- GPT-4.1-nano 기반 상담 서비스
- 개인화된 리포트 생성 시스템
- 자연어 질의응답 처리
- 프롬프트 엔지니어링 최적화

**기술적 구현:**
```python
# LLM 상담 관련 파일
services/chatbot_service.py    # LLM 상담 서비스
utils/prompt_templates.py      # 프롬프트 템플릿
utils/report_generator.py      # 리포트 생성기
```

### Phase 5: FastAPI 백엔드 및 통합 (2주)
**주요 개발 항목:**
- RESTful API 엔드포인트 구현
- 전체 시스템 통합
- 성능 최적화
- 에러 핸들링 및 로깅

**API 엔드포인트 설계:**
```python
# API 엔드포인트
POST /api/v1/saju/analyze           # 사주 분석
GET  /api/v1/health/predict         # 건강 리스크 예측
GET  /api/v1/insurance/recommend    # 보험 추천
POST /api/v1/chat/consult           # AI 상담
GET  /api/v1/report/generate        # 리포트 생성
```

---

## 6. 확장 기능: 관상 분석 (Phase 6)

### 6-1. 한국인 안면 데이터 활용 계획

#### 관상학 데이터 수집
* **한국인 얼굴 빅데이터**: 연령대별, 성별 한국인 안면 특징 데이터
* **관상학 이론 체계화**: 전통 관상학 원리의 AI 모델 적용
* **얼굴-건강 상관관계**: 안면 특징과 건강 상태 간의 통계적 분석

#### 기술적 구현 방향
```python
# 관상 분석 확장 모듈
services/face_analysis.py         # 얼굴 분석 AI
utils/physiognomy_rules.py        # 관상학 규칙
models/face_health_correlation.py # 얼굴-건강 상관관계
```

#### 통합 분석 시스템
* **사주 + 관상 융합**: 사주팔자와 관상 정보를 결합한 종합 분석
* **정확도 향상**: 두 가지 전통 이론의 교차 검증으로 예측 정확도 개선
* **시각적 리포트**: 얼굴 분석 결과를 포함한 시각화된 리포트

---

## 7. 파일 구조

```
forsure_ai/
├── main.py                      # FastAPI 메인 실행 파일
├── services/                    # 핵심 서비스 모듈
│   ├── saju_analysis.py         # 사주팔자 분석 엔진
│   ├── health_predictor.py      # 건강 리스크 예측
│   ├── insurance_recommender.py # 보험 추천 시스템
│   ├── chatbot_service.py       # LLM 상담 서비스
│   └── face_analysis.py         # 관상 분석 (확장)
├── utils/                       # 유틸리티 함수
│   ├── pdf_processor.py         # PDF 문서 처리
│   ├── rag_utils.py             # RAG 관련 유틸리티
│   ├── ohang_calculator.py      # 오행 계산기
│   ├── risk_calculator.py       # 리스크 계산기
│   ├── meilisearch_client.py    # 검색 엔진 클라이언트
│   ├── prompt_templates.py      # LLM 프롬프트 템플릿
│   └── report_generator.py      # 리포트 생성기
├── config/                      # 설정 파일
│   ├── model_config.py          # AI 모델 설정
│   ├── saju_rules.py           # 사주 해석 규칙
│   ├── insurance_config.py      # 보험 상품 설정
│   └── settings.py             # 앱 전체 설정
├── models/                      # 데이터 모델
│   ├── saju_schema.py          # 사주 데이터 스키마
│   ├── health_schema.py        # 건강 데이터 스키마
│   ├── insurance_schema.py     # 보험 데이터 스키마
│   └── api_schema.py           # API 요청/응답 스키마
├── data/                        # 데이터 파일
│   ├── saju_knowledge/         # 사주 지식 PDF 파일
│   ├── insurance_products/     # 보험 상품 데이터
│   ├── health_correlation/     # 건강 상관관계 데이터
│   └── face_data/             # 관상 데이터 (확장)
├── api/                         # API 라우터
│   ├── saju_routes.py          # 사주 분석 API
│   ├── health_routes.py        # 건강 예측 API
│   ├── insurance_routes.py     # 보험 추천 API
│   ├── chat_routes.py          # 상담 API
│   └── dependencies.py        # 의존성 관리
├── tests/                       # 테스트 코드
│   ├── test_saju_analysis.py   # 사주 분석 테스트
│   ├── test_health_prediction.py # 건강 예측 테스트
│   ├── test_insurance_recommendation.py # 보험 추천 테스트
│   └── test_integration.py     # 통합 테스트
├── docs/                        # 문서
│   ├── api_documentation.md    # API 문서
│   ├── saju_theory.md         # 사주 이론 설명
│   └── system_architecture.md # 시스템 구조 문서
├── requirements.txt             # 의존성 패키지
├── .env                        # 환경 변수
├── docker-compose.yml          # Docker 설정
└── README.md                   # 프로젝트 설명
```

---

## 8. 비즈니스 모델 및 시장 전략

### 8-1. 타겟 시장
* **1차 타겟**: 30-50대 한국인 (사주에 관심 + 보험 필요성 인식)
* **2차 타겟**: 보험 설계사 및 재무 상담사 (B2B 툴 활용)
* **3차 타겟**: 글로벌 한류 관심층 (K-문화 + AI 기술)

### 8-2. 수익 모델
* **개인 구독**: 월 9,900원 (무제한 분석 및 상담)
* **프리미엄 리포트**: 건당 19,900원 (상세 분석서)
* **B2B 라이센스**: 보험사/설계사 대상 API 제공
* **데이터 수익**: 익명화된 사주-건강 상관관계 데이터 판매

### 8-3. FOR SURE만의 차별화 포인트
* **문화적 친숙함**: 한국인에게 익숙한 사주 문화 활용
* **과학적 접근**: AI와 빅데이터로 전통 이론을 현대적 해석
* **실용적 가치**: 단순 재미가 아닌 실제 보험 가입 도움
* **개인화 극대화**: 개인별 맞춤형 건강 리스크 예측

---

## 9. 기대 효과 및 성공 지표

### 9-1. 정량적 성과 지표
* **사용자 수**: 1년 내 10만 명 가입 목표
* **추천 정확도**: 85% 이상의 보험 추천 만족도
* **수익**: 1년 내 월 1억 원 매출 달성
* **파트너십**: 5개 이상 보험사와 제휴 체결

### 9-2. 정성적 가치
* **전통문화 현대화**: 사주학의 과학적 접근을 통한 문화 재해석
* **예방의학 기여**: 개인별 건강 리스크 사전 예측으로 질병 예방
* **보험 접근성**: 복잡한 보험 상품을 쉽게 이해하고 선택할 수 있는 도구
* **기술 혁신**: 전통 지식과 AI의 성공적 융합 사례

이 **FOR SURE** 프로젝트는 전통 사주학과 현대 AI 기술의 혁신적 결합을 통해 실용적 가치를 창출하는 독창적인 InsurTech 서비스가 될 것입니다.

---

## 10. FOR SURE 브랜딩 및 네이밍 전략

### 10-1. 브랜드 컨셉
* **FOR SURE**: "확실히", "틀림없이"라는 의미로 보험 추천의 신뢰성 강조
* **이중 의미**: 
  - **For Sure (확실함)**: AI 기반 정확한 예측과 추천
  - **Four Sure (네 가지 확신)**: 사주(운명) + 건강 + 보험 + AI 기술의 4가지 요소 결합
* **브랜드 슬로건**: "당신의 운명을 확실하게 보장하다"

### 10-2. 타겟 메시지
* **신뢰성**: "수천 년 검증된 사주학 + 최신 AI 기술"
* **개인화**: "당신만을 위한 맞춤형 보험 설계"
* **예측력**: "미래의 리스크를 미리 준비하세요"
* **편리함**: "복잡한 보험, FOR SURE가 쉽게 해결"

