# 🚀 Vercel 배포 가이드 (최종 수정)

## ✅ 수정 완료 사항

1. **vercel.json 최적화**
   - `functions` 설정 제거 (HTML을 서버리스 함수로 인식하는 문제 해결)
   - `routes` 설정 제거 (불필요한 라우팅 제거)
   - iframe 임베딩을 위한 헤더 최적화
   - `X-Frame-Options: ALLOWALL` 설정으로 노션 임베딩 허용

2. **정적 사이트 최적화**
   - package.json 없음 확인 (정적 사이트로 인식)
   - 순수 HTML/CSS/JS 구조 유지

## 🔧 배포 방법

### 방법 1: GitHub 연동 배포 (권장)
1. 수정된 파일들을 GitHub에 푸시:
```bash
git add .
git commit -m "Fix Vercel static site deployment"
git push
```

2. Vercel에서 새 프로젝트 생성:
   - [Vercel Dashboard](https://vercel.com/dashboard) 접속
   - "New Project" 클릭
   - GitHub 저장소 선택
   - **중요 설정**:
     - Framework Preset: **"Other"**
     - Build Command: **비워두기**
     - Output Directory: **"."** (점 하나)
     - Install Command: **비워두기**
   - "Deploy" 클릭

### 방법 2: 기존 프로젝트 재배포
1. Vercel 대시보드에서 프로젝트 선택
2. "Settings" → "General" → "Framework Preset"을 "Other"로 변경
3. "Build & Development Settings"에서:
   - Build Command: 비워두기
   - Output Directory: `.`
   - Install Command: 비워두기
4. "Deployments" 탭에서 "Redeploy" 클릭

## 🎯 배포 성공 확인

배포 완료 후:
1. `https://your-project.vercel.app` 접속
2. 계산기가 정상 작동하는지 확인
3. 브라우저 개발자 도구에서 콘솔 에러 없는지 확인

## 📱 노션에서 사용

배포 성공 후 노션에서:
```
1. /embed 입력
2. Vercel URL 붙여넣기
3. 엔터 → 완료!
```

## 🌐 웹사이트 iframe 임베딩

```html
<iframe 
    src="https://your-project.vercel.app" 
    width="400" 
    height="600" 
    frameborder="0"
    style="border-radius: 12px;">
</iframe>
```

## 🔍 문제 해결

만약 여전히 오류가 발생한다면:

1. **500 에러**: Vercel 대시보드 → Functions 탭에서 에러 로그 확인
2. **빌드 실패**: Build 로그에서 구체적인 에러 메시지 확인
3. **iframe 차단**: 브라우저 콘솔에서 X-Frame-Options 관련 에러 확인

## 📋 최종 파일 구조
```
프로젝트/
├── index.html                    # 메인 계산기
├── notion-pet-calculator-responsive.html
├── iframe-examples.html
├── vercel.json                   # 수정된 Vercel 설정
├── README.md
└── vercel-deploy-guide.md        # 이 파일
```

이제 정적 사이트로 정상 배포될 것입니다! 🎉