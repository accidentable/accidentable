# accidentable

컴퓨터공학과 4학년입니다. 해커톤에 14회 참가하면서 아이디어를 빠르게 서비스로 만들어 사람들 앞에 내놓는 일을 반복해 왔고, 그 과정에서 AI 코딩 도구와 함께 일하는 방식에 익숙해졌습니다. 아래 세 프로젝트는 그 경험이 어떻게 이어졌는지를 순서대로 보여 줍니다. 이슈를 보고 두 시간 만에 만들어 실제 사용자와 언론 반응을 겪은 서비스, 그렇게 쌓인 열네 번의 경험을 제 판단으로 다시 정리하려고 만든 위키, 그리고 어떤 정보를 넘기고 어떤 정보는 직접 가지고 있어야 하는지를 고민한 신원정보 프로토타입입니다.

## 대표 프로젝트

### 1. 타코 트럼프 (타코알리미): [accidentable/tacotrump](https://github.com/accidentable/tacotrump)

트럼프 행정부의 강경책이 시장 압박 때문에 물러설 가능성을 시장 지표 여섯 개로 0~6점과 4단계 레벨로 보여 주던 웹 서비스입니다. 2026년 3월, 뉴스에서 본 "TACO" 이슈를 AI 코딩 도구로 두 시간 만에 혼자 만들어 Vercel에 올렸고, 운영하던 학회 SNS에 공유한 것이 여러 커뮤니티로 퍼져 KPI뉴스에 소개됐습니다([기사](https://m.kpinews.kr/newsView/1065595079655327), 2026-04-03). 이후 엿새 동안 43번 커밋하며 레벨이 바뀔 때만 오는 푸시 알림, 다국어, 공개 API를 붙였습니다. 유료 마케팅 없이 3주 동안 방문자 56,253명, 페이지뷰 104,037을 기록한 뒤 운영을 마쳤고, 5월에는 서버리스를 직접 다뤄 보려고 AWS Lambda로 옮기는 실험을 했습니다.

지표 구성과 알림 정책 같은 판단은 제가 했고 코드 대부분은 AI와 같이 썼습니다. 빠르게 만든 대가로 두 벌의 백엔드가 어긋난 채 배포된 것까지 README에 그대로 적어 두었습니다.

- React · Vite · TypeScript / Python 서버리스(Vercel) / Redis / Web Push

### 2. My_WIKI: [accidentable/My_WIKI](https://github.com/accidentable/My_WIKI) · [사이트](https://hackathon-wiki-rho.vercel.app/)

해커톤 14회의 README, 기획서, 대화 기록을 원자료로 넣으면 LLM이 규칙에 따라 위키로 정리하고, 그 결과를 면접 준비 사이트로 만드는 저장소입니다. Karpathy의 LLM Knowledge Base 틀을 가져왔지만, 만든 이유는 구현을 LLM에 지나치게 기대던 습관을 떨쳐내고 LLM이 대신 짜고 넘어간 것을 제 말로 설명할 수 있게 되는 데 있습니다. 프로젝트 문서 14개, 개념 문서 49개, 교훈 문서 4개가 있습니다. 원자료는 사람만 쓰고 LLM은 읽기만 하며, 원자료의 확신 수준을 위키가 높이지 못하게 하는 규칙과 그것을 확인하는 두 층 점검(결정적 검사 + LLM 판단 검사)을 두었습니다.

타코 트럼프 코드를 넣었을 때 두 백엔드의 점수 로직이 어긋난 것과 크론 설정이 주석과 다른 것이 정리 과정에서 드러났습니다. 다음 프로젝트에서 무엇을 조심할지가 이런 식으로 쌓입니다.

- Markdown 위키 / Python 점검·빌드 스크립트 / GitHub Actions / Claude Code · Codex 에이전트 규칙

### 3. SabonX: [accidentable/Trust404_th](https://github.com/accidentable/Trust404_th) · [데모](https://211-233-200-43.nip.io/)

신분증 사본을 사장님에게 넘기지 않고, DID·VC로 필요한 정보만 증명해 월급 확인을 잇는 해커톤 프로토타입입니다(TRUST404 Track 02). 발급기관이 서명한 자격증명에서 이름만 선택 공개하고, 주민등록번호는 수신자만 풀 수 있게 봉인하며, 정보가 바뀌어 폐기된 증명은 서명이 유효해도 온체인 폐기 기록을 조회해 거절합니다. 실제 기관 연동과 법적 효력은 범위 밖이고, 그 한계를 README에 적었습니다.

이 프로젝트를 하면서 AI 시대에 프로젝트가 많이 만들어질수록 어떤 정보를 제공하고 어떤 정보는 직접 가지고 있어야 하는지가 중요해지겠다고 느꼈습니다. 이 생각은 개인적인 회고이고, 구현은 신원정보 보호에 한정됩니다.

- TypeScript · React / Node.js · Express / SD-JWT VC · JWE / Solidity · Sepolia
- `[주의: 현재 해커톤 심사 중. 저장소를 수정하지 않습니다.]`

## 분야별 프로젝트

대표 프로젝트 셋을 포함해 해커톤과 개인 프로젝트를 [My_WIKI 사이트](https://hackathon-wiki-rho.vercel.app/)와 같은 네 분야로 나누면 이렇습니다. 저장소가 공개된 것만 링크했고, 나머지는 비공개이거나 코드가 로컬에만 있습니다.

**블록체인 · 신원**
- SabonX: DID·VC로 신분증 사본 없이 급여 확인을 잇는 프로토타입 (TRUST404 Track 02, 2026-09) · [Trust404_th](https://github.com/accidentable/Trust404_th)
- Memory Market: AI와 일한 대화 기록을 Sui에서 기간 한정으로 파는 시장. Claude Code 플러그인 + Move 컨트랙트 (Blockthon 2026) · 저장소 비공개
- Ko-Walk: 상장기업 본사를 걸어서 방문해 AR로 주식 토큰을 모으는 앱 기획 (하나금융 AR 해커톤) · 비공개
- AI TrustSeal: AI 개인정보 처리 로그를 체인에 앵커링하고 데이터 영수증을 주는 SDK 기획 · 저장소 없음
- Aptos 시각화, Mantle, NFT 민팅 실험: 2025년 블록체인 학습·해커톤 결과물 · [Aptos_visualization](https://github.com/accidentable/Aptos_visualization) · [One-Percent-Mantle](https://github.com/accidentable/One-Percent-Mantle)

**LLM · 에이전트**
- My_WIKI: 해커톤 경험을 LLM이 규칙에 따라 위키로 정리하고 면접 노트로 만드는 저장소 · [My_WIKI](https://github.com/accidentable/My_WIKI)
- 구독컷: 해외 구독·클라우드 이상청구의 첫 72시간 대응을 돕는 에이전트 (2026 금융 AI Challenge) · [Finance_AI](https://github.com/accidentable/Finance_AI)
- 컴플라이언스렌즈: 금융 광고 콘텐츠를 게시 전 자동 사전심의하는 준법 에이전트 (JB금융 Fin:AI Challenge) · [my-hack](https://github.com/accidentable/my-hack)
- 공시 Agent: DART 공시 4,204건을 구조화하고 근거 검증을 거쳐 접수번호 붙은 답을 내는 에이전트 (미래에셋증권 AI Festival 2026) · 팀 저장소 비공개
- FRAME: 채용 영상에서 기준별 지원자 발언을 찾아 원본 구간으로 연결하는 도구 (원티드 AI Championship 2026) · 팀 저장소 비공개
- SNS 신메뉴 AI 컨설팅: SNS 유행 신메뉴를 대구 개인 카페의 재료·예산에 맞춰 시험 판매로 잇는 프로토타입 (2026 AI Blockchain Challenge in Daegu) · 로컬만
- FRED 채팅: 원하는 FRED 경제 지표를 채팅으로 한눈에 보는 도구 · [FRED-](https://github.com/accidentable/FRED-)

**데이터 분석 · 금융**
- 유행 리스크 조기경보: 검색 트렌드와 카드 결제 데이터로 유행 수명을 재고 가맹점 대출·창업 경보를 제안 (BC카드 빅데이터 해커톤 2026) · 분석 스크립트 로컬만
- 끝물레이더: 뉴스 공급 신호로 디저트 유행 단계를 판정하는 포화 경보 기획 (2026 뉴스빅데이터 해커톤) · 저장소 없음
- MA5 돌파 역발상 봇: 한국투자증권 OpenAPI 실전 계좌로 도는 자동매매 봇 (2026-09 투자대회) · 로컬만
- K-리그 AI 해커톤 결과물 · [K-league-Hackathon](https://github.com/accidentable/K-league-Hackathon)

**웹 · 앱**
- 타코 트럼프: 시장 지표 6개로 트럼프 정책 번복 가능성을 점수화하던 웹 서비스 (2026-03, 종료) · [tacotrump](https://github.com/accidentable/tacotrump)
- Smash Lab: 사진 속 물건을 브라우저에서 잘라내 소재별로 부수는 모바일 웹 3D 데모 (원티드 해커톤 2026) · 로컬만

## 개발을 보는 눈

세 프로젝트를 지나며 생각이 이렇게 옮겨 왔습니다.

타코 트럼프에서는 코드를 빨리 뽑아내는 일의 값이 내려갔다는 것을 체감했습니다. 그래서 남는 일은 어떤 이슈를 잡아 어떤 형태로 만들어 누구에게 보여 줄지 정하는 일, 그리고 나온 결과를 검토하고 운영하는 일이라고 생각하게 됐습니다.

빨리 만든 것이 쌓이자, 정작 "왜 그렇게 만들었는지"를 제 말로 설명하지 못하는 부분이 보였습니다. My_WIKI는 그 부분을 원자료와 제 판단, LLM의 해석으로 나누어 되짚는 시도입니다. 원자료가 조심스럽게 쓴 것을 위키가 확정적으로 바꾸는 일이 가장 흔한 왜곡이라는 것을 여기서 배웠습니다.

SabonX에서는 만드는 속도가 빨라질수록 무엇을 넘기고 무엇을 남길지 정하는 경계가 중요해진다고 느꼈습니다. 개인정보뿐 아니라 생각까지 AI에 전달하는 시대라, 이 경계를 설계에 넣는 일을 앞으로도 계속 붙들고 있으려 합니다.

AI로 짠 코드는 숨기지 않고, 제가 결정한 것과 맡긴 것, 검토한 것을 나누어 적습니다.

## 연락처

- GitHub: [@accidentable](https://github.com/accidentable)
