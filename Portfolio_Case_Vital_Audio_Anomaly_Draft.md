# AV/AVN 오디오 파열음 재현 및 패치 검증

> **초안 상태:** Vital Auto 재직 중 사용자 회고를 바탕으로 작성. 당시 Vital Auto 자료는 남아 있지 않으며, 고객/차량 식별 정보와 원본 로그는 포함하지 않았다. 외부 공개 전 회사·고객 기밀 범위를 확인해야 한다.

## 배경

Motrex 외주 프로젝트에서 HKMC 해외향 MS400A·MS500A AV/AVN을 IVI Test Engineer로 검증했다. BAT 테스트 중 Billie Eilish의 “Bad Guy”를 재생해 두고 시험하던 중 평소와 다른 음을 감지했다. 처음에는 다른 팀원들이 이상을 알아채지 못했지만, 음량을 크게 올려 다시 듣자 파열음이 확인됐다.

## 본인 수행

1. 청감상 이상을 다시 확인하고 동료에게 교차 확인을 요청했다.
2. 음량을 높여 파열음을 재현했다.
3. 음역대별 음원을 사용하고 볼륨 수준을 바꿔 시험했다.
4. 스피커에서도 파열음이 발생하는 것을 확인하고 협력사에 전달했다.
5. 수정 방향은 고주파 대역을 강제로 낮추고 seek up/down 시 mute delay를 넣는 것이었다.
6. 패치 버전에서 재시험해 정상 동작을 확인하고 이슈를 종료했다.

## 결과와 근거 한계

- 일상 기능 시험에 그치지 않고 발견한 음향 이상을 재현 가능한 조건으로 좁혀 협력사에 전달했다.
- 패치 적용 버전에서 재검증해 이상이 재발하지 않는 것을 확인했다.
- 사용자는 파열음이 스피커에서 발생했다고 설명했다. 고주파 대역 감쇠와 탐색 시 mute delay가 수정 방향이었다. 구현 담당자 및 내부 설계 상세는 확인하지 않았다.

## 이력서 문장 초안

**한국어**

HKMC 해외향 AV/AVN BAT 검증 중 스피커 파열음을 발견하고, 음역대·볼륨·스피커 조건을 바꿔 재현 범위를 좁혀 협력사에 전달했습니다. 고주파 대역 감쇠와 seek up/down 시 mute delay를 적용한 수정 버전에서 정상 동작을 확인했습니다. *(회사 기록이 남아 있지 않은 회고 기반 사례)*

**English**

During black-box validation of overseas-market AV/AVN systems, identified speaker popping, narrowed reproduction conditions by varying audio frequency, volume, and speaker configuration, and reported the findings to the supplier. Verified a fix that reduced high-frequency output and added a mute delay during seek up/down. *(Retrospective account; original company records are unavailable.)*

## 외부 공개 전 확인

MS400A/MS500A 모델명, 음원명, BAT 용어 및 상세 시험 조건을 공개해도 되는지 전 직장·고객 기밀 기준을 확인한다.
