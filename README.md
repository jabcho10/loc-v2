# LOC 분할매매 v2

SOXL·TQQQ LOC 분할매매 v2 규칙의 백테스트 결과와 주문표입니다. v1([loc5-backtest](https://github.com/jabcho10/loc5-backtest))과 같은 틀에 v2 규칙을 넣었습니다.

| | SOXL v2 | TQQQ |
|---|---|---|
| 매수 | 종가 ≤ 3일평균 × 0.995 | 종가 ≤ 3일평균 × 0.995 |
| 매도 (전량) | 종가 ≥ 3일평균 × 1.009 | 종가 ≥ 3일평균 × 1.012 |
| 평소 분할 | 5분할, 하루 1티어 | 5분할, 하루 1티어 |
| QQQ 12개월 < 0 | 20분할 | 20분할 |
| 직전 사이클 손실 | 10분할 | – |
| 3일 연속 하락 | 추가 매수 중지 | – |

- `index.html` — 백테스트. 내장 일봉(SOXL 2001~, TQQQ 1999~, QQQ)으로 브라우저에서 다시 계산합니다.
- `order.html` — 다음 거래일 LOC 주문표와 계좌 기록(브라우저 저장).
- `prices.json` — SOXL·TQQQ·QQQ 최근 400거래일 종가. GitHub Actions(`.github/workflows/prices.yml`)가 매일 장 마감 후 `scripts/update_prices.py`로 갱신합니다. QQQ는 배당 조정 종가입니다.

내장 데이터는 로컬 작업 폴더의 `backtest/build_site.py`로 만듭니다.
