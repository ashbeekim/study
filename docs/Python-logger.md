# Logger

## Logging의 목적
프로젝트의 구조나 구상에 따라 표현하는 단어는 달라질 수 있으나, 현재까지 이해한 바로는 다음과 같은 상황에서 해결하기 위한 추적의 장치로 기록되는 것이 로그를 작성하고 확인하는 목적이다.
* Bug : 프로그래머의 설계 및 구현에서 발생하는 에러
* Fault : 사용자에 의해 생성된 실수/Validation 후 실행 결과의 차이
* Error : SW 개발/유지보수 중 발생한 부정확한 결과이자 Defect의 원인
* Failure : 배포 후 사용자가 문제를 발견한 경우, release 후 사용자가 발견한 경우
* Defect : 버그, 오류, 에러, 실패, 문제점, 개선사항 등 포괄적인 범위의 의미를 가짐


## Log Level이란?
이번에 refactoring을 시도하며, 간단하게 알아봤으나 숙지나 응용이 익숙하지 않아서 현재까지 엉킨 개념을 정리하자면,
| level | usage |
|-------|-------|
| DEBUG | 상세한 정보, 보통 테스트 단계에서 발생한 문제 확인 시 사용 |
| INFO | 예상대로 작동하는지에 대한 확인, 협업 시 용이 |
| WARNING | 예상치 못한 문제점, 근시일 내 개선해야할 사항 등에 대한 표시, 정상 작동 |
| ERROR | 심각한 문제로 일부 기능을 수행하지 못한 경우 출력 |
| CRITICAL | 심각한 에러, 프로그램 자체가 계속 실행되지 않을 수 있음 출력 |

[ref) 파이썬 공식문서-ver3.9](https://docs.python.org/ko/3.9/howto/logging.html)

위와 같이 통상 5단계로 정의된다. 상기의 5단계 중 python이 정의한 default값은 WARNING으로 로그 출력 기준이나 단계의 조정은 config 파일에 설정되어 있다.


## 주의사항
위의 내용까지만 조사한 뒤, 크게 의식하거나 생각하지 못했던 부분이 다음에 기술할 내용이다.
1. log 파일도 데이터란 사실
2. 개인정보 및 시스템 주요 정보 보안

그리고 저와 같은 초보자들은 놓치고 있었을 수 있던 부분이 사내 개발자들은 이제껏 어떤 로그를 보이도록 했는가.

예, 저는 그걸 놓쳐서 지금 이러한 개념을 잊지 않기 위해 작성했습니다.