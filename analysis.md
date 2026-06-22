# Supabase 기반 사용자 게시판 및 관리자/광고주 대시보드 구축 — 제안 분석 로그

> 생성일: 2026-06-22
> 공고 URL: https://www.wishket.com/project/156240/

## 1. 공고 파싱 결과

```yaml
job:
  title: "Supabase 기반 사용자 게시판 및 관리자/광고주 대시보드 구축"
  category: "개발 · 웹 · 기타(IT 서비스 구축)"
  budget_range: "15,000,000원"
  duration: "60일"
  tech_stack: [Supabase, PostgreSQL, Auth, Storage, Edge Functions, Next.js, React, Flutter WebView]
  description: "앱 내 자체 광고 시스템 + 사용자 커뮤니티 게시판 통합 구축. 상용 UI 템플릿 활용 어드민/광고주 대시보드 + Flutter 웹뷰 연동 사용자 게시판 프론트엔드."
  requirements:
    - "4단계 권한(관리자/광고주/유료/무료) 관리 및 승인·반려, 불량 유저 제재"
    - "게시글(광고/공지/일반) HTML 에디터, 복수 이미지 업로드, 예약발행, 신고 처리"
    - "광고 캠페인 CRUD(기간/플랜/타겟/자동 만료), 5종 소재(피드 카드/전면 팝업/하단 배너/바텀시트/하단 슬라이드)"
    - "광고 클릭 리다이렉트 라우팅, 노출/클릭/CTR 집계 그래프 + CSV"
    - "광고주 로그인 및 본인 캠페인 통계 + CSV"
    - "사용자 게시판(웹뷰): 익명 닉네임 글(500자/이미지 3장), 댓글·대댓글, 신고, 스포일러, 투표글, 좋아요·스크랩"
    - "클라이언트 단 이미지 리사이징·압축, AI 번역(캐시/재시도/원문보기, DB 미저장), SEO(slug/OG/JSON-LD)"
    - "트래킹 배치 최적화(Supabase 부하 방지), AI 번역 API Key 프록시(Edge Functions)"
    - "Flutter 앱 웹뷰(WebView) 브릿지 연동"
  client_questions: []
  deadline: "2026-06-29"
  job_post_url: "https://www.wishket.com/project/156240/"
  urls: []
  images: []
```

부가 정보: 지원자 10명, 예상 시작일 "계약 체결 후 즉시", 신규 프로젝트, 협업 인력 내부 디자이너 1인·기획자 1인, 클라이언트 측 PM·Flutter 앱 개발자(웹뷰 브릿지 협업).

## 2. URL/이미지 분석

- 공고 본문에 외부 참고 URL 없음.
- "참고 자료 1"은 "미팅 예정 파트너에게만 공개"되어 접근 불가.
- 첨부 이미지 없음.
- 판정: **참고 URL/이미지 없음** — 텍스트 요구사항 기반으로 제안서 작성.

## 3. 실현 가능성 분석 (내부용)

- 프로젝트 유형: 풀스택 웹앱(Supabase BE + Next.js FE) + 상용 어드민 템플릿 → "가능(+10% 버퍼)"
- 강점 영역: FE 중심(사용자 게시판 + 어드민 커스터마이징)이 핵심, 어드민은 상용 템플릿으로 디자인 공수 절감.
- 기본 공수(AI 반영 후 최종): 65 M/D
  - 기획/설계 6, 디자인 7, 사용자 게시판 FE 14, 어드민·광고주 FE 12, 백엔드(Supabase·Edge·트래킹·웹뷰) 20, QA/배포 6
- 달력 변환: 65 M/D ÷ 다수 인력(약 1.5인 병행) ≈ 43 영업일 ≈ 60 달력일 이내 수용 가능.
- 클라이언트 예상 기간(60일) vs 산정: **60일 내 수용 가능** — 다수 인력 투입으로 단계 병행하여 기간 유지.
- 판정: **추천** — 기간 유지, 금액 가격경쟁력 확보(85%).
- 리스크: 광고 트래킹 DB 부하(배치 인서트·집계 테이블 분리로 대응), WebView 브릿지(클라이언트 Flutter 개발자와 협업 필요), 4단계 권한 RLS 설계 정합성.

## 4. 포트폴리오 매칭

| 프로젝트 | 매칭 근거 | 점수 |
|---------|----------|------|
| **EZ-Approve** | 상용 UI 템플릿(MUI) 어드민, RBAC 7역할/승인·반려, HTML 리치 에디터·이미지 업로드 → 관리자 영역 직접 대응 | ★★★★★ |
| **Calendar Share** | Supabase(PostgreSQL·Auth·Storage) 백엔드 구축, 좋아요·스크랩 소셜, 이미지 업로드 → 핵심 스택 직접 대응 | ★★★★★ |
| **Fortune App** | 자체 광고 SDK 노출·클릭 트래킹, 광고 소재 노출, 수익화 → 광고 캠페인·통계 영역 직접 대응 | ★★★★☆ |

세 프로젝트가 각각 어드민/RBAC, Supabase 백엔드, 자체 광고 트래킹의 3대 축을 정확히 커버.

## 5. 최종 제안 요약

- 지원 금액: **12,750,000원 (VAT 별도)** — 클라이언트 예상 15,000,000원의 85%
- 지원 기간: **60일** — 클라이언트 예상 유지(다수 인력 단계 병행)
- 핵심 제안 포인트:
  1. 백오피스는 상용 UI 템플릿 커스터마이징으로 비용 절감, 게시판·트래킹·통계 핵심 기능에 예산 집중
  2. 자체 광고 시스템(노출·클릭 트래킹, 5종 소재, CTR 집계·CSV) 구축 경험
  3. Supabase 풀스택(RLS 4단계 권한, Auth, Storage, Edge Functions) + API Key 프록시 보안
  4. 트래킹 배치 최적화로 DB 부하 방지, Flutter WebView 브릿지 연동 및 SSR SEO

## 6. 최종 산출물 (8단계 출력 전문)

### 제안서 사이트 URL
https://proposal-router.claude-ai-b27.workers.dev/proposal-supabase-community-board-ad-dashboard/

### 지원 금액
12,750,000원 (VAT 별도)

### 지원 기간
60일

### 클라이언트 질문 답변
해당 없음 (공고 내 클라이언트 작성 질문 없음)

### 지원 내용 (전체 텍스트)

안녕하세요, Supabase 기반 사용자 게시판 및 관리자/광고주 대시보드 구축 프로젝트에 지원합니다.

본 프로젝트에 대한 상세 제안서(견적서, 공수계산서, PRD, 일정, 포트폴리오)를 별도 페이지로 준비하였습니다. 아래 링크에서 확인해 주시면 감사하겠습니다.
▶ 제안서 상세 페이지: https://proposal-router.claude-ai-b27.workers.dev/proposal-supabase-community-board-ad-dashboard/
▶ 위시켓 포트폴리오: https://www.wishket.com/partners/p/blueverse1/

---

<프로젝트 진행 제안>

■ 프로젝트 분석
- 커뮤니티 게시판으로 유저 체류 시간을 높이고, 자체 광고 시스템으로 수익화 기반을 마련하는 통합 구축 프로젝트로 이해하였습니다.
- 관리자·광고주 백오피스는 상용 UI 템플릿(MUI 등) 커스터마이징으로 비용을 절감하고, 게시판·광고 트래킹·통계 등 핵심 기능에 예산을 집중하여 Supabase 기반으로 효율적으로 구축합니다.
- 4단계 권한(관리자/광고주/유료/무료) RBAC, 5종 광고 소재, 노출·클릭·CTR 집계, Flutter 웹뷰 연동, SEO까지 요구사항을 빠짐없이 반영합니다.

■ 작업 일정 (총 60일)

[Phase 1] Day 1–10 — 기획/설계
- 요구사항 정의, 사용자 게시판 화면설계, Supabase ERD·RLS 설계, 어드민 상용 템플릿 선정

[Phase 2] Day 11–24 — 어드민 & 광고 캠페인
- 상용 템플릿 세팅, 4단계 권한 승인·반려, 회원/게시판 관리(HTML 에디터·예약발행), 광고 캠페인 CRUD·5종 소재

[Phase 3] Day 25–42 — 사용자 게시판(웹뷰)
- 글/댓글/대댓글/신고, 스포일러, 투표글, 좋아요·스크랩, 이미지 리사이징·AI 번역·SEO, 광고 소재 노출

[Phase 4] Day 43–52 — 트래킹/통계 & 광고주 대시보드
- 노출·클릭 트래킹 배치 최적화, CTR 집계 그래프·CSV, 광고주 대시보드, Flutter WebView 브릿지

[Phase 5] Day 53–60 — QA & 배포
- 통합 QA, 성능·부하 검증, 배포, 운영·관리자 매뉴얼

■ 마일스톤 및 산출물
- M2(Day 24): 어드민 템플릿 세팅 및 캠페인 기능 — 클라이언트 "3주 내" 마일스톤 충족
- M3(Day 42): 사용자 게시판(댓글/신고 포함) 및 5종 광고 소재 — "6주 내" 충족
- M4(Day 52): 트래킹·통계 — "8주 내" 충족
- 최종 산출물: 프론트엔드 소스코드, Supabase 스키마/Edge Functions 코드, 기획/디자인 원본(사용자 게시판), 운영·관리자 매뉴얼

■ 미팅 시 협의 필요 사항
- 어드민 상용 UI 템플릿(MUI 등) 선정 및 라이선스 범위
- 4단계 권한별 세부 기능 범위(유료/무료 차등)
- AI 번역 API 제공사(OpenAI/DeepL 등) 및 비용 부담 주체
- Flutter 앱 웹뷰 브릿지 통신 규격(인증 토큰 전달 방식)

---

<유사 프로젝트 진행 경험>

▶ EZ-Approve (전자결재 SaaS) (2026.01~2026.03)
- 프로젝트 유형: B2B SaaS / 기업용 어드민
- 핵심 기능: 7역할 RBAC·승인/반려 워크플로우, MUI 어드민 50+ 페이지, Lexical HTML 리치 에디터
- 유사점: 4단계 권한 승인·반려, 게시판 관리 어드민, HTML 에디터·이미지 업로드, 상용 템플릿(MUI) 커스터마이징
- 기술 스택: NestJS, Next.js, TypeScript, MUI, Lexical, MySQL

▶ Calendar Share (소셜 캘린더 앱) (2025.01~)
- 프로젝트 유형: B2C 앱 / 소셜 (Supabase)
- 핵심 기능: Supabase(PostgreSQL·Auth·Storage) 백엔드, 좋아요·스크랩 소셜, 이미지 처리
- 유사점: Supabase 풀스택 구축, 좋아요·스크랩 기능, 이미지 업로드 — 본 프로젝트 핵심 스택 직접 대응
- 기술 스택: Supabase, PostgreSQL, Firebase, Flutter

▶ Fortune App (라이프스타일 앱) (2024.07~2024.09)
- 프로젝트 유형: B2C 앱 / 광고 수익화
- 핵심 기능: 자체 광고 SDK 노출·클릭 트래킹, 포인트·리워드, 소셜 로그인
- 유사점: 자체 광고 시스템(노출·클릭 트래킹), 소재 노출, 수익화 기반 — 광고 캠페인·통계 영역 직접 대응
- 기술 스택: Flutter, Firebase, Node.js, BLoC

---

<사용 기술과 툴>

▶ 개발 기술
- Supabase (PostgreSQL, Auth, Storage, Edge Functions), Row Level Security
- Next.js, React, TypeScript, MUI, Recharts
- Flutter WebView 브릿지 연동

▶ 개발 도구 및 인프라
- 버전 관리: GitHub
- CI/CD: GitHub Actions
- 클라우드: Supabase / Vercel
- 컨테이너: Docker

▶ 커뮤니케이션
- 일일 진행 공유: Slack 또는 카카오톡
- 주간 미팅: Zoom / Google Meet
- 문서 공유: Notion 또는 Google Docs
- 이슈 트래킹: GitHub Issues 또는 Linear

### 관련 포트폴리오 추천
1. EZ-Approve — 상용 UI 템플릿(MUI) 어드민, RBAC·승인/반려, HTML 리치 에디터
2. Calendar Share — Supabase(PostgreSQL·Auth·Storage) 풀스택 백엔드, 좋아요·스크랩 소셜
3. Fortune App — 자체 광고 노출·클릭 트래킹, 광고 수익화
