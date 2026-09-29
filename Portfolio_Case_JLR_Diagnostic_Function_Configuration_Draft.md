# JLR Auto VIN 및 진단 기능 구성·검증

**회사:** EZDS  
**기간:** 2019.07–2022.03 (사용자 확인)  
**역할 경계:** OEM 진단 기능 분석, 기존 진단기 DB 구성·검증·배포. 소스 코드 작성은 하지 않음.  
**근거:** 사용자 회고, 2026-09-28. 당시 사내 자료는 남아 있지 않음.

## 사례 요약

JLR OEM 진단 프로그램의 차량 식별 및 서비스 기능을 분석해, 사내 진단기에 적용할 수 있도록 기존 데이터베이스와 기능 항목을 구성하고 검증했다. 사용자 설명에 따르면 이 기간의 JLR 비코딩 진단 업무는 모두 본인이 담당했다.

## Auto VIN 구성

OEM의 VIN 기반 식별 동작과 식별 가능한 항목을 분석했다. 모델명, 트림, 엔진, 구동 타입 등 OEM이 VIN으로 판별하는 당시 현존 모델 정보를 확인해 사내 진단기의 Auto VIN 데이터로 구성했다. 이후 차량 식별과 진단 기능 접근을 확인했다. 사용자는 Auto VIN 적용 후 고객 문의가 줄었다고 기억하지만, 감소율·측정 기간·문의 분류의 원본 근거는 남아 있지 않다.

## Injector Coding 및 ECU Flash

사용자는 OEM 진단 프로그램에서 해당 기능의 동작을 분석하고, 사내 진단기 데이터베이스에 기능을 구성해 시험 및 배포까지 수행했다. 기존 진단기 환경에서의 분석·DB 구성·검증으로 설명하며, 소스 코드 개발로 표현하지 않는다.

## 이력서 문장 초안

### 한국어

JLR OEM 진단 동작과 VIN 기반 차량 식별 규칙을 분석해 당시 현존 모델의 Auto VIN 데이터를 사내 진단기용 데이터베이스에 구성했습니다. Injector Coding 및 ECU Flash 동작도 OEM 기준으로 분석해 진단기 DB에 적용하고 검증·배포했습니다. Auto VIN 적용 후 관련 고객 문의가 감소했으나, 측정된 감소율이나 기준 자료는 남아 있지 않습니다. (사용자 회고 기반; 소스 코드 개발 제외.)

### English

Analyzed JLR OEM diagnostic behavior and VIN-based vehicle identification, then configured Auto VIN data for the models available at the time in the in-house diagnostic database. Also analyzed OEM Injector Coding and ECU Flash behavior, configured the corresponding diagnostic functions, and validated and released them. The user recalls fewer customer inquiries after the Auto VIN update, but no measured reduction rate or baseline records remain. (Retrospective account; no source-code development.)

## 공개 범위와 미확인 수치

공개 포트폴리오에는 구체적인 OEM 식별 규칙, VIN 문자열·디코딩 테이블, 차량별 데이터, ECU/기능 식별자, 통신 페이로드, 고객 정보 또는 내부 DB 형식을 넣지 않는다. 사람인 이력서의 JLR 15개 모델 추가, 문의/요구 40% 이상 감소, 필드 불량률 감소는 측정 기준과 근거가 남아 있지 않아 확인된 사실로 제시하지 않는다. 모델 범위와 기능 구성 방식은 이 초안처럼 추상적으로만 설명한다.
