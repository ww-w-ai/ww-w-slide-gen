# 다음 소개서는 여기서 시작합니다.

[English](README.md) | 한국어

멋진 슬라이드를 만들 때마다 에디터를 새로 만들 필요는 없습니다. ww-w Slide Gen은 복사해서 쓰는 HTML 프레젠테이션 엔진, 바로 편집되는 텍스트, 직접 바꿀 수 있는 디자인 시스템을 제공합니다.

폴더를 복사하세요. 브랜드를 설정하세요. 내용을 쓰세요.

## 시작하기

Node.js 20 이상이 필요합니다. 별도 패키지 설치는 필요 없습니다.

```sh
cp -R /absolute/path/ww-w-slide-gen /absolute/path/my-deck
node /absolute/path/my-deck/scripts/build-deck.js
open /absolute/path/my-deck/html/deck.html      # macOS
start /absolute/path/my-deck/html/deck.html     # Windows
xdg-open /absolute/path/my-deck/html/deck.html  # Linux
```

대상 경로는 새 디렉터리여야 합니다. 생성된 소개서는 이미지와 폰트를 하나의 HTML 파일 안에 담습니다. 아무 데스크톱 브라우저로 열어 보세요. 브라우저의 인쇄 기능으로 PDF로 저장할 수 있습니다.

## 내 것으로 만들기

| 수정 대상 | 목적 |
|---|---|
| `deck.config.json` | 제목, 푸터, 내보내기 파일명, 페이지 순서, 저장소 네임스페이스 |
| `html/theme.css` | 브랜드 색상, 타이포그래피, 여백, 표면 |
| `html/components.css` | 공통 제목·카드·스크린샷·푸터 컴포넌트 |
| `html/pages.css` | 페이지별 레이아웃 |
| `html/pages/*.html` | 편집 가능한 슬라이드 콘텐츠 |
| `templates/blank-slide.html` | 새 페이지를 만들 때 복사할 빈 템플릿 |
| `assets/` | 폰트, 원본 스크린샷, 텍스트 없는 아트워크 |

기본 제공 갤러리는 표지, 3열 콘텐츠, 스크린샷 증거, 프로세스, 비교, 편집 가능한 텍스트가 있는 아트워크를 포함합니다.

스타일시트 목록에서 `theme.css` 바로 뒤에 `themes/cobalt.css`를 추가하면 두 번째 비주얼 방향을 시도할 수 있습니다. 같은 컴포넌트와 엔진을 쓰면서 팔레트, 여백, 모서리만 바뀝니다.

단계별 안내는 [CUSTOMIZE.ko.md](CUSTOMIZE.ko.md), 브랜드 정의는 [디자인 시스템 가이드](docs/design-system-guide.ko.md), 이를 구현하는 방법은 [CSS 가이드](docs/css-customization.ko.md)를 참고하세요. [기본 디자인 시스템](docs/design-system.ko.md)은 그대로 바꿔 쓸 수 있는 작동 예시입니다.

## 발표와 편집

**← / →**로 이동하고, **E**로 편집 모드에 들어가고, 텍스트를 더블클릭해 바꿉니다. **M**은 페이지 순서를 바꿉니다. **?**는 단축키 안내를 엽니다. **Cmd/Ctrl+S**는 현재 편집 중인 소개서를 다운로드합니다 — 원본 소스 파일은 덮어쓰지 않습니다. 다시 빌드하기 전에 브라우저에서 한 편집을 먼저 저장하세요. 다음 빌드의 기준은 항상 소스 파일입니다.

**Cmd/Ctrl+P**는 현재 슬라이드를 인쇄합니다. 전체 소개서를 PDF로 만들려면 브라우저 개발자 도구에서 `document.body.classList.add('print-all')`로 body에 `print-all`을 추가한 뒤 인쇄하세요. CSS 페이지 크기로, 배경 그래픽을 켜고, 브라우저 머리글/바닥글은 끈 상태로 인쇄합니다.

텍스트 제거에는 이미지 생성 워크플로를 쓸 수 있습니다. 선택 사항인 레거시 AI 지우개 모델과 런타임은 포함돼 있지 않습니다 — [이미지 워크플로](docs/image-workflow.ko.md)를 참고하세요.

## 사본 점검

```sh
npm --prefix /absolute/path/my-deck test
```

Node 점검은 조립, 자산 폐쇄성, 런타임 문법, 이동한 빌드를 확인합니다. 브라우저 레이아웃, 편집, 다운로드, PDF 결과는 여전히 브라우저로 직접 확인해야 합니다. 이 템플릿은 신뢰할 수 있는 로컬 HTML 소스를 대상으로 하며, 신뢰할 수 없는 업로드를 대상으로 하지 않습니다.

코드(스크립트·CSS·HTML)는 [MIT](LICENSE), 문서 본문은 [CC BY 4.0](LICENSE-CONTENT.md)입니다. 번들된 Pretendard 폰트는 SIL OFL 라이선스를 유지합니다. [제3자 고지](THIRD-PARTY-NOTICES.md)를 참고하세요.
공식 워크플로: [원본을 비교한 뒤 별도의 최종본을 만든다](docs/comparison-workflow.ko.md). 비교용 소개서는 보존하세요. `npm run build:final`을 실행하면 퍼블리싱본만 남은 복제본을 만듭니다.
