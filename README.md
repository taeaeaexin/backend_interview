# 매일 한 문제씩
매일 백엔드 면접 공부

<details>
  <summary>(24.12.30) 서버 모니터링을 위한 주요 지표에는 어떤 것들이 있으며, 각각의 중요성을 설명해주세요.</summary>
  </br>
  <p>서버 모니터링의 주요 지표로는 CPU 사용률(서버 과부하 여부를 판단), 메모리 사용률(메모리 부족이나 누수 감지), 디스크 I/O(입출력 병목 현상 확인), 네트워크 대역폭(트래픽 과부하 및 비정상 활동 감지) 등이 있습니다. 이 지표들은 서버 성능 최적화와 장애 예방을 위해 필수적으로 모니터링해야 합니다. 각각은 시스템의 안정성과 효율성을 유지하는 데 중요한 역할을 합니다.</p>
</details>

<details>
  <summary>(25.01.01) HTTP METHOD에 대해 설명해 보세요</summary>
  </br>
  <p>HTTP 메서드는 클라이언트가 서버에 요청하는 방식과 의도를 나타냅니다. GET은 데이터를 조회할 때, POST는 데이터를 생성하거나 전송할 때, PUT은 데이터를 전체적으로 수정하거나 생성할 때, PATCH는 데이터를 부분적으로 수정할 때, DELETE는 데이터를 삭제할 때 사용됩니다. 각 메서드는 특정 상황에 맞게 선택하여 사용됩니다.</p>
</details>

<details>
  <summary>(25.01.02) JVM에서 "웜업"이란 무엇인가요?</summary>
  </br>
  <p>JVM에서 "웜업"이란 애플리케이션 초기 실행 단계에서 JIT 컴파일러가 자주 호출되는 메서드(핫스팟)를 네이티브 코드로 컴파일하고 최적화하여 성능을 점차적으로 끌어올리는 과정입니다. 이는 인터프리터 방식으로 시작한 실행이 최적화된 네이티브 코드로 전환되며 성능이 안정화되는 데 중요한 역할을 합니다.</p>
</details>

<details>
  <summary>(25.01.03) 서버의 가용성(Availability)을 높이기 위해 어떤 설계 방식을 사용할 수 있나요?</summary>
  </br>
  <p>서버의 가용성을 높이려면 여러 서버에 일을 나눠주는 로드 밸런싱을 사용해 한 서버가 고장나도 다른 서버가 대신 일하도록 하면 됩니다. 또, 중요한 서버를 여러 개 만들어 두는 이중화로 한 서버가 멈춰도 나머지가 계속 작동하게 할 수 있어요. 마지막으로, 서버를 24시간 감시하고 문제를 빨리 고치는 모니터링도 필요합니다.</p>
</details>

<details>
  <summary>(25.01.05) Transactional Outbox 패턴에 대해 설명해주세요 이를 사용하는 이유와 구현 시 고려해야 할 점은 무엇인가요?</summary>
  </br>
  <p>Transactional Outbox 패턴은 데이터베이스 트랜잭션과 메시지 발행을 원자적으로 처리하기 위한 설계 방식입니다. 데이터를 저장할 때 메시지를 함께 "Outbox" 테이블에 기록하고, 이후 메시지 브로커로 전송합니다. 이를 사용하면 데이터 일관성과 메시지 전달의 신뢰성을 확보할 수 있습니다. 구현 시 Outbox 테이블의 데이터 정리 정책과 메시지 전송 실패 시 재처리를 고려해야 하며, 메시지가 중복될 수 있으므로 중복 방지 로직도 필요합니다. 이 패턴은 분산 시스템에서 데이터와 이벤트의 정합성을 유지하는 데 유용합니다.</p>
</details>

<details>
  <summary>(25.01.06) https://www.google.com/을 접속했을 때 웹 통신의 흐름을 설명하세요</summary>
  </br>
  <p>브라우저는 DNS를 통해 IP 주소를 조회하고, HTTPS 요청을 서버로 보내며, 서버는 TLS 핸드셰이크를 통해 안전한 연결을 설정한 후 응답 데이터를 전송해 브라우저가 이를 렌더링합니다.</p>
</details>

<details>
  <summary>(25.01.07) 제 생일은 언제일까요</summary>
  </br>
  <p>오늘입니다. 축하해주세요!</p>
</details>

<details>
  <summary>(25.01.08) 클러스터드 인덱스(Clustered Index)란 무엇이며, 비클러스터드 인덱스(Non-Clustered Index)와의 차이점을 설명해주세요</summary>
  </br>
  <p>클러스터드 인덱스는 내부 힙 자료구조에 있는 실제 데이터 정렬에 영향을 끼칩니다.
일반적으로 PK가 이 클러스터 인덱스로 지정되어있으며 비클러스터 인덱스의 경우 실제 데이터 정렬에는 영향을 끼치지 않습니다. 대신 인덱스를 관리하는 자료구조에 해당 데이터를 찾기위한 주소를 관리합니다. 이때, 다만 dbms에 따라 차이가 있을 수 있습니다. 예를 들어 사용중인 Postgres는 PK라고 할지라도 실제 정렬엔 영향을 가하진 않습니다.</p>
</details>

<details>
  <summary>(25.01.09) Bubble Sort란 무엇일까요?</summary>
  </br>
  <p>Bubble Sort는 Selection Sort와 유사한 알고리즘으로 서로 인접한 두 원소의 대소를 비교하고, 조건에 맞지 않다면 자리를 교환하며 정렬하는 알고리즘입니다.</p>
</details>

<details>
  <summary>(25.01.10) 모노레포(Monorepo)란 무엇이며, 프론트엔드 프로젝트에서 사용하는 이유는 무엇인가요?</summary>
  </br>
  <p>모노레포(Monorepo)는 여러 프로젝트의 코드를 하나의 저장소에서 관리하는 방식입니다. 프론트엔드 프로젝트에서는 주로 컴포넌트 라이브러리, 웹 애플리케이션, 유틸리티 패키지 등을 통합적으로 관리하기 위해 사용됩니다. 이 방식은 코드 재사용성과 일관성을 높이고, 단일 저장소 내에서 변경사항을 쉽게 추적할 수 있어 협업 효율성을 극대화하는 데 유리합니다. 특히, 대규모 프로젝트에서 의존성과 버전 관리를 체계적으로 할 수 있다는 점이 큰 장점입니다.</p>
</details>



<details>
  <summary>(25.01.11) Selection Sort란 무엇일까요?</summary>
<p>Selection Sort는 Bubble Sort과 유사한 알고리즘으로, 해당 순서에 원소를 넣을 위치는 이미 정해져 있고, 어떤 원소를 넣을지 선택하는 알고리즘입니다. Selection Sort와 Insertion Sort를 헷갈려하는 사람들이 종종 있는데, Selection Sort는 배열에서 해당 자리를 선택하고 그 자리에 오는 값을 찾는 것이라고 생각하면 편합니다.</p>
</details>

<details>
  <summary>(25.01.12) Insertion Sort란 무엇일까요?</summary>
<p>손 안의 카드를 정렬하는 방법과 유사합니다. Insertion Sort는 Selection Sort와 유사하지만, 좀 더 효율적인 정렬 알고리즘입니다. Insertion Sort는 2번째 원소부터 시작하여 그 앞(왼쪽)의 원소들과 비교하여 삽입할 위치를 지정한 후, 원소를 뒤로 옮기고 지정된 자리에 자료를 삽입 하여 정렬하는 알고리즘입니다. 최선의 경우 O(N)이라는 엄청나게 빠른 효율성을 가지고 있어, 다른 정렬 알고리즘의 일부로 사용될 만큼 좋은 정렬 알고리즘입니다.</p>
</details>

<details>
  <summary>(25.01.13) Quick Sort란 무엇일까요?</summary>
<p>Quick Sort은 분할 정복(divide and conquer) 방법 을 통해 주어진 배열을 정렬합니다.
  (분할 정복(divide and conquer) 방법 : 문제를 작은 2개의 문제로 분리하고 각각을 해결한 다음, 결과를 모아서 원래의 문제를 해결하는 전략) 
  Quick Sort은 불안정 정렬에 속하며, 다른 원소와의 비교만으로 정렬을 수행하는 비교 정렬에 속한다. 또한 Merge Sort와 달리 Quick Sort는 배열을 비균등하게 분할합니다</p>
</details>

<details>
  <summary>(25.01.14) [컬쳐핏] 자신의 의견이 팀의 다수 의견과 다를 때, 의견을 고수하거나 조율했던 사례를 알려주세요.</summary>
<p>다 같이 동의하고 랜덤으로 추첨한 조의 조장이 조원이 마음에 안든다며 한명을 바꿔달라 했었는데 회장이었던 제가 규칙은 규칙이다며 거절했었습니다.
하지만 저를 제외한 다른 임원들은 그 정도는 양해해주자며 의견이 갈려 '이런 사소한 규칙 하나부터 무너지면 질서가 무너진다'고 설득한 뒤 투표로 진행했습니다.
투표 결과 '바꿔준다'가 되었고 저는 결과에 승복하며 조원을 바꿔주었습니다.</p>
</details>

<details>
  <summary>(25.01.15) [실제 받았던 질문] Spring과 SpringBoot의 차이점을 간단히 말해세요.</summary>
<p>Spring은 Java 웹 개발 프레임워크입니다. 이것을 더 쓰기 쉽게 만든 프레임워크가 SpringBoot입니다.</p>
</details>

<details>
  <summary>(25.01.16) [실제 받았던 질문] 전시상황에 전우가 군사 기밀을 유출했다면 어떻게 할것인가요?</summary>
<p>전우란 전장의 벗이라는 뜻입니다. 하지만 세상에 어떤 사람이 친구를 위험에 빠트리겠습니까. 저는 이런일이 발생한다면 전우가 아닌 적으로 간주하겠습니다.</p>
</details>

<details>
  <summary>(25.01.17) 컴퓨터 하드웨어의 종류를 말하세요.</summary>
<p>중앙처리장치(CPU), 기억장치 : RAM, HDD, 입출력 장치 : 마우스, 프린터 등이 있습니다.</p>
</details>

<details>
  <summary>(25.01.18) 중앙처리장치(CPU)란 무엇일까요?</summary>
<p>인간으로 따지면 두뇌에 해당하는 부분 주기억장치에서 프로그램 명령어와 데이터를 읽어와 처리하고 명령어의 수행 순서를 제어함 중앙처리장치는 비교와 연산을 담당하는 산술논리연산장치(ALU)와 명령어의 해석과 실행을 담당하는 제어장치, 속도가 빠른 데이터 기억장소인 레지스터로 구성되어있음
개인용 컴퓨터와 같은 소형 컴퓨터에서는 CPU를 마이크로프로세서라고도 부름</p>
</details>

<details>
  <summary>(25.01.19) 중앙처리장치(CPU)의 작동 원리를 설명하세요.</summary>
<p>CPU는 컴퓨터에서 가장 핵심적인 역할을 수행하는 부분. '인간의 두뇌'에 해당
크게 연산장치, 제어장치, 레지스터 3가지로 구성됨
1. 주기억장치는 입력장치에서 입력받은 데이터 또는 보조기억장치에 저장된 프로그램 읽어옴
2. CPU는 프로그램을 실행하기 위해 주기억장치에 저장된 프로그램 명령어와 데이터를 읽어와 처리하고 결과를 다시 주기억장치에 저장
3. 주기억장치는 처리 결과를 보조기억장치에 저장하거나 출력장치로 보냄
4. 제어장치는 1~3 과정에서 명령어가 순서대로 실행되도록 각 장치를 제어</p>
</details>

<details>
  <summary>(25.01.2) </summary>
<p></p>
</details>
