# data_algorhythm-project

배송 경로 최적화 실험을 위한 자료구조/알고리즘 프로젝트입니다.  
동일한 고객 좌표 데이터에서 `Baseline(Queue/FIFO)`, `Greedy(Nearest Neighbor)`, `MST(Prim + DFS)` 경로를 비교하고, 이동거리(km)와 계산시간(ms)을 분석합니다.

## 프로젝트 개요

- 기준 출발지(PP 센터): `lat=37.4786`, `lon=127.123`
- 고객 데이터: 50개 좌표(`id`, `lat`, `lon`, `dong`)
- 핵심 비교 항목:
  - 총 이동거리(km)
  - 알고리즘 계산시간(ms)
  - Baseline 대비 개선율

## 노트북 결과 요약

- Baseline 단독 검증(`N=50`)
  - 경로 길이: `51개 노드`
  - 총 이동거리: `104.37 km`
  - 계산시간: `0.99 ms`

- Validation 비교 결과
  - `N=10`
    - Baseline: `19.485 km`, `0.0 ms`
    - Greedy: `8.503 km`, `0.0 ms`, 개선율 `56.36%`
    - MST-DFS: `9.105 km`, `0.0 ms`, 개선율 `53.27%`
  - `N=50`
    - Baseline: `104.374 km`, `1.0 ms`
    - Greedy: `13.604 km`, `0.0 ms`, 개선율 `86.97%`
    - MST-DFS: `14.876 km`, `4.0 ms`, 개선율 `85.75%`
  - `N=100` 요청 시
    - 데이터가 50개라 노트북에서 `N=50`으로 자동 조정
    - 거리 결과는 `N=50`과 동일

- 복잡도 정리(노트북 내 요약)
  - Baseline: 시간 `O(N)`, 공간 `O(N)`
  - Greedy: 시간 `O(N^2)`, 공간 `O(N)`
  - MST-DFS: 시간 `O(N^2 log N)`, 공간 `O(N^2)`
