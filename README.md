# 스타템포착 — 공식 웹사이트 001 상품 등록 배포본

**현재 상태:** 이전 좋은물건노트 상품 001~015 초기화 후, 스타템포착 신규 001번 상품 1개 등록. 기존 상품과 영상 파일은 포함하지 않습니다.

- **001번 제휴 iframe:** `https://coupa.ng/cqB5Lh` (원문 그대로 보존)
- 저장 위치: `products.js` 및 `partner-html/001.html`
- 현재 상품 수: **1개** (기존 상품 15개는 복구하지 않음).

## 배포 방법 (GitHub Pages)

- ZIP 압축을 풀고 안의 **파일·폴더 자체**를 GitHub Pages 배포 브랜치의 저장소 루트에 업로드하세요. `index.html`은 반드시 저장소 최상위에 둡니다.
- 기존 저장소의 구 상품 파일도 반드시 삭제하세요. GitHub에서 새 파일만 덮어쓰면 삭제된 `partner-html/001.html`~`015.html` 및 `video/001.mp4` 등이 서버에 남을 수 있습니다.
- 배포 브랜치/루트는 GitHub Pages 설정과 일치해야 합니다. 배포 후 사이트 제목, 상품 1개, 001/1 검색, 모바일 페이지 전환을 점검하세요.
- **기존 GTM 컨테이너 ID(`GTM-TBPN8QQW`) 및 하단 쿠팡 공식 광고 캐러셀의 trackingCode(`AF4347646`)은 변경하지 않았습니다.** 새 브랜드에서 해당 계정·권한을 계속 사용할지 확인하세요. 기존 dataLayer 이벤트 이름 `goodnote_search`, `goodnote_view_content`도 연결을 깨지 않기 위해 그대로입니다.

## 추가 상품 등록

쿠팡 공식 제휴 iframe을 문자 단위로 변경하지 않고 신규 등록합니다.

```sh
python tools/register_product.py --number 002 --partner-html-file /path/to/002.html --dry-run
python tools/register_product.py --number 002 --partner-html-file /path/to/002.html
```

- 등록된 상품: `001`, 다음 신규 상품번호는 `002`. 번호와 공식 쿠팡 iframe 원문 외의 임의 제품 정보는 만들지 않습니다.
- 카드는 모바일 2열/PC 4열, 상품번호 검색(`1`=`001`, `10`=`010`), 최신/오래된순 정렬, 모바일 페이지당 10개, PC 12개씩 더보기 그대로입니다.
- 새 상품은 `products.js`와 `partner-html/NNN.html`에 함께 기록되며, 등록 스크립트는 기존 `products.js`의 보관본을 사이트 루트 밖에 생성합니다.
- 하단 쿠팡 제휴 안내, 광고 캐러셀 및 `smtm1389@gmail.com` 광고·협업 문의 링크를 유지했습니다.
- 외부 제공 제휴 코드/광고의 동작과 수익 귀속은 배포 후 브라우저에서 확인해야 합니다.

주의: 이 ZIP은 **새 사이트용 수정본**이며 GitHub 저장소에 자동 배포된 것은 아닙니다.
