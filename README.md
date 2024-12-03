# 무조건 신상 4죠

## 1️⃣ 프로젝트 개요
패션은 단순히 옷을 입는 것을 넘어, 개인의 정체성과 개성을 표현하는 중요한 수단입니다. 옷을 통해 자신의 가치관, 취향, 분위기를 드러낼 수 있으며, 이를 통해 다른 사람들에게 강렬한 첫인상을 남길 수 있습니다. 
하지만 여러가지 이유때문에 패션에 대해 무관심하거나, 어려워하는 사람들, 소위 “패알못”들은  끊임없이 빠르게 변화하는 트렌드에 대처하기 힘들어 패션테러를 일으켜 우리를 안타깝게 만듭니다. 
그래서 저희는  국내 대표 패션 플랫폼인 무신사에서 제공해 주는 데이터를 바탕으로 사용자의 취향과 실질적인 니즈에 맞춘 가격, 온도 및 계절, 리뷰 기반 추천 서비스를 제공하는 챗봇을 기획했습니다.

---

<br><br>
## 2️⃣ TEAM BYTEBITE (사일런스)

| 이름  | 역할      | 업무         |
|-----|---------|------------|
| 박지호 | 팀장      | 문서화, PT 및 발표  |
| 정재석 | 서기     | Streamlit 인터페이스 디자인  |
| 김건태 | 팀원 | 데이터 전처리 |
| 이규혁 | 팀원      | 웹 크롤링 |
| 김민철 | 팀원      |  API 및 모델 학습, 서비스 기능 테스트 |

<br><br>

## 3️⃣ 프로젝트 일정
| 날짜            | 업무                 |
|---------------|--------------------|
| 11.22 ~ 11.24 | 아이디어 회의          |
| 11.25 | 프로젝트 주제 결정 및 역할 분담          |
| 11.25 ~ 11.28 | 각자 역할에 맞는 작업 수행 |
| 11.29 | 여러 이슈 수집 및 해결방안 모색 |
| 11.30 ~ 12.02 | 데이터 전처리 관련 추가 업무 |
| 12.03 | 추가기능 구현 및 프론트엔드 수정 |
| 12.04 | 프로젝트 완성 및 발표 |

<br><br>

## 4️⃣ 기능 소개
```
여러가지 카테고리를 통해 무신사에서 크롤링 한 데이터를 바탕으로 사용자가 원하는
패션아이템(이미지, url, 리뷰요약)을 추천합니다
- 월별
- 온도별
- 가격별
- 키워드별
- 패션 아이템 카테고리별
간단한 인터페이스로 누구나 쉽게 접근 가능
사용자가 선택한 조건에 따라 정확한 추천과 빠른 결과 제공
추천 항목에 대한 리뷰 요약과 구매 링크 제공으로 사용자 편의성 극대화
```
<br><br>

## 5️⃣ 사용 기술 
🖥️ 프론트엔드
- Streamlit
- HTML/CSS

📀 백엔드
- FastAPI
- LangChain

📊 데이터 검색 및 모델
- RAG
- ko-sbert-nli
- FAISS
- Prompt Engineering

💾 데이터 관리
- FAISS 인덱스
- dotenv 라이브러리

🌐 웹 크롤링 및 API
- requests 라이브러리
- GoogleGenerativeAI

🔠 언어 및 환경
- Python

💬 협업도구
- GitHub
- Slack
- Notion

## 6️⃣ 서비스 아키텍쳐
- 🏗️ 서비스 아키텍쳐
<br><br>
![서비스아키텍쳐](https://github.com/user-attachments/assets/29b3800c-2af4-4255-aea2-86f131387b58)
<br><br>
- 🖼️ 와이어프레임
<br><br>
![와이어프레임](https://github.com/user-attachments/assets/8d2f3cf4-2469-4346-be27-60bea26ee6cd)

<br><br>

## 7️⃣ 프로젝트 파일 구조

```
📦
├─ .streamlit
 └─ config.toml            # 설정 파일 (모델 경로 및 환경 변수 등)
├─ data
 └─ data_sample.csv        # 데이터 샘플 (CSV 형식)
├─ faiss_index
 └─ index.faiss            # FAISS 인덱스 파일 (벡터 검색용)
 └─ index.pkl              # 추가 데이터 또는 인덱스 객체 (피클 형식)
├── app.py                 # Streamlit 기반의 사용자 인터페이스를 제공하는 파일
├── api.py                 # FastAPI 서버와 RAG 모델 연결을 처리하는 파일
├── rag.py                 # RAG(검색 및 생성) 모델 로직 정의
├── README.md              # 프로젝트 개요 및 설명 문서
└── rag_CVS_전처리_디버그.ipynb  # 데이터 전처리 및 디버깅 노트북
```
## 8️⃣ 트러블 슈팅
### ISS-001
**문제 해결을 위한 접근: GPT API 키 작동 불안정 및 무료 대체 옵션으로 구글 Gemini 사용**

현재 사용 중인 GPT API 키가 불안정하여 갑작스럽게 작동하지 않는 상황이 발생할 수 있습니다. 또한, 캠프 교육이 종료되면 GPT API를 계속 사용할 수 없으므로, 이를 대체할 수 있는 방법으로 구글의 **Gemini** 서비스를 사용하는 방향으로 전환하기로 하였습니다. 구글 Gemini는 무료로 사용할 수 있는 AI 모델로, GPT와 유사한 기능을 제공하므로 향후 사용에 있어 문제를 최소화할 수 있습니다.

**1. GPT API 작동 불안정 문제**
- **원인**: 캠프에서 제공된 GPT API 키가 제한적이거나, 캠프 종료 후 유효하지 않게 될 가능성이 존재합니다.
- **해결 방법**: 캠프 종료 전 후 GPT API 키의 작동 여부를 확인하고, 필요한 경우 대체 API 키를 확보하거나 사용을 중단할 준비가 필요합니다.

**2. 구글 Gemini 대체 방법**
- **구글 Gemini 소개**: 구글의 Gemini는 최근 공개된 무료 AI 모델로, GPT와 유사한 기능을 제공하며 텍스트 생성, 요약, 번역 등의 다양한 작업을 수행할 수 있습니다. 또한, 구글 계정만 있으면 바로 사용할 수 있어 접근성이 뛰어납니다.
- **사용 방법**:
  1. 구글 계정으로 [Gemini 웹사이트](https://gemini.google.com/)에 로그인합니다.
  2. 제공된 인터페이스를 통해 다양한 텍스트 생성 작업을 수행할 수 있습니다.
  3. 무료 사용이 가능하며, 구체적인 API 사용 방법은 구글 개발자 문서에서 확인할 수 있습니다.

**3. 향후 계획**
- **GPT API 대체**: 캠프 종료 후 GPT API를 사용하지 못하는 경우, 구글 Gemini를 주요 대체 서비스로 활용하며, Gemini의 API와 관련된 추가적인 문서를 참고하여 API 연동 방법을 익힐 예정입니다.
- **기타 대체 서비스 검토**: 만약 Gemini 외에도 다른 무료 또는 저비용 대체 서비스가 필요한 경우, OpenAI의 GPT-3 API 또는 다른 AI 모델들의 무료 사용 정책을 살펴보겠습니다.

**결론**
현재 GPT API 키의 불안정성 문제를 해결하기 위해 구글 Gemini를 사용하자는 방향으로 전환하였으며, 이를 통해 교육 이후에도 문제 없이 AI 기능을 활용할 수 있을 것입니다. 추가적인 문제가 발생할 경우, 다른 대체 서비스와의 통합 방법을 빠르게 적용하여 유연하게 대응할 계획입니다.






-----------
### ISS-002
**문제 해결: LLM 모델 변경 시 임베딩 최적화 및 중간 지점 확보**

LLM(대형 언어 모델)을 교체하는 경우, 각 모델이 사용하는 임베딩 방식이 다르기 때문에 임베딩도 새로 조정해야 할 필요가 있습니다. GPT와 구글의 모델은 각기 다른 임베딩 방법을 사용하고 있으며, 이를 매번 바꿔야 한다면 처리 과정이 길어지고 비효율적일 수 있습니다. 따라서 LLM 모델을 변경하더라도 두 모델 간의 격차가 최소화될 수 있도록 중간 지점을 확보하는 방식으로 접근했습니다.

**1. LLM 모델과 임베딩의 최적화**
- **문제**: GPT와 구글 각 모델은 고유한 방식으로 텍스트를 임베딩합니다. 이로 인해 모델을 교체할 때마다 임베딩 방식을 새로 맞추어야 한다는 문제점이 발생합니다. 만약 이를 그대로 두면, 모델 간에 성능 차이가 커질 수 있습니다.
- **해결 방법**: 각 모델에 최적화된 임베딩을 사용하는 대신, **jhgan/ko-sbert-nli** 모델을 로컬에서 사용하여, 두 모델 간의 임베딩 격차를 줄이는 방법을 적용했습니다. 이 모델은 텍스트를 임베딩하는 데 있어 다양한 LLM 모델에 대해 중립적인 역할을 할 수 있습니다.

**2. jhgan/ko-sbert-nli 사용 이유**
- **모델 선택**: **jhgan/ko-sbert-nli**는 Hugging Face에서 제공하는 한국어 BERT 기반의 모델로, 자연어 추론(NLI) 작업을 위한 임베딩을 지원합니다. 이 모델은 다양한 LLM에서 발생할 수 있는 임베딩 차이를 최소화하는 데 유용하며, 한국어 텍스트에 대해 최적화된 성능을 보입니다.
- **로컬 실행**: 이 모델을 로컬로 실행함으로써 LLM의 변경이 있을 때마다 임베딩 방식을 다시 조정할 필요 없이, 공통된 임베딩 공간을 사용할 수 있습니다. 이렇게 하면 LLM 모델을 바꿔도 두 모델 간의 성능 격차가 크게 벌어지지 않도록 중간 지점을 제공할 수 있습니다.

**3. 과정**
- **로컬 설치**: `jhgan/ko-sbert-nli` 모델을 Hugging Face에서 다운로드하여 로컬 환경에 설치하고, 로컬에서 직접 임베딩을 처리하도록 설정합니다.
- **통합**: 임베딩된 텍스트는 이후 LLM 모델로 전달되어 처리되며, 각 LLM 모델에 최적화된 방식으로 동작합니다. 이 때, 임베딩 단계에서 발생할 수 있는 불필요한 변환을 줄여 성능의 일관성을 유지할 수 있습니다.

**4. 향후 계획**
- **LLM 모델 교체 시 효율성**: 향후 다른 LLM 모델로 교체가 필요할 경우, 이 임베딩 방식을 유지함으로써 중간 지점을 최소화하고, 처리 시간을 단축할 수 있습니다. 또한, 새로운 LLM이 도입될 때마다 임베딩 최적화 작업을 반복하는 번거로움을 피할 수 있습니다.
- **기타 대체 모델**: 만약 `ko-sbert-nli` 모델의 성능이 특정 상황에서 부족할 경우, 다른 고성능 임베딩 모델을 고려하여 적절히 대체할 수 있습니다.

**결론**
LLM 모델을 교체할 때마다 임베딩 방식도 함께 변경해야 하는 문제를 해결하기 위해 **jhgan/ko-sbert-nli** 모델을 로컬에서 사용하여 중간 지점을 설정하였습니다. 이 방법을 통해 모델 변경에 따른 성능 차이를 최소화하고, 공정 효율성을 크게 향상시킬 수 있었습니다.

-----
### ISS-003
**문제 해결: RAG 코드의 FAISS 벡터 저장 및 로드 최적화**

RAG(Retrieval-Augmented Generation) 모델을 사용할 때, 매번 리트리버 데이터를 새로 생성하는 것은 시간이 많이 소요되고 비효율적입니다. 이를 방지하기 위해 생성된 데이터를 로컬에 저장하고, 이를 불러오는 방식으로 최적화하였습니다. 또한, 코드의 가독성을 높이고 복잡성을 줄이며, 속도를 향상시키기 위해 RAG 코드 파일을 두 부분으로 나누어 관리하게 되었습니다.

**1. 문제: 매번 리트리버 데이터가 생성되는 문제**
- **원인**: FAISS 벡터 스토어는 매번 새로운 문서 데이터가 주어질 때마다 벡터를 생성하게 되므로, 반복적인 검색 작업에서 불필요하게 시간이 소요됩니다.
- **해결 방법**: 벡터화된 데이터를 로컬에 저장하여, 다음 작업에서 다시 생성할 필요 없이 이미 생성된 벡터 인덱스를 불러와 사용할 수 있도록 개선했습니다. 이렇게 하면, 벡터화 과정의 중복을 방지하고 전체 처리 속도를 크게 향상시킬 수 있습니다.

**2. 개선된 코드 흐름**
- **FAISS 벡터 스토어 생성**:  
  먼저, `splits_RCTS`라는 문서 데이터가 주어졌을 때, 이를 벡터화하여 FAISS 인덱스를 생성합니다.

  ```python
  # FAISS VectorStore 생성
  faiss_vectorstore = FAISS.from_documents(documents=splits_RCTS, embedding=embeddings)
  ```

- **로컬에 저장된 FAISS 인덱스 불러오기**:  
  이미 저장된 FAISS 인덱스를 로컬에서 불러옵니다. 이 과정에서 `allow_dangerous_deserialization=True`로 설정하여 보안 상 문제가 없을 경우, 로컬에서 안전하게 불러올 수 있도록 합니다.

  ```python
  # 로컬에 저장된 FAISS 인덱스를 불러오기 (보안 상 신뢰할 수 있으면 True로 설정)
  loaded_faiss = FAISS.load_local("faiss_index", embeddings, allow_dangerous_deserialization=True)
  ```

- **검색기 설정**:  
  불러온 FAISS 인덱스를 사용하여 검색기를 설정합니다. 이 때, 가장 유사한 3개의 문서를 검색하도록 설정했습니다.

  ```python
  # 검색기 설정 (가장 유사한 3개의 문서를 검색)
  faiss_retriever = loaded_faiss.as_retriever(search_kwargs={"k": 3})
  ```

**3. 코드 분할로 인한 최적화**
- **문제**: 하나의 파일에 모든 로직을 작성할 경우 코드가 복잡해지고, 유지보수가 어려워질 수 있습니다.
- **해결 방법**: 코드를 두 파일로 나누어 관리함으로써 가독성을 높이고, 코드 변경 시 다른 부분에 미치는 영향을 최소화했습니다. 
  - `rag_01.py`에서는 FAISS 벡터 스토어를 생성하고 이를 로컬에 저장하는 부분을 담당합니다.
  - `rag_02.py`에서는 로컬에 저장된 FAISS 인덱스를 불러오고, 검색기를 설정하는 부분을 담당합니다.

  이를 통해 각 코드 파일의 역할을 명확히 하여 관리하기 쉬운 구조로 변경했습니다.

**4. 성능 최적화**
- **속도 향상**: 벡터 인덱스를 매번 새로 생성하지 않고, 로컬에 저장된 인덱스를 불러옴으로써, 매번 FAISS 벡터 스토어를 생성하는 시간을 절약할 수 있습니다.
- **효율성**: 데이터가 많아질수록 이 방식이 더욱 효과적이며, 실시간 검색에서 성능을 크게 향상시킬 수 있습니다.

**5. 향후 계획**
- **백업 및 복원**: 로컬에 저장된 FAISS 인덱스를 백업하여, 서버 장애 등 예기치 못한 상황에서 복원할 수 있는 시스템을 구축할 예정입니다.
- **다양한 LLM 모델 지원**: 다른 LLM 모델을 추가할 때, 각 모델에 최적화된 벡터 스토어와 검색기 설정을 별도로 관리하여 유연성을 높일 수 있습니다.

**결론**
RAG 모델의 성능 최적화를 위해 FAISS 벡터 스토어를 로컬에 저장하고, 이를 불러오는 방식으로 리트리버 데이터를 처리했습니다. 또한, 코드의 가독성을 높이고 복잡성을 줄이기 위해 코드를 두 부분으로 나누어 관리했습니다. 이러한 최적화 작업을 통해 검색 속도를 개선하고, 전체적인 성능을 향상시킬 수 있었습니다.



-------------------------
### ISS-004
**문제 해결: Streamlit과 RAG 파일의 API 통신 최적화 및 실시간 개발 동기화**

팀원들이 각기 다른 작업을 진행하는 가운데, **Streamlit**과 **RAG 파일**이 서로 API로 긴밀하게 소통해야 하는 상황에서, **Git을 통한 동기화**가 속도 문제로 어려움을 겪었습니다. Git을 통한 코드 동기화는 효율적이지만, 팀원들이 각각의 작업 내용을 실시간으로 반영하고 확인하는 데 시간이 많이 소요되었습니다. 이를 해결하기 위해 **ngrok**을 활용하여 로컬 네트워크를 외부와 연결하고, 실시간으로 개발 상황을 반영하는 방법을 적용하였습니다.

**1. 문제: Git을 통한 동기화의 속도 이슈**
- **원인**: Git을 사용하여 코드와 성과물을 동기화하는 과정에서, 파일 크기나 커밋 수가 많아지면 동기화 속도가 느려져 실시간으로 진행 상황을 확인하거나 반영하는 데 시간이 많이 소요되었습니다. 특히, **Streamlit과 RAG 파일** 간의 API 통신을 실시간으로 조정해야 하는 상황에서 이 문제가 두드러졌습니다.
- **해결 방법**: **ngrok**을 사용하여 로컬 개발 환경을 외부에서 접근 가능하도록 설정하고, 팀원들이 각자의 작업을 실시간으로 반영할 수 있는 시스템을 구축했습니다. 이를 통해 작업 중인 애플리케이션을 즉시 외부와 공유하고 피드백을 받을 수 있게 되었습니다.

**2. ngrok을 통한 실시간 연결**
- **ngrok 사용 이유**: `ngrok`은 로컬 서버를 외부 네트워크에 안전하게 노출시키는 도구로, 개발 중인 애플리케이션을 즉시 외부에서 접근 가능하게 만들어 줍니다. 이를 통해 각 팀원은 Git의 동기화 없이 **Streamlit 앱**과 **RAG 모델**의 개발 상황을 실시간으로 확인하고 수정할 수 있었습니다.
  
- **설정 과정**:
  1. 로컬에서 실행 중인 **Streamlit 서버**가 `http://localhost:8000`에서 동작하도록 설정합니다.
  2. `ngrok`을 사용하여 해당 로컬 서버를 외부에서 접근할 수 있는 URL로 변환합니다.
     ```bash
     ngrok http 8000
     ```
  3. ngrok을 실행하면, 외부에서 접속 가능한 URL을 제공합니다. 예를 들어:
     ```
     https://secure-ant-instantly.ngrok-free.app
     ```
  4. 이 URL을 통해 팀원들은 로컬 서버를 외부에서 바로 확인하고, 서로 작업 중인 결과물을 실시간으로 반영할 수 있습니다.

- **실시간 소통**: ngrok을 사용함으로써 팀원들이 각자 작업하는 동안, **Streamlit**과 **RAG** 간의 실시간 API 통신과 결과를 바로바로 확인할 수 있게 되었고, 각자의 작업을 즉시 반영하고 테스트할 수 있었습니다.

**3. Git과 ngrok의 협업**
- **효율적인 협업**: Git을 사용하여 기본적인 코드 관리와 버전 관리를 지속하면서, ngrok을 통해 실시간으로 진행 중인 변경 사항을 팀원들과 공유했습니다. 각 팀원이 로컬에서 작업한 내용을 ngrok을 통해 바로 외부에 노출시켜, 서로의 작업을 확인하고 즉시 피드백을 주고받을 수 있었습니다.
- **속도 개선**: Git의 동기화 속도가 느려질 수 있는 상황에서도, ngrok을 활용한 실시간 공유 덕분에 팀원들이 서로의 작업을 실시간으로 반영하고, 개발 진행 상황을 동기화할 수 있었습니다.

**4. 향후 계획**
- **지속적인 실시간 피드백 시스템 구축**: ngrok을 활용한 실시간 피드백 시스템을 계속해서 활용하고, 필요시에는 **CI/CD 파이프라인**과 결합하여 코드 변경 사항을 실시간으로 배포하고 테스트할 수 있는 시스템을 더욱 강화할 예정입니다.
- **자동화 도입**: ngrok과 Git을 활용한 실시간 동기화 시스템을 자동화하여, 팀원들이 작업한 내용을 실시간으로 반영하고 Git으로 동기화하는 과정을 최소화할 수 있도록 할 것입니다.

**결론**
`ngrok`을 활용하여 로컬 개발 서버를 외부와 실시간으로 연결하고, 팀원들이 각자 작업하는 부분을 즉시 반영하여 개발 상황을 실시간으로 소통할 수 있게 되었습니다. 이를 통해 Git을 통한 동기화에서 발생할 수 있는 속도 문제를 해결하고, 실시간 개발 피드백을 통해 협업 효율성을 크게 향상시킬 수 있었습니다.


