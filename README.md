# meta-ad-landing

메타(페이스북·인스타그램) 광고용 랜딩페이지.

> **공부체질을 바꾸는 1:1 코칭**

## 구성

| 경로 | 설명 |
| --- | --- |
| `랜딩페이지.dc.html` | 랜딩페이지 본문 (단일 HTML) |
| `assets/` | 로고, 멘토 사진, 비포애프터 이미지 |
| `image-slot.js` | 이미지 슬롯 편집 스크립트 |
| `support.js` | 캔버스 에디터 지원 스크립트 |
| `vercel.json` | `/` → `랜딩페이지.dc.html` 리라이트 (시안 미리보기용) |

## 로컬에서 보기

```bash
# 파일을 그대로 브라우저로 열거나
start 랜딩페이지.dc.html

# 또는 간단한 로컬 서버로
npx serve .
```

## 제외된 파일

`docs/`, `uploads/` 는 참고용 PDF·영상 원본(약 110MB)이라 `.gitignore` 로 제외했습니다.
필요하면 별도 드라이브나 Git LFS 로 관리하세요.

## 실제 배포 위치

이 디자인은 메인 사이트 레포에 React 라우트로 이식되어 있습니다.
**이 레포는 디자인 원본 보관용이며, 실제 서비스되는 코드는 아래입니다.**

- 배포 URL: `https://mentorang.com/lp/coaching`
- 코드: [`Winkcorp/mentorang-website-mvp-LTH`](https://github.com/Winkcorp/mentorang-website-mvp-LTH) → `src/app/lp/coaching/page.tsx`
- 이식 PR: [#2](https://github.com/Winkcorp/mentorang-website-mvp-LTH/pull/2)

메인 사이트 안에 넣은 이유는 메타 픽셀·GA4·Clarity 를 그대로 상속받고,
같은 도메인의 1st-party 쿠키로 광고 전환 추적 정확도를 확보하기 위해서입니다.

**문구나 디자인을 고칠 때는 메인 사이트 레포의 `page.tsx` 를 고쳐야 반영됩니다.**
이 레포의 `.dc.html` 은 캔버스 에디터로 시안을 다시 만들 때만 씁니다.

### Vercel 미리보기

이 레포를 Vercel 에 붙이면 시안을 URL 로 볼 수 있습니다. 진입 파일명이 `index.html` 이
아니라서 `vercel.json` 의 리라이트로 `/` 를 연결해뒀습니다. 없으면 404 가 납니다.
빌드 설정은 필요 없습니다 (Framework Preset: Other, 빌드 커맨드 비움).

어디까지나 **시안 확인용**이고, 광고에 실제로 태우는 URL 은 `https://mentorang.com/lp/coaching` 입니다.
