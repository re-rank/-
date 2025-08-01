# 계산기 임베딩 가이드

## 방법 1: GitHub Pages 호스팅

1. GitHub 저장소 생성
2. `notion-pet-calculator-responsive.html` 파일 업로드
3. Settings > Pages에서 GitHub Pages 활성화
4. 생성된 URL을 iframe으로 임베딩:

```html
<iframe src="https://yourusername.github.io/repository-name/notion-pet-calculator-responsive.html" 
        width="400" 
        height="600" 
        frameborder="0">
</iframe>
```

## 방법 2: Netlify 호스팅

1. Netlify에 HTML 파일 드래그 앤 드롭
2. 생성된 URL을 iframe으로 사용

## 방법 3: CodePen 사용

1. CodePen에서 새 Pen 생성
2. HTML, CSS, JS 분리해서 입력
3. 생성된 URL을 iframe으로 임베딩