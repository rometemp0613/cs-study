# 데이터베이스 (Database) 학습 기록

**학습 방식**: Claude와 함께 실습 중심 학습
**학습 시작일**: 기록 보완 필요

**참고 도서**: "SQL 전문가 가이드" (한국데이터산업진흥원), "친절한 SQL 튜닝" (조시형), "Database System Concepts" (Silberschatz)
**목표**: SQLP(SQL 전문가) 자격증 합격 + 실무 DB 역량
**DBMS**: 공통 이론 위주, SQLP 특화 파트(Part 5~12)에서 Oracle 보충
**선수과목**: 자료구조, 이산수학
**후속과목**: 분산 DB, 빅데이터

---

## SQLP 시험 과목 매핑

| SQLP 과목 | 배점 | 해당 Part |
|-----------|------|-----------|
| 1과목: 데이터 모델링의 이해 | 20점 (객관식) | Part 2 |
| 2과목: SQL 기본 및 활용 | 40점 (객관식) | Part 3, 4 |
| 3과목: SQL 고급활용 및 튜닝 | 70점 (객관식 40 + 서술형 30) | Part 5~11 |
| 서술형 | 30점 (3과목 내) | Part 12 |

> 3과목 관련 항목 42개(49%) — 배점(70점)이 가장 크고 난이도도 최고이므로 집중 배분

---

## 진도 체크리스트

### Part 1: 관계형 DB 기초 이론 [배경지식] (5개)

- [x] **데이터베이스 시스템 개요**
  - 핵심: DBMS, 데이터 독립성, 3단계 스키마
- [x] **관계형 데이터 모델**
  - 핵심: 릴레이션, 튜플, 속성, 도메인
- [ ] **키의 종류와 무결성 제약조건**
  - 핵심: 슈퍼키, 후보키, 기본키, 외래키, 무결성
- [ ] **관계 대수**
  - 핵심: σ, π, ⋈, ∪, −, ×, ÷
- [ ] **관계 해석**
  - 핵심: 튜플/도메인 관계 해석, 관계 대수와의 동치

### Part 2: 데이터 모델링의 이해 [SQLP 1과목] (11개)

- [ ] **데이터 모델링의 이해**
  - 핵심: 3가지 관점, 개념적/논리적/물리적 단계
- [ ] **엔터티(Entity)**
  - 핵심: 유무형, 기본/중심/행위 엔터티
- [ ] **속성(Attribute)**
  - 핵심: 기본/설계/파생, 단일/복합/다중값
- [ ] **관계(Relationship)**
  - 핵심: 차수(1:1, 1:M, M:N), 선택성(필수/선택)
- [ ] **식별자(Identifier)**
  - 핵심: 본질 vs 인조, 식별관계 vs 비식별관계
- [ ] **E-R 다이어그램과 표기법**
  - 핵심: IE/Barker, ERD 작성 절차
- [ ] **정규화와 성능**
  - 핵심: FD, 1NF~BCNF, 정규화가 성능 향상시키는 경우
- [ ] **반정규화**
  - 핵심: 테이블 병합/분할/추가, 컬럼 중복, 판단 기준
- [ ] **대량 데이터에 따른 성능**
  - 핵심: 파티셔닝 설계, 슈퍼/서브타입 변환
- [ ] **데이터베이스 구조와 성능**
  - 핵심: PK/FK 순서, 물리적 설계 고려사항
- [ ] **분산 데이터베이스와 성능**
  - 핵심: 6가지 투명성, GSI

### Part 3: SQL 기본 [SQLP 2과목] (10개)

- [ ] **관계형 데이터베이스 개요**
  - 핵심: SQL 표준, Oracle/SQL Server/PostgreSQL 차이
- [ ] **DDL**
  - 핵심: CREATE/ALTER/DROP/TRUNCATE, 제약조건
- [ ] **DML**
  - 핵심: INSERT/UPDATE/DELETE/MERGE, SELECT 기본
- [ ] **TCL**
  - 핵심: COMMIT/ROLLBACK/SAVEPOINT, ACID
- [ ] **WHERE 절과 연산자**
  - 핵심: BETWEEN/IN/LIKE/IS NULL, NULL 3값 논리
- [ ] **단일행 함수 (문자/숫자/날짜)**
  - 핵심: SUBSTR/ROUND/SYSDATE 등
- [ ] **단일행 함수 (변환/CASE/NULL)**
  - 핵심: TO_CHAR/CASE/NVL/COALESCE
- [ ] **GROUP BY와 HAVING**
  - 핵심: 집계함수, SELECT 논리적 처리 순서
- [ ] **ORDER BY와 정렬**
  - 핵심: NULLS FIRST/LAST, 정렬과 성능
- [ ] **조인 기초**
  - 핵심: EQUI/Non-EQUI/SELF/CROSS/OUTER JOIN

### Part 4: SQL 활용 [SQLP 2과목] (11개)

- [ ] **표준 조인 (ANSI/ISO)**
  - 핵심: INNER/NATURAL/USING/ON, Oracle(+) 문법
- [ ] **집합 연산자**
  - 핵심: UNION/INTERSECT/MINUS, 중복 제거 비용
- [ ] **계층형 질의**
  - 핵심: CONNECT BY, START WITH, LEVEL, 재귀 CTE
- [ ] **서브쿼리**
  - 핵심: 스칼라/인라인 뷰/상관, EXISTS/NOT EXISTS
- [ ] **그룹 함수 (고급)**
  - 핵심: ROLLUP/CUBE/GROUPING SETS
- [ ] **윈도우 함수**
  - 핵심: ROW_NUMBER/RANK/LAG/LEAD, PARTITION BY, ROWS/RANGE
- [ ] **Top N 쿼리와 페이징**
  - 핵심: ROWNUM, FETCH FIRST, 부분범위 처리
- [ ] **DCL**
  - 핵심: GRANT/REVOKE/ROLE, 시스템 vs 객체 권한
- [ ] **절차형 SQL 기초**
  - 핵심: PL/SQL, 변수/조건문/반복문/예외처리
- [ ] **저장 프로시저와 함수/트리거**
  - 핵심: PROCEDURE/FUNCTION/TRIGGER, 커서
- [ ] **뷰와 임시 테이블**
  - 핵심: CREATE VIEW, Materialized View, GTT

### Part 5: DB 아키텍처와 SQL 처리 [SQLP 3과목] (6개)

- [ ] **Oracle 아키텍처 기초**
  - 핵심: SGA/PGA, 서버/백그라운드 프로세스
- [ ] **SQL 파싱과 최적화 과정**
  - 핵심: 소프트/하드 파싱, 실행 흐름
- [ ] **SQL 공유와 재사용**
  - 핵심: 라이브러리 캐시, 바인드 변수의 중요성
- [ ] **바인드 변수와 바인드 피킹**
  - 핵심: Adaptive Cursor Sharing, 한계
- [ ] **데이터 저장 구조**
  - 핵심: 블록/익스텐트/세그먼트/테이블스페이스
- [ ] **데이터베이스 I/O 메커니즘**
  - 핵심: 논리적/물리적 I/O, BCHR, Direct Path I/O

### Part 6: SQL 분석 도구 [SQLP 3과목] (4개)

- [ ] **실행계획 읽기**
  - 핵심: EXPLAIN PLAN, DBMS_XPLAN, 읽는 순서
- [ ] **SQL 트레이스와 10046 이벤트**
  - 핵심: tkprof, Call 통계, 대기 이벤트
- [ ] **AutoTrace와 DISPLAY_CURSOR**
  - 핵심: Starts/E-Rows/A-Rows, 예상 vs 실제
- [ ] **응답 시간 분석**
  - 핵심: CPU+Wait Time, AWR/ASH/ADDM

### Part 7: 인덱스와 인덱스 튜닝 [SQLP 3과목] (8개)

- [ ] **인덱스 구조와 원리**
  - 핵심: B*Tree, 루트/브랜치/리프, ROWID
- [ ] **인덱스 Range Scan**
  - 핵심: 리프 블록 연결, 스캔 시작/종료점
- [ ] **인덱스 기본 사용법**
  - 핵심: 선두 컬럼 가공 금지, 묵시적 형변환
- [ ] **인덱스 확장 기능**
  - 핵심: Full/Unique/Skip/Fast Full Scan, 비트맵
- [ ] **결합 인덱스 설계**
  - 핵심: 컬럼 순서, 선택도, 카디널리티
- [ ] **테이블 액세스 최소화**
  - 핵심: 클러스터링 팩터, 손익분기점, Covered Index
- [ ] **인덱스 스캔 효율화**
  - 핵심: BETWEEN vs IN, LIKE, 비효율 판단
- [ ] **인덱스 설계 실전**
  - 핵심: 공통 선두 컬럼, NL조인용, 소트 제거용

### Part 8: 조인 튜닝 [SQLP 3과목] (6개)

- [ ] **NL 조인**
  - 핵심: 원리, 드라이빙 테이블, Prefetch, 배치 I/O
- [ ] **NL 조인 튜닝 실전**
  - 핵심: 조인 순서, OLTP 환경, 부분범위 처리
- [ ] **소트 머지 조인**
  - 핵심: 양쪽 정렬 후 머지, 비등가 조인
- [ ] **해시 조인**
  - 핵심: Build/Probe Input, 대용량 조인, 수행 조건
- [ ] **스칼라 서브쿼리와 조인**
  - 핵심: 캐싱 효과, Unnesting
- [ ] **고급 조인 기법**
  - 핵심: 세미/안티 조인, Join Elimination

### Part 9: SQL 옵티마이저 [SQLP 3과목] (5개)

- [ ] **옵티마이저 종류와 원리**
  - 핵심: RBO vs CBO, 통계정보, ALL_ROWS/FIRST_ROWS
- [ ] **통계정보와 카디널리티 추정**
  - 핵심: 히스토그램, Selectivity
- [ ] **SQL 공유와 재사용 심화**
  - 핵심: Child Cursor, SQL Plan Baseline
- [ ] **쿼리 변환 (서브쿼리/뷰)**
  - 핵심: Unnesting, 뷰 Merging, Predicate Pushing
- [ ] **쿼리 변환 (조건절/조인)**
  - 핵심: Transitive Closure, OR Expansion

### Part 10: 고급 SQL 튜닝 [SQLP 3과목] (7개)

- [ ] **소트 튜닝**
  - 핵심: Sort 종류, 인덱스로 소트 대체, Top N 알고리즘
- [ ] **DML 튜닝 - INSERT**
  - 핵심: Direct Path, Append, nologging, Bulk
- [ ] **DML 튜닝 - UPDATE/DELETE/MERGE**
  - 핵심: 수정 가능 조인 뷰, 파티션 Exchange
- [ ] **데이터베이스 Call 최소화**
  - 핵심: User/Recursive Call, Array Size, One SQL
- [ ] **파티셔닝**
  - 핵심: Range/List/Hash, Partition Pruning, Local/Global 인덱스
- [ ] **배치 프로그램 튜닝**
  - 핵심: 병렬 처리, 파티션 활용, PL/SQL 최적화
- [ ] **고급 SQL 활용**
  - 핵심: 피벗, 누적합, 선분이력, CTE, CONNECT BY 응용

### Part 11: Lock과 트랜잭션 동시성 제어 [SQLP 3과목] (6개)

- [ ] **Lock 기본 개념**
  - 핵심: 공유/배타 Lock, Row/Table Level, 호환성 매트릭스
- [ ] **Oracle Lock과 래치/뮤텍스**
  - 핵심: TX/TM Lock, Latch, Enqueue
- [ ] **블로킹과 데드락**
  - 핵심: 블로킹 vs 데드락, 탐지/해결, Timeout
- [ ] **트랜잭션 격리 수준**
  - 핵심: 4단계, Dirty/Non-Repeatable/Phantom Read
- [ ] **MVCC**
  - 핵심: Undo, Snapshot, SCN, CR 블록, 읽기 일관성
- [ ] **동시성 제어 실전**
  - 핵심: 비관적/낙관적, SELECT FOR UPDATE, 채번 로직

### Part 12: 실전 종합 & 서술형 대비 [SQLP 서술형 30점] (6개)

- [ ] **실행계획 분석 종합 실전**
  - 핵심: 복잡한 실행계획 해석, 비효율 구간 식별
- [ ] **인덱스 설계 실전 문제**
  - 핵심: 최적 인덱스 설계, 추가 vs 변경 판단
- [ ] **SQL 튜닝 실전 - 조인 최적화**
  - 핵심: 힌트로 조인 방식 변경, 쿼리 리팩토링
- [ ] **SQL 튜닝 실전 - 소트/DML**
  - 핵심: ORDER BY 최적화, 대량 DML, 배치 시나리오
- [ ] **서술형 대비 - ERD 분석과 SQL 작성**
  - 핵심: ERD 해석, 힌트 포함 SQL, 답안 작성 요령
- [ ] **SQLP 모의고사 및 오답 분석**
  - 핵심: 시간 배분, 오답 패턴, 취약 영역 보강

---

## 학습 일지

| 날짜 | 주제 | 주요 내용 | 비고 |
|------|------|----------|------|
| 2026-02-16 | 데이터베이스 시스템 개요 | DBMS, 데이터 독립성(논리적/물리적), 3단계 스키마(외부/개념/내부) | 첫 수업! |
| 2026-03-08 | 관계형 데이터 모델 | 릴레이션, 튜플, 속성, 도메인, 차수/카디널리티, 스키마/인스턴스, 4특성(유무무원) | 20일 만에 복귀 |

---

## 진행 현황

- **총 항목**: 85개
- **완료**: 2개
- **진행률**: 2.4%

---

## 디렉토리 구조

```
cs/database/
├── README.md
├── CLAUDE.md
├── notes/
└── logs/
```
