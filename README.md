# 기획자 박민규 포트폴리오

Notion 포트폴리오 페이지를 정적 HTML로 옮긴 GitHub Pages 사이트입니다. 빌드 도구 없이 HTML과 CSS만 사용합니다.

## 구조

```
index.html            메인 페이지 (소개 · 경력 · 대표 프로젝트 · 기획서 PDF · 게임 경험 · 역량 · 학력)
projects/*.html       대표 프로젝트 상세 4개
game/*.html           게임 경험 정리 상세 2개
assets/style.css      공통 스타일 (라이트/다크 자동)
assets/img/           이미지
assets/files/         기획서 PDF, DOCX
```

## 배포

GitHub 저장소의 Settings → Pages 에서 `main` 브랜치의 루트(`/`)를 소스로 선택하면 됩니다.

## 수정 방법

내용 수정은 각 HTML 파일을 직접 편집하면 됩니다. 새 기획서 PDF를 추가하려면 `assets/files/`에 파일을 넣고 `index.html`의 `#portfolio` 섹션에 카드를 하나 복사해서 채우면 됩니다.
