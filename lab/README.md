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
