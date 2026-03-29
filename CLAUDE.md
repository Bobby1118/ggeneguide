# SD건담 G제네레이션 이터널 — 공략본 프로젝트

## 프로젝트 개요
개인용 게임 공략 웹페이지. SD건담 G제네레이션 이터널(SD Gundam G Generation Eternal)의 종합 공략본.
구글 드라이브에 업로드하여 어디서든 열람 가능하도록 **단일 HTML 파일(index.html)**로 관리.

## 폴더 구조
```
지제네 공략/
├── index.html          ← 메인 공략본 (드라이브에서 이 파일을 열면 됨)
├── CLAUDE.md           ← 이 파일 (프로젝트 지침)
├── src/                ← 섹션별 개별 HTML (편집용 원본)
│   ├── styles.css      ← 공통 CSS (index.html에는 인라인으로 포함됨)
│   ├── 최신.html
│   ├── 육성.html
│   ├── 시리즈별.html
│   ├── 편성.html
│   ├── 전투.html
│   ├── 이터널로드.html
│   ├── 제네타워.html
│   ├── 맵이벤트.html
│   └── 참고.html
└── backup/             ← 원본 백업
    └── guide.html      ← 최초 단일 파일 버전
```

## 핵심 지침

### 파일 관계
- **index.html** = 최종 배포용. CSS/JS 전부 인라인. 외부 의존성 없음 (Google Fonts 제외)
- **src/*.html** = 섹션별 편집용 원본. 내용 수정 시 여기서 작업
- src 파일 수정 후 반드시 **index.html에 동기화** 해야 함 (수동 병합 필요)

### 콘텐츠 구조 (탭 9개)
1. **최신** — 1주년 업데이트, 로드맵, 가챠, 보상
2. **육성** — 기체 로드맵, SP/SSP화, 파일럿, ULT, 파밍, 자원관리
3. **시리즈별** — 시리즈별 SR/SSR/UR 추천 기체+파일럿
4. **편성** — 서포터, 태그, 역할별/콘텐츠별 편성, 고기방패
5. **전투** — 지원공격/방어, 텐션, 무기타입, 지형, 오토vs수동
6. **이터널로드** — 노멀~익스퍼트 공략, 유닛+파일럿 세팅, 육성 로드맵
7. **제네타워** — 층별 기믹 공략, 이스트/웨스트 타워
8. **맵이벤트** — 대규모 공략전 메커니즘, 편성전략, 초보자 가이드
9. **참고** — 공식사이트, 커뮤니티, 위키, 유튜브, 도구

### 디자인 규칙
- 다크 테마 (건담 메카닉 컨셉)
- CSS 변수: `--accent-red`, `--accent-gold`, `--accent-blue`, `--accent-green`, `--accent-purple`
- 카드 기반 레이아웃. 강조 박스: `.highlight`(금), `.warn`(빨강), `.tip`(파랑)
- 등급 뱃지: `.tier-badge.tier-ss`(빨강), `.tier-s`(금), `.tier-a`(파랑), `.tier-b`(초록)
- 접이식 상세: `<details>/<summary>` 사용
- 미니 네비: `.section-nav` + `jumpTo()` 함수
- 메인 탭: `.nav-btn` + `showTab()` 함수

### 수정 작업 시 주의사항
1. **index.html 수정 시** — CSS는 `<style>` 내부, JS는 `<script>` 내부에 있음. 외부 파일 참조 금지
2. **내용 추가 시** — 해당 탭 패널(`<div id="탭이름" class="tab-panel">`) 안에 삽입
3. **새 섹션 추가 시** — 섹션에 고유 ID 부여 + 해당 탭의 `.section-nav`에 점프 링크 추가
4. **등급 표시** — 캐릭터/기체 이름 옆에 반드시 SR/SSR/UR 등급 뱃지 표시
5. **구글 드라이브 호환** — 외부 CSS/JS 참조 불가. 반드시 인라인으로 유지
6. **한국어** — 모든 콘텐츠는 한국어로 작성

### 게임 정보 소스 (최신화 시 참고)

**한국어 (커뮤니티/뉴스)**
- 디시 마갤: https://gall.dcinside.com/mgallery/board/lists/?id=sdggeneeternal
  - 검색 키워드: "SP화 추천", "이터널로드 공략", "티어", "파일럿 추천", "편성"
- 나무위키: https://namu.wiki/w/SD건담%20지%20제네레이션%20이터널
- 게임플: https://www.gameple.co.kr (검색: "지제네 이터널")
- 게임뷰: https://www.gamevu.co.kr (검색: "G제네레이션 이터널")
- LD플레이어 블로그: https://kr.ldplayer.net/blog/ (검색: "g generation eternal")

**일본어 (가장 정확한 데이터)**
- Gamerch: https://gamerch.com/ggene-et/ — 유닛 DB, 파일럿/서포터 티어 최고
- Altema: https://altema.jp/ggeneeternal/ — 리세마라, 지형별 정리
- Game8: https://game8.jp/ggeneeternal — 종합 공략
- GameWith: https://gamewith.jp/ggeneeternal/ — 최신 업데이트 가장 빠름

**영어**
- LDShop: https://www.ldshop.gg/blog/ (검색: "sd gundam gget") — 이터널로드/타워 상세 공략
- Vortex Gaming: https://vortexgaming.io — SP추천, 티어표 분석
- PocketGamer: https://www.pocketgamer.com/sd-gundam-g-generation-eternal/ — 티어 리스트
- dotgg: https://dotgg.gg/sd-gundam-g-generation-eternal/ — 티어 리스트

**공식**
- 공식사이트(한국): https://gget.ggame.jp/kr/
- 공식사이트(영어): https://gget.ggame.jp/en/
- 공식 X(일본): https://x.com/ggene_eternal — 가장 빠른 업데이트 소식
- 공식 X(영어): https://x.com/ggene_eternalEN

### 최신화 작업 절차
유저가 "최신화 해줘" 또는 "업데이트 반영해줘" 요청 시:
1. 위 소스들에서 웹 검색으로 최신 정보 수집 (검색어: "G제네 이터널 [주제] 2026", "ggeneeternal [topic]")
2. 변경 사항 파악 (신규 참전작, 신규 UR, 밸런스 패치, 이벤트 등)
3. index.html의 해당 탭 패널 내용 직접 수정 (인라인)
4. 변경된 섹션의 src/*.html도 같이 업데이트
5. 날짜 기준 업데이트 (footer의 기준 날짜 변경)

### 현재 콘텐츠 기준일
- **2026년 3월 29일** 기준 (1주년 업데이트 반영)
- 1주년 로드맵 (2026.03.24 생방송 발표) 반영 완료
- 4월 이벤트 일정 반영 완료 (강적습격 스콜피오, 대규모 공략전, 프리미엄 유닛 조립 v2)
- 마스터리그 시즌 10 반영 완료

### 업데이트가 필요한 시점
- 신규 참전작 추가 (4월: 00후반+W EW, 4~5월: NT, 5~6월: 선더볼트/CROSS DIMENSION/STARGAZER)
- 신규 UR 유닛/파일럿 출시 시 → 시리즈별 탭, 육성 탭 업데이트
- 이터널로드/제네타워 신규 스테이지 추가 시 → 해당 탭 업데이트
- 밸런스 패치/SSP화 변경 시 → 육성 탭, 편성 탭 업데이트
- 서포터 신규 추가 시 → 편성 탭 서포터 티어표 업데이트
