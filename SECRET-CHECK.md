# 비밀값 검색 결과 (T04-C11)

이 프로젝트는 비밀키가 필요 없는 공개 데이터(미국 해군천문대 USNO)를 사용합니다.
호출 주소: `https://aa.usno.navy.mil/api/rstt/oneday?date=날짜&coords=36.35,127.38&tz=9`

| 검사 위치 | 방법 | 결과 |
|---|---|---|
| 브라우저 코드 | 배포된 `index.html` 전체를 읽고 `key`, `token`, `secret`, `password`, `authorization` 단어 확인 | 0건 |
| 네트워크 요청 | 개발자 도구 Network 탭 → `oneday?date=...` → Headers → Request Headers 확인 | 0건 (Accept, Origin, Referer, User-Agent 등 브라우저 기본 항목만 있고 Authorization, 키 항목 없음) |
| 네트워크 응답 | 같은 화면의 Response headers 확인 | 0건 (서버 안내 항목만 있고 비밀값 없음) |
| 배포 파일 | GitHub 저장소의 `index.html` 확인 | 0건 |
| Git 기록 | 코드를 올릴 때 키·비밀번호를 넣은 적 없음 (호출 주소에 날짜와 좌표만 사용) | 0건 |

- 검사 날짜(KST): 2026-10-19
- 사용한 API: USNO (키 불필요)
- 이 페이지가 밖으로 보낸 요청: 해군천문대 1건 (Network 탭 하단 `2 requests` 중 나머지 1건은 페이지 자체)
- 참고: 응답 안의 `Access-Control-Allow-Headers: Authorization`은 서버가 받을 수 있는 항목 이름을 알리는 안내일 뿐, 실제 비밀값이 아닙니다.
