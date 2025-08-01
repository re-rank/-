# 🔧 Vercel 배포 오류 해결 완료!

## ✅ 수정된 내용

1. **vercel.json 업데이트**
   - `outputDirectory: "."` 추가 (현재 폴더를 출력 디렉토리로 설정)
   - `buildCommand`, `installCommand` 설정 추가

2. **package.json 최적화**
   - 불필요한 스크립트 제거
   - 정적 사이트용으로 간소화

## 🚀 이제 다시 배포하세요!

### 방법 1: GitHub에서 다시 배포
1. 수정된 `vercel.json`과 `package.json` 파일을 GitHub에 커밋
2. Vercel에서 자동으로 재배포됩니다

### 방법 2: Vercel에서 수동 재배포
1. Vercel 대시보드에서 프로젝트 선택
2. "Deployments" 탭
3. "Redeploy" 버튼 클릭

### 방법 3: 새로 배포 (권장)
1. Vercel 대시보드에서 "New Project"
2. 같은 GitHub 저장소 선택
3. Framework Preset: "Other" 선택
4. Build Command: 비워두기
5. Output Directory: `.` (점 하나)
6. Install Command: 비워두기
7. "Deploy" 클릭

## 📋 배포 설정 요약

```
Framework Preset: Other
Build Command: (비워두기)
Output Directory: .
Install Command: (비워두기)
Root Directory: ./
```

## 🎯 배포 성공 후

배포가 성공하면 `https://your-project.vercel.app` 형태의 URL이 생성됩니다.

### 노션에서 사용:
```
1. /embed 입력
2. Vercel URL 붙여넣기
3. 완료!
```

### 웹사이트에서 사용:
```html
<iframe 
    src="https://your-project.vercel.app" 
    width="400" 
    height="600" 
    frameborder="0"
    style="border-radius: 12px;">
</iframe>
```

이제 오류 없이 배포될 것입니다! 🎉