# 변경 이력

이 문서는 사용자에게 보이는 변경사항을 기록합니다.
각 버전의 상세 내용은 [릴리즈 페이지](../../releases)에 있습니다.

형식은 [Keep a Changelog](https://keepachangelog.com/ko/1.1.0/)를 따르고,
버전은 [유의적 버전](https://semver.org/lang/ko/)을 따릅니다.

## [0.1.1] — 2026-09-03

### 새로 생김

- 디자인 토큰 교체 + Pretendard·Jua 글꼴 로드
- Grape Soda host game picker + full UI restyle (#9)
- exporter logs in and carries session cookie on ingest
- host login gate + 401 redirects
- host images same-origin; drop legacy static-SVG fallback
- proxy forwards cookies + binary bodies for host image auth
- login/logout/me endpoints + real security filter chain
- startup admin seeder (env-driven, idempotent, prod-guarded)
- pluggable AdminAuthProvider seam + LocalPasswordAuthProvider
- admin_user table (V4), entity, repository
- add spring-security starter with permit-all baseline
- 4 art-only panel PNGs + HTML frame/labels/captions
- assemble game rounds from filter-then-random questions
- token-free exporter from committed source to ingest endpoint
- resvg SVG->PNG rasterizer
- filter-then-random round assembler with answer-safe DTO
- protected PNG image endpoint (no-store, etag, svg never served)
- admin ingest endpoint (upsert question + choices)
- JPA entities + filter repository for questions
- V2 Postgres schema for question + choices
- reject localhost/loopback game origin
- 연간차트 데이터와 수집 파이프라인 (#6)
- 2018 연간차트 TOP100 4컷 100곡 + 연출 규칙 66개 (#5)
- 모델·effort 비교 러너 + 대량생산 스킬
- 팀 공용 ssongle-4cut 스킬 패키징
- 가사 → 4컷 만화 생성 파이프라인
- 곡 풀 149곡 시드 + 검증 스크립트
- Kahoot-style realtime game loop (milestone 1) (#2)
- remove Tailscale/deploy job from release — publish-only, manual deploys for now
- CI/PR guardrails + health endpoints + deploy pipeline (US2-US4)
- Stage 1 full-stack baseline — portable compose stack, API contract, CI/CD scaffolding

### 고침

- proxy must return NextResponse so Set-Cookie reaches the browser
- set SameSite=Lax on session cookie to back CSRF-disabled claim
- close unclosed <g> in 2019-033 brazier helper
- surface server error when creating a game fails
- Enter joins with a Korean nickname (IME composition)
- ws handshake rejected by 8KB header cap when localhost cookies pile up
- frontend healthcheck uses 127.0.0.1 (busybox wget resolves localhost to ::1)

## [0.1.0] — 2026-09-03

### 새로 생김

- 쏭글쏭글의 새 얼굴 — 보라(Grape Soda) 팔레트, 새 글꼴, 첫 화면부터 시상대까지 화면 전부를 새로 그렸습니다
- **쏭나물 꾸미기** — 로그인한 참가자는 모자 · 안경 · 목 · 손 아이템과 몸 색을 따로 골라 내 쏭나물을 만들 수 있습니다. 꾸민 모습은 대기실 이름표 · 순위표 · 시상대에 그대로 보입니다
- 마이페이지 — 내 옷장 · 상점 · 닉네임 바꾸기

### 바뀜

- 큰 화면(TV)의 문제 화면에서 보기 목록이 사라졌습니다. 만화 4칸이 화면을 꽉 채우고, 답은 각자 폰에서만 고릅니다
- 정답이 공개되면 방장이 누르지 않아도 몇 초 뒤 자동으로 다음 문제로 넘어갑니다
- 게임 만들기가 한 화면으로 — 연도 카드를 누르면 난이도 · 문제 수 · 장르가 같은 화면에 펼쳐집니다. 기본값이면 두 번 눌러 시작
- 순위표에 지난 문제 대비 오르내림(▲▼)이 표시됩니다

### 알아 두세요

- 지금은 2018 · 2019 · 2020년 노래로 놀 수 있습니다. 다른 연도는 준비 중입니다
- 아이템 가격과 포인트는 아직 조정 중이라 바뀔 수 있습니다
