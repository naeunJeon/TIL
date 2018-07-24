
# 프로세스와 스레드
## 프로세스
- 운영체제에서 실행중인 하나의 작업
- 운영체제로부터 주소공간과 자원을 할당받음

## 스레드
- 프로세스내에서 실행되는 흐름의 단위
- 프로세스가 생성되면 하나의 스레드가 생성되는데 이것을 메인스레드라고 함
- 환경에 따라 메인스레드 외에도 여러개의 스레드가 병행적으로 일을 처리하며 이것을 **멀티스레드**라고 함
- 프로세스내의 주소공간과 자원을 공유하면서 실행

## 스레드 장단점
장점
 - 메모리 공유로 인한 시스템 자원 소모가 적음
 - Context Switching 에 대한 오버헤드가 줄어듬

단점
 - 디버깅이 어려움
 - 단일 프로세서 시스템에서는 효과를 기대하기 어려움
 - 하나의 스레드에 예외가 발생하여 오류가 생기면 다른 프로세스 자체가 종료될 수 있기 때문에 다른 스레드에도 영향을 미치게 됨