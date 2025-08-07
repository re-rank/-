# 노션 반려동물 가계부 계산기
반려동물 관련 비용을 계산할 수 있는 핑크 테마의 계산기입니다.

## 🚀 GitHub 업로드 및 Vercel 배포 방법

### 📤 처음 GitHub에 올리는 경우

#### 방법 1: GitHub 웹사이트에서 직접 업로드
1. [GitHub](https://github.com)에 로그인
2. 우측 상단 "+" 버튼 → "New repository" 클릭
3. Repository 설정:
   - Repository name: `pet-calculator` (원하는 이름)
   - Description: "반려동물 가계부 계산기" (선택사항)
   - Public 선택
   - "Create repository" 클릭
4. "uploading an existing file" 클릭
5. 프로젝트 폴더의 모든 파일 드래그 앤 드롭:
   - `index.html`
   - `README.md`
   - `package.json`
   - `vercel.json`
6. Commit message 입력 (예: "Initial commit")
7. "Commit changes" 클릭

#### 방법 2: Git 명령어 사용
```bash
# 1. 프로젝트 폴더에서 Git 초기화
git init

# 2. 모든 파일 추가
git add .

# 3. 첫 커밋
git commit -m "Initial commit"

# 4. GitHub 저장소와 연결 (your-username을 실제 GitHub 아이디로 변경)
git remote add origin https://github.com/your-username/pet-calculator.git

# 5. 코드 푸시
git push -u origin main
```

### 🔗 Vercel 연동 방법

#### 1단계: Vercel 계정 생성
1. [Vercel](https://vercel.com) 접속
2. "Sign Up" 클릭
3. "Continue with GitHub" 선택 (GitHub 계정으로 로그인)

#### 2단계: 프로젝트 배포
1. Vercel 대시보드에서 "New Project" 클릭
2. "Import Git Repository" 섹션에서:
   - GitHub 저장소 목록이 보이지 않으면 "Add GitHub Account" 클릭
   - 권한 요청 승인
3. 방금 만든 `pet-calculator` 저장소 옆 "Import" 클릭
4. 프로젝트 설정:
   - Framework Preset: "Other" 선택
   - Root Directory: 그대로 두기 (`.`)
   - Build Command: 비워두기
   - Output Directory: 그대로 두기
5. "Deploy" 클릭
6. 배포 완료! (1-2분 소요)

#### 3단계: 배포 URL 확인
1. 배포 완료 후 자동으로 생성된 URL 확인
   - 예: `https://pet-calculator.vercel.app`
2. "Visit" 버튼 클릭하여 사이트 확인

### 🔄 자동 배포 설정
GitHub에 코드를 푸시하면 Vercel이 자동으로 재배포합니다:
```bash
# 파일 수정 후
git add .
git commit -m "Update calculator design"
git push
```

### 💡 커스텀 도메인 설정 (선택사항)
1. Vercel 프로젝트 대시보드 → "Settings" → "Domains"
2. 원하는 도메인 입력 (예: `calculator.yourdomain.com`)
3. DNS 설정 안내 따라하기

## 📱 iframe 임베딩 코드
배포 완료 후 아래 코드를 사용하여 어디든 임베딩 가능합니다:

### 노션용
```
1. 노션에서 /embed 입력
2. Vercel URL 붙여넣기
```

### 웹사이트용 기본 코드
```html
<iframe 
    src="https://your-project.vercel.app" 
    width="400" 
    height="600" 
    frameborder="0"
    style="border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
</iframe>
```

### 반응형 코드 (권장)
```html
<div style="width: 100%; max-width: 400px; height: 600px; margin: 20px auto;">
    <iframe 
        src="https://your-project.vercel.app" 
        style="width: 100%; height: 100%; border: none; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
    </iframe>
</div>
```

## ✨ 특징
- 📱 모바일 최적화
- 🎨 핑크 테마 디자인
- ⌨️ 키보드 입력 지원
- 🖱️ 터치 친화적 인터페이스
- 🔢 기본 계산 기능 (사칙연산, 백분율)

## 🎨 버튼 폰트 크기 커스터마이징

### 특정 버튼의 폰트 크기 변경하기

#### 1. ID를 사용한 특정 버튼 스타일링
```css
/* AC 버튼만 폰트 크기 변경 */
#clear {
    font-size: 20px !important;
}

/* = 버튼만 폰트 크기 변경 */
#equals {
    font-size: 24px !important;
}
```

#### 2. 클래스를 사용한 그룹 스타일링
```css
/* 모든 operator 버튼 폰트 크기 변경 */
.operator {
    font-size: 22px !important;
}
```

### 숫자 버튼만 폰트 크기 변경하기

#### 방법 1: 숫자 버튼에 공통 클래스 추가
```html
<!-- HTML에서 숫자 버튼에 number 클래스 추가 -->
<button class="number" onclick="appendToDisplay('1')">1</button>
<button class="number" onclick="appendToDisplay('2')">2</button>
<!-- ... 나머지 숫자 버튼들 -->

<style>
/* CSS에서 number 클래스 스타일링 */
.number {
    font-size: 24px !important;
}
</style>
```

#### 방법 2: 속성 선택자 사용
```css
/* onclick에 'appendToDisplay'가 포함된 버튼들 선택 */
button[onclick*="appendToDisplay('0')"],
button[onclick*="appendToDisplay('1')"],
button[onclick*="appendToDisplay('2')"],
button[onclick*="appendToDisplay('3')"],
button[onclick*="appendToDisplay('4')"],
button[onclick*="appendToDisplay('5')"],
button[onclick*="appendToDisplay('6')"],
button[onclick*="appendToDisplay('7')"],
button[onclick*="appendToDisplay('8')"],
button[onclick*="appendToDisplay('9')"] {
    font-size: 24px !important;
}
```

#### 방법 3: JavaScript로 동적 적용
```javascript
// 페이지 로드 시 숫자 버튼 찾아서 스타일 적용
document.addEventListener('DOMContentLoaded', function() {
    const buttons = document.querySelectorAll('button');
    buttons.forEach(button => {
        const text = button.textContent.trim();
        if (text >= '0' && text <= '9') {
            button.style.fontSize = '24px';
        }
    });
});
```

### 적용 예시

현재 index.html에 위 스타일을 적용하려면:

1. `<style>` 태그 내부에 원하는 CSS 규칙 추가
2. 또는 특정 버튼의 style 속성에 직접 추가:
   ```html
   <button onclick="appendToDisplay('5')" style="font-size: 24px;">5</button>
   ```

### 팁
- `!important`를 사용하면 다른 스타일보다 우선 적용됩니다
- 반응형 디자인을 위해 `em` 또는 `rem` 단위 사용을 고려하세요
- 너무 큰 폰트는 버튼 레이아웃을 깨뜨릴 수 있으니 적절한 크기를 선택하세요

## 🛠️ 파일 구조
```
├── index.html          # 메인 계산기 파일
├── vercel.json         # Vercel 설정
├── package.json        # 프로젝트 정보
└── README.md          # 이 파일
```