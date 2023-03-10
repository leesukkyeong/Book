# **인프라를 지탱하는 응용이론**


## 캐시
특징
- 돈의 cash가 아니라 cache임
- 숨기는 장소라는 의미가 있음
- 사용 빈도가 높은 데이터를 고속으로 엑세스 할 수 있는 위치에 두는 것을 의미
- 임의 저장소를 의미
- 데이터 재사용을 전제로 함
- 장점: 데이터에 고속으로 엑세스 가능
- 단점: 실제 데이터에 대한 엑세스 부하를 줄임

적합한 시스템
- 참조 빈도가 높은 데이터
- 캐시의 데이터가 손실되어도 문제가 없는 시스템

부적합한 시스템
- 데이터 갱신 빈도가 높은 시스템
- 대량의 데이터에 엑세스하는 시스템
<br></br>

## 끼어들기
- 급한 일을 먼저하도록 cpu에게 알리는 역할
- 지금 하는 일을 중단하고 급한 일을 먼저 끝낸 후 원래 일을 진행하는 것
- 예: 키보드의 입력 등 특정 이벤트 발생 시 cpu에게 이것을 알려서 해당 이벤트에 대응하는 처리를 끝낸 후 원래 하던 일을 처리하는 것
<br></br>

## 폴링
정의
- 정기적으로 어떤 상태인지, 어떤 요구를 가지고 있는 지 확인하는 것
- 끼어들기의 반대 개념

특징
- 질의 방향이 단방향
- 질의는 일정 간격에 따라 정기적으로 발생

장점
- 반복만 하면 되어 프로그래밍이 쉬움
- 상대가 응답하는지 확인 가능
- 모아서 일괄적 처리 가능

적합한 처리
- 일정 간격으로 처리를 실행하면 좋은 것
- 감시

부적합한 처리
- 상태가 아닌 입력 내요에 따라 실행 내용을 변경하는 처리
- 처리 우선순위를 정해야 하는 처리
<br></br>

## I/0크기
정의
- 데이터를 주고 받을 때 사용되는 I/O의 크기
- 인프라 설계나 성능 튜닝에 중요

장점
- 데이터 크기에 따라 효율적 관리 가능
<br></br>

## 저널링
정의
- 트랜젝션이나 매일 갱신되는 데이터의 변경 이력(저널)을 남겨두는 것

특징
- 데이터 자체가 아닌 처리 내용을 기록
- 데이터의 일관성이나 일치성이 확보되면 필요 없음
- 롤백, 롤포워드에 이용됨

장점
- 시스템 장애 시 복구가 빠름
- 적은 리소스를 소비해 데이터 보호 가능

적합한 시스템
- 데이터 갱신이 발생하는 시스템

부적합한 시스템
- 데이터 안정성보다 성능을 요구하는 시스템
<br></br>

## 복제
정의
- 복사본을 만드는 것
- DB나 저장소 등에서 자주 사용되는 기술

특징
- 장애 시 데이터 손실 예방
- 복제를 이용한 부하분산이 가능

장점
- 복제 데이터를 캐시처럼 사용 가능

적합한 시스템
- 데이터 손실을 허용하지 않고 복구 속도가 빨라야 하는 시스템
- 데이터 참조가 많은 시스템

부적합한 시스템
- 데이터 갱신이 많은 시스템
<br></br>

## 마스터-워커
정의
- 주종 관계를 가리킴
- 상호 접속 관계의 일종, 한 사람이 관리자가 되어서 모든 것을 제어
- 마스터-워커의 반대는 peer to peer(P2P)

장점
- 관리자가 1명이라 구현이 쉬움
- 동기화할 필요가 없어 통신량이 줄어듦

단점
- 마스터가 없어지면 관리 불가(인수인계 구조 필요)
- 마스터의 부하가 높아짐
<br></br>

## 압축
- 압축의 기본은 '중복 패턴 인식', 그것을 '변경'하는 것
- 장점: 크기 줄이기
- 단점: 처리 시간 걸림
- 가역 압축(복원 가능)과 비가역 압축(사람이 인식할 수 없는 부분을 생략)으로 나뉨
<br></br>

## 오류 검출
정의
- 데이터의 파손 여부를 확인하는 기법
<br></br>
