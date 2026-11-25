# 스튜디오 밸런스 — 소상공인 1페이지 홈페이지 샘플 (필라테스)

인천 구월동의 **가상 1:1 필라테스 스튜디오**를 기준으로 제작한 1페이지 랜딩 샘플입니다.
지비스 스튜디오의 '1페이지 홈페이지 제작 대행' 상품을 크몽·당근에서 소개할 때 보여주는 실제 라이브 포트폴리오입니다.

- 라이브: **<https://sample-pilates-landing.vercel.app>** (Vercel `parkjibin` 팀 · GitHub `10jibin27-code/sample-pilates-landing` 연동 — main 브랜치에 푸시하면 자동 재배포)
- 구성: 정적 HTML + CSS + 바닐라 JS (빌드 도구·외부 라이브러리 없음)
- 폰트: Google Fonts (IBM Plex Sans KR / Manrope)
- 사진: `images` 명령으로 생성한 가상 스튜디오 이미지 8장 + OG 커버 (`assets/`)

## 구성 요소

| 섹션 | 내용 |
| --- | --- |
| 상단 배지 | `샘플 페이지 · 지비스 스튜디오 제작` 안내 바 |
| 헤더 | 로고·메뉴·수업 운영 상태 표시·체험 신청 CTA·모바일 햄버거 |
| 히어로 | 스튜디오 풀블리드 사진 + 대표 문구 + 체험/프로그램 CTA |
| 팩트바 | 1:1 · 4명 · 50분 · 07:00 · 3분 (사진 위에 겹치는 요약 바) |
| 프로그램 | 1:1 개인 레슨 · 듀엣 · 소수정예 그룹 카드(시간·1회·10회 가격) + 첫 체험 안내 |
| 왜 밸런스 | 수업 철학 3가지 (상태 확인 · 호흡 · 홈 루틴) |
| 시간표 | 요일별 수업 시간표 표(1:1·듀엣·그룹 구분, 모바일 가로 스크롤) + 범례 |
| 이용권 | 그룹·1:1·듀엣 10회권 카드(회당 금액 포함) + 결제·변경 안내 |
| 강사 | 대표·강사 2인 소개(사진·경력·전문 분야) |
| 공간 | 스튜디오 사진 3장 + 편의시설 태그 |
| 오시는 길 | 요일별 운영 시간 표(오늘 행 자동 강조) + 약도 카드 + 네이버지도·카카오맵 |
| 체험 신청 | 이름·연락처·관심 수업·운동 경험·날짜·시간·몸 상태 폼 → 입력 검증 후 신청 내용 정리·복사 패널 + 카카오톡 채널·네이버 예약 |
| FAQ | 6문항 아코디언 |
| 하단 배지 | '지비스 스튜디오 제작 샘플' 안내 |
| 모바일 하단 바 | 프로그램 / 길찾기 / 체험 신청 고정 바 |

## 동작하는 기능

- 오늘 요일 기준 **수업 운영 중·종료 자동 판정**(평일 07:00–22:00, 토 09:00–15:00, 일 휴무)과 운영 시간 표 행 강조
- 체험 신청 폼 **입력 검증**(이름 2자, 연락처 9~11자리, 오늘 이후 날짜)과 오류 메시지
- 신청 내용 자동 정리 → **클립보드 복사**, Esc·배경 클릭으로 닫기
- 시간표 가로 스크롤(모바일 안내 문구), 스크롤 등장 애니메이션, 스티키 헤더, 부드러운 앵커 이동
- `prefers-reduced-motion` 존중, 시맨틱 마크업·포커스 링·본문 건너뛰기 링크
- 구조화 데이터(`ExerciseGym` JSON-LD), OG 태그, 파비콘

## 수정 방법

| 바꾸고 싶은 것 | 위치 |
| --- | --- |
| 스튜디오 이름·소개 | `index.html` 의 `.brand`, `.hero` |
| 프로그램·가격 | `index.html` 의 `.pcard`, `.plan` |
| 시간표 | `index.html` 의 `#ttTable` |
| 운영 시간 | `index.html` 의 `#hoursTable` + `app.js` 의 `SCHEDULE` (둘 다 수정) |
| 주소·지도 링크 | `index.html` 의 `.mapcard` (네이버·카카오 검색 URL) |
| 강사 | `index.html` 의 `.tcard` |
| 사진 | `assets/` 의 jpg 교체 (같은 파일명 유지) |
| 색상 | `styles.css` 의 `:root` 변수 |

## 검수 스크린샷

`screenshots/` 폴더 — 데스크톱(1440) 전체 `desktop-full.jpg`, 히어로 `desktop-hero.jpg`, 섹션별 `desktop-program.jpg`·`desktop-time.jpg`·`desktop-price.jpg`·`desktop-teacher.jpg`·`desktop-space.jpg`·`desktop-visit.jpg`·`desktop-reserve.jpg`·`desktop-faq.jpg`·`desktop-sample-cta.jpg`, 체험 신청 패널 `desktop-reserve-modal.jpg`, 모바일(390) 전체 `mobile-full.jpg`·`mobile-hero.jpg`·`mobile-nav-open.jpg`·`mobile-reserve-modal.jpg` — 모두 실제 라이브 화면 캡처(jpg).

## 배포 (2026-11-25)

| 항목 | 값 |
| --- | --- |
| GitHub | `10jibin27-code/sample-pilates-landing` (Public, `main`) |
| Vercel | `parkjibin` 팀 · 프로젝트 `sample-pilates-landing` (Framework `Other`, 빌드 없음) |
| 라이브 | <https://sample-pilates-landing.vercel.app> |
| 접근 보호 | 없음 — 로그인 없이 누구나 열람(200 OK) |

수정 후 배포는 `git add -A && git commit -m "..." && git push` 만 하면 Vercel이 자동으로 다시 배포합니다.

## 샘플 표기

가상 스튜디오입니다. 상호·대표자·사업자등록번호·전화번호·주소가 모두 가상이고, 페이지 상단·하단에 '샘플' 표기를 넣었으며 `noindex`로 검색 노출을 막았습니다. 실제 손님에게는 **샘플이라는 점을 먼저 말하고** 링크를 보여주세요.
