# 노션 계산기 위젯 사용 방법

## 빠른 시작 가이드

### 1. GitHub Pages로 호스팅하기 (가장 쉬운 방법)

1. GitHub 계정 생성 (없다면)
2. 새 저장소(Repository) 만들기
3. `calculator-widget.html` 파일 업로드
4. Settings → Pages → Source를 "Deploy from a branch"로 설정
5. Branch를 "main"으로 선택 후 Save
6. 몇 분 후 `https://[username].github.io/[repository-name]/calculator-widget.html` 주소로 접근 가능

### 2. Netlify로 호스팅하기 (드래그 앤 드롭)

1. [Netlify](https://www.netlify.com/) 접속
2. "Drop site folder here" 영역에 폴더 드래그
3. 자동으로 생성된 URL 사용

### 3. 노션에 삽입하기

1. 노션 페이지에서 `/embed` 입력
2. 호스팅된 URL 붙여넣기
3. 크기 조정 가능

## 직접 테스트용 임시 호스팅

### Python 사용 (로컬 테스트)
```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000
```
브라우저에서 `http://localhost:8000/calculator-widget.html` 접속

### Node.js 사용 (로컬 테스트)
```bash
npx http-server
```

## 문제 해결

- **404 오류**: 파일이 웹에 호스팅되지 않았거나 URL이 잘못됨
- **iframe 차단**: 일부 호스팅은 iframe을 차단할 수 있음
- **HTTPS 필요**: 노션은 HTTPS URL만 허용

## 파일 구조

```
calculator-widget.html  - 메인 계산기 파일 (이것만 호스팅하면 됨)
iframe-example.html    - iframe 사용 예시 (참고용)
notion-widget-guide.md - 이 설명서
```