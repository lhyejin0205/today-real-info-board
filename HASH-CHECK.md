# 공개 자료 꾸러미 확인 기록 (카드 3)

- 공개 package ID: `aleph-t04-real-information-board-public-contract-v2`
- 해시 방식: SHA-256
- 확인 날짜(KST): 2026-10-19

## 파일 해시 대조

| 항목 | 결과 |
|---|---|
| `asset-manifest.json`에 적힌 파일 수 | 17개 |
| 내려받은 ZIP 안의 파일 해시와 목록 해시가 같은 파일 | 17개 / 17개 일치 |
| 파일 크기(bytes)가 목록과 같은 파일 | 17개 / 17개 일치 |
| ZIP 안의 전체 항목 수 | 18개 (목록 17개 + `asset-manifest.json` 자신) |

목록에 자기 자신(`asset-manifest.json`)은 해시가 적혀 있지 않아서, 18개 항목 중 17개를 대조했습니다.

## 합성 fixture 검사 결과

공개 fixture 9개를 같은 순서로 재생해서, 각 fixture에 적힌 기대값과 비교했습니다.

| 시험 | 기대한 상태 | 결과 |
|---|---|---|
| 정상 D1-A, D1-B, D2 | fresh / none, 일별 행 1건, 1건, 2건, 변화값 +15 | 일치 |
| 느린 응답 (timeout) | stale / timeout, 마지막 정상값 105, 행 1건 | 일치 |
| 접근 거절 (401) | stale / auth, 마지막 정상값 105, 행 1건 | 일치 |
| 호출 제한 (429) | stale / rate_limit, 마지막 정상값 105, 행 1건 | 일치 |
| 오프라인 | stale / offline, 마지막 정상값 105, 행 1건 | 일치 |
| 형식 변경 | stale / schema_error, 마지막 정상값 105, 행 1건 | 일치 |
| 오류 뒤 회복 (RECOVER-D2) | fresh / none, 행 2건, 저장값 120, 변화값 +15 | 일치 |

합성 fixture의 값과 날짜(2026-08-24 등)는 연습용 가짜 값이며, 실제 달 모양 데이터와는 따로 저장됩니다.
