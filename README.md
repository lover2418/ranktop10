# RANKTOP10 — 첫 번째 웹사이트

모바일/PC 반응형 정적 웹사이트. 카테고리 8개(전체 제외), 실시간 화면 내 검색, 순위 상세페이지, JSON 시연 데이터 8개(각 10개 항목)가 포함됩니다.

## 빠른 실행

`index.html`을 파일 탐색기에서 직접 열면 JSON 로딩이 차단될 수 있습니다. 반드시 로컬 웹 서버를 사용하세요.

```bash
python -m http.server 8000
```

브라우저에서 http://localhost:8000 접속.

## GitHub 업로드

1. GitHub에서 `ranktop10` 저장소 생성.
2. 이 압축 파일을 풀고 **ranktop10-site 폴더 안의 파일들**을 저장소 루트에 업로드 (`index.html`이 최상위에 위치해야 함).
3. 변경 사항 커밋.

## Cloudflare Pages 배포

1. Cloudflare → Workers & Pages → Create → Pages → Connect to Git.
2. GitHub 저장소 선택.
3. Framework preset: None, Build command: `exit 0`, Build output directory: `.` (프로젝트 루트).
4. Deploy 후 발급된 `*.pages.dev` 주소로 확인.
5. Pages 프로젝트 → Custom domains → `ranktop10.kr` 추가. 루트 도메인은 Cloudflare DNS와 네임서버 설정이 필요할 수 있습니다. 화면의 안내에 따라 가비아에서 설정하세요.

## 순위 추가 및 변경

`data/rankings.json`에서 각 객체를 수정합니다. `id`는 고유해야 하고 영문 소문자/하이픈을 권장합니다. `category`는 `IT`, `경제`, `여행`, `음식`, `쇼핑`, `건강`, `문화`, `세계` 중 하나입니다. `items` 배열은 10개 항목을 넣으세요. `sourceUrl`은 검증된 HTTPS URL만 넣으세요.

**주의:** 현재 모든 항목은 가상 데모 데이터입니다. 공개 운영 전에 검증된 실제 순위와 출처로 교체하고, `privacy.html`도 운영 상황에 맞게 수정하세요. 정적 웹사이트이므로 관리자 로그인, 자동 수집, 서버 데이터베이스, 실시간 순위 갱신 기능은 포함되어 있지 않습니다.
