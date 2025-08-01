# Vercel 호스팅 및 iframe 임베딩 가이드

## 1. Vercel 호스팅 방법

### 방법 A: 웹 인터페이스 사용 (가장 간단)

1. **Vercel 계정 생성**
   - https://vercel.com 접속
   - GitHub, GitLab, 또는 이메일로 회원가입

2. **프로젝트 배포**
   - Vercel 대시보드에서 "New Project" 클릭
   - "Browse all templates" 대신 "Import Git Repository" 건너뛰기
   - 또는 직접 파일 업로드

### 방법 B: 드래그 앤 드롭 배포

1. **폴더 구조 준비**
   ```
   calculator-project/
   ├── index.html (notion-pet-calculator-responsive.html을 이름 변경)
   └── (다른 파일들...)
   ```

2. **Vercel CLI 설치 및 배포**
   ```bash
   npm i -g vercel
   vercel login
   vercel --prod
   ```

### 방법 C: GitHub 연동 (권장)

1. **GitHub 저장소 생성**
   - GitHub에서 새 저장소 생성
   - `notion-pet-calculator-responsive.html`을 `index.html`로 이름 변경
   - 저장소에 업로드

2. **Vercel에서 GitHub 저장소 연결**
   - Vercel 대시보드에서 "New Project"
   - GitHub 저장소 선택
   - "Deploy" 클릭

## 2. iframe 임베딩 코드

배포 완료 후 생성된 URL (예: `https://your-project.vercel.app`)을 사용:

### 기본 iframe 코드
```html
<iframe 
    src="https://your-project.vercel.app" 
    width="400" 
    height="600" 
    frameborder="0"
    style="border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
</iframe>
```

### 반응형 iframe 코드
```html
<div style="position: relative; width: 100%; max-width: 400px; height: 600px;">
    <iframe 
        src="https://your-project.vercel.app" 
        style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: none; border-radius: 12px;"
        allowfullscreen>
    </iframe>
</div>
```

### 노션용 임베딩
1. 노션 페이지에서 `/embed` 입력
2. 생성된 Vercel URL 붙여넣기
3. 크기 조정

## 3. 추가 설정

### vercel.json 파일 (선택사항)
```json
{
  "functions": {
    "index.html": {
      "memory": 128
    }
  },
  "headers": [
    {
      "source": "/(.*)",
      "headers": [
        {
          "key": "X-Frame-Options",
          "value": "ALLOWALL"
        }
      ]
    }
  ]
}
```

## 4. 문제 해결

### iframe이 로드되지 않는 경우
- X-Frame-Options 헤더 확인
- HTTPS 사용 확인
- 브라우저 콘솔에서 오류 메시지 확인

### 모바일에서 작동하지 않는 경우
- viewport 메타 태그 확인
- 터치 이벤트 지원 확인

## 5. 대안 서비스들

- **Netlify**: 드래그 앤 드롭으로 간단 배포
- **GitHub Pages**: GitHub 저장소 기반 무료 호스팅
- **Surge.sh**: 명령어 한 줄로 배포
- **Firebase Hosting**: Google의 호스팅 서비스