# 매일 한 문제씩
매일 백엔드 면접 공부

<details>
  <summary>(24.12.30) 서버 모니터링을 위한 주요 지표에는 어떤 것들이 있으며, 각각의 중요성을 설명해주세요.</summary>
  <p>- 서버 모니터링의 주요 지표로는 CPU 사용률(서버 과부하 여부를 판단), 메모리 사용률(메모리 부족이나 누수 감지), 디스크 I/O(입출력 병목 현상 확인), 네트워크 대역폭(트래픽 과부하 및 비정상 활동 감지) 등이 있습니다. 이 지표들은 서버 성능 최적화와 장애 예방을 위해 필수적으로 모니터링해야 합니다. 각각은 시스템의 안정성과 효율성을 유지하는 데 중요한 역할을 합니다.</p>
</details>

<details>
  <summary>(25.01.01) HTTP METHOD에 대해 설명해 보세요</summary>
  <p>- HTTP 메서드는 클라이언트가 서버에 요청하는 방식과 의도를 나타냅니다. GET은 데이터를 조회할 때, POST는 데이터를 생성하거나 전송할 때, PUT은 데이터를 전체적으로 수정하거나 생성할 때, PATCH는 데이터를 부분적으로 수정할 때, DELETE는 데이터를 삭제할 때 사용됩니다. 각 메서드는 특정 상황에 맞게 선택하여 사용됩니다.</p>
</details>

<details>
  <summary>(25.01.02) JVM에서 "웜업"이란 무엇인가요?</summary>
  <p>- JVM에서 "웜업"이란 애플리케이션 초기 실행 단계에서 JIT 컴파일러가 자주 호출되는 메서드(핫스팟)를 네이티브 코드로 컴파일하고 최적화하여 성능을 점차적으로 끌어올리는 과정입니다. 이는 인터프리터 방식으로 시작한 실행이 최적화된 네이티브 코드로 전환되며 성능이 안정화되는 데 중요한 역할을 합니다.</p>
</details>

<details>
  <summary>(25.01.03) 서버의 가용성(Availability)을 높이기 위해 어떤 설계 방식을 사용할 수 있나요?</summary>
  <p>- 서버의 가용성을 높이려면 여러 서버에 일을 나눠주는 로드 밸런싱을 사용해 한 서버가 고장나도 다른 서버가 대신 일하도록 하면 됩니다. 또, 중요한 서버를 여러 개 만들어 두는 이중화로 한 서버가 멈춰도 나머지가 계속 작동하게 할 수 있어요. 마지막으로, 서버를 24시간 감시하고 문제를 빨리 고치는 모니터링도 필요합니다.</p>
</details>

<details>
  <summary>(25.01.05) Transactional Outbox 패턴에 대해 설명해주세요 이를 사용하는 이유와 구현 시 고려해야 할 점은 무엇인가요?</summary>
  <p>- Transactional Outbox 패턴은 데이터베이스 트랜잭션과 메시지 발행을 원자적으로 처리하기 위한 설계 방식입니다. 데이터를 저장할 때 메시지를 함께 "Outbox" 테이블에 기록하고, 이후 메시지 브로커로 전송합니다. 이를 사용하면 데이터 일관성과 메시지 전달의 신뢰성을 확보할 수 있습니다. 구현 시 Outbox 테이블의 데이터 정리 정책과 메시지 전송 실패 시 재처리를 고려해야 하며, 메시지가 중복될 수 있으므로 중복 방지 로직도 필요합니다. 이 패턴은 분산 시스템에서 데이터와 이벤트의 정합성을 유지하는 데 유용합니다.</p>
</details>

<details>
  <summary>(25.01.06) https://www.google.com/을 접속했을 때 웹 통신의 흐름을 설명하세요</summary>
  <p>- 브라우저는 DNS를 통해 IP 주소를 조회하고, HTTPS 요청을 서버로 보내며, 서버는 TLS 핸드셰이크를 통해 안전한 연결을 설정한 후 응답 데이터를 전송해 브라우저가 이를 렌더링합니다.</p>
</details>

<details>
  <summary>(25.01.07) 제 생일은 언제일까요</summary>
  <p>- 오늘입니다. 축하해주세요!</p>
</details>

<details>
  <summary>(25.01.08) 클러스터드 인덱스(Clustered Index)란 무엇이며, 비클러스터드 인덱스(Non-Clustered Index)와의 차이점을 설명해주세요</summary>
  <p>- 클러스터드 인덱스는 내부 힙 자료구조에 있는 실제 데이터 정렬에 영향을 끼칩니다.
일반적으로 PK가 이 클러스터 인덱스로 지정되어있으며 비클러스터 인덱스의 경우 실제 데이터 정렬에는 영향을 끼치지 않습니다. 대신 인덱스를 관리하는 자료구조에 해당 데이터를 찾기위한 주소를 관리합니다. 이때, 다만 dbms에 따라 차이가 있을 수 있습니다. 예를 들어 사용중인 Postgres는 PK라고 할지라도 실제 정렬엔 영향을 가하진 않습니다.</p>
</details>

<details>
  <summary>(25.01.09) Bubble Sort란 무엇일까요?</summary>
  <p>- Bubble Sort는 Selection Sort와 유사한 알고리즘으로 서로 인접한 두 원소의 대소를 비교하고, 조건에 맞지 않다면 자리를 교환하며 정렬하는 알고리즘입니다.</p>
</details>

<details>
  <summary>(25.01.10) 모노레포(Monorepo)란 무엇이며, 프론트엔드 프로젝트에서 사용하는 이유는 무엇인가요?</summary>
  <p>- 모노레포(Monorepo)는 여러 프로젝트의 코드를 하나의 저장소에서 관리하는 방식입니다. 프론트엔드 프로젝트에서는 주로 컴포넌트 라이브러리, 웹 애플리케이션, 유틸리티 패키지 등을 통합적으로 관리하기 위해 사용됩니다. 이 방식은 코드 재사용성과 일관성을 높이고, 단일 저장소 내에서 변경사항을 쉽게 추적할 수 있어 협업 효율성을 극대화하는 데 유리합니다. 특히, 대규모 프로젝트에서 의존성과 버전 관리를 체계적으로 할 수 있다는 점이 큰 장점입니다.</p>
</details>

<details>
  <summary>(25.01.11) Selection Sort란 무엇일까요?</summary>
  <p>- Selection Sort는 Bubble Sort과 유사한 알고리즘으로, 해당 순서에 원소를 넣을 위치는 이미 정해져 있고, 어떤 원소를 넣을지 선택하는 알고리즘입니다. Selection Sort와 Insertion Sort를 헷갈려하는 사람들이 종종 있는데, Selection Sort는 배열에서 해당 자리를 선택하고 그 자리에 오는 값을 찾는 것이라고 생각하면 편합니다.</p>
</details>

<details>
  <summary>(25.01.12) Insertion Sort란 무엇일까요?</summary>
  <p>- 손 안의 카드를 정렬하는 방법과 유사합니다. Insertion Sort는 Selection Sort와 유사하지만, 좀 더 효율적인 정렬 알고리즘입니다. Insertion Sort는 2번째 원소부터 시작하여 그 앞(왼쪽)의 원소들과 비교하여 삽입할 위치를 지정한 후, 원소를 뒤로 옮기고 지정된 자리에 자료를 삽입 하여 정렬하는 알고리즘입니다. 최선의 경우 O(N)이라는 엄청나게 빠른 효율성을 가지고 있어, 다른 정렬 알고리즘의 일부로 사용될 만큼 좋은 정렬 알고리즘입니다.</p>
</details>

<details>
  <summary>(25.01.13) Quick Sort란 무엇일까요?</summary>
  <p>- Quick Sort은 분할 정복(divide and conquer) 방법 을 통해 주어진 배열을 정렬합니다.
  (분할 정복(divide and conquer) 방법 : 문제를 작은 2개의 문제로 분리하고 각각을 해결한 다음, 결과를 모아서 원래의 문제를 해결하는 전략) 
  Quick Sort은 불안정 정렬에 속하며, 다른 원소와의 비교만으로 정렬을 수행하는 비교 정렬에 속한다. 또한 Merge Sort와 달리 Quick Sort는 배열을 비균등하게 분할합니다</p>
</details>

<details>
  <summary>(25.01.14) [컬쳐핏] 자신의 의견이 팀의 다수 의견과 다를 때, 의견을 고수하거나 조율했던 사례를 알려주세요.</summary>
  <p>- 다 같이 동의하고 랜덤으로 추첨한 조의 조장이 조원이 마음에 안든다며 한명을 바꿔달라 했었는데 회장이었던 제가 규칙은 규칙이다며 거절했었습니다.
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
  <p>- 중앙처리장치(CPU), 기억장치 : RAM, HDD, 입출력 장치 : 마우스, 프린터 등이 있습니다.</p>
</details>

<details>
  <summary>(25.01.18) 중앙처리장치(CPU)란 무엇일까요?</summary>
  <p>- 인간으로 따지면 두뇌에 해당하는 부분 주기억장치에서 프로그램 명령어와 데이터를 읽어와 처리하고 명령어의 수행 순서를 제어함 중앙처리장치는 비교와 연산을 담당하는 산술논리연산장치(ALU)와 명령어의 해석과 실행을 담당하는 제어장치, 속도가 빠른 데이터 기억장소인 레지스터로 구성되어있음
개인용 컴퓨터와 같은 소형 컴퓨터에서는 CPU를 마이크로프로세서라고도 부름</p>
</details>

<details>
  <summary>(25.01.19) 중앙처리장치(CPU)의 작동 원리를 설명하세요.</summary>
  <p>- CPU는 컴퓨터에서 가장 핵심적인 역할을 수행하는 부분. '인간의 두뇌'에 해당
크게 연산장치, 제어장치, 레지스터 3가지로 구성됨
1. 주기억장치는 입력장치에서 입력받은 데이터 또는 보조기억장치에 저장된 프로그램 읽어옴
2. CPU는 프로그램을 실행하기 위해 주기억장치에 저장된 프로그램 명령어와 데이터를 읽어와 처리하고 결과를 다시 주기억장치에 저장
3. 주기억장치는 처리 결과를 보조기억장치에 저장하거나 출력장치로 보냄
4. 제어장치는 1~3 과정에서 명령어가 순서대로 실행되도록 각 장치를 제어</p>
</details>

<details>
  <summary>(25.01.20) 캐시 메모리(Cache Memory)란 무엇일까요? </summary>
  <p>- 속도가 빠른 장치와 느린 장치에서 속도 차이에 따른 병목 현상을 줄이기 위한 메모리를 말한다.</p>
</details>

<details>
  <summary>(25.01.21) [WorkShop] yeild가 무엇일까요? </summary>
  <p>- yeild는 return과 비슷하다고 생각했는데 다릅니다. 반환, 돌려주다라는 영어 단어인데 비동기처리할 때 많이 사용합니다. 누구한테 돌려주는지 중요한데 분기가 나왔던 지점에 return 합니다.
  분기를 조절한다고 생각하면 좋습니다. for문의 label과 같비슷한 역할을 한다고 합니다.</p>
</details>

<details>
  <summary>(25.01.22) [WorkShop] Enum은 언제 사용할까요? </summary>
  <p>- 날짜, 요일, 계절등 불변의 항목을 열거할 때 사용합니다. 프로젝트를 할 때 코드로 관리할 것과 enum으로 관리할 것을 구분해야합니다.</p>
</details>

<details>
  <summary>(25.01.23) [WorkShop] Method signature에 대해서 설명하세요 </summary>
  <p>- 메소드 이름 + 매개변수 타입과 개수</p>
</details>

<details>
  <summary>(25.01.24) 오늘은 불금! 놀러가야징</summary>
  <p>맛있는 순두부 찌개를 먹었답니다</p>
</details>

<details>
  <summary>(25.01.25) Is-a 관계를 설명하세요. </summary>
  <p>- A is a B라는 관계는 A는 B의 일종이다는 의미 (Dog is an Animal)</p>
</details>

<details>
  <summary>(25.01.26) 상속이란 무엇일까요?</summary>
  <p>- 상속은 기존 클래스를 재사용해 새로운 클래스를 작성하는것입니다</p>
</details>

<details>
  <summary>(25.01.27) Singleton Patter이란 무엇일까요?</summary>
  <p>- 단 하나의 유일한 객체를 만들기 위한 코드 패턴입니다. 메모리 절약을 위해 인스턴스가 필요할 때 기존 인스턴스 활용</p>
</details>

<details>
  <summary>(25.01.28) instanceof는 어떤 연산자일까요?</summary>
  <p>- 매개변수가 아니더라도 변수가 참조하는 객체의 타입을 확인할 때 사용하는 연산자입니다.
  좌항의 객체가 우항의 타입이면 true를 출력합니다.</p>
</details>

<details>
  <summary>(25.01.29) Schema란 무엇일까요? (새해 복 많이받으세요!)</summary>
  <p>- 현실과 데이터베이스 사이에 있는 데이터구조. 데이터베이스 조건 Specification을 Description한 Meta-Data</p>
</details>

<details>
  <summary>(25.01.30) 쇼트서킷이란 무엇일까요?</summary>
  <p>- 논리연산자에서 좌측 피연산자만으로도 결과가 확정 된 경우, 굳이 우측 피 연산자의 계산 과정을 진행하지 않는 기능입니다.</p>
</details>

<details>
  <summary>(25.01.31) 다형성(Polymorphism)이란 무엇일까요?</summary>
  <p>- 다형성이란 프로그램 언어 각 요소들(상수, 변수, 식, 객체, 메소드 등)이 다양한 자료형(type)에 속하는 것이 허가되는 성질을 가리킨다.</p>
</details>

<details>
  <summary>(25.02.01) NullPointException2이란 무엇일까요?</summary>
  <p>- 변수가 Null인 상태에서 객체의 데이터나 메소드를 사용하려 하면 발생하는 예외(오류)입니다. reference type이 참조할 데이터가 null일때 생깁니다.</p>
</details>

<details>
  <summary>(25.02.02) Java에서 실수의 정확한 산술 연산을 하려면 어떻게 해야하나요?</summary>
  <p>- double과 float가 부동 소수점을 사용하기 떄문에 정확하지 않아 정수 연산으로 진행합니다.</p>
</details>

<details>
  <summary>(25.02.03) Interface의 역할은 무엇일까요?</summary>
  <p>- 다형성 구현의 주된 기술입니다. 두 객체를 연결하는 역할을 하며 상속보다 공유되는 메소드에 집중합니다.</p>
</details>

<details>
  <summary>(25.02.04) Java에서의 예외처리에 대해서 설명하세요.</summary>
  <p>- 일반 예외와 실행 예외로 나뉩니다. 일반 예외는 컴파일러가 예외 처리 코드 여부를 검사하는 예외고, 실행 예외는 컴파일러가 예외 처리 코드 여부를 검사하지 않는 예외입니다.</p>
</details>

<details>
  <summary>(25.02.05) 와일드카드 타입 파라미터란 무엇일까요?</summary>
  <p>- 제네릭 타입을 매개값이나 리턴 타입으로 사용할 때 범위에 있는 모든 타입으로 대체할 수 있는 타입 파라미터 ?로 표시</p>
</details>

<details>
  <summary>(25.02.06) Builder 디자인 패턴의 장점과 단점이 무엇일까요? </summary>
  <p>- 개발자 코드 작성 및 유지보수 장점이 있고, Builder클래스 자체가 복잡하고 객체 생성시 메모리 낭비가 심하다는 단점이 있습니다.</p>
</details>

<br/>

**[알고리즘]** Queue에 대해서 설명하세요
<details>
  <summary>25.02.07</summary>
  <p>- 큐의 주요 연산으로는 enqueue(삽입), dequeue(삭제), peek(조회)이 있습니다. enqueue는 데이터를 추가하는 연산, dequeue는 데이터를 제거하는 연산입니다. peek은 삭제 없이 front 데이터 출력입니다.<br/>
    - 큐는 운영체제의 프로세스 스케줄링, 프린터의 작업 대기열, 네트워크 패킷 처리, BFS 알고리즘 등에서 활용됩니다. 특히, CPU 스케줄링에서는 먼저 요청된 작업이 먼저 실행되는 특성을 이용해 프로세스를 관리합니다. <br/>
    - 원형 큐는 배열 기반 큐에서 발생하는 공간 낭비 문제를 해결하기 위해 설계된 구조입니다.
  </p>
</details>

<br/>

**[휴가]** 오늘은 코엑스를 갑니다
<details>
  <summary>25.02.08</summary>
  <p>- 예에 재밌게 놀다 와야지</p>
</details>

<br/>

**[휴가]** 재밌게 놀다가 까먹었다
<details>
  <summary>25.02.09</summary>
  <p>- 내일 열심히하자</p>
</details>

<br/>

**[알고리즘]** 스택과 큐의 삽입,삭제,출력 메서드를 설명하세요
<details>
  <summary>25.02.10</summary>
  <p>- Stack Method : push(e), pop(), peek() / Queue Method : offer(e), poll(), peek()</p>
</details>

<br/>

**[알고리즘]** 해시의 특성을 이용하는 분야 하나를 설명해보세요
<details>
  <summary>25.02.11</summary>
  <p>- 데이터베이스 인덱싱 : 데이터베이스에 저장된 데이터를 효율적으로 검색할 때</p>
</details>

<br/>

**[알고리즘]** 이진트리를 설명해보세요
<details>
  <summary>25.02.12</summary>
  <p>- 이진 트리는 각각의 노드가 최대 두 개의 자식 노드를 가지는 트리 자료 구조입니다.</p>
</details>

<br/>

**[알고리즘]** 분할정복이랑 무엇일까요?
<details>
  <summary>25.02.13</summary>
  <p>- 크고 방대한 문제를 조금씩 나눠가며 풀 수 있는 문제 단위로 나눈 다음 다시 합쳐서 해결</p>
</details>


<br/>

**[휴가]** 오늘은 졸업식!
<details>
  <summary>25.02.14</summary>
  <p>- 놀러가야지 헤헤</p>
</details>

<br/>

**[휴가]** 오늘은 정처기 시험!
<details>
  <summary>25.02.15</summary>
  <p>- 95/65/65/80/70 으로 합격!</p>
</details>

<br/>

**[휴가]** 아.. 주말 삭제
<details>
  <summary>25.02.16</summary>
  <p>- 월요일 싫어..</p>
</details>

<br/>

**[알고리즘]** DFS와 백트래킹의 차이점을 설명하세요
<details>
  <summary>25.02.17</summary>
  <p>- DFS는 모든 경로를 탐색해 최고의 경로를 찾지만, 백트래킹은 유망하지 않다면 되돌아간다.</p>
</details>

<br/>

**[알고리즘]** 백트래킹과 가지치기의 차이점을 설명하세요
<details>
  <summary>25.02.18</summary>
  <p>- 백트래킹은 지금 행동이 다음 행동에 영향을 미치고, 가지치기 조건을 벗어나면 잘라냄</p>
</details>

<br/>

**[TIP]** 시뮬레이션 문제 푸는 요령
<details>
  <summary>25.02.19</summary>
  <p>  
    
- 문제를 읽고 pseudo code를 작성하기 (흐름대로) <br/>
    
- 조건 파악하기 (종료 조건, 상태가 변하는 조건) <br/>
    
- 문제에서 제공한 dir, r, c와 같은 값은 최대한 그대로 사용 (직관적인 이해 쉬워짐) <br/>
  
- 방향 회전의 경우 modulo 연산을 이용하면 쉽게 표현 가능 (연속적인 값 변화를 이용한 간단한 Trick)</p>
</details>

<br/>

**[알고리즘]** 동적 계획법(Dynamic Programming)이란 무엇일까요?
<details>
  <summary>25.02.20</summary>
  <p>- 복잡한 문제를 간단한 여러 개의 문제로 나누어 푸는 방법</p>
</details>

<br/>

**[주짓수]** 오모플라타란 무엇일까요?
<details>
  <summary>25.02.21</summary>
  <p>- 포르투갈어로 견갑골이란 뜻입니다. 주짓수, 유도의 서브미션 기술 이름입니다. 이걸 왜 쓰냐면 오모플라타 걸려서 어깨가 아직도 아파요</p>
</details>

<br/>

**[SQLD]** Modeling이란 무엇일까요?
<details>
  <summary>25.02.22</summary>
  <p>- 모델링이란 현실세계를 대상으로 일종의 모델을 만드는 것을 의미합니다.</p>
</details>

<br/>

**[SQLD]** 정규화란 무엇일까요?
<details>
  <summary>25.02.23</summary>
  <p>- 데이터의 중복을 최소화하면서 테이블을 보다 잘 조직된 상태로 분해하는 과정</p>
</details>

<br/>

**[알고리즘]** 다익스트라 알고리즘이란 무엇일까요?
<details>
  <summary>25.02.24</summary>
  <p>- A노드에서 출발하여 F노드로 가는 최단 경로를 구하는 문제해결하는 알고리즘</p>
</details>

<br/>

**[데이터베이스]** 관계테이블
<details>
  <summary>25.02.25</summary>
  <p>- 필요에 의해서 생겨난 테이블</p>
</details>

<br/>

**[데이터베이스]** 데이터 조작어 검색할때 쓰는 문은?
<details>
  <summary>25.02.26</summary>
  <p>- SELECT/FROM</p>
</details>

<br/>

**[데이터베이스]** SELECT FROM문을 실행 순서대로 말해보세요
<details>
  <summary>25.02.27</summary>
  <p>- FROM -> WHERE -> GROUP BY -> HAVING -> SELECT -> ORDER BY </p>
</details>

<br/>

**[데이터베이스]** subquery의 종류와 설명을 말해주세요
<details>
  <summary>25.02.28</summary>
  <p>
- 중첩질의 : WHERE 부속질의 <br/>
    
- 스칼라 부속 질의 : SELECT 부속질의 <br/>
    
- 인라인 뷰 : FROM 부속질의
</p>
</details>

<br/>

**[데이터베이스]** SYSDATE()와 NOW()의 차이점
<details>
  <summary>25.03.01</summary>
  <p>
- NOW() : 쿼리가 수행되는 시간에 고정 <br/>
    
- SYSDATE() : 함수가 호출될 때마다 시간 변함 <br/>
  </p>
</details>

<br/>

**[데이터베이스]** 뷰의 장점을 설명하세요
<details>
  <summary>25.03.02</summary>
  <p>
- 편리함, 재사용성, 보안성, 독립성 <br/>
- 중요 데이터가 포함된 테이블 중 상담에 필요한 일부 컬럼만 view로 만들어서 제공
  </p>
</details>

<br/>

**[데이터베이스]** 인덱스의 특징을 설명하세요
<details>
  <summary>25.03.03</summary>
  <p>
    - 빠른 검색과 함께 효율적인 레코드 접근 가능 <br/>
    - 데이터에서 수정, 삭제 등 변경이 발생하면 인덱스 재구성 해야 함 <br/>
    - 검색에서는 이득, 등록수정삭제에서는 손해
  </p>
</details>

<br/>

**[데이터베이스]** 데이터 모델링이란 무엇일까요
<details>
  <summary>25.03.04</summary>
  <p> - 데이터 모델링은 조직의 정보 수집과 관리 시스템을 정의하는 시각적 표현 또는 청사진을 생성하는 프로세스 </p>
</details>

<br/>

**[데이터베이스]** 데이터 모델링 순서를 설명하세요
<details>
  <summary>25.03.05</summary>
  <p> - 해당 도메인의 Business Logic을 이해, 요구사항 분석 <br/>
- 개체 Entity 도출 (네모) <br/>
- 관계 RelationShip 도출 (마름모) <br/>
- 대응 차수 (Cardinality) 검토, N:M 관계는 별도의 관계 RelationShip 추가 (마름모) <br/>
- 상세 속성 (Attributes) 도출 <br/>
- FK 검토 (Identigying, Non-Identifying </p>
</details>

<br/>

**[프로젝트]** 프로젝트 중
<details>
  <summary>25.03.06</summary>
  <p> - 으아아 </p>
</details>

<br/>

**[프로젝트]** 프로젝트 마무리
<details>
  <summary>25.03.07</summary>
  <p> - 으아아아아아 </p>
</details>

<br/>

**[SQLD]** SQLD 시험을 봤습니다
<details>
  <summary>25.03.08</summary>
  <p> - 자유다 </p>
</details>

<br/>

**[쉬는 날]** 오늘까지만 좀 쉴게요
<details>
  <summary>25.03.09</summary>
  <p> - 야호 </p>
</details>

<br/>

**[데이터베이스]** 트랜잭션의 성질 4가지를 설명하세요
<details>
  <summary>25.03.10</summary>
  <p>
    - 원자성 : 전부 수행하거나 아예 수행하지 않아야 한다. <br/>
    - 일관성 : 테이블이 생성될 때마다 무결성 제약조건을 통해 명시되어 일관성을 유지한다. <br/>
    - 고립성 : 각 트랜잭션은 다른 트랜잭션의 방해를 받지 않고 독립적으로 수행된다. <br/>
    - 지속성 : 정상적으로 완료되거나 부분 완료된 데이터는 반드시 데이터베이스에 기록되어야 한다. <br/>
  </p>
</details>

<br/>

**[데이터베이스]** 고립수준의 종류를 말하세요
<details>
  <summary>25.03.11</summary>
  <p>
    - READ UNCOMMITTED <br/>
    - READ COMMITTED <br/>
    - REPEATABLE READ <br/>
    - SERIZLIZABLE <br/>
  </p>
</details>

<br/>

**[데이터베이스]** MyBatis란 무엇일까요?
<details>
  <summary>25.03.12</summary>
  <p> - SQL을 직접 사용하면서도 객체 매핑을 쉽게 할 수 있는 프레임워크 </p>
</details>

<br/>

**[데이터베이스]** JPA란 무엇일까요?
<details>
  <summary>25.03.13</summary>
  <p> -  JPA(Java Persistence API)는 자바에서 관계형 데이터베이스를 객체 지향적으로 다룰 수 있도록 지원하는 ORM(Object-Relational Mapping) 기술입니다. SQL 대신 객체(Entity) 중심으로 데이터베이스를 조작할 수 있도록 도와주며, 개발자가 직접 SQL을 작성하지 않아도 데이터베이스 연동이 가능합니다. </p>
</details>

<br/>

**[데이터베이스]** Scale UP과 Scale Out의 차이를 말하세요
<details>
  <summary>25.03.14</summary>
  <p> - Scale up은 전통적인 DB의 방식인 RDBMS에서 단일 서버 성능 향상을 위해 사용하고, Scale out은 비정형 데이터 데이터간의 Join이 없기 때문에 빠르게 처리가 가능하여 NoSQL에서 사용함 </p>
</details>

<br/>

**[데이터베이스]** RDBMS와 NoSQL의 차이를 말하세요
<details>
  <summary>25.03.15</summary>
    <p>
    - RDBMS : 테이블 기반의 고정된 스키마 <br/>
    - NoSQL : 여러 종류 구조의 유연한 스키마  <br/>
  </p>
</details>

<br/>

**[데이터베이스]** MongoDB의 특징을 설명하세요
<details>
  <summary>25.03.16</summary>
    <p>
    - Document-Oriented NoSQL 데이터베이스 <br/>
    - JSON-LIKE 형식의 BSON(Binary JSON) 문서를 사용하여 데이터 저장 <br/>
    - 복제와 샤딩을 통해 고가용성과 확장성을 제공 <br/>
    - 대규모 데이터 저장 및 처리, 실시간 분석 등 분야에 사용 <br/>
  </p>
</details>
