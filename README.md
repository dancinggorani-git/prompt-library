# 프롬프트 라이브러리

생성형 AI 프롬프트 보관 PWA

## 로컬 실행
```bash
npx serve .
# 또는
python3 -m http.server 8080
```
브라우저에서 `http://localhost:8080` 열기

## 배포 (GitHub + Netlify)

### 최초 설정
1. GitHub에서 새 레포 생성 (예: `prompt-library`)
2. 이 폴더를 push
   ```bash
   git init
   git add .
   git commit -m "init"
   git remote add origin https://github.com/YOUR_ID/prompt-library.git
   git push -u origin main
   ```
3. [netlify.com](https://netlify.com) → New site → Import from GitHub → 레포 선택
4. Build command: 비워두기 / Publish directory: `.` → Deploy

### 업데이트
```bash
# 파일 수정 후
git add .
git commit -m "프롬프트 추가"
git push
# → Netlify가 자동으로 30초 내 재배포
```

## 폴더 구조
```
prompt-library/
├── index.html       앱 본체
├── manifest.json    PWA 설정
├── sw.js            Service Worker (오프라인 지원)
├── netlify.toml     Netlify 헤더 설정
├── icons/           앱 아이콘 (선택)
│   ├── icon-192.png
│   └── icon-512.png
└── README.md
```

## 기기 간 동기화
앱 내 ⚙ 버튼 → JSON 내보내기/가져오기  
또는 JSON을 iCloud Drive / Google Drive에 저장해서 기기 간 공유
