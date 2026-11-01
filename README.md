# 내 통역 비서

한국어로 말하면 영어·일본어·베트남어·태국어로 실시간 통역해서 음성으로 들려주는 웹앱입니다.
상대방 말하기 버튼으로 반대 방향(외국어 → 한국어) 통역도 됩니다.

## GitHub Pages로 배포하기

1. GitHub에서 새 저장소를 만듭니다 (예: `live-interpreter`, **Public**).
2. 이 폴더의 파일을 전부 저장소 최상단에 올립니다.
   - 웹에서: 저장소 화면 → **Add file → Upload files** → 파일 전부 끌어다 놓기 → **Commit changes**
   - 터미널에서:
     ```bash
     git init
     git add .
     git commit -m "내 통역 비서 첫 배포"
     git branch -M main
     git remote add origin https://github.com/<내아이디>/live-interpreter.git
     git push -u origin main
     ```
3. 저장소 **Settings → Pages** 로 이동합니다.
4. **Source** 를 `Deploy from a branch`, 브랜치 `main`, 폴더 `/ (root)` 로 고르고 **Save**.
5. 1~2분 뒤 `https://<내아이디>.github.io/live-interpreter/` 주소가 생깁니다.

> `.nojekyll` 파일은 숨김 파일이라 웹 업로드 시 빠질 수 있지만, 없어도 동작에는 문제 없습니다.

## 휴대폰에 앱처럼 설치하기

- **안드로이드 (Chrome)**: 주소 접속 → 메뉴(⋮) → **홈 화면에 추가** 또는 **앱 설치**
- **아이폰 (Safari)**: 주소 접속 → 공유 버튼 → **홈 화면에 추가**

처음 말하기를 누르면 마이크 권한을 묻습니다. **허용**을 눌러 주세요.

## 파일 구성

| 파일 | 역할 |
|---|---|
| `index.html` | 앱 전체 (화면, 음성 인식, 번역, 음성 출력) |
| `manifest.webmanifest` | 홈 화면 설치용 앱 정보 |
| `icon.svg`, `icon-192.png`, `icon-512.png` | 앱 아이콘 |
| `.nojekyll` | GitHub Pages가 파일을 그대로 서빙하도록 설정 |

## 번역 엔진

- **빠른 번역 (기본)**: 키 없이 바로 사용. 말하는 도중 미리보기 번역까지 보여줍니다. 비공식 무료 주소를 사용하므로 사용량이 많으면 막힐 수 있습니다.
- **Claude**: 설정에서 Anthropic API 키를 넣으면 말투(정중/편하게)와 나만의 용어집을 반영해 더 자연스럽게 통역합니다. 키는 내 기기 브라우저에만 저장됩니다.

> ⚠️ 저장소가 공개(Public)여도 API 키는 코드에 들어가지 않고 각자 기기에만 저장되므로 안전합니다. 키를 `index.html` 안에 직접 적어 넣지는 마세요.

## 지원 브라우저

- 안드로이드 / PC: Chrome, Edge
- 아이폰: Safari (iOS 14.5 이상)
- Firefox는 음성 인식을 지원하지 않습니다 (글자 입력 통역만 가능).
