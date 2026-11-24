# lab/ — 실험용 디자인 시안

이 폴더는 **포트폴리오 사이트의 디자인을 다시 잡아보기 위한 실험용 시안**입니다.
루트의 `index.html`, `assets/style.css`, `projects/*`, `game/*` 등 **기존 페이지는 전혀 수정하지 않았고**, 이 폴더의 새 파일만 추가했습니다.
텍스트·링크·PDF·이미지는 현재 사이트의 것을 그대로 가져왔으며, 새로 지어낸 문구는 없습니다.

- 메인 시안: `lab/index.html` (+ `lab/lab.css`)
- 상세 페이지 시안 1개: `lab/projects/kalpa-character.html` (다른 상세 페이지 링크는 기존 페이지로 연결)
- 경량 이미지 사본: `lab/assets/*.webp` (원본은 `assets/img/` 그대로, 복사하지 않고 WebP 로 변환한 사본만 추가)
- 공유 썸네일: `lab/assets/og.png` (1200×630, `lab/assets/og-source.html` 을 캡처해 생성)
- 스크린샷: `lab/screenshots/` (1440px·390px × 라이트·다크)

배포 후 주소: https://mongssill.github.io/portfolio/lab/

## 디자인 결정 요약

1. **뼈대는 유지, 밀도와 위계만 올림.** 섹션 순서(경력 → 대표 프로젝트 → 기획서 PDF → 게임 경험 → 역량 → 학력)와 "왼쪽 라벨 | 오른쪽 내용" 구조는 그대로 두고, 슬라이드·탭 같은 인터랙션은 넣지 않았습니다.
2. **히어로를 첫 화면의 중심으로.** 제목을 48px(모바일 30px)로 키우고 리드 문구는 기존 문장의 첫 문장만 남겨 2줄 이내로 줄였습니다. 바로 아래에 "기획서 PDF 보기"(#portfolio)와 "연락하기"(mailto) 버튼 2개를 두어 방문자가 다음 행동을 바로 찾게 했습니다.
3. **색 역할 정리.** 파랑 액센트는 링크·주요 버튼·현재 섹션 표시에만 쓰고, 태그 4종(UI/Story/Plot/Production)은 채도 낮은 회색 배경 + 짙은 글자로 통일해 포인트가 분산되지 않게 했습니다. 다크 모드에서는 밝은 파랑 버튼 위에 짙은 글자를 써서 대비를 확보했습니다.
4. **섹션 라벨의 위계를 뒤집음.** 영문은 11.5px 대문자·자간 .12em·흐린 색으로 내리고, 한글을 24px 굵은 제목으로 올렸습니다. 데스크톱에서는 라벨이 스크롤을 따라오도록(sticky) 했습니다.
5. **대표 프로젝트 카드에 썸네일 추가, 2열.** 상세 페이지에 있는 이미지 중 각 프로젝트에 맞는 것을 썸네일로 썼고, 맞는 이미지가 없는 "5장 연출"은 태그(Story) 색 기반의 단색 플레이스홀더로 비워 두었습니다. 기간은 썸네일 좌상단에 작게 표시합니다.
6. **PDF 카드 정리.** 썸네일을 카드 폭 가득(16:9)으로 키우고 위에 게임명 라벨을 얹었습니다. "PDF 보기"와 "Google Drive" 버튼 두 개를 하나로 합쳐 기본 버튼은 로컬 PDF, Google Drive 는 아래의 작은 텍스트 링크로 내렸습니다.
7. **모바일 내비 유지.** 640px 이하에서 메뉴가 사라지지 않도록 햄버거 버튼으로 접히는 메뉴(아주 작은 JS)를 넣었고, 상단 고정은 그대로입니다. 현재 보고 있는 섹션은 IntersectionObserver 로 내비에 표시합니다.
8. **이미지 경량화.** 커버(1.7MB PNG → 25KB WebP), 프로필, 썸네일 6장을 WebP 사본으로 만들어 첫 화면 로딩을 줄였습니다. 상세 페이지의 비교 이미지는 원본을 그대로 참조합니다.
9. **상세 페이지.** "← 돌아가기 / 제목 / 기간 / 태그 / 첨부 파일"을 한 블록으로 묶고, 본문은 01 프로젝트 개요(상황) → 02 주요 작업(내가 한 일) → 03 핵심 성과(결과) 순서로 왼쪽 번호가 달린 h2 로 표시합니다. 비교 이미지는 좌우 배치, 모바일에서는 세로로 바뀝니다.
10. **접근성.** 모든 이미지 alt 유지, 키보드 포커스 표시(outline) 추가, 보조 텍스트 색을 WCAG AA(4.5:1 이상) 기준으로 조정했습니다.

## 확인 방법

빌드 도구가 없으므로 정적 서버로 저장소 루트를 띄운 뒤 `/lab/` 로 접속하면 됩니다. 스크린샷은 Playwright(Chrome 채널)로 1440px·390px 뷰포트, 라이트·다크 색상 스킴에서 전체 페이지를 캡처한 것입니다.

---

## 2차 시안 (2026-11-24)

1차 시안 위에 같은 브랜치(`lab/redesign`)로 쌓은 변경입니다. 기존 파일은 여전히 건드리지 않았습니다.

### 바뀐 점

- **섹션 순서 변경과 번호 부여.** 히어로 → 01 대표 프로젝트 → 02 AI로 만든 게임 → 03 기획서 PDF → 04 플레이한 게임 → 05 경력 → 06 보유 역량 → 07 학력. 경력은 그대로, 역량은 한 줄 칩 목록, 학력은 한 줄로 압축했습니다.
- **우측 고정 섹션 내비(1024px 이상).** 번호 + 한글 이름 7개가 화면 오른쪽에 세로로 고정되고, IntersectionObserver 로 현재 섹션의 점이 커지고 글자가 진해집니다. 1280px 미만에서는 점과 번호만 보이고 라벨은 호버·포커스 때 나타납니다. 히어로·짙은 블록 위를 지날 때는 흰 톤으로 바뀝니다. 상단 바는 이름과 "연락하기" 버튼만 남겼고, 1024px 미만에서는 1차의 햄버거 메뉴를 유지합니다.
- **AI로 만든 게임 섹션(신규).** 라이트 모드에서도 짙은 블록으로 톤을 구분합니다. 게임 1개(태그 보스전)를 가로형 카드 하나로 크게 두었고, 왼쪽은 인게임 스크린샷 3장 캐러셀(좌우 버튼, 점, 키보드 ←/→, 터치 스와이프), 오른쪽은 설명과 버튼 2개("직접 해보기 ↗" primary, "아티팩트 문서 보기 ↗")와 "PC 키보드 전용" 안내입니다. 설명은 `ai-seed-kit/games/g2-slice/README.md` 의 문장을 요약한 것으로, 새 사실을 더하지 않았습니다.
  - 스크린샷은 공개 주소 https://mongssill.github.io/ai-seed-kit-games/g2-slice/ 를 Playwright(Chrome)로 1280×720 에서 열어 캔버스 영역만 2배 해상도로 찍었습니다. 시작 화면 → Enter 로 시작 → 방향키·A·S 입력 뒤 전투 중 → `?test` 로 열어 그로기 게이지가 찬 상태에서 F 를 눌러 그로기 연출(눈 클로즈업) 순입니다. 그로기 장면은 `?test` 모드의 "확인용" 워터마크 문구만 캡처 시점에 가렸고, 게임 파일은 수정하지 않았습니다.
- **플레이한 게임 섹션(신규).** 공식 키아트 카드 5장(위 키아트 / 게임명 / 장르 칩 / 기록(있을 때만) / 관찰 한 줄 / 연결 기획서 링크). 장르 필터 칩(전체 / 배틀로얄 / 수집형 RPG / MOBA / MMORPG / 액션 RPG)은 작은 JS 로 동작하고 기본은 전체입니다. 기록은 현재 사이트에 있는 것만 썼습니다(배틀그라운드 540시간, 리버스:1999 700일, 리그 오브 레전드 290레벨). 연결 기획서는 `#portfolio` 의 해당 카드로 앵커되고, 몬길: 스타다이브는 AI 게임 섹션으로 연결됩니다. 섹션 머리에 기존 두 상세 페이지(`game/passion.html`, `game/perspective.html`) 링크를 "자세히"로 두었습니다.
  - **관찰 메모는 비워 두었습니다.** 각 카드의 `<p class="obs" data-observation="">` 안에 주인이 직접 쓸 자리이며, 비어 있는 동안은 "관찰 메모 추가 예정" 안내가 흐리게 보입니다. 텍스트를 넣고 `data-observation` 값을 아무 문자열로 채우면 안내가 사라집니다.
- **인터랙션.** 섹션과 카드가 뷰포트에 들어올 때 살짝 올라오며 나타납니다(`prefers-reduced-motion: reduce` 면 끔). 상세 페이지의 구/신 모델링 비교는 좌우로 끌어 비교하는 슬라이더(range input 기반, 키보드 ←/→ 가능, 모바일 터치 가능)로 바꿨습니다. 가로 슬라이드·탭 전환 같은 페이지 단위 인터랙션은 넣지 않았습니다.
- **히어로.** 커버 위에 흰 글자 제목을 올리는 짙은 히어로로 바꾸고 아래 밝은 본문으로 이어지게 했습니다. 문구는 1차 것 그대로이고, 연락처는 히어로 아래 한 줄 스트립으로 내렸습니다.

### 키아트 출처 (모두 공식 사이트의 공유용 대표 이미지, `og:image`)

| 게임 | 파일 | 출처 |
|---|---|---|
| 배틀그라운드 | `lab/assets/games/pubg.webp` | https://pubg.com/ko 의 og:image → https://wstatic-prod.pubg.com/web/live/static/og/img-og-pubg.jpg |
| 리버스:1999 | `lab/assets/games/reverse1999.webp` | https://re1999.bluepoch.com/ 의 og:image → https://webres-hw.bluepoch.com/shareCard/3-9en-banben.jpg |
| 리그 오브 레전드 | `lab/assets/games/lol.webp` | https://www.leagueoflegends.com/ko-kr/ 의 og:image → https://cmsassets.rgpub.io/sanity/images/dsfx7636/content_organization_live/bdc123b2cae1ff76fea465b287240cab8f3208a7-1200x630.jpg |
| 메이플스토리 | `lab/assets/games/maplestory.webp` | https://maplestory.nexon.com/ 의 og:image → https://lwi.nexon.com/maplestory/2026/1119_intro_EFA0504AEC2E9DE0/exception/meta.jpg (400×400 정사각, 카드에서는 가운데를 16:9 로 잘라 보여 줌) |
| 몬길: 스타다이브 | `lab/assets/games/mongil-stardive.webp` | https://stardive.netmarble.com/ 의 og:image → https://sgimage.netmarble.com/images/netmarble/monster2/20260305/m3sm1772674620510.jpg |

모두 가로 600px 이하 WebP 사본으로 저장했습니다(각 16~46KB). 공식 출처를 못 찾은 게임은 없습니다. 이미지 저작권은 각 게임사에 있으며, 포트폴리오 안에서 플레이 경험을 설명하기 위한 대표 이미지로만 사용합니다. 저작권자의 요청이 있으면 게임명 타이포 플레이스홀더로 바꿉니다.

### 2차에서 새로 추가된 파일

- `lab/assets/ai/g2-title.webp`, `g2-fight.webp`, `g2-groggy.webp` (태그 보스전 인게임 스크린샷)
- `lab/assets/games/*.webp` (공식 키아트 사본 5장)
- `lab/screenshots/index-desktop-1440-sections-ai-games.png` (AI 게임 + 플레이한 게임 섹션 캡처)

---

## 3차 시안 (2026-11-24)

같은 브랜치에 쌓은 세 번째 변경입니다. 기존 파일은 여전히 건드리지 않았고, "플레이한 게임" 섹션의 게임 목록·카드 내용과 구조(필터 칩, 카드 CSS)는 주인이 직접 채울 예정이라 손대지 않았습니다.

### 바뀐 점

- **AI로 만든 게임 · 태그 보스전(게임 2) 수정.** 캐러셀에서 시작 화면을 빼고 연출 장면으로 바꿨습니다. 첫 장은 그로기 연출 중 **보스가 빛 고리에 묶인 순간**(눈 클로즈업보다 무대 전체가 보여 "장면"으로 읽힘), 둘째 장은 **노란 전조가 빛나는 순간**, 셋째 장은 **회피 반격 순간**("회피 반격!" 문구와 화면 번쩍임)입니다. 설명 아래의 "조작" 한 줄은 뺐고 "PC 키보드 전용"은 유지했습니다.
- **AI로 만든 게임 · 길 건너기(게임 1) 추가.** 같은 형식의 카드를 태그 보스전 아래에 세로로 배치했습니다(순서: 게임 2 → 게임 1). 설명은 `ai-seed-kit/games/g1-copy/README.md` 의 문장을 요약한 것이고, "내가 한 것"은 README 의 A~F 중 원작 분석 · 규칙 정의와 reviewer 반복 검토 · 직접 플레이 확인 · 테스터 피드백 반영만 추렸습니다. 세로 캔버스(432×672)라 카드 안에서 캐러셀 폭을 줄이고 세로 비율로 두었습니다. 카드 머리 라벨은 "게임 2 · 큰 게임의 일부 · 원작 몬길: 스타다이브", "게임 1 · 완전 카피 · 원작 길건너친구들"로 통일했습니다.
  - 스크린샷은 공개 주소를 Playwright(Chrome) 1280×720 에서 열어 캔버스 영역만 2배로 찍었습니다. 태그 보스전은 `?test`(게이지 찬 상태) → F → 연출 단계(`bind`)에서 1장, 일반 판에서 보스에게 붙은 뒤 보스 상태가 `telegraph` 인 순간 1장, 그 전조 범위 안에서 Shift 를 눌러 반격이 터진 순간(줌 발생 시점) 1장입니다. 2차처럼 `?test` 의 "확인용" 워터마크 문구만 캡처 시점에 가렸고 게임 파일은 수정하지 않았습니다. 길 건너기는 `?far`(100칸 앞 시작)로 열어 방향키를 보내며 진행한 뒤 찻길·강·선로가 함께 보이는 장면, 다른 지형 구간, 게임 오버 결과창을 찍었습니다.
- **보유 역량: 공식 아이콘 카드 + 작업 방식 도식.** 역량 7개를 아이콘(좌) / 이름 + 기존 한 줄 설명(우) 카드로 바꿨습니다. 아이콘 타일은 브랜드 원색이 살도록 라이트·다크 모두 연한 톤입니다. 카드 아래에 인라인 SVG 도식을 넣었고, 720px 이하에서는 세로 흐름의 HTML 목록으로 바뀝니다.
- **새 섹션 05 게임 밖 활동.** "플레이한 게임" 머리에 있던 "자세히" 링크 두 개로는 게임 외 활동이 눈에 띄지 않아 별도 섹션으로 뺐습니다. 2단: 왼쪽 "게임 안에서 — 5년의 기록"(메이플 스크린샷 2장 + 2000일 출석 이미지), 오른쪽 "게임 밖에서 — 현장의 기록"(오프라인 사진 3장). 문장은 기존 `game/passion.html` 의 것을 다듬은 한 줄씩만 두었고, "자세히" 링크 두 개는 섹션 하단의 작은 링크로 옮겼습니다. 섹션 번호는 05 게임 밖 활동, 06 경력, 07 보유 역량, 08 학력로 다시 매겼고 우측 내비와 햄버거 메뉴에도 반영했습니다.

### 아이콘 출처

| 역량 | 파일 | 출처 | 구분 |
|---|---|---|---|
| ChatGPT | `lab/assets/icons/openai-black.svg` | OpenAI Brand Guidelines https://openai.com/brand/ 의 로고 패키지 https://cdn.openai.com/brand/openai-logos.zip 안의 `OAI_OpenAI-Blossom_Black.svg` | **공식** |
| Word | `lab/assets/icons/word.svg` | Microsoft Fluent UI 브랜드 아이콘 CDN https://res-1.cdn.office.net/files/fabric-cdn-prod_20230815.002/assets/brand-icons/product/svg/word_48x1.svg | **공식**(Microsoft 가 배포하는 제품 아이콘) |
| Excel | `lab/assets/icons/excel.svg` | 같은 CDN 의 `excel_48x1.svg` | **공식** |
| PowerPoint | `lab/assets/icons/powerpoint.svg` | 같은 CDN 의 `powerpoint_48x1.svg` | **공식** |
| Notion | `lab/assets/icons/notion.svg` | Simple Icons https://simpleicons.org/?q=notion (https://cdn.simpleicons.org/notion). 공식 브랜드 페이지 https://www.notion.com/brand 는 다운로드 링크가 스크립트로 렌더링되어 직접 받지 못함 | Simple Icons |
| Unity | `lab/assets/icons/unity.svg` | Simple Icons https://simpleicons.org/?q=unity (https://cdn.simpleicons.org/unity). 공식 페이지 https://unity.com/legal/branding_trademarks 에서는 워드마크 SVG 만 직접 받을 수 있어 심볼은 Simple Icons 를 씀. 색은 Unity 로고 기본색(검정 계열 `#222C37`) | Simple Icons |
| Claude | `lab/assets/icons/claude.svg` | Simple Icons https://simpleicons.org/?q=claude (https://cdn.simpleicons.org/claude, 브랜드색 `#D97757`). 공식 페이지 https://www.anthropic.com/brand 는 스크립트 렌더링이라 직접 받지 못함 | Simple Icons |

도식의 Claude Code · Codex(OpenAI) 아이콘은 위 파일을 재사용했고, Orca 는 공식 아이콘을 찾기 어려워 글자 마크 "O"로 두었습니다. 나(왼쪽 노드)는 프로필 사진입니다.

### 작업 방식 도식 문구 (주인 확인용)

- 제목: **Orca로 Claude와 Codex를 묶어 일합니다**
- 부제: 지시 → 분배 → 구현/검토 → 결과 → 내 검수로 되돌아오는 흐름입니다.
- 노드: 나(기획 · 판단 · 검수) → Orca(작업 관리 — 봇·워커에게 일을 나누고 한곳에서 봄) → Claude Code(구현 · 규칙 검사 · 문서) / Codex(초안 · 검토 · 리뷰어 역할) → 결과물(AI 게임 · 기획서 · 이 포트폴리오)
- 화살표 라벨: 지시 / 분배 / 구현 · 검사 / 초안 · 리뷰 / 내 검수 (다시 지시)

### 비워 둔 캡션 자리 (주인이 채울 곳)

`lab/index.html` 의 `#beyond` 섹션, 각 `<figure data-caption="">` 안 `<figcaption>` 입니다. 캡션을 쓰고 `data-caption` 값을 아무 문자열로 채우면 "캡션 추가 예정" 안내가 사라집니다.

1. `assets/beyond/maple-play-1.webp` — 메이플스토리 플레이 스크린샷 1
2. `assets/beyond/maple-play-2.webp` — 메이플스토리 플레이 스크린샷 2
3. `assets/beyond/maple-2000days.webp` — 2000일 출석 기록
4. `assets/beyond/offline-1.webp` — 오프라인 행사 사진 1
5. `assets/beyond/offline-2.webp` — 오프라인 행사 사진 2
6. `assets/beyond/offline-3.webp` — 오프라인 행사 사진 3

### 3차에서 새로 추가·삭제된 파일

- 추가: `lab/assets/ai/g2-groggy-bind.webp`, `g2-telegraph.webp`, `g2-counter.webp`, `g1-play.webp`, `g1-terrain.webp`, `g1-over.webp` / `lab/assets/icons/*.svg` 7개 / `lab/assets/beyond/*.webp` 6장 / `lab/screenshots/index-desktop-1440-sections-v3.png`
- 삭제: 2차의 `lab/assets/ai/g2-title.webp`, `g2-fight.webp`, `g2-groggy.webp` (더 쓰지 않음)

---

## 4차 수정 (2026-11-24)

같은 브랜치에 쌓은 네 번째 변경입니다. 기존 파일은 여전히 건드리지 않았습니다.

- **작업 방식 도식 글자 넘침 수정.** Orca 상자를 192px 폭으로 넓히고 보조 문구를 두 줄("봇·워커에게 일을 나누고 / 진행과 결과를 한곳에서 봄")로 나눴습니다. Claude Code·Codex 상자는 210px 폭으로 넓히고 보조 문구를 두 줄("구현 · 규칙 검사 / 문서 정리", "초안 · 검토 / 리뷰어 역할")로 나눴습니다. 화살표 라벨 5종(지시, 분배×2, 구현 · 검사, 초안 · 리뷰, 내 검수)은 뒤에 배경색 패드(`var(--bg-soft)`)를 깔아 선과 겹쳐 보이지 않게 했습니다. 확인 캡처: `lab/screenshots/how-i-work-1440.png`, `how-i-work-1024.png`.
- **AI로 만든 게임 순서 변경.** 게임 1 "길 건너기"가 위, 게임 2 "태그 보스전"이 아래입니다. 태그 보스전 캐러셀은 2차 때 찍은 **눈 클로즈업(`g2-groggy.webp`) → 전투 중(`g2-fight.webp`)** 두 장으로 되돌렸고(커밋 e02961a 에서 그대로 복구, 다시 찍지 않음), 3차의 `g2-groggy-bind`·`g2-telegraph`·`g2-counter` 는 캐러셀에서 빼고 파일도 지웠습니다. 2차의 시작 화면(`g2-title`)은 복구하지 않았습니다.
- **플레이한 게임: 메이플스토리를 메인 게임 카드로.** 필터 칩 아래에 가로형 큰 카드(왼쪽 키아트 / 오른쪽 내용) 하나를 두었습니다. 라벨 "가장 오래 한 게임", 장르 칩 MMORPG, 기록 "플레이 기간 10년", 관찰 메모 자리(비움), 2000일 출석 이미지를 작은 증빙 썸네일로, 연결 기획서 링크 2개. 아래 격자에서는 메이플스토리 카드를 뺐고 나머지 4장은 그대로입니다. 필터 칩은 메인 카드에도 적용됩니다(MMORPG 가 아니면 메인 카드도 숨김). 다른 게임은 추가하지 않았습니다.
- **게임 밖 활동을 큰 캐러셀로.** 데스크톱은 왼쪽 1/3 에 현재 그룹의 제목·한 줄 문장(3차 것 그대로)·"n / 6", 오른쪽 2/3 에 이미지 1장(높이 480px, `object-fit: contain`, 어두운 회색 패드) + 좌우 화살표 + 하단 점 6개 + 캡션 자리. 슬라이드 6장(메이플 1·2, 2000일 출석, 오프라인 1·2·3)이고 4번째부터 그룹 2로 넘어가면 왼쪽 글이 바뀝니다. 키보드 ←/→, 터치 스와이프 지원, 자동 재생 없음. 모바일은 위에 글, 아래에 캐러셀(이미지 높이 260~300px). 이미지는 `lab/assets/beyond/*.webp` 를 긴 변 1400px 사본으로 다시 만들었습니다. 캡션은 여전히 비어 있습니다(`<figure data-caption="">`, "캡션 추가 예정"). 섹션 하단의 "자세히" 링크 두 개는 유지.
- 스크린샷: 기존 이름 덮어쓰기 + `index-desktop-1440-sections-v4.png`(AI 게임 → 플레이한 게임 → 게임 밖 활동), `how-i-work-1440.png`, `how-i-work-1024.png` 추가.

### 4차에서 비워 둔 자리 (주인이 채울 곳)

- 게임 밖 활동 캐러셀 6장의 캡션: `#beyond .carousel.big .slide[data-caption=""] figcaption`
- 메이플스토리 메인 카드와 나머지 4장의 관찰 메모: `.game-card .obs[data-observation=""]`

---

## 5차 (2026-11-24): "플레이한 게임"을 플레이 로그 형식으로

같은 브랜치에 쌓은 다섯 번째 변경입니다. 기존 파일은 여전히 건드리지 않았습니다.

### 구조 (위에서 아래로)

1. **메인 게임 카드** — 4차의 메이플스토리 카드 그대로(가장 오래 한 게임 · MMORPG · 플레이 기간 10년 · 2000일 출석 썸네일 · 연결 기획서 2개 · 관찰 메모 자리).
2. **요약 띠** — 플레이한 게임 **74종**(아래 목록 73종 + 메인 게임, 중복 제거) · 플랫폼 **4**(PC · 모바일 · 닌텐도 · PlayStation) · 가장 오래 한 게임 **10년**(메이플스토리) · 장르 그룹 **19**(아래 선반 수).
3. **장르 분포 바** — 19개 그룹의 게임 수 비율로 칸을 나눈 누적 막대. 액센트 한 색의 명도 6단계만 씁니다(`color-mix`). 칸이 좁으면 이름을 숨기고(작은 JS), 호버·포커스 시 "플랫폼 · 그룹명 · N종" 툴팁. 플랫폼 탭과 무관하게 전체 기준이며, 전략적 팀 전투는 PC·모바일 두 그룹에 모두 들어 있어 바에서는 두 번(합 74), 총계에서는 한 번 셉니다.
4. **플랫폼 탭 3개** — PC(7그룹) / 모바일(4) / 콘솔(8). 기본 PC. 탭 아래에 그 플랫폼의 장르 선반이 세로로 쌓입니다. JS 가 없으면 세 패널이 모두 펼쳐져 보입니다.
5. **장르 선반** — 왼쪽: 그룹명 + N종 + 관찰 메모 자리(`data-observation=""`, "관찰 메모 추가 예정"). 오른쪽: 대표작(★) 커버 1~4장(3:4, 135×180px, 기록이 있으면 커버 아래 표시) + "+N 더 보기" 버튼 → 나머지 게임이 텍스트 칩으로 펼쳐집니다(접기 가능, 기본 접힘, JS 없으면 모두 보임). 대표작이 없는 그룹(모바일 · 전략 · 오토배틀러)은 칩만 바로 보입니다.
6. 섹션 하단 작은 글씨: "명칭 확인 중인 게임은 ※ 표시".

동작: 탭은 클릭과 ←/→ 키, 선반 펼침은 버튼(`aria-expanded`), 툴팁은 CSS. `prefers-reduced-motion` 이면 전환 효과를 끕니다. 모바일(820px 이하)에서는 선반이 세로로 쌓이고 커버 줄은 가로 스크롤, "+N 더 보기"는 커버 줄 아래 전체 폭 버튼입니다.

### 총계 산출 방식

- 게임 종수: 아래 표의 게임을 이름 기준으로 세되 **전략적 팀 전투(PC·모바일 중복)는 한 번**, **칼파는 한 번**만 셉니다 → 73종. 여기에 메인 게임 메이플스토리를 더해 **74종**.
- 장르 그룹: 선반 수 19(PC 7 + 모바일 4 + 콘솔 8). 메인 게임의 MMORPG 는 선반이 아니라 그룹 수에 넣지 않았습니다.
- 생성: 목록은 스크래치의 생성기 스크립트(데이터 → HTML)로 만들어 `lab/index.html` 에 정적으로 넣었습니다. 사이트에는 JSON 이나 빌드 단계가 없습니다.

### 대표작 커버 출처 (`lab/assets/games/covers/`, 모두 480×640 WebP)

| 대표작 | 파일 | 출처 | 비고 |
|---|---|---|---|
| 리그 오브 레전드 | lol.webp | https://www.leagueoflegends.com/ko-kr/ og:image (2차에서 받음) | 가로 로고 이미지라 흐린 배경 위에 레터박스 |
| Dota 2 | dota2.webp | Steam 스토어 세로 캡슐 https://store.steampowered.com/app/570/ | |
| PUBG: 배틀그라운드 | pubg.webp | Steam 세로 캡슐 https://store.steampowered.com/app/578080/ | |
| 오버워치 | overwatch.webp | Steam 세로 캡슐 https://store.steampowered.com/app/2357570/ | |
| Vampire Survivors | vampire-survivors.webp | Steam 세로 캡슐 https://store.steampowered.com/app/1794680/ | |
| Enter the Gungeon | enter-the-gungeon.webp | Steam 세로 캡슐 https://store.steampowered.com/app/311690/ | |
| Hollow Knight: Silksong | silksong.webp | Steam 세로 캡슐 https://store.steampowered.com/app/1030300/ | |
| 산나비 | sanabi.webp | Steam 세로 캡슐 https://store.steampowered.com/app/1562700/ | |
| Baba Is You | baba-is-you.webp | Steam 세로 캡슐 https://store.steampowered.com/app/736260/ | |
| 러브 딜리버리 | love-delivery.webp | Steam 세로 캡슐 https://store.steampowered.com/app/1817940/ | |
| 칼파: 코스믹 심포니 | kalpa.webp | Steam 세로 캡슐 https://store.steampowered.com/app/2717010/ | |
| 리버스: 1999 | reverse1999.webp | https://re1999.bluepoch.com/ og:image (2차에서 받음) | 레터박스 |
| 승리의 여신: 니케 | nikke.webp | https://nikke-kr.com/ og:image | 레터박스 |
| 블루 아카이브 | blue-archive.webp | https://bluearchive.nexon.com/ og:image (현재 이벤트 키비주얼) | 레터박스 |
| 원신 | genshin.webp | https://genshin.hoyoverse.com/ko/home og:image | |
| 쿠키런: 킹덤 | cookierun-kingdom.webp | https://www.cookierun-kingdom.com/ko/ og:image | |
| 브롤스타즈 | brawl-stars.webp | https://supercell.com/en/games/brawlstars/ og:image | |
| 젤다의 전설 브레스 오브 더 와일드 | zelda-botw.webp | 닌텐도 코리아 스토어 https://store.nintendo.co.kr/70010000009367 제품 이미지 | |
| Pokémon LEGENDS 아르세우스 | pokemon-legends-arceus.webp | https://store.nintendo.co.kr/70010000039947 제품 이미지 | |
| 슈퍼 마리오 오디세이 | mario-odyssey.webp | https://store.nintendo.co.kr/70010000009372 제품 이미지 | |
| 슈퍼 마리오 갤럭시 2 | mario-galaxy-2.webp | https://store.nintendo.co.kr/70010000104194 제품 이미지 | |
| 별의 커비 디스커버리 | kirby-forgotten-land.webp | https://store.nintendo.co.kr/hacparzgakor 제품 이미지 | |
| 레이튼 교수와 이상한 마을 | layton-curious-village.webp | **타이포 타일** — Level-5 공식 페이지(layton.jp)에서 받을 수 있는 이미지 없음 | |
| 리듬 세상 | rhythm-heaven-ds.webp | **타이포 타일** — 닌텐도 공식 DS 페이지 없음 | |
| 놀러오세요 동물의 숲 | animal-crossing-wild-world.webp | **타이포 타일** — nintendo.co.jp DS 페이지에 og:image 없음 | |
| 라쳇 & 클랭크 (PS2) | ratchet-clank-ps2.webp | **타이포 타일** — PlayStation 사이트에는 PS4 리메이크만 있음 | |

가로형 원본은 주요 피사체 기준으로 세로 크롭했고, 로고 중심의 가로 이미지 4장(리그 오브 레전드 · 리버스: 1999 · 블루 아카이브 · 니케)은 잘리면 읽히지 않아 흐린 배경 위에 원본을 그대로 올리는 레터박스로 만들었습니다. 대표작이 아닌 게임의 이미지는 받지 않았습니다.

### 명칭 확인 결과 (모든 게임)

공식 사이트·공식 스토어 페이지(Steam KR, App Store KR, 닌텐도 코리아 스토어)에서 직접 확인한 표기는 "확인", 보도자료 인용 기사 같은 2차 출처만 있거나 아무 데서도 못 찾은 것은 "※ 미확인"으로 두고 페이지에도 ※ 를 붙였습니다. 영문 공식명만 있는 게임은 영문 그대로 썼습니다.

| 플랫폼 | 그룹 | 원래 메모 | 쓴 표기 | 확인 출처 | 상태 |
|---|---|---|---|---|---|
| — | 메인 | 메이플스토리 | 메이플스토리 | https://maplestory.nexon.com/ (2차에서 확인) | 확인 |
| PC | MOBA · 전략 | 리그 오브 레전드 | 리그 오브 레전드 | https://www.leagueoflegends.com/ko-kr/ | 확인 |
| PC | MOBA · 전략 | Dota 2 | Dota 2 | https://store.steampowered.com/app/570/ | 확인 |
| PC | MOBA · 전략 | 전략적 팀 전투(TFT) | 전략적 팀 전투 | https://apps.apple.com/kr/app/id1480616748 | 확인 |
| PC | 슈팅 · 배틀로얄 | 배틀그라운드 | PUBG: 배틀그라운드 | https://pubg.com/ko | 확인 |
| PC | 슈팅 · 배틀로얄 | 오버워치 | 오버워치 | https://overwatch.blizzard.com/ko-kr/ | 확인 |
| PC | 슈팅 · 배틀로얄 | Apex 레전드 | Apex 레전드 | https://store.steampowered.com/app/1172470/ | 확인 |
| PC | 로그라이트 · 서바이버 | Vampire Survivors | Vampire Survivors | https://store.steampowered.com/app/1794680/ | 확인 |
| PC | 로그라이트 · 서바이버 | 엔터 더 건전 | Enter the Gungeon | https://store.steampowered.com/app/311690/ | 확인 |
| PC | 로그라이트 · 서바이버 | Brotato | Brotato | https://store.steampowered.com/app/1942280/ | 확인 |
| PC | 로그라이트 · 서바이버 | Spelunky 2 | Spelunky 2 | https://store.steampowered.com/app/418530/ | 확인 |
| PC | 로그라이트 · 서바이버 | Cult of the Lamb | Cult of the Lamb | https://store.steampowered.com/app/1313140/ | 확인 |
| PC | 로그라이트 · 서바이버 | Ship of Fools | Ship of Fools | https://store.steampowered.com/app/1286580/ | 확인 |
| PC | 액션 · 메트로배니아 | 할로우 나이트: 실크송 | Hollow Knight: Silksong | https://store.steampowered.com/app/1030300/ | 확인 |
| PC | 액션 · 메트로배니아 | 산나비 | 산나비 | https://store.steampowered.com/app/1562700/ | 확인 |
| PC | 퍼즐 · 시뮬레이션 | Baba Is You | Baba Is You | https://store.steampowered.com/app/736260/ | 확인 |
| PC | 퍼즐 · 시뮬레이션 | 팀파이트 매니저 | 팀파이트 매니저 | https://store.steampowered.com/app/1372810/ | 확인 |
| PC | 스토리 · 연애 시뮬레이션 (국산 인디) | 러브 딜리버리 | 러브 딜리버리 | https://store.steampowered.com/app/1817940/ | 확인 |
| PC | 스토리 · 연애 시뮬레이션 (국산 인디) | 썸썸편의점 | 썸썸 편의점 | https://store.steampowered.com/app/1217390/ | 확인 |
| PC | 스토리 · 연애 시뮬레이션 (국산 인디) | 기적의 분식집 | 기적의 분식집 | https://store.steampowered.com/app/995460/ | 확인 |
| PC | 스토리 · 연애 시뮬레이션 (국산 인디) | 방구석의 인어아가씨 | 방구석에 인어아가씨 | https://apps.apple.com/kr/app/id904882274 | 확인 |
| PC | 리듬 | 칼파(KALPA) | 칼파: 코스믹 심포니 | https://store.steampowered.com/app/2717010/ | 확인 |
| 모바일 | 수집형 RPG | 리버스:1999 | 리버스: 1999 | https://apps.apple.com/kr/app/id6449023119 | 확인 |
| 모바일 | 수집형 RPG | 승리의 여신: 니케 | 승리의 여신: 니케 | https://nikke-kr.com/ | 확인 |
| 모바일 | 수집형 RPG | 블루 아카이브 | 블루 아카이브 | https://bluearchive.nexon.com/ | 확인 |
| 모바일 | 수집형 RPG | 원신 | 원신 | https://apps.apple.com/kr/app/id1517783697 | 확인 |
| 모바일 | 수집형 RPG | 트릭컬 리바이브 | 트릭컬 리바이브 | https://apps.apple.com/kr/app/id6443824730 | 확인 |
| 모바일 | 수집형 RPG | 젠레스 존 제로 | 젠레스 존 제로 | https://apps.apple.com/kr/app/id1606356401 | 확인 |
| 모바일 | 수집형 RPG | 스텔라 소라 | 스텔라 소라 | https://apps.apple.com/kr/app/id6738407268 | 확인 |
| 모바일 | 수집형 RPG | 헤븐 번즈 레드 | 헤븐 번즈 레드 | https://apps.apple.com/kr/app/id1576831351 | 확인 |
| 모바일 | 수집형 RPG | 몬길: 스타다이브 | 몬길: STAR DIVE | https://stardive.netmarble.com/ | 확인 |
| 모바일 | 방치형 · 키우기 | 쿠키런: 킹덤 | 쿠키런: 킹덤 | https://www.cookierun-kingdom.com/ko/ | 확인 |
| 모바일 | 방치형 · 키우기 | 세븐나이츠 키우기 | 세븐나이츠 키우기 | https://apps.apple.com/kr/app/id1658717149 | 확인 |
| 모바일 | 방치형 · 키우기 | Mini Warriors | Mini Warriors ※ | https://apps.apple.com/kr/app/id6742878205 | ※ 미확인 |
| 모바일 | 전략 · 오토배틀러 | 전략적 팀 전투(TFT) | 전략적 팀 전투 | https://apps.apple.com/kr/app/id1480616748 | 확인 |
| 모바일 | 캐주얼 · 실시간 | 브롤스타즈 | 브롤스타즈 | https://apps.apple.com/kr/app/id1229016807 | 확인 |
| 모바일 | 캐주얼 · 실시간 | 포켓몬 GO | Pokémon GO | https://apps.apple.com/kr/app/id1094591345 | 확인 |
| 콘솔 | 젤다의 전설 | 젤다의 전설: 야생의 숨결 | 젤다의 전설 브레스 오브 더 와일드 | https://store.nintendo.co.kr/70010000009367 | 확인 |
| 콘솔 | 젤다의 전설 | 지혜의 투영 | 젤다의 전설 지혜의 투영 | https://store.nintendo.co.kr/70010000084620 | 확인 |
| 콘솔 | 젤다의 전설 | 몽환의 모래시계 | 젤다의 전설 몽환의 모래시계 ※ | https://www.gamemeca.com/view.php?gid=70372 | ※ 미확인 — 한국닌텐도 보도자료를 인용한 기사(2차 출처) |
| 콘솔 | 젤다의 전설 | 꿈꾸는 섬 | 젤다의 전설 꿈꾸는 섬 | https://store.nintendo.co.kr/70010000022823 | 확인 |
| 콘솔 | 포켓몬스터 | Pokémon LEGENDS 아르세우스 | Pokémon LEGENDS 아르세우스 | https://store.nintendo.co.kr/70010000039947 | 확인 |
| 콘솔 | 포켓몬스터 | 포켓몬스터 디아루가·펄기아·Pt 기라티나 | 포켓몬스터DP 디아루가·펄기아 / 포켓몬스터Pt 기라티나 ※ | https://www.gamemeca.com/view.php?gid=82367 | ※ 미확인 — 한국닌텐도 보도자료를 인용한 기사(2차 출처) |
| 콘솔 | 포켓몬스터 | 포켓몬스터 소드 | 포켓몬스터소드 | https://store.nintendo.co.kr/70010000026251 | 확인 |
| 콘솔 | 포켓몬스터 | 포켓몬스터 바이올렛 | 포켓몬스터바이올렛 | https://store.nintendo.co.kr/70010000053973 | 확인 |
| 콘솔 | 마리오 | 슈퍼 마리오 오디세이 | 슈퍼 마리오 오디세이 | https://store.nintendo.co.kr/70010000009372 | 확인 |
| 콘솔 | 마리오 | 슈퍼 마리오 갤럭시 2 | 슈퍼 마리오 갤럭시 2 | https://store.nintendo.co.kr/70010000104194 | 확인 |
| 콘솔 | 마리오 | 슈퍼 마리오 64 DS | 슈퍼 마리오 64 DS ※ | https://www.gamemeca.com/view.php?gid=52608 | ※ 미확인 — 유통사 보도 기사만 확인(2차 출처) |
| 콘솔 | 마리오 | 마리오 카트 DS (“카트”로만 적혀 있어 DS 로 추정) | 마리오 카트 DS ※ | https://www.gamemeca.com/view.php?gid=52608 | ※ 미확인 — 작품 특정이 추정이며 기사(2차 출처)만 확인 |
| 콘솔 | 마리오 | 마리오 카트 월드 | 마리오 카트 월드 | https://store.nintendo.co.kr/beepaaaaakor | 확인 |
| 콘솔 | 마리오 | 뉴 슈퍼 마리오브라더스 | 뉴 슈퍼 마리오브라더스 ※ | — | ※ 미확인 — 공식 페이지·보도 모두 확인 못 함 |
| 콘솔 | 마리오 | 동키콩 바난자 | 동키콩 바난자 | https://store.nintendo.co.kr/7000200 | 확인 |
| 콘솔 | 마리오 | 마리오 vs. 동키콩(DS) | 마리오 vs. 동키콩 | https://store.nintendo.co.kr/70010000072193 | 확인 |
| 콘솔 | 마리오 | 슈퍼 마리오 메이커 2 | 슈퍼 마리오 메이커 2 | https://store.nintendo.co.kr/70010000020843 | 확인 |
| 콘솔 | 마리오 | 마리오 파티 (어느 작품인지 확인 필요) | 마리오 파티 ※ | — | ※ 미확인 — 시리즈 중 어느 작품인지 미확정 |
| 콘솔 | 마리오 | 요시 아일랜드 DS | 요시 아일랜드 DS ※ | — | ※ 미확인 — 공식 페이지·보도 모두 확인 못 함 |
| 콘솔 | 마리오 | 슈퍼 페이퍼 마리오 | 슈퍼 페이퍼 마리오 ※ | — | ※ 미확인 — 공식 페이지·보도 모두 확인 못 함 |
| 콘솔 | 마리오 | 페이퍼 마리오 1000년의 문 | 페이퍼 마리오 1000년의 문 | https://store.nintendo.co.kr/70010000079169 | 확인 |
| 콘솔 | 마리오 | 마리오&루이지 RPG 2 | 마리오&루이지 RPG 시간의 파트너 ※ | https://www.gamemeca.com/view.php?gid=86775 | ※ 미확인 — 한국닌텐도 보도자료를 인용한 기사(2차 출처) |
| 콘솔 | 별의 커비 | 별의 커비 디스커버리 | 별의 커비 디스커버리 | https://store.nintendo.co.kr/hacparzgakor | 확인 |
| 콘솔 | 별의 커비 | 별의 커비 도팡 일당의 습격 | 별의 커비 도팡 일당의 습격 ※ | — | ※ 미확인 — 공식 페이지·보도 모두 확인 못 함 |
| 콘솔 | 별의 커비 | 별의 커비 울트라 슈퍼 디럭스 | 별의 커비 울트라 슈퍼 디럭스 ※ | — | ※ 미확인 — 공식 페이지·보도 모두 확인 못 함 |
| 콘솔 | 별의 커비 | 털실 커비 이야기 | 털실 커비 이야기 ※ | https://www.gamemeca.com/view.php?gid=91962 | ※ 미확인 — 한국닌텐도 보도자료를 인용한 기사(2차 출처) |
| 콘솔 | 레이튼 교수 | 레이튼 교수와 이상한 마을 | 레이튼 교수와 이상한 마을 ※ | https://www.gamemeca.com/view.php?gid=72987 | ※ 미확인 — 한국닌텐도 보도자료를 인용한 기사(2차 출처) |
| 콘솔 | 레이튼 교수 | 레이튼 교수와 악마의 상자 | 레이튼 교수와 악마의 상자 ※ | — | ※ 미확인 — 공식 페이지·보도 모두 확인 못 함 |
| 콘솔 | 레이튼 교수 | 레이튼 교수와 최후의 시간여행 | 레이튼 교수와 최후의 시간여행 ※ | — | ※ 미확인 — 공식 페이지·보도 모두 확인 못 함 |
| 콘솔 | 리듬 | 리듬 세상 | 리듬 세상 ※ | https://www.gamemeca.com/view.php?gid=83934 | ※ 미확인 — DS 판 소개 기사만 확인(2차 출처) |
| 콘솔 | 리듬 | 리듬 천국 미라클 스타즈 | 리듬 천국 미라클 스타즈 | https://store.nintendo.co.kr/hacpbfltakor | 확인 |
| 콘솔 | 리듬 | 도와줘! 리듬 히어로 | 도와줘! 리듬 히어로 ※ | — | ※ 미확인 — 공식 페이지·보도 모두 확인 못 함 |
| 콘솔 | 그 외 닌텐도 | 놀러오세요 동물의 숲 | 놀러오세요 동물의 숲 ※ | https://www.gamemeca.com/view.php?gid=83193 | ※ 미확인 — 후속작 기사에 국내 판매량과 함께 언급(2차 출처) |
| 콘솔 | 그 외 닌텐도 | 엘레비츠: 카이와 제로의 신비한 모험 | 엘레비츠: 카이와 제로의 신비한 모험 ※ | — | ※ 미확인 — 공식 페이지·보도 모두 확인 못 함 |
| 콘솔 | 그 외 닌텐도 | 메이플스토리 DS | 메이플스토리DS ※ | https://www.gamemeca.com/view.php?gid=79968 | ※ 미확인 — 한국닌텐도 보도자료를 인용한 기사(2차 출처) |
| 콘솔 | 그 외 닌텐도 | 그려라 터치! 내가 만드는 세상 | 그려라 터치! 내가 만드는 세상 ※ | — | ※ 미확인 — 공식 페이지·보도 모두 확인 못 함 |
| 콘솔 | 그 외 닌텐도 | 짱구 크레용 대작전 | 짱구는 못말려 DS 알쏭달쏭 크레용 대작전! ※ | https://www.gamemeca.com/view.php?gid=70428 | ※ 미확인 — 유통사(대원미디어) 발표 기사(2차 출처) |
| 콘솔 | PlayStation | 라쳇 & 클랭크(PS2) — “PS2 로 했었음, 명칭 확인 필요” | 라쳇 & 클랭크 ※ | https://www.gamemeca.com/view.php?gid=47912 | ※ 미확인 — PS2 국내판은 2편 「라쳇 & 클랭크 : 공구전사 대박몰이」(2004) 기사만 확인. 어느 편인지 미확정 |

### 5차에서 비워 둔 자리

- 19개 선반의 관찰 메모: `.shelf-head .obs[data-observation=""]`
- 메인 카드 관찰 메모: `#game-maplestory .obs[data-observation=""]`

---

## 6차 (2026-11-24): 플레이한 게임을 가로로 흐르는 커버 스트림으로, 커버는 74종 전부

같은 브랜치에 쌓은 여섯 번째 변경입니다. 기존 파일은 여전히 건드리지 않았습니다. 게임 이름은 5차에서 확인한 공식 표기 그대로이고, ※(공식 페이지 직접 확인 못 함) 표시도 그대로입니다.

### 구조 (위에서 아래로)

1. **메인 카드(메이플스토리)** — 4차 카드를 유지하되 높이를 줄였고(커버 16:10, 본문 여백 축소), 2000일 출석 썸네일은 그대로입니다. 연결 기획서 라벨은 "이 게임에서 만든 것"으로 통일.
2. **요약 띠** — 74종 · 플랫폼 4 · 10년 · 장르 그룹 19. **장르 분포 바**는 칸이 버튼이 되어 누르면 아래 줄들에서 그 장르 타일만 밝아지고 나머지는 흐려집니다(다시 누르거나 "필터 해제"로 해제, 해제 전까지 줄은 멈춤). 호버 툴팁 "플랫폼 · 그룹 · N종" 유지.
3. **줄 A "작업으로 이어진 게임"** — 연결 작업이 있는 5개(메이플스토리 → 기획서 2개, PUBG: 배틀그라운드 → 기획서, 리버스: 1999 → 기획서, 몬길: STAR DIVE → AI 게임 '태그 보스전'의 원작, 칼파: 코스믹 심포니 → 참여작·대표 프로젝트)를 가로 카드 5장으로 한 줄에. 자동 흐름 없음. 타일 배지는 "기획서" / "AI 게임" / "참여작".
4. **줄 B·C·D 플랫폼별 커버 스트림** — PC(21) · 모바일(15) · 콘솔(38). 각 줄은 모든 커버가 좌우로 천천히 흐르는 무한 루프(CSS `@keyframes translateX`, 내용을 두 번 복제, 한 바퀴 60~90초, 줄마다 방향 교대). 마우스를 올리거나 포커스가 들어가면 멈춥니다. 왼쪽 끝에 플랫폼 이름과 종수 세로 라벨. 타일 순서: 연결 작업 있는 게임 → 기록 있는 게임 → 나머지(5차 그룹 순서). 타일 = 커버(3:4, 184px) + 이름(말줄임) + 기록 배지 + 연결 배지, 호버 시 살짝 확대.
   - **타일 클릭 → 팝오버**(`<dialog>`): 커버 크게, 정식 명칭, 플랫폼, 장르 그룹, 기록, 관찰 메모 자리(`data-observation=""`), 연결 작업 링크. Esc·바깥 클릭·× 로 닫힘, 닫히면 원래 타일로 포커스 복귀. 네이티브 dialog 라 포커스 트랩은 브라우저가 처리합니다.
   - **움직임 줄이기(`prefers-reduced-motion`)·터치 기기(`hover: none`)** 에서는 자동 흐름을 끄고 가로 스크롤 + 좌우 화살표로 같은 줄을 보여 줍니다. 화살표는 데스크톱에서도 항상 보이며, 누르면 그 줄은 수동 모드(흐름 정지 + 스크롤)가 됩니다. Tab 으로 타일에 들어와도 그 줄이 멈추고 타일이 보이도록 스크롤합니다. 탭이 비활성화되면 멈춥니다.
5. 장르 선반·플랫폼 탭·"더 보기"는 없앴습니다. 장르 정보는 분포 바 필터와 팝오버에만 남습니다.
6. 하단 작은 글씨(※ 안내 + 커버 출처 안내) 유지.

세로 길이: 5차 2,550px(선반 하나 펼친 상태) → 6차 1,773px(1440px 기준). 절반에는 못 미쳤습니다. 메인 카드 + 요약 띠 + 분포 바 + 줄 A + 스트림 3줄을 모두 두면 이 정도가 하한이었고, 더 줄이려면 메인 카드를 빼거나 스트림을 2줄로 합쳐야 합니다.

### 성능·접근성

- 커버 74장 × 2(복제) = 148 `<img>`, 모두 `loading="lazy" decoding="async"`, 복제본 타일은 `aria-hidden="true"` + `tabindex="-1"`. 커버 폴더 총 1.7MB(74장, 평균 23KB). 5차 대비 추가분은 약 0.6MB.
- 자동 흐름은 `transform` 만 애니메이션(레이아웃 변화 없음, `will-change: transform`).
- 타일은 `<button>`, 팝오버는 `<dialog aria-labelledby>`.

### 74종 이미지 출처 (①공식 스토어/사이트 ②공식 해외 페이지 ③Wikipedia 박스아트)

집계: ① 50 · ② 10 · ③ 11 · 타일 3. 모두 `lab/assets/games/covers/<slug>.webp`, 360×480. 가로·정사각 원본은 흐린 배경 위 레터박스, 세로 원본은 3:4 크롭. 닌텐도 코리아 스토어 패키지 이미지 중 흰 여백이 큰 것은 여백을 잘라 썼습니다.

| 플랫폼 | 게임 | 파일 | 구분 | 출처 | 비고 |
|---|---|---|---|---|---|
| 메인 | 메이플스토리 | `maplestory.webp` | ① | 메이플스토리 공식 사이트 og:image (2차에서 받음) https://maplestory.nexon.com/ | 가로/정사각 원본 → 레터박스 |
| PC | 리그 오브 레전드 | `lol.webp` | ① | https://www.leagueoflegends.com/ko-kr/ og:image |  |
| PC | Dota 2 | `dota2.webp` | ① | Steam 세로 캡슐 https://store.steampowered.com/app/570/ |  |
| PC | 전략적 팀 전투 | `tft.webp` | ① | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id1480616748 | 가로/정사각 원본 → 레터박스 |
| PC | PUBG: 배틀그라운드 | `pubg.webp` | ① | Steam 세로 캡슐 https://store.steampowered.com/app/578080/ |  |
| PC | 오버워치 | `overwatch.webp` | ① | Steam 세로 캡슐 https://store.steampowered.com/app/2357570/ |  |
| PC | Apex 레전드 | `apex-legends.webp` | ① | Steam KR 세로 캡슐 https://store.steampowered.com/app/1172470/ |  |
| PC | Vampire Survivors | `vampire-survivors.webp` | ① | Steam 세로 캡슐 https://store.steampowered.com/app/1794680/ |  |
| PC | Enter the Gungeon | `enter-the-gungeon.webp` | ① | Steam 세로 캡슐 https://store.steampowered.com/app/311690/ |  |
| PC | Brotato | `brotato.webp` | ① | Steam KR 세로 캡슐 https://store.steampowered.com/app/1942280/ |  |
| PC | Spelunky 2 | `spelunky-2.webp` | ① | Steam KR 세로 캡슐 https://store.steampowered.com/app/418530/ |  |
| PC | Cult of the Lamb | `cult-of-the-lamb.webp` | ① | Steam KR 세로 캡슐 https://store.steampowered.com/app/1313140/ |  |
| PC | Ship of Fools | `ship-of-fools.webp` | ① | Steam KR 세로 캡슐 https://store.steampowered.com/app/1286580/ |  |
| PC | Hollow Knight: Silksong | `silksong.webp` | ① | Steam 세로 캡슐 https://store.steampowered.com/app/1030300/ |  |
| PC | 산나비 | `sanabi.webp` | ① | Steam 세로 캡슐 https://store.steampowered.com/app/1562700/ |  |
| PC | Baba Is You | `baba-is-you.webp` | ① | Steam 세로 캡슐 https://store.steampowered.com/app/736260/ |  |
| PC | 팀파이트 매니저 | `teamfight-manager.webp` | ① | Steam KR 세로 캡슐 https://store.steampowered.com/app/1372810/ |  |
| PC | 러브 딜리버리 | `love-delivery.webp` | ① | Steam 세로 캡슐 https://store.steampowered.com/app/1817940/ |  |
| PC | 썸썸 편의점 | `sumsum-convenience.webp` | ① | Steam KR 세로 캡슐 https://store.steampowered.com/app/1217390/ |  |
| PC | 기적의 분식집 | `miracle-snack-shop.webp` | ① | Steam KR 세로 캡슐 https://store.steampowered.com/app/995460/ |  |
| PC | 방구석에 인어아가씨 | `mermaid-in-my-room.webp` | ① | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id904882274 | 가로/정사각 원본 → 레터박스 |
| PC | 칼파: 코스믹 심포니 | `kalpa.webp` | ① | Steam 세로 캡슐 https://store.steampowered.com/app/2717010/ |  |
| 모바일 | 리버스: 1999 | `reverse1999.webp` | ① | https://re1999.bluepoch.com/ og:image |  |
| 모바일 | 승리의 여신: 니케 | `nikke.webp` | ① | https://nikke-kr.com/ og:image |  |
| 모바일 | 블루 아카이브 | `blue-archive.webp` | ① | https://bluearchive.nexon.com/ og:image |  |
| 모바일 | 원신 | `genshin.webp` | ① | https://genshin.hoyoverse.com/ko/home og:image |  |
| 모바일 | 트릭컬 리바이브 | `trickcal-revive.webp` | ① | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id6443824730 | 가로/정사각 원본 → 레터박스 |
| 모바일 | 젠레스 존 제로 | `zenless-zone-zero.webp` | ① | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id1606356401 | 가로/정사각 원본 → 레터박스 |
| 모바일 | 스텔라 소라 | `stella-sora.webp` | ① | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id6738407268 | 가로/정사각 원본 → 레터박스 |
| 모바일 | 헤븐 번즈 레드 | `heaven-burns-red.webp` | ① | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id1576831351 | 가로/정사각 원본 → 레터박스 |
| 모바일 | 몬길: STAR DIVE | `mongil-stardive.webp` | ① | 몬길: STAR DIVE 공식 사이트 og:image https://stardive.netmarble.com/ | 가로/정사각 원본 → 레터박스 |
| 모바일 | 쿠키런: 킹덤 | `cookierun-kingdom.webp` | ① | https://www.cookierun-kingdom.com/ko/ og:image |  |
| 모바일 | 세븐나이츠 키우기 | `seven-knights-idle.webp` | ① | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id1658717149 | 가로/정사각 원본 → 레터박스 |
| 모바일 | Mini Warriors ※ | `mini-warriors.webp` | 타일 | — | ①②③ 모두 실패: Google Play 스토어 페이지 og:image: HTTP 404 |
| 모바일 | 브롤스타즈 | `brawl-stars.webp` | ① | https://supercell.com/en/games/brawlstars/ og:image |  |
| 모바일 | Pokémon GO | `pokemon-go.webp` | ① | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id1094591345 | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 젤다의 전설 브레스 오브 더 와일드 | `zelda-botw.webp` | ① | 닌텐도 코리아 스토어 https://store.nintendo.co.kr/70010000009367 |  |
| 콘솔 | 젤다의 전설 지혜의 투영 | `zelda-echoes-of-wisdom.webp` | ① | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/70010000084620 | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 젤다의 전설 몽환의 모래시계 ※ | `zelda-phantom-hourglass.webp` | ② | nintendo.co.jp DS 소프트 페이지 https://www.nintendo.co.jp/ds/azej/ | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 젤다의 전설 꿈꾸는 섬 | `zelda-links-awakening.webp` | ① | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/70010000022823 | 가로/정사각 원본 → 레터박스 |
| 콘솔 | Pokémon LEGENDS 아르세우스 | `pokemon-legends-arceus.webp` | ① | 닌텐도 코리아 스토어 https://store.nintendo.co.kr/70010000039947 |  |
| 콘솔 | 포켓몬스터DP 디아루가·펄기아 / 포켓몬스터Pt 기라티나 ※ | `pokemon-dp-pt.webp` | ② | nintendo.co.jp DS 소프트 페이지 https://www.nintendo.co.jp/ds/adaj/ | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 포켓몬스터소드 | `pokemon-sword.webp` | ① | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/70010000026251 | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 포켓몬스터바이올렛 | `pokemon-violet.webp` | ① | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/70010000053973 | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 슈퍼 마리오 오디세이 | `mario-odyssey.webp` | ① | 닌텐도 코리아 스토어 https://store.nintendo.co.kr/70010000009372 |  |
| 콘솔 | 슈퍼 마리오 갤럭시 2 | `mario-galaxy-2.webp` | ① | 닌텐도 코리아 스토어 https://store.nintendo.co.kr/70010000104194 |  |
| 콘솔 | 슈퍼 마리오 64 DS ※ | `super-mario-64-ds.webp` | ② | nintendo.co.jp DS 소프트 페이지 https://www.nintendo.co.jp/ds/asmj/ | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 마리오 카트 DS ※ | `mario-kart-ds.webp` | ② | nintendo.co.jp DS 소프트 페이지 https://www.nintendo.co.jp/ds/amcj/ | 가로/정사각 원본 → 레터박스 · 흰 여백 제거 |
| 콘솔 | 마리오 카트 월드 | `mario-kart-world.webp` | ① | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/beepaaaaakor | 흰 여백 제거 |
| 콘솔 | 뉴 슈퍼 마리오브라더스 ※ | `new-super-mario-bros.webp` | ③ | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/New_Super_Mario_Bros. (파일: https://en.wikipedia.org/wiki/File%3ANewSuperMarioBrothers.jpg) | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 동키콩 바난자 | `donkey-kong-bananza.webp` | ① | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/7000200 | 흰 여백 제거 |
| 콘솔 | 마리오 vs. 동키콩 | `mario-vs-donkey-kong.webp` | ① | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/70010000072193 | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 슈퍼 마리오 메이커 2 | `super-mario-maker-2.webp` | ① | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/70010000020843 | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 마리오 파티 ※ | `mario-party.webp` | 타일 | — | ①②③ 모두 실패:  |
| 콘솔 | 요시 아일랜드 DS ※ | `yoshis-island-ds.webp` | ③ | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/Yoshi's_Island_DS (파일: https://en.wikipedia.org/wiki/File%3AYoshi'sIslandDScover.PNG) | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 슈퍼 페이퍼 마리오 ※ | `super-paper-mario.webp` | ② | nintendo.co.jp Wii 소프트 페이지 https://www.nintendo.co.jp/wii/r8pj/ | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 페이퍼 마리오 1000년의 문 | `paper-mario-ttyd.webp` | ① | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/70010000079169 | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 마리오&루이지 RPG 시간의 파트너 ※ | `mario-luigi-partners-in-time.webp` | ② | nintendo.co.jp DS 소프트 페이지 https://www.nintendo.co.jp/ds/armj/ | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 별의 커비 디스커버리 | `kirby-forgotten-land.webp` | ① | 닌텐도 코리아 스토어 https://store.nintendo.co.kr/hacparzgakor |  |
| 콘솔 | 별의 커비 도팡 일당의 습격 ※ | `kirby-squeak-squad.webp` | ③ | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/Kirby%3A_Squeak_Squad (파일: https://en.wikipedia.org/wiki/File%3AKirby%20-%20Squeak%20Squad%20Coverart.png) | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 별의 커비 울트라 슈퍼 디럭스 ※ | `kirby-super-star-ultra.webp` | ③ | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/Kirby_Super_Star_Ultra (파일: https://en.wikipedia.org/wiki/File%3AKirbySuperStarUltra.png) | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 털실 커비 이야기 ※ | `kirbys-epic-yarn.webp` | ② | nintendo.co.jp Wii 소프트 페이지 https://www.nintendo.co.jp/wii/rk5j/ | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 레이튼 교수와 이상한 마을 ※ | `layton-curious-village.webp` | ② | Level-5 레이튼 시리즈 공식 페이지 https://www.layton.jp/fushigi/ | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 레이튼 교수와 악마의 상자 ※ | `layton-diabolical-box.webp` | ② | Level-5 레이튼 시리즈 공식 페이지 https://www.layton.jp/akuma/ | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 레이튼 교수와 최후의 시간여행 ※ | `layton-unwound-future.webp` | ③ | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/Professor_Layton_and_the_Unwound_Future (파일: https://en.wikipedia.org/wiki/File%3AProfessor%20Layton%20and%20the%20Unwound%20Future.png) | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 리듬 세상 ※ | `rhythm-heaven-ds.webp` | ③ | Wikipedia(en) 문서 대표 이미지(박스아트) https://en.wikipedia.org/wiki/Rhythm_Heaven | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 리듬 천국 미라클 스타즈 | `rhythm-heaven-megamix.webp` | ① | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/hacpbfltakor | 흰 여백 제거 |
| 콘솔 | 도와줘! 리듬 히어로 ※ | `rhythm-heaven-fever.webp` | ② | nintendo.co.jp Wii 소프트 페이지 https://www.nintendo.co.jp/wii/somj/ | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 놀러오세요 동물의 숲 ※ | `animal-crossing-wild-world.webp` | ③ | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Animal_Crossing:_Wild_World (파일: https://en.wikipedia.org/wiki/File:Animal_Crossing_Wild_World_cover.png) | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 엘레비츠: 카이와 제로의 신비한 모험 ※ | `elebits-ds.webp` | ③ | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/Elebits%3A_The_Adventures_of_Kai_and_Zero (파일: https://en.wikipedia.org/wiki/File%3AElebits%20-%20The%20Adventures%20of%20Kai%20and%20Zero%20-%20cover.png) | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 메이플스토리DS ※ | `maplestory-ds.webp` | ③ | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/MapleStory_DS (파일: https://en.wikipedia.org/wiki/File%3AMapleStoryDS.jpg) | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 그려라 터치! 내가 만드는 세상 ※ | `drawn-to-life.webp` | ③ | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/Drawn_to_Life (파일: https://en.wikipedia.org/wiki/File%3ADrawn%20to%20Life%20coverart.jpg) | 가로/정사각 원본 → 레터박스 |
| 콘솔 | 짱구는 못말려 DS 알쏭달쏭 크레용 대작전! ※ | `shin-chan-ds.webp` | 타일 | — | ①②③ 모두 실패: Wikipedia(ja) 문서 대표 이미지(박스아트): Unexpected end of JSON input | Wikipedia(en) 문서 대표 이미지(박스아트): Unexpected end of JSON input | wiki infobox: Unexpected token 'Y',  |
| 콘솔 | 라쳇 & 클랭크 ※ | `ratchet-clank-ps2.webp` | ③ | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/Ratchet_%26_Clank_(2002_video_game) (파일: https://en.wikipedia.org/wiki/File%3ARaCbox.jpg) |  |

### 끝내 못 구한 3종 (타이포 타일)

- **Mini Warriors** — App Store 에는 후속판 "Mini Warriors Reborn!"만 남아 있고(다른 제품), Google Play 원작 페이지는 찾지 못함, Wikipedia 문서 없음.
- **마리오 파티** — 시리즈 중 어느 작품인지 미확정이라 특정 작품의 이미지를 붙일 수 없음.
- **짱구는 못말려 DS 알쏭달쏭 크레용 대작전!** — 한국닌텐도/닌텐도 공식 페이지 없음, ja·en Wikipedia 문서에 박스아트 없음.

5차의 타일 4장 중 레이튼 교수와 이상한 마을(Level-5 공식 페이지 ②), 리듬 세상(Wikipedia ③), 놀러오세요 동물의 숲(Wikipedia ③), 라쳇 & 클랭크(Wikipedia ③, 2002년 PS2 원작 박스아트)는 모두 이미지로 바꿨습니다.

### 연결 작업 매핑

| 게임 | 배지 | 연결 |
|---|---|---|
| 메이플스토리 | 기획서 | `#pdf-maple-party` 파티 모집 게시판 · `#pdf-maple-observatory` 월묘의 까막산 천문대 |
| PUBG: 배틀그라운드 | 기획서 | `#pdf-pubg` 전리품 상자 파츠 루팅 프리셋 |
| 리버스: 1999 | 기획서 | `#pdf-reverse1999` 계정 단위 신규 성장 시스템 ‘잔향’ |
| 몬길: STAR DIVE | AI 게임 | `#ai-game` AI 게임 ‘태그 보스전’의 원작 |
| 칼파: 코스믹 심포니 | 참여작 | `#projects` 대표 프로젝트 · 스토리 연출·FCG 기획 |

### 6차에서 비워 둔 자리

- 메인 카드 관찰 메모: `#game-maplestory .obs[data-observation=""]`
- 팝오버 관찰 메모: `#gd-obs[data-observation=""]` (현재는 모든 게임이 같은 자리를 공유합니다. 게임별 메모가 생기면 타일의 `data-*` 로 옮기면 됩니다.)

---

## 7차 (2026-11-24): 스트림 드래그 · 필터 숨김 방식 · 가로 라벨

같은 브랜치에 쌓은 일곱 번째 변경입니다. 기존 파일은 여전히 건드리지 않았습니다.

### 스트림 조작 (드래그 · 관성 · 화살표 · 키보드 · 자동 흐름)

- **무한 루프는 유지**했습니다. 6차의 CSS `@keyframes` 대신 **JS 가 한 변수(`x`)로 위치를 들고** `requestAnimationFrame` 마다 `translate3d` 로 적용합니다. 자동 흐름·드래그·관성·화살표·키보드가 모두 같은 `x` 를 움직이므로 복제본과 어긋나지 않고, 한 바퀴(복제본 절반 폭) 경계를 넘으면 `x` 를 그만큼 보정해 끊김 없이 이어집니다.
- **드래그**: pointer events(마우스·터치 공용). `pointerdown` 뒤 6px 이상 움직이면 드래그로 보고 포인터를 캡처하며, 놓을 때 직전 속도를 관성으로 써서 가볍게 감속합니다(초당 약 88% 감속, 최대 1800px/s). 6px 이상 움직인 뒤의 클릭은 캡처 단계에서 막아 팝오버가 열리지 않습니다. 6px 미만이면 그대로 타일 클릭으로 전달됩니다.
- **화살표**: 한 번에 타일 3장 폭(약 450px)을 420ms 이징으로 이동. 데스크톱에서도 항상 표시. 줄에 포커스가 있을 때 ←/→ 도 같은 동작.
- **자동 흐름**: 호버 중에는 멈추고, 드래그·화살표·키보드로 건드린 줄은 **마우스가 떠나고 4초 뒤 현재 위치에서** 다시 천천히 흐릅니다(한 바퀴 약 75초, 줄마다 방향 교대). 탭이 비활성화되면 멈춥니다. `prefers-reduced-motion` 또는 `hover: none` 기기는 자동 흐름 없이 드래그·화살표만.
- **스크롤바 제거**: `scrollbar-width: none` + `::-webkit-scrollbar { display: none }`. 스크롤은 드래그·화살표·키보드로만.

### 장르 필터

- 필터를 켜면 **해당 장르 타일만 남기고 나머지는 `hidden`** 으로 DOM 에서 숨깁니다(복제본도 숨김, 줄은 단일 구간 모드로 전환되어 양 끝에서 멈춤). 해당 장르가 없는 줄은 "이 플랫폼에는 없음" 한 줄로, 작업으로 이어진 게임 줄도 같은 방식. 남은 타일이 한 화면에 들어오면 화살표와 가장자리 그라데이션을 숨깁니다. 필터 중 자동 흐름 정지.
- 장르 키는 **플랫폼 접두어 포함**(`pc-리듬` / `console-리듬`)이라 PC 리듬과 콘솔 리듬이 섞이지 않습니다. 분포 바 19칸과 칩 19개는 같은 키를 가리키며 어느 쪽을 눌러도 함께 활성화됩니다. 활성 칩은 액센트 채움, 분포 바의 활성 칸은 테두리 강조 + 나머지 칸 흐림. 맨 앞 "전체 74" 칩이 기본 활성.
- 상태 줄(분포 바 위): "전체 74종 보는 중" / "수집형 RPG · 9종 보는 중 ✕". URL 해시에는 넣지 않습니다.

### 라벨

- 세로 회전 라벨과 왼쪽 회색 띠를 없애고, 각 줄 위 왼쪽에 **"PC · 21종"** 형태의 가로 라벨(섹션 영문 라벨과 같은 11.5px 대문자·자간 .12em 톤, 종수만 액센트 굵게)을 두었습니다. 콘솔 줄은 그 옆에 기종 목록 작은 글씨, 오른쪽 끝에 "드래그 · 화살표 · ←/→" 힌트(640px 이하에서는 숨김). 세 줄의 스타일·간격이 같고 줄은 전체 폭을 씁니다. 1440·1024·390 에서 확인.

### 동작 확인 방법 (Playwright, Chrome 채널)

데스크톱 1440×900 과 모바일 390×844(터치) 두 환경에서 스크립트로 확인했습니다.

| 항목 | 방법 | 결과 (데스크톱 / 모바일) |
|---|---|---|
| 자동 흐름 | 1초 간격으로 `transform` 의 x 읽기 | −77 → −120 (흐름) / 0 → 0 (터치 기기라 꺼짐) |
| 드래그 | `mouse.down` → 20px씩 10번 `move` → `up`, 전후 x 비교 | −320 → −358 (관성으로 조금 더) / −200 → −235 |
| 드래그 뒤 클릭 억제 | 120px 드래그 후 팝오버 `open` 확인 | false / false |
| 짧은 클릭·탭 | 타일 중앙 `mouse.down/up` 또는 `touchscreen.tap` | 팝오버 열림(리그 오브 레전드) / 열림 |
| 화살표·키보드 | next 클릭 → x, 줄 포커스 후 ← → x | −600 → −1051 → −601 / −433 → −841 → −433 |
| 재개 | 마우스를 치우고 4.6초·5.6초에 x 읽기 | 다시 흐름 / (터치 기기 해당 없음) |
| 필터 | 칩 "수집형 RPG" 클릭 후 줄별 보이는 타일 수 | [0, 9, 0], 상태 "수집형 RPG · 9종 보는 중", PC·콘솔 줄 "없음" 표시, 작업 줄 2장 |
| 분포 바 칸 | "마리오" 칸 클릭 → 칩 활성 동기화 | [0, 0, 14], 활성 칩 `console-마리오` |
| 해제 | ✕ 클릭 | [21, 15, 38] |
| 스크롤바 | `scrollbar-width` 계산값 | none / none |
| JS 오류 | pageerror·console.error 수집 | 0 / 0 |

---

## 8차 (2026-11-24): 커버 정리 · 리듬 통합 · 마리오 파티 DS · 게임 밖 활동 챕터형 · AI 캐러셀 깨짐 수정

같은 브랜치에 쌓은 여덟 번째 변경입니다. 기존 파일은 여전히 건드리지 않았습니다.

### 커버 교체 (가로 키아트 레터박스 → 바른 비율의 공식 이미지)

- **모바일 15종 전부 → 공식 앱 아이콘**(App Store KR `artworkUrl` 1024 원본 → 512×512 WebP). 모바일 줄 타일은 **1:1 정사각 + 둥근 모서리(22%)**, 높이는 다른 줄과 같은 184px(모바일 폭에서 165px). 작업으로 이어진 게임 줄의 리버스: 1999 · 몬길: STAR DIVE 카드와 팝오버도 정사각으로 바뀝니다. Mini Warriors 는 스토어에 없어 **주인 제공 아이콘**을 썼습니다.
- **콘솔 29종 → 박스아트**. 닌텐도 KR 스토어와 nintendo.com(US) 제품 페이지의 og:image 는 모두 16:9 키아트라 박스아트로 쓸 수 없어, **Wikipedia 문서의 박스아트 파일(③)** 을 썼습니다. DS·GBA·Wii 패키지는 거의 정사각(세로 1.2배 미만)이라 3:4 틀에 **박스 대표색을 어둡게 한 단색 패드** 위에 원본 비율 그대로 올렸습니다(흐린 배경 없음). 세로형 박스(슈퍼 페이퍼 마리오, 털실 커비 이야기, 페이퍼 마리오 1000년의 문, 리듬 히어로)는 3:4 크롭. 짱구는 못말려 DS 는 **주인 제공 박스아트**.
- **PC 2종**: 리그 오브 레전드는 Riot 공식 세로 키아트를 찾지 못해 **로고(Wikimedia Commons SVG)를 가운데 둔 단색 타일**(Riot 남색 `#0a1428`), 방구석에 인어아가씨(모바일 앱이지만 PC 줄)는 **앱 아이콘을 가운데 둔 단색 타일**. 나머지 PC 19종은 Steam 세로 캡슐 그대로.
- 메인 카드(메이플스토리)는 가로 이미지가 맞으니 그대로. 커버 폴더 총 2.0MB(74장).

**교체 전/후: 46장** (모바일 15 / 콘솔 29 / PC 2). 구분: ① 15 · ③ 29 · 주인 제공 2. **글자 타일 0.**

여전히 세로형 박스아트가 아닌 것(가로·정사각 원본을 단색 패드에 올린 것): 젤다의 전설 지혜의 투영(en 위키 infobox 가 가로 키아트), 포켓몬스터소드·바이올렛·DP(위키 infobox 가 두 버전 패키지를 나란히 놓은 가로 합성), 마리오 vs. 동키콩(2024 리메이크 Switch 아이콘 — 문서의 박스아트 파일은 GBA 원작), 그 밖의 DS 패키지 20종(원래 거의 정사각).

| 플랫폼 | 게임 | 파일 | 교체 전 (6차) | 교체 후 (8차) | 구분 | 처리 |
|---|---|---|---|---|---|---|
| 모바일 | 리버스: 1999 | `reverse1999.webp` | https://re1999.bluepoch.com/ og:image (레터박스) | App Store KR 앱 아이콘(1024) https://apps.apple.com/kr/app/id6449023119 | ① | 1:1 아이콘 |
| 모바일 | 승리의 여신: 니케 | `nikke.webp` | https://nikke-kr.com/ og:image (레터박스) | App Store KR 앱 아이콘(1024) https://apps.apple.com/kr/app/id1585915174 | ① | 1:1 아이콘 |
| 모바일 | 블루 아카이브 | `blue-archive.webp` | https://bluearchive.nexon.com/ og:image (레터박스) | App Store KR 앱 아이콘(1024) https://apps.apple.com/kr/app/id1571873795 | ① | 1:1 아이콘 |
| 모바일 | 원신 | `genshin.webp` | https://genshin.hoyoverse.com/ko/home og:image (크롭) | App Store KR 앱 아이콘(1024) https://apps.apple.com/kr/app/id1517783697 | ① | 1:1 아이콘 |
| 모바일 | 트릭컬 리바이브 | `trickcal-revive.webp` | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id6443824730 (letterbox) | App Store KR 앱 아이콘(1024) https://apps.apple.com/kr/app/id6443824730 | ① | 1:1 아이콘 |
| 모바일 | 젠레스 존 제로 | `zenless-zone-zero.webp` | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id1606356401 (letterbox) | App Store KR 앱 아이콘(1024) https://apps.apple.com/kr/app/id1606356401 | ① | 1:1 아이콘 |
| 모바일 | 스텔라 소라 | `stella-sora.webp` | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id6738407268 (letterbox) | App Store KR 앱 아이콘(1024) https://apps.apple.com/kr/app/id6738407268 | ① | 1:1 아이콘 |
| 모바일 | 헤븐 번즈 레드 | `heaven-burns-red.webp` | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id1576831351 (letterbox) | App Store KR 앱 아이콘(1024) https://apps.apple.com/kr/app/id1576831351 | ① | 1:1 아이콘 |
| 모바일 | 몬길: STAR DIVE | `mongil-stardive.webp` | 몬길: STAR DIVE 공식 사이트 og:image https://stardive.netmarble.com/ (letterbox) | App Store KR 앱 아이콘(1024) https://apps.apple.com/kr/app/id6483252725 | ① | 1:1 아이콘 |
| 모바일 | 쿠키런: 킹덤 | `cookierun-kingdom.webp` | https://www.cookierun-kingdom.com/ko/ og:image (크롭) | App Store KR 앱 아이콘(1024) https://apps.apple.com/kr/app/id1509450845 | ① | 1:1 아이콘 |
| 모바일 | 세븐나이츠 키우기 | `seven-knights-idle.webp` | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id1658717149 (letterbox) | App Store KR 앱 아이콘(1024) https://apps.apple.com/kr/app/id1658717149 | ① | 1:1 아이콘 |
| 모바일 | 전략적 팀 전투 | `tft.webp` | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id1480616748 (letterbox) | App Store KR 앱 아이콘(1024) https://apps.apple.com/kr/app/id1480616748 | ① | 1:1 아이콘 |
| 모바일 | 브롤스타즈 | `brawl-stars.webp` | https://supercell.com/en/games/brawlstars/ og:image (크롭) | App Store KR 앱 아이콘(1024) https://apps.apple.com/kr/app/id1229016807 | ① | 1:1 아이콘 |
| 모바일 | Pokémon GO | `pokemon-go.webp` | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id1094591345 (letterbox) | App Store KR 앱 아이콘(1024) https://apps.apple.com/kr/app/id1094591345 | ① | 1:1 아이콘 |
| 모바일 | Mini Warriors ※ | `mini-warriors.webp` | 글자 타일 | 주인이 직접 제공한 앱 아이콘 owner-images/mini-warriors-icon.png | 주인 제공 | 1:1 아이콘 |
| PC | 리그 오브 레전드 | `lol.webp` | https://www.leagueoflegends.com/ko-kr/ og:image (가로 키아트, 레터박스) | Wikimedia Commons 파일 https://commons.wikimedia.org/wiki/File:League%20of%20Legends%202019%20vector.svg | ③ | 로고 단색 타일 |
| PC | 방구석에 인어아가씨 | `mermaid-in-my-room.webp` | App Store KR 앱 아이콘 https://apps.apple.com/kr/app/id904882274 (letterbox) | App Store KR 앱 아이콘(1024) https://apps.apple.com/kr/app/id904882274 | ① | 아이콘 단색 타일 |
| 콘솔 | 젤다의 전설 지혜의 투영 | `zelda-echoes-of-wisdom.webp` | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/70010000084620 (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/The_Legend_of_Zelda%3A_Echoes_of_Wisdom (파일: https://en.wikipedia.org/wiki/File%3AThe%20Legend%20of%20Zelda%20%E2%80%93%20Echoes%20of%20Wisdom.jpg) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 젤다의 전설 꿈꾸는 섬 | `zelda-links-awakening.webp` | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/70010000022823 (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/The_Legend_of_Zelda%3A_Link's_Awakening_(2019_video_game) (파일: https://en.wikipedia.org/wiki/File%3AThe%20Legend%20of%20Zelda%20Link's%20Awakening%20(2019%20video%20game).jpg) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 젤다의 전설 몽환의 모래시계 ※ | `zelda-phantom-hourglass.webp` | nintendo.co.jp DS 소프트 페이지 https://www.nintendo.co.jp/ds/azej/ (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/The_Legend_of_Zelda%3A_Phantom_Hourglass (파일: https://en.wikipedia.org/wiki/File%3AThe%20Legend%20of%20Zelda%20Phantom%20Hourglass%20Game%20Cover.jpg) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 포켓몬스터DP 디아루가·펄기아 / 포켓몬스터Pt 기라티나 ※ | `pokemon-dp-pt.webp` | nintendo.co.jp DS 소프트 페이지 https://www.nintendo.co.jp/ds/adaj/ (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Pok%C3%A9mon_Diamond_and_Pearl (파일: https://en.wikipedia.org/wiki/File%3APokemonDiamondPearlBoxArt.jpg) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 포켓몬스터소드 | `pokemon-sword.webp` | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/70010000026251 (letterbox) | Wikipedia(ko) 문서 박스아트 파일 https://ko.wikipedia.org/wiki/%ED%8F%AC%EC%BC%93%EB%AA%AC%EC%8A%A4%ED%84%B0_%EC%86%8C%EB%93%9C%C2%B7%EC%8B%A4%EB%93%9C (파일: https://ko.wikipedia.org/wiki/File%3A%ED%8F%AC%EC%BC%93%EB%AA%AC%EC%8A%A4%ED%84%B0_%EC%86%8C%EB%93%9C_%EC%8B%A4%EB%93%9C.png) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 포켓몬스터바이올렛 | `pokemon-violet.webp` | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/70010000053973 (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Pok%C3%A9mon_Scarlet_and_Violet (파일: https://en.wikipedia.org/wiki/File%3APok%C3%A9mon_Scarlet_and_Violet_banner.png) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 슈퍼 마리오 64 DS ※ | `super-mario-64-ds.webp` | nintendo.co.jp DS 소프트 페이지 https://www.nintendo.co.jp/ds/asmj/ (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Super_Mario_64_DS (파일: https://en.wikipedia.org/wiki/File%3ASuper%20Mario%2064%20DS%20Coverart.png) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 마리오 카트 DS ※ | `mario-kart-ds.webp` | nintendo.co.jp DS 소프트 페이지 https://www.nintendo.co.jp/ds/amcj/ (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Mario_Kart_DS (파일: https://en.wikipedia.org/wiki/File%3AMario%20Kart%20DS%20cover.jpg) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 뉴 슈퍼 마리오브라더스 ※ | `new-super-mario-bros.webp` | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/New_Super_Mario_Bros. (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/New_Super_Mario_Bros. (파일: https://en.wikipedia.org/wiki/File%3ANewSuperMarioBrothers.jpg) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 마리오 vs. 동키콩 | `mario-vs-donkey-kong.webp` | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/70010000072193 (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Mario_vs._Donkey_Kong_(2024_video_game) (파일: https://en.wikipedia.org/wiki/File%3AMario_vs._Donkey_Kong_Nintendo_Switch_remake_icon.jpg) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 슈퍼 마리오 메이커 2 | `super-mario-maker-2.webp` | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/70010000020843 (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Super_Mario_Maker_2 (파일: https://en.wikipedia.org/wiki/File%3ASuper%20Mario%20Maker%202.jpg) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 마리오 파티 DS | `mario-party.webp` | 글자 타일 | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Mario_Party_DS (파일: https://en.wikipedia.org/wiki/File%3AMario_Party_DS_US_cover.jpg) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 요시 아일랜드 DS ※ | `yoshis-island-ds.webp` | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/Yoshi's_Island_DS (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Yoshi's_Island_DS (파일: https://en.wikipedia.org/wiki/File%3AYoshi'sIslandDScover.PNG) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 슈퍼 페이퍼 마리오 ※ | `super-paper-mario.webp` | nintendo.co.jp Wii 소프트 페이지 https://www.nintendo.co.jp/wii/r8pj/ (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Super_Paper_Mario (파일: https://en.wikipedia.org/wiki/File%3ASuper%20Paper%20Mario%20cover.jpg) | ③ | 3:4 크롭 |
| 콘솔 | 페이퍼 마리오 1000년의 문 | `paper-mario-ttyd.webp` | 닌텐도 코리아 스토어 제품 이미지 https://store.nintendo.co.kr/70010000079169 (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Paper_Mario%3A_The_Thousand-Year_Door (파일: https://en.wikipedia.org/wiki/File%3APaper%20Mario%20The%20Thousand-Year%20Door%20(artwork).jpg) | ③ | 3:4 크롭 |
| 콘솔 | 마리오&루이지 RPG 시간의 파트너 ※ | `mario-luigi-partners-in-time.webp` | nintendo.co.jp DS 소프트 페이지 https://www.nintendo.co.jp/ds/armj/ (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Mario_%26_Luigi%3A_Partners_in_Time (파일: https://en.wikipedia.org/wiki/File%3AMario%20%26%20Luigi%20-%20Parnters%20In%20Time%20(box%20art).jpg) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 별의 커비 도팡 일당의 습격 ※ | `kirby-squeak-squad.webp` | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/Kirby%3A_Squeak_Squad (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Kirby%3A_Squeak_Squad (파일: https://en.wikipedia.org/wiki/File%3AKirby%20-%20Squeak%20Squad%20Coverart.png) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 별의 커비 울트라 슈퍼 디럭스 ※ | `kirby-super-star-ultra.webp` | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/Kirby_Super_Star_Ultra (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Kirby_Super_Star_Ultra (파일: https://en.wikipedia.org/wiki/File%3AKirbySuperStarUltra.png) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 털실 커비 이야기 ※ | `kirbys-epic-yarn.webp` | nintendo.co.jp Wii 소프트 페이지 https://www.nintendo.co.jp/wii/rk5j/ (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Kirby's_Epic_Yarn (파일: https://en.wikipedia.org/wiki/File%3AKirby's%20Epic%20Yarn%20Title.png) | ③ | 3:4 크롭 |
| 콘솔 | 레이튼 교수와 이상한 마을 ※ | `layton-curious-village.webp` | Level-5 레이튼 시리즈 공식 페이지 https://www.layton.jp/fushigi/ (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Professor_Layton_and_the_Curious_Village (파일: https://en.wikipedia.org/wiki/File%3AProfessor%20Layton%20and%20the%20Curious%20Village%20NA%20Boxart.JPG) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 레이튼 교수와 악마의 상자 ※ | `layton-diabolical-box.webp` | Level-5 레이튼 시리즈 공식 페이지 https://www.layton.jp/akuma/ (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Professor_Layton_and_the_Diabolical_Box (파일: https://en.wikipedia.org/wiki/File%3ADiabolical%20Box.jpg) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 레이튼 교수와 최후의 시간여행 ※ | `layton-unwound-future.webp` | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/Professor_Layton_and_the_Unwound_Future (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Professor_Layton_and_the_Unwound_Future (파일: https://en.wikipedia.org/wiki/File%3AProfessor%20Layton%20and%20the%20Unwound%20Future.png) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 리듬 세상 ※ | `rhythm-heaven-ds.webp` | Wikipedia(en) 문서 대표 이미지(박스아트) https://en.wikipedia.org/wiki/Rhythm_Heaven (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Rhythm_Heaven_(video_game) (파일: https://en.wikipedia.org/wiki/File%3ARhythmHeaven.PNG) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 도와줘! 리듬 히어로 ※ | `rhythm-heaven-fever.webp` | nintendo.co.jp Wii 소프트 페이지 https://www.nintendo.co.jp/wii/somj/ (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Rhythm_Heaven_Fever (파일: https://en.wikipedia.org/wiki/File%3ARhythm-heaven-fever.jpg) | ③ | 3:4 크롭 |
| 콘솔 | 놀러오세요 동물의 숲 ※ | `animal-crossing-wild-world.webp` | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Animal_Crossing:_Wild_World (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Animal_Crossing%3A_Wild_World (파일: https://en.wikipedia.org/wiki/File%3AAnimal_Crossing_Wild_World_cover.png) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 엘레비츠: 카이와 제로의 신비한 모험 ※ | `elebits-ds.webp` | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/Elebits%3A_The_Adventures_of_Kai_and_Zero (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Elebits%3A_The_Adventures_of_Kai_and_Zero (파일: https://en.wikipedia.org/wiki/File%3AElebits%20-%20The%20Adventures%20of%20Kai%20and%20Zero%20-%20cover.png) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 메이플스토리DS ※ | `maplestory-ds.webp` | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/MapleStory_DS (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/MapleStory_DS (파일: https://en.wikipedia.org/wiki/File%3AMapleStoryDS.jpg) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 그려라 터치! 내가 만드는 세상 ※ | `drawn-to-life.webp` | Wikipedia(en) 문서 infobox 박스아트 파일 https://en.wikipedia.org/wiki/Drawn_to_Life (letterbox) | Wikipedia(en) 문서 박스아트 파일 https://en.wikipedia.org/wiki/Drawn_to_Life (파일: https://en.wikipedia.org/wiki/File%3ADrawn%20to%20Life%20coverart.jpg) | ③ | 3:4 단색 패드(박스 비율 유지) |
| 콘솔 | 짱구는 못말려 DS 알쏭달쏭 크레용 대작전! ※ | `shin-chan-ds.webp` | 글자 타일 | 주인이 직접 제공한 NDS 패키지 박스아트 owner-images/shinchan-ds-boxart.png | 주인 제공 | 3:4 단색 패드(박스 비율 유지) |

### 장르 "리듬" 통합

PC 의 리듬(칼파: 코스믹 심포니)과 콘솔의 리듬(리듬 세상 · 리듬 천국 미라클 스타즈 · 도와줘! 리듬 히어로)을 **하나의 장르 "리듬"(4종)** 으로 합쳤습니다. 장르 키가 플랫폼 접두어 대신 공용 `rhythm` 이 되어 분포 바 칸 1개 · 칩 1개(툴팁 "PC · 콘솔 · 리듬")로 보이고, 필터를 켜면 PC 줄 1종 + 콘솔 줄 3종이 함께 남습니다. 같은 이름이 다른 플랫폼에 또 있는지 전부 점검했고 리듬만 중복이었습니다. 장르 그룹 수 19 → **18**, 요약 띠와 분포 바 모두 갱신.

### 마리오 파티 → 마리오 파티 DS

주인 확인에 따라 **마리오 파티 DS** 로 표기하고 ※ 를 뗐습니다. 공식 표기 확인: 한국닌텐도 발표를 인용한 게임메카 기사 https://www.gamemeca.com/view.php?gid=71286 ("'마리오 파티 DS'를 한글화하여 정식 발매"). 닌텐도 코리아 사이트에는 DS 타이틀 페이지가 남아 있지 않아 1차 출처는 없습니다(다른 DS 타이틀과 같은 상황이지만, 주인이 작품을 특정했으므로 지시대로 ※ 제거). 박스아트는 Wikipedia(en) `Mario_Party_DS_US_cover.jpg`.

### 게임 밖 활동: 챕터형 캐러셀

- 사진 6장을 한 장씩 넘기던 캐러셀을 **챕터 2개**로 바꿨습니다. 챕터 1 "게임 안에서 · 5년의 기록" = 메이플 스크린샷 2장 + 2000일 출석 이미지, 챕터 2 "게임 밖에서 · 현장의 기록" = 오프라인 사진 3장. 각 챕터는 **왼쪽 큰 1장 + 오른쪽 위아래 2장 격자**(모바일에서는 위 큰 1장 + 아래 2장)로 한 화면에 보이고, 칸은 `object-fit: cover` 로 채웁니다.
- 좌우 화살표·점 2개·키보드 ←/→·스와이프는 **챕터 전환**. 왼쪽 글(챕터 제목·한 줄 문장·"1 / 2")은 유지.
- 칸을 누르면 **원본 비율 확대 보기**(`<dialog>`, Esc·바깥 클릭으로 닫힘, 캡션 표시). 캡션 자리는 칸 아래 띠로 유지(`<figure data-caption="">`, "캡션 추가 예정").
- 섹션 하단의 "자세히" 링크 두 개(`game/passion.html`, `game/perspective.html`)는 **삭제**했습니다. 기존 파일은 그대로 있고 lab 에서 링크만 없앴습니다.

### AI로 만든 게임 캐러셀 깨짐 수정 (주인 보고)

원인: 7차에 추가한 게임 스트림 규칙 `.track { display:flex; width:max-content; … }` 이 범위 없이 모든 `.track` 에 걸려, AI 게임 카드의 `.carousel .track` 과 게임 밖 활동의 `.carousel.big .track` 폭이 0 으로 접혔습니다. `.track` · `.tile` 계열 규칙을 모두 `.stream .track` · `.stream .tile` 로 범위를 좁혔고, JS 는 이미 `root.querySelector('.track')`, `car.querySelectorAll('.slide')` 처럼 컨테이너 안에서만 찾고 있어 손대지 않았습니다. 확인 캡처 `lab/screenshots/ai-cards-1440.png`(두 카드 모두 정상 비율), 게임 밖 활동은 `beyond-chapter-1440.png`.

### 8차에서 비워 둔 자리

- 사진 6장 캡션: `#beyond .photo-grid figure[data-caption=""] figcaption` (확대 보기에도 같은 문구가 표시됩니다)
- 관찰 메모: 메인 카드 `#game-maplestory .obs`, 팝오버 `#gd-obs`
