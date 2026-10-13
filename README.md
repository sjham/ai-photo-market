# 자세히 보면

[실행 페이지](https://sjham.github.io/ai-photo-market/) · [기술 학습 안내](https://sjham.github.io/ai-photo-market/learning-guide.html) · [GitHub 저장소](https://github.com/sjham/ai-photo-market)

화면에 고정된 AI 시장 사진이 스크롤에 따라 확대·이동하고, 사진 위의 설명 상자로 여섯 가지 단서를 살펴보는 교육용 페이지입니다. 이미지·CSS·JavaScript가 모두 `index.html`에 들어 있어 이 파일 하나만 열어도 작동합니다. 외부 라이브러리, 폰트 다운로드, API 키가 필요 없습니다.

## GitHub에 올리고 배포하기

1. GitHub에서 **새 Public 저장소**를 만듭니다. 기본 브랜치는 **main**으로 둡니다.
2. 저장소의 **Add file → Upload files**에서 `index.html`, `learning-guide.html`, `README.md`를 올리고 **Commit changes**를 누릅니다. ZIP 파일 자체를 올리면 배포되지 않습니다.
3. **Add file → Create new file**을 누르고 파일 이름에 **`.github/workflows/deploy.yml`**을 입력합니다. 제공된 `deploy.yml`의 내용을 전부 붙여 넣고 **Commit changes**를 누릅니다. 점으로 시작하는 `.github` 폴더가 업로드에서 빠지는 것을 막기 위한 방법입니다.
4. **Settings → Pages → Build and deployment → Source**를 **GitHub Actions**로 바꿉니다.
5. **Actions → GitHub Pages 자동 배포 → Run workflow → main → Run workflow**를 한 번 누릅니다. 첫 업로드가 Pages 설정보다 먼저 실행되어 실패한 경우에도 이 방법으로 배포할 수 있습니다. 초록색 체크가 나타나면 **Settings → Pages → Visit site**에서 접속합니다.

이후 `main`의 `index.html`을 수정하면 자동으로 다시 배포됩니다. 일반적인 주소는 `https://사용자이름.github.io/저장소이름/`입니다.

## 페이지 사용법

- 사진을 클릭하면 확대 화면이 열립니다. 클릭, +/− 버튼, 마우스 휠, 모바일 핀치로 확대·축소하고, 드래그로 사진을 움직입니다.
- 확대 화면에서 방향키로 이동하고 `+`, `-`, `0`으로 확대·축소·초기화합니다. `Esc` 또는 ×로 닫습니다.
- **먼저 사진만 살펴보기**를 눌러 직접 관찰한 뒤, 아래로 스크롤하거나 화살표·작은 점 버튼을 눌러 여섯 단서를 봅니다.
- **의심되는 곳 표시하기**를 눌러 파란 관찰 점을 최대 6개 남깁니다. 확대 화면의 **단서와 비교**에서 노란 학습 주석과 위치를 비교합니다. 영역의 겹침은 정답률이나 AI 판별 성능이 아닙니다. 표시는 새로고침하면 지워집니다.
- 확대 화면에서 표시 모드를 켠 뒤 방향키로 사진을 움직이고 `Enter` 또는 스페이스로 중앙에 표시할 수도 있습니다. 마지막 표시 삭제·모두 지우기로 다시 관찰합니다.
- 마지막의 **여섯 단서 한눈에 보기**를 누르면 모든 위치를 확인할 수 있습니다.

## 기술 학습

`learning-guide.html`은 JavaScript 화면 동작, 사진 좌표, Transformers.js 모델 실행의 역할과 한계를 설명합니다. 인터넷 연결 없이 문서 자체를 읽을 수 있으며, 공식 자료 링크는 인터넷이 필요합니다. 사진 페이지에는 Transformers.js를 적용하지 않았습니다. 사진의 진위 판별 과제와 일반 사물 인식은 다르기 때문입니다.

## 이미지와 출처

사진은 기본 이미지 생성 도구로 만든 **가상의 AI 이미지**이며 실제 방문·사건을 기록한 사진이 아닙니다. 교육용 단서가 보이도록 구성했습니다. 사진 아래와 확대 화면, 페이지 하단에 AI 생성 표시를 유지합니다. 시각적 오류만으로 이미지의 진위를 확정하지 말고 출처와 원본도 확인하세요.

사용자가 제공한 [NYT 참고 페이지](https://www.nytimes.com/interactive/2026/10/08/technology/ai-generated-image-look-close.html)의 저장 HTML에서 확인한 고정 사진, 회색 설명 상자, 800ms 확대·이동 구조를 반영했습니다. 우리말 교육용 콘텐츠로 직접 구현한 페이지입니다. 이미지 생성 프롬프트는 `index.html`의 주석에 기록되어 있습니다.

배포 설정은 [GitHub 공식 안내](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages)를 따릅니다. 이 버전은 위 실행 페이지에 게시되어 있습니다. 새 저장소에 복사해 배포할 때는 위 GitHub 설정 절차를 따르세요.
