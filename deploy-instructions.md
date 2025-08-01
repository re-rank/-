# 🚀 즉시 배포 가이드

## 방법 1: GitHub + Vercel (권장)

### 1단계: GitHub 저장소 생성
1. https://github.com 접속
2. "New repository" 클릭
3. 저장소 이름: `pet-calculator` (또는 원하는 이름)
4. Public으로 설정
5. "Create repository" 클릭

### 2단계: 파일 업로드
현재 폴더의 모든 파일을 GitHub에 업로드:
- `index.html`
- `vercel.json`
- `package.json`
- `README.md`

### 3단계: Vercel 배포
1. https://vercel.com 접속
2. "Continue with GitHub" 클릭하여 로그인
3. "New Project" 클릭
4. 방금 만든 저장소 선택
5. "Deploy" 클릭
6. 배포 완료! (약 1-2분 소요)

### 4단계: URL 확인
배포 완료 후 `https://your-project-name.vercel.app` 형태의 URL 생성

---

## 방법 2: Vercel CLI (빠른 방법)

### 1단계: Vercel CLI 설치
```bash
npm i -g vercel
```

### 2단계: 로그인 및 배포
```bash
vercel login
vercel --prod
```

---

## 📱 iframe 사용법

배포 완료 후 생성된 URL을 사용하여 iframe 생성:

### 노션에서 사용
```
1. 노션 페이지에서 /embed 입력
2. 생성된 Vercel URL 붙여넣기
3. 완료!
```

### 다른 웹사이트에서 사용
```html
<!-- 기본 iframe -->
<iframe 
    src="https://your-project.vercel.app" 
    width="400" 
    height="600" 
    frameborder="0"
    style="border-radius: 12px;">
</iframe>

<!-- 반응형 iframe (권장) -->
<div style="width: 100%; max-width: 400px; height: 600px; margin: 0 auto;">
    <iframe 
        src="https://your-project.vercel.app" 
        style="width: 100%; height: 100%; border: none; border-radius: 12px;">
    </iframe>
</div>
```

---

## ✅ 체크리스트

- [ ] GitHub 저장소 생성
- [ ] 파일 업로드 완료
- [ ] Vercel 계정 생성
- [ ] 저장소 연결 및 배포
- [ ] URL 확인
- [ ] iframe 코드 생성
- [ ] 노션/웹사이트에 임베딩

---

## 🆘 문제 해결

### iframe이 로드되지 않는 경우
1. URL이 HTTPS인지 확인
2. 브라우저 콘솔에서 오류 메시지 확인
3. vercel.json 파일이 올바르게 업로드되었는지 확인

### 모바일에서 작동하지 않는 경우
1. viewport 메타 태그 확인
2. 터치 이벤트 지원 확인
3. 브라우저 호환성 확인

도움이 필요하면 언제든 문의하세요!