# 노션에 계산기 위젯 적용하는 방법

## 방법 1: CodePen을 이용한 임베드 (추천)

1. **CodePen 계정 만들기**
   - https://codepen.io 접속
   - Sign Up으로 무료 계정 생성

2. **새 Pen 만들기**
   - 로그인 후 "Create" → "New Pen" 클릭
   - HTML 섹션에 `notion-pet-calculator.html`의 `<body>` 안의 내용만 복사
   - CSS 섹션에 `<style>` 태그 안의 내용만 복사
   - JS 섹션에 `<script>` 태그 안의 내용만 복사

3. **Pretendard 폰트 추가**
   - CSS 섹션 최상단에 아래 코드 추가:
   ```css
   @import url('https://cdn.jsdelivr.net/gh/orioncactus/pretendard@v1.3.9/dist/web/static/pretendard.min.css');
   ```

4. **Pen 저장 및 공유 링크 얻기**
   - 상단의 "Save" 버튼 클릭
   - "Embed" 버튼 클릭
   - "Copy Link" 버튼으로 임베드 URL 복사

5. **노션에 임베드**
   - 노션 페이지에서 `/embed` 입력
   - 복사한 CodePen URL 붙여넣기
   - 계산기 위젯이 나타남

## 방법 2: GitHub Pages 이용

1. **GitHub 계정 및 저장소 생성**
   - GitHub 계정 생성 (https://github.com)
   - 새 저장소(Repository) 생성

2. **HTML 파일 업로드**
   - `notion-pet-calculator.html` 파일을 저장소에 업로드

3. **GitHub Pages 활성화**
   - Settings → Pages
   - Source를 "Deploy from a branch"로 설정
   - Branch를 "main"으로 선택
   - Save 클릭

4. **노션에 임베드**
   - `https://[username].github.io/[repository-name]/notion-pet-calculator.html`
   - 노션에서 `/embed` 입력 후 위 URL 붙여넣기

## 방법 3: Netlify Drop 이용 (가장 간단)

1. **Netlify Drop 접속**
   - https://app.netlify.com/drop 접속

2. **파일 드래그 앤 드롭**
   - `notion-pet-calculator.html` 파일을 드래그해서 업로드

3. **생성된 URL 복사**
   - 업로드 완료 후 생성된 URL 복사

4. **노션에 임베드**
   - 노션에서 `/embed` 입력
   - 복사한 URL 붙여넣기

## 위젯 크기 조정

노션에 임베드된 후:
- 위젯 선택 → 모서리 드래그로 크기 조정
- 계산기가 반응형으로 제작되어 자동으로 크기 맞춤

## 주의사항

- 무료 호스팅 서비스는 트래픽 제한이 있을 수 있음
- HTTPS 프로토콜을 사용하는 URL만 노션에 임베드 가능
- 개인 용도로만 사용 권장