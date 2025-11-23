# RecipeSoup - 앱 설치 유도 랜딩 페이지

## 페이지 구조

### 1. 히어로 섹션 (Hero Section)
```
┌─────────────────────────────────────┐
│     [RecipeSoup 로고/아이콘]         │
│                                     │
│    요리와 감정을 함께 기록하는       │
│      감성 레시피 다이어리            │
│                                     │
│   [iOS 다운로드] [Android 다운로드]   │
│                                     │
│   [앱 스크린샷 미리보기 이미지]       │
└─────────────────────────────────────┘
```

**카피**
- 메인 헤드라인: "요리와 감정을 함께 기록하는 감성 레시피 다이어리"
- 서브 헤드라인: "왜 만들었는지, 누구를 위해 만들었는지, 그 순간의 감정까지 함께 기록하세요"

**CTA 버튼**
- iOS: "App Store에서 다운로드"
- Android: "Google Play에서 다운로드"

---

### 2. 주요 기능 섹션 (Key Features)
```
┌─────────────────────────────────────┐
│          왜 RecipeSoup?             │
│                                     │
│  ┌───────┐  ┌───────┐  ┌───────┐  │
│  │ 아이콘│  │ 아이콘│  │ 아이콘│  │
│  │재료검색│  │레시피│  │ 즐겨찾기│ │
│  └───────┘  └───────┘  └───────┘  │
└─────────────────────────────────────┘
```

**기능 1: 재료 기반 레시피 검색**
- 아이콘: 🔍
- 제목: "냉장고 재료로 뭐 먹지?"
- 설명: "집에 있는 재료를 입력하면 딱 맞는 레시피를 추천해드려요"

**기능 2: 다양한 레시피 탐색**
- 아이콘: 📖
- 제목: "무한한 레시피 라이브러리"
- 설명: "한식, 양식, 중식, 일식까지 다양한 레시피를 만나보세요"

**기능 3: 나만의 레시피 북**
- 아이콘: ⭐
- 제목: "마음에 드는 레시피 저장"
- 설명: "좋아하는 레시피를 즐겨찾기에 저장하고 언제든 다시 확인하세요"

**기능 4: 간편한 레시피 공유**
- 아이콘: 🔗
- 제목: "친구와 함께 요리해요"
- 설명: "좋은 레시피는 공유! 카카오톡으로 간편하게 나눠보세요"

---

### 3. 스크린샷 갤러리 (Screenshot Gallery)
```
┌─────────────────────────────────────┐
│         앱 미리보기                  │
│                                     │
│  [스샷1]  [스샷2]  [스샷3]  [스샷4]  │
│  홈화면   검색    레시피   즐겨찾기   │
└─────────────────────────────────────┘
```

**스크린샷 항목**
1. 홈 화면 - 메인 피드 및 추천 레시피
2. 재료 검색 화면 - 재료 입력 및 검색 결과
3. 레시피 상세 화면 - 재료 및 조리 과정
4. 즐겨찾기 화면 - 저장된 레시피 목록

---

### 4. 사용자 후기 (Social Proof)
```
┌─────────────────────────────────────┐
│       RecipeSoup 사용자 후기         │
│                                     │
│  "남은 재료로 이렇게 맛있는          │
│   요리를 만들 수 있다니!"            │
│   - 김○○ 님                         │
│                                     │
│  "레시피 검색이 정말 편해요"         │
│   - 이○○ 님                         │
└─────────────────────────────────────┘
```

---

### 5. 다운로드 CTA (Bottom Call-to-Action)
```
┌─────────────────────────────────────┐
│   지금 바로 RecipeSoup을 시작하세요  │
│                                     │
│   [iOS 다운로드] [Android 다운로드]   │
│                                     │
│     무료 다운로드 | 회원가입 불필요   │
└─────────────────────────────────────┘
```

---

### 6. 푸터 (Footer)
```
┌─────────────────────────────────────┐
│  RecipeSoup                         │
│                                     │
│  개인정보처리방침 | 서비스 이용약관   │
│  고객지원 | 문의하기                 │
│                                     │
│  © 2024 RecipeSoup. All rights reserved │
└─────────────────────────────────────┘
```

---

## 기술 구현 가이드

### 플랫폼 감지 로직
```javascript
function detectPlatform() {
  const userAgent = navigator.userAgent || navigator.vendor || window.opera;

  // iOS 감지
  if (/iPad|iPhone|iPod/.test(userAgent) && !window.MSStream) {
    return 'ios';
  }

  // Android 감지
  if (/android/i.test(userAgent)) {
    return 'android';
  }

  return 'desktop';
}

function redirectToStore() {
  const platform = detectPlatform();

  if (platform === 'ios') {
    window.location.href = 'https://apps.apple.com/app/recipesoup/YOUR_APP_ID';
  } else if (platform === 'android') {
    window.location.href = 'https://play.google.com/store/apps/details?id=com.recipesoup.app';
  }
}
```

### 스토어 링크 정보
- **iOS App Store**: `https://apps.apple.com/kr/app/recipesoup/[APP_ID]`
- **Android Play Store**: `https://play.google.com/store/apps/details?id=com.recipesoup.app.recipesoup`

### Deep Link 설정
```
// Universal Link (iOS)
https://recipesoup.app/download

// App Link (Android)
https://recipesoup.app/download
```

---

## SEO 최적화

### Meta Tags
```html
<meta name="description" content="냉장고 속 재료로 만드는 나만의 레시피. RecipeSoup으로 남은 재료도 특별한 요리로 만들어보세요.">
<meta name="keywords" content="레시피, 요리, 재료검색, 냉장고재료, 요리앱, RecipeSoup">

<!-- Open Graph -->
<meta property="og:title" content="RecipeSoup - 냉장고 속 재료로 만드는 레시피">
<meta property="og:description" content="집에 있는 재료로 무엇을 만들까? RecipeSoup이 답을 드려요!">
<meta property="og:image" content="https://recipesoup.app/og-image.jpg">
<meta property="og:url" content="https://recipesoup.app">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="RecipeSoup - 냉장고 속 재료로 만드는 레시피">
<meta name="twitter:description" content="집에 있는 재료로 무엇을 만들까? RecipeSoup이 답을 드려요!">
<meta name="twitter:image" content="https://recipesoup.app/twitter-image.jpg">
```

---

## 디자인 가이드라인

### 컬러 팔레트
- Primary: #FF6B6B (따뜻한 레드 - 음식의 온기)
- Secondary: #4ECDC4 (신선한 민트 - 재료의 신선함)
- Accent: #FFD93D (활기찬 옐로우 - 요리의 즐거움)
- Background: #FFFFFF
- Text: #2D3436

### 타이포그래피
- 헤드라인: Pretendard Bold, 32-48px
- 서브헤드라인: Pretendard SemiBold, 20-24px
- 본문: Pretendard Regular, 16-18px
- CTA 버튼: Pretendard Bold, 16-18px

### 버튼 스타일
- iOS 버튼: 검정 배경 + 흰색 텍스트 (Apple 가이드라인)
- Android 버튼: 초록 배경 + 흰색 텍스트 (Google Play 가이드라인)
- 호버 효과: 살짝 어두워지는 효과
- 모서리: 8px 라운드

---

## 콘텐츠 전략

### 핵심 메시지
1. **문제 제시**: "냉장고에 재료는 있는데 뭘 만들어야 할지 모르겠다면?"
2. **솔루션 제공**: "RecipeSoup이 재료 기반으로 레시피를 추천해드려요"
3. **행동 유도**: "지금 바로 다운로드하고 오늘 저녁 메뉴를 찾아보세요!"

### 차별화 포인트
- ✅ 재료 기반 검색 (다른 앱과의 차별점)
- ✅ 무료 사용 (진입 장벽 낮음)
- ✅ 간편한 즐겨찾기 (사용자 편의성)
- ✅ 레시피 공유 기능 (소셜 요소)

---

## 성과 측정 (Analytics)

### 추적해야 할 지표
1. **페이지 방문자 수**
2. **다운로드 버튼 클릭률** (iOS vs Android)
3. **실제 앱 설치 전환율**
4. **페이지 체류 시간**
5. **이탈률 (Bounce Rate)**
6. **트래픽 소스** (SNS, 검색, 직접 유입 등)

### Google Analytics 이벤트
```javascript
// iOS 다운로드 버튼 클릭
gtag('event', 'download_button_click', {
  'platform': 'ios',
  'location': 'hero_section'
});

// Android 다운로드 버튼 클릭
gtag('event', 'download_button_click', {
  'platform': 'android',
  'location': 'hero_section'
});
```

---

## 실행 체크리스트

### 런칭 전 확인사항
- [ ] 스토어 링크 정확성 확인 (iOS, Android)
- [ ] 모바일 반응형 디자인 테스트
- [ ] 다양한 기기에서 테스트 (iPhone, Android 폰, 태블릿)
- [ ] 로딩 속도 최적화 (이미지 압축, 캐싱)
- [ ] SEO 메타태그 설정
- [ ] Google Analytics 연동
- [ ] 소셜 공유 미리보기 테스트
- [ ] 크로스 브라우저 테스트 (Safari, Chrome, Samsung Internet)
- [ ] 다운로드 버튼 동작 확인
- [ ] 404 에러 페이지 설정

### 마케팅 준비
- [ ] 앱 스토어 최적화 (ASO)
- [ ] SNS 공유용 이미지 제작
- [ ] 런칭 이벤트 기획
- [ ] 인플루언서 협업 준비
- [ ] 프레스 릴리스 작성

---

## 향후 개선 방향

### A/B 테스팅 아이디어
1. 히어로 이미지 변형 (폰 목업 vs 실제 사용 장면)
2. CTA 버튼 문구 ("다운로드" vs "무료로 시작하기")
3. 스크린샷 개수 및 배치
4. 사용자 후기 위치 (상단 vs 중간 vs 하단)

### 추가 기능 고려사항
- QR 코드 추가 (데스크톱 방문자용)
- 동영상 데모 (앱 사용 시연)
- FAQ 섹션
- 언론 보도 내역 (Media Coverage)
- 앱 리뷰 평점 표시
- 다운로드 수 표시 (사회적 증거)

---

## 참고 링크

- 개인정보처리방침: `/privacy.html`
- 고객지원: `/support.html`
- 앱 스토어 (iOS): [추가 필요]
- 플레이 스토어 (Android): `https://play.google.com/store/apps/details?id=com.recipesoup.app.recipesoup`
