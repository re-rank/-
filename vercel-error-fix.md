# 🔧 Vercel 500 오류 해결

## ❌ 문제
- "FUNCTION_INVOCATION_FAILED" 오류
- 정적 HTML 파일이 서버리스 함수로 잘못 인식됨

## ✅ 해결 방법

### 1. vercel.json 수정 완료
- `routes` 설정 추가로 모든 요청을 index.html로 라우팅
- `functions` 설정으로 메모리 최적화
- 헤더 설정 개선

### 2. package.json 삭제 완료
- Node.js 프로젝트로 인식되는 것을 방지
- 순수 정적 사이트로 배포되도록 설정

## 🚀 재배포 방법

### 옵션 1: GitHub 푸시 (자동 재배포)
```bash
git add .
git commit -m "Fix Vercel 500 error"
git push
```

### 옵션 2: Vercel 대시보드에서 재배포
1. Vercel 대시보드 접속
2. 프로젝트 선택
3. "Deployments" 탭
4. 최신 배포에서 "Redeploy" 클릭

### 옵션 3: 새 프로젝트로 배포 (권장)
1. Vercel에서 "New Project"
2. GitHub 저장소 선택
3. **중요 설정**:
   - Framework Preset: **"Other"**
   - Build Command: **비워두기**
   - Output Directory: **"."**
   - Install Command: **비워두기**
4. "Deploy" 클릭

## 📋 최종 파일 구조
```
프로젝트/
├── index.html          # 메인 계산기
├── vercel.json         # Vercel 설정 (수정됨)
├── README.md
├── deploy-instructions.md
├── iframe-examples.html
└── vercel-error-fix.md # 이 파일
```

## 🎯 배포 성공 확인
배포 성공 후:
1. `https://your-project.vercel.app` 접속
2. 계산기가 정상 작동하는지 확인
3. 노션에서 `/embed`로 테스트

## 💡 추가 팁
- 앞으로는 package.json 없이 순수 HTML로 배포
- vercel.json만으로 모든 설정 관리
- 정적 사이트이므로 빌드 과정 불필요

이제 500 오류 없이 정상 배포될 것입니다! 🎉