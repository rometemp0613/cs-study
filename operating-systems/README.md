# 운영체제 (Operating Systems) 학습 기록

**참고 도서**: "운영체제: 아주 쉬운 세 가지 이야기" (OSTEP, Remzi & Andrea Arpaci-Dusseau)
**선수과목**: 자료구조, 컴퓨터 구조
**후속과목**: 분산 시스템, 임베디드 시스템

---

## 진도 체크리스트

### Intro

- [x] **운영체제 소개** (Ch.2 Introduction)
  - 핵심: 가상화, 동시성, 영속성 — OS의 3대 주제

### Part 1: Virtualization (가상화)

- [x] **프로세스** (Ch.4 Processes)
  - 핵심: 프로세스 개념, 상태 전이, 자료구조
- [ ] **프로세스 API** (Ch.5 Process API)
  - 핵심: fork(), exec(), wait(), 프로세스 생성
- [ ] **제한적 직접 실행** (Ch.6 Direct Execution)
  - 핵심: 유저/커널 모드, 트랩, 타이머 인터럽트
- [ ] **CPU 스케줄링: 기초** (Ch.7 CPU Scheduling)
  - 핵심: FIFO, SJF, RR, 반환시간/응답시간
- [ ] **CPU 스케줄링: MLFQ** (Ch.8 Multi-Level Feedback Queue)
  - 핵심: 다단계 피드백 큐, 규칙, 우선순위 부스트
- [ ] **CPU 스케줄링: 비례 배분** (Ch.9 Lottery Scheduling)
  - 핵심: 추첨 스케줄링, 보폭 스케줄링
- [ ] **멀티프로세서 스케줄링** (Ch.10 Multi-CPU Scheduling)
  - 핵심: 캐시 친화성, 단일/다중 큐, Linux O(1)/CFS
- [ ] **주소 공간** (Ch.13 Address Spaces)
  - 핵심: 주소 공간 추상화, 가상 메모리 목표
- [ ] **메모리 API** (Ch.14 Memory API)
  - 핵심: malloc(), free(), 메모리 관련 오류
- [ ] **주소 변환** (Ch.15 Address Translation)
  - 핵심: 동적 재배치, 베이스-바운드 레지스터
- [ ] **세그멘테이션** (Ch.16 Segmentation)
  - 핵심: 세그먼트, 외부 단편화, 빈 공간 관리
- [ ] **빈 공간 관리** (Ch.17 Free Space Management)
  - 핵심: 분할/병합, best fit/worst fit/first fit/next fit
- [ ] **페이징: 개요** (Ch.18 Introduction to Paging)
  - 핵심: 페이지/프레임, 페이지 테이블, 주소 변환
- [ ] **페이징: TLB** (Ch.19 TLBs)
  - 핵심: TLB 동작, TLB 미스 처리, 컨텍스트 스위칭
- [ ] **페이징: 더 작은 테이블** (Ch.20 Smaller Tables)
  - 핵심: 멀티레벨 페이지 테이블, 역 페이지 테이블
- [ ] **스왑: 메커니즘** (Ch.21 Swap Mechanisms)
  - 핵심: 스왑 공간, 페이지 폴트, 페이지 교체
- [ ] **스왑: 정책** (Ch.22 Swap Policies)
  - 핵심: FIFO, LRU, Clock 알고리즘, 스래싱
- [ ] **완전한 VM 시스템: VAX/VMS** (Ch.23.1)
  - 핵심: VMS 주소 공간, 페이지 교체 정책, 세그먼트 FIFO
- [ ] **완전한 VM 시스템: Linux** (Ch.23.2)
  - 핵심: Linux 주소 공간, 페이지 테이블, 대용량 페이지, OOM killer

### Part 2: Concurrency (동시성)

- [ ] **스레드 소개** (Ch.26 Concurrency and Threads)
  - 핵심: 스레드 개념, 공유 데이터, 경쟁 조건
- [ ] **스레드 API** (Ch.27 Thread API)
  - 핵심: pthread_create, join, mutex, 조건 변수
- [ ] **락** (Ch.28 Locks)
  - 핵심: 스핀 락, 비교-교환, 티켓 락, 큐 기반 락
- [ ] **락 기반 자료구조** (Ch.29 Locked Data Structures)
  - 핵심: 병행 카운터, 병행 연결 리스트, 병행 큐, 병행 해시 테이블
- [ ] **조건 변수** (Ch.30 Condition Variables)
  - 핵심: wait(), signal(), 생산자-소비자 문제
- [ ] **세마포어** (Ch.31 Semaphores)
  - 핵심: 이진/카운팅 세마포어, 식사하는 철학자
- [ ] **동시성 버그** (Ch.32 Concurrency Bugs)
  - 핵심: 교착상태, 비교착상태 버그, 예방/회피
- [ ] **이벤트 기반 동시성** (Ch.33 Event-Based Concurrency)
  - 핵심: select()/poll()/epoll, 이벤트 루프

### Part 3: Persistence (영속성)

- [ ] **I/O 장치** (Ch.36 I/O Devices)
  - 핵심: I/O 포트, 인터럽트, DMA
- [ ] **하드 디스크** (Ch.37 Hard Disk Drives)
  - 핵심: 디스크 구조, 디스크 스케줄링 (SSTF, SCAN, C-SCAN)
- [ ] **RAID** (Ch.38 RAID)
  - 핵심: RAID 0/1/4/5, 스트라이핑, 미러링, 패리티
- [ ] **파일과 디렉토리** (Ch.39 Files and Directories)
  - 핵심: inode, 파일 디스크립터, 디렉토리 구조
- [ ] **파일 시스템 구현** (Ch.40 File System Implementation)
  - 핵심: VSFS, inode, 데이터 비트맵, 슈퍼블록
- [ ] **지역성과 FFS** (Ch.41 FFS)
  - 핵심: 실린더 그룹, 블록 할당 정책
- [ ] **FSCK와 저널링** (Ch.42 FSCK and Journaling)
  - 핵심: 일관성 문제, fsck, 저널링(WAL)
- [ ] **로그 구조 파일 시스템** (Ch.43 Log-Structured File System)
  - 핵심: LFS, 세그먼트, 가비지 컬렉션
- [ ] **플래시 기반 SSD** (Ch.44 Flash-Based SSDs)
  - 핵심: NAND 플래시, FTL, wear leveling
- [ ] **데이터 무결성과 보호** (Ch.45 Data Integrity)
  - 핵심: 체크섬, 디스크 오류 모델, ZFS

### Part 4: Distributed Systems (분산 시스템)

- [ ] **분산 시스템** (Ch.48 Distributed Systems)
  - 핵심: 통신, 장애 모델, RPC
- [ ] **네트워크 파일 시스템** (Ch.49 NFS)
  - 핵심: NFSv2 프로토콜, 무상태 서버, 캐싱
- [ ] **앤드류 파일 시스템** (Ch.50 AFS)
  - 핵심: 전체 파일 캐싱, 콜백, NFS와 비교

### Part 5: Security (보안)

- [ ] **보안 개요** (Ch.53 Intro Security)
  - 핵심: 보안 목표 (CIA), 위협 모델, 설계 원칙
- [ ] **인증** (Ch.54 Authentication)
  - 핵심: 패스워드, 해싱, 다중 인증
- [ ] **접근 제어** (Ch.55 Access Control)
  - 핵심: ACL, 능력(Capability), RBAC
- [ ] **암호학** (Ch.56 Cryptography)
  - 핵심: 대칭/비대칭 암호, 해시, 디지털 서명
- [ ] **분산 보안** (Ch.57 Distributed Security)
  - 핵심: 세션 키, TLS/SSL, 인증서

---

## 학습 일지

| 날짜 | 주제 | 주요 내용 | 비고 |
|------|------|----------|------|
| 2026-02-08 | Ch.2 운영체제 소개 | 가상화/동시성/영속성 3대 주제, 설계 목표, OS 역사 | 첫 수업! |
| 2026-02-08 | Ch.4 프로세스 | 프로세스 정의, 상태 전이(Running/Ready/Blocked), PCB, 메커니즘 vs 정책 | |

---

## 진행 현황

- **총 항목**: 46개
- **완료**: 2개
- **진행률**: 4%

---

## 디렉토리 구조

```
operating-systems/
├── README.md
├── CLAUDE.md
├── .gitignore
├── notes/
│   ├── intro/
│   ├── part1-virtualization/
│   ├── part2-concurrency/
│   ├── part3-persistence/
│   ├── part4-distributed/
│   └── part5-security/
├── review/            ← 3단계 암기 시스템
│   ├── 1-new/         ← 새로 배운 용어
│   ├── 2-practicing/  ← 복습 중
│   └── 3-mastered/    ← 완벽 암기
├── logs/
└── textbook/          ← OSTEP 챕터 PDF (.gitignore 처리)
```
