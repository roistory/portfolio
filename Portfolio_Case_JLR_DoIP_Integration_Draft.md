# JLR DoIP 진단 환경 통합·검증

**작성 기준:** 사용자 회고, 2026-09-28  
**회사:** EZDS 사내 프로젝트  
**기간:** 전체 프로젝트 기간은 2023.02–2023.08. 원래 사용자 피드백 기간까지 포함해 1년으로 계획했으나, 기능 분석·구성과 실제 배포를 2–6월에 완료하고 이후 2개월은 사용자 피드백을 받는 기간으로 상정했다. 따라서 1년은 실제 프로젝트 수행 기간이 아니라 원래 계획 기간이다. 사용자 피드백의 실제 종료 여부·날짜는 미확인. 사람인 PDF에는 “1년 목표 중 핵심 완료 4개월”, LinkedIn에는 2023.02–2023.07로 기재되어 있으나, 사용자가 설명한 일정 상세를 본문 기준으로 반영한다.  
**기밀 처리:** 회사 자료와 원본 로그는 보유하지 않음. 본 초안에는 특정 차량·고객 데이터나 통신 페이로드를 포함하지 않음.

## 한 줄 요약

JLR DoIP 차량을 대상으로 OEM 진단 프로그램의 진단 흐름을 사내 진단기·시뮬레이터와 실차 환경에서 재현하고 비교할 수 있도록 통신 분석, 진단 DB 구성, 검증 환경 및 통신 기술 가이드를 마련하고 배포 후 안정화까지 담당했다. 소프트웨어 코드 개발은 담당하지 않았다.

## 배경과 목표

세계여행 후 EZDS가 DoIP 프로젝트의 적임자로 연락해 담당을 요청했다. 프로젝트는 회사 자체 프로젝트였고 기존 JLR 담당 업무도 함께 수행했다. 처음에는 사내 시뮬레이터에서 DoIP 진단 통신이 되지 않아 다른 검증이 막혔다. 목표는 OEM 진단 프로그램이 DoIP 차량에서 수행하는 진단 동작을 사내 진단기·시뮬레이터·VCI·실차 환경에서도 분석하고 검증할 수 있도록 통신과 테스트 환경을 갖추는 것이었다.

## 담당 업무

- JLR Pathfinder와 JLR Diagnostic을 사용해 OEM DoIP 진단 흐름을 확인했다.
- Wireshark 캡처와 사내 시뮬레이터 출력의 로직 및 통신 내역을 대조했다.
- 사내 시뮬레이터가 JLR OEM 진단 환경과 DoIP 통신을 하는지 확인했다.
- DoIP 통신을 분석하고 통신 범위의 기술 가이드를 작성했다.
- 사내 진단기용 DoIP DB를 규격에 맞게 구성하고 진단기·VCI·시뮬레이터·실차 연동을 검증했다.
- OEM 진단 프로그램의 DoIP 진단 흐름을 참고해 검증 환경에서 진단 기능을 재현하고 테스트했다.
- 배포 후 고객 문의와 프로젝트 안정화 업무를 맡았다.

## 이력서에만 기재된 추가 주장

사람인 PDF는 실차 DoIP 패킷 캡처와 Routing/Target Address 분석, GDS VCI 및 VCI Simulator 환경, OBD-RJ45 케이블 설계·제작(5V 주입), DoIP 데이터를 UDS 관점으로 분석해 진단기에 적용, 단계별 테스트 케이스 및 문서 표준화 등을 추가 기재한다. DoIP 및 UDS 진단 지원 차종 각 40% 확대도 성과로 적혀 있다. 이 세부 내용은 이번 대화에서 사용자가 확인하지 않았으며 원본 자료도 없어 본 초안의 확정 수행·성과 문구에는 포함하지 않는다.

## 문제 해결 사례

사내 시뮬레이터에서 DoIP 진단 통신이 시작되지 않아 통신 로직 및 환경을 확인하던 중 OBD 케이블 문제를 발견했다. 케이블 문제를 해결한 후 막혀 있던 시뮬레이터·OEM·실차 연동 검증을 진행할 수 있었다. 이 사례는 사용자 회고에 근거하며 당시 캡처·결함 기록은 남아 있지 않다.

## 사용 도구와 경계

**도구:** Wireshark, JLR Pathfinder, JLR Diagnostic, 사내 진단기, 사내 시뮬레이터, VCI, DoIP 실차 환경  
**본인 역할:** 통신 분석·해석, 시뮬레이터/진단 DB 구성, 로그·동작 비교, 테스트 환경 검증, 기술 문서 및 배포 후 지원  
**역할에 포함되지 않은 업무:** C/C++ 등 소스 코드 개발

## 결과

- 사내 DoIP 진단 통신을 OEM 프로그램·시뮬레이터·Wireshark·진단기·VCI·실차 맥락에서 검증하는 환경을 마련했다.
- 통신 전용 기술 가이드를 작성했다.
- OBD 케이블 문제를 해결해 차단되어 있던 DoIP 시뮬레이터 검증을 재개했다.
- 배포 후 CS와 안정화까지 지원했다.
- 전체 기간은 2023.02–08. 원래 1년 계획이었으며, 기능 분석·구성·배포는 2–6월에 마치고 이후 2개월은 사용자 피드백 기간으로 상정했다. 실제 피드백 종료일은 미확인.

## 이력서 문장 초안

### 한국어

EZDS 사내 JLR DoIP 진단 환경 통합 프로젝트를 담당해 OEM 진단 흐름과 DoIP 통신을 분석하고, Wireshark·JLR 진단 프로그램·사내 시뮬레이터 및 진단기·VCI·실차 간 동작을 대조했습니다. 진단 DB와 테스트 환경을 구성하고 통신 기술 가이드를 작성했으며, 시뮬레이터 연결 장애를 OBD 케이블 문제로 찾아 해결했습니다. 배포 후 고객 지원과 안정화까지 담당했습니다. (사용자 회고; 전체 프로젝트 2023.02–08, 원래 1년 계획 중 분석·구성·배포를 2–6월 완료하고 후속 2개월은 피드백 기간으로 상정; 원본 자료 없음; 소스 코드 개발 제외.)

### English

Owned an in-house JLR DoIP diagnostic-environment integration project at EZDS, analyzing OEM diagnostic flows and comparing communications across Wireshark, JLR diagnostic software, the in-house simulator and diagnostic tool, VCI, and real vehicles. Configured diagnostic data and the test environment, wrote a communication-focused technical guide, and traced a simulator connectivity issue to an OBD cable. Supported the project through post-release customer support and stabilization. (Retrospective account; the full project ran from February to August 2023 against an original one-year plan including user feedback. Analysis, configuration, and release were completed from February to June, with the following two months planned for user feedback. Original records are unavailable; no source-code development.)

## 확인이 필요한 이력서 표현

사람인 PDF에는 “1년 목표 중 핵심 완료 4개월”이라고 적혀 있다. 사용자 설명에 따르면 이는 원래 사용자 피드백 기간을 포함해 1년으로 계획했던 프로젝트에서 기능 분석·구성과 실제 배포를 2–6월에 완료한 기간을 가리킨다. 전체 프로젝트 기간은 2023.02–08이며, 이후 2개월은 피드백 기간으로 상정했다.

### 사용자 추가 확인 (2026-09-28)

사용자는 2023.02–08이 프로젝트 전체 기간이라고 확인했다. 원래 계획은 사용자 피드백 기간까지 포함해 1년이었으며, 기능 분석·구성과 실제 배포를 2–6월에 완료하고 이후 2개월을 사용자 피드백 기간으로 상정했다. 따라서 1년은 계획 기간이고 실제 수행 기간은 7개월이다. 피드백 기간의 실제 종료 및 결과 기록은 미확인. 직접 수행 범위는 다음과 같이 추가 확인했다.

- OBD-RJ45 케이블을 직접 제작해 사내 시뮬레이터와 JLR OEM 간 DoIP 통신을 성립시켰다.
- 초기 연결 설정을 위해 Routing/Target Address를 분석하고 시뮬레이터를 구성했다.
- DoIP 지원 차량의 진단기 기본 기능인 DTC Read, DTC Clear, Information을 추가했다.
- 이 기능과 통신 환경 구성은 프로그래밍 코드 작성이 아니라 기존 진단기·시뮬레이터 환경과 DB에 구성한 업무였다.

이력서에 있는 DoIP·UDS 지원 차종 40% 확대는 사용자가 확인하지 않았고 산식·분모도 남아 있지 않아 정량 성과로 쓰지 않는다.
