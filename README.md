# 한일로보틱스 홈페이지

[hanilrobotics.kr](https://hanilrobotics.kr) — GitHub Pages로 배포되는 한 페이지짜리 정적 사이트입니다.
빌드 과정 없이 `index.html`을 고쳐서 main 브랜치에 올리면 바로 반영됩니다.

## 파일 구성

| 파일 | 역할 |
| --- | --- |
| `index.html` | 페이지 전체 (HTML·CSS·JS 한 파일) |
| `favicon.png`, `apple-touch-icon.png` | 브라우저 탭·휴대폰 홈 화면 아이콘 (HR 로고) |
| `assets/` | 로고, 히어로 영상, 제품 이미지(부스 그래픽 D39에서 가져옴), 기술 단계 이미지, 시연 영상 |
| `og-image.png` | 카카오톡·링크드인 등에서 링크를 공유할 때 뜨는 미리보기 이미지 (1200×630) |
| `robots.txt`, `sitemap.xml` | 검색엔진 수집용 |
| `CNAME` | 커스텀 도메인 설정 — 지우지 마세요 |

## 문구 고치기

- **한국어**: `index.html` 본문 텍스트를 바로 수정합니다.
- **영어·일본어**: `index.html` 아래쪽 `<script>`의 `T` 객체에서, 태그의 `data-i18n` 값과 같은 key를 찾아 `en` / `ja`를 수정합니다.
- **새 문구 추가**: 태그에 `data-i18n="새.key"`를 달고 `T`에 `'새.key': { en: '...', ja: '...' }`를 추가합니다.
  빠뜨리면 브라우저 콘솔에 `[i18n] 번역 없음` 경고가 뜹니다.
- 언어별 바로가기 링크(명함·메일에 사용): `https://hanilrobotics.kr/?lang=en`, `https://hanilrobotics.kr/?lang=ja`
- 언어는 방문자 브라우저 설정을 따라 자동 선택됩니다 (한국어 → KO, 일본어 → JP, 그 외 → EN). 검색엔진 봇에는 항상 한국어로 보입니다.

## 사진·영상 바꾸기

- 이미지·영상은 모두 `assets/`에 있습니다. 같은 이름으로 덮어쓰면 그대로 반영됩니다.
- 히어로 영상 `assets/hero-weld.mp4`(1600×900, 10초 루프, 무음)는 HR3 URDF로 렌더링한 위빙 용접 장면입니다. 배경색 `#b4b4b4`가 페이지 히어로 색(`--studio`)과 같아 경계가 보이지 않습니다. 영상을 바꿀 때는 배경색을 맞추거나 `--studio` 값을 함께 바꾸세요.
- 포스터 이미지는 `assets/hero-weld.jpg`, 시연 섹션 영상은 `assets/demo-path.mp4`입니다.

## 배포 전 확인

1. 저장소 **Settings → Pages**에서 **Enforce HTTPS**가 켜져 있는지 확인합니다.
   체크박스가 비활성화되어 있으면 DNS가 GitHub Pages를 가리키는지(A 레코드 185.199.108.153 / .109 / .110 / .111.153,
   `www`는 `hjpark-hanilrobotics.github.io`로 CNAME) 확인하고, 도메인 업체가 자동으로 만든 기본 레코드가 있으면 지웁니다.
2. 네이버 서치어드바이저·구글 서치 콘솔에 사이트를 등록하고, 받은 소유 확인 값을 `index.html` `<head>`의 주석 자리에 넣습니다.
3. 링크 공유 미리보기는 카카오 개발자 사이트의 '공유 디버거'에서 캐시를 초기화하면 바로 새 이미지로 바뀝니다.
