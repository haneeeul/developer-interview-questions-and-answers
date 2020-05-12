# Coding Interview
개발자 인터뷰 질문 모음과 팁 & 최소 답변입니다. 모든 내용을 자세하게 담기엔 가성비가 떨어지므로 모르는 부분이 나오신다면 검색을 통해 추가적인 학습을 추천합니다.

### Table of Content
- [Basics](#basics)
- [OS](#os)
- [Network](#network)
- [Database](#database)
- [Datastructure](#datastructure)
- [Algorithm](#algorithm)
- [Etc](#etc)
- [PL:Python](#python)
- [PL:Java](#java)
- [PL:JavaScript](#javascript)
- [Backend:Django](#django)
- [Backend:Spring](#spring)
- [Frontend:React](#react)
- [Mobile:Android](#android)
- [Mobile:IOS](#ios)


### Basics
* 자기소개
  * 이력 중심으로 간단하게 설명하되 신입이라면 성장 욕구를 간단히 어필하는 문구를 넣어도 좋음
* 가장 성공적이었던 프로젝트가 무엇이고 왜 성공적이라고 생각하는지
  * 현재 지원한 공고에 맞는 프로젝트를 성공적인 프로젝트로 지정하여 말하는 것이 유리
* 프로젝트 진행 시 불화에 대해서 어떻게 대처했는지
  * 솔직하게 말하되 같이 일할 수 있는 사람이라는 인식을 심어주는 것이 중요
* 우리 회사 서비스 중에 사용해본 것
  * 지원한 공고에 맞는 회사 기술 블로그를 분석하고 그와 연관된 서비스를 말하는 것이 유리 
* 지금까지 했던 프로젝트 중 하면서 어려웠던 부분과 극복한 방법
  * 프로젝트는 지원한 회사의 직무에 연관되어 있으면 더 좋음
  * 극복한 방법은 다양한 방법이 존재하지만 같이 일할 수 있는 정도의 사람이라는 이미지를 심어 줄 수 있는 내용으로 답변
* 최근 관심 있게 보고 있는 기술
  * 지원한 회사의 직무에 연관되어 있으면 유리
* 이전 직장에서 아쉬웠던 부분과 왜 이직하려는지
  * 이직하고자 하는 회사만의 분명한 장점을 생각해놓고 답변하는 것이 좋음
* 우리 회사에 궁금한 점
  * 인터넷에서 검색할 수 있는 정보는 지양하고 회사 내부 또는 팀 내부나 지원한 포지션에 관련된 것이 좋음
* 본인의 장점과 단점
  * 장점은 솔직하게 말하는 것이 좋고 단점은 무조건적인 단점이 아닌 장점으로 볼 수도 있고 단점으로 볼 수도 있는 것이 좋음
* 5년 후의 나의 모습은 어떠한가
  * 기술에 대해서 진취적인 인상을 심어주는 답변이 좋음
* (사전 코딩 테스트가 있었다면) 코딩 테스트 코드에 대한 질문
  * 부족한 구현이나 최적화 할 수 있는 부분이 있다면 생각해보고 가는 것이 좋음


### OS
* 프로세스 생성 과정
  * 프로세스 관리 정보를 갖는 Process Control Bolock를 생성하고 프로그램의 코드를 읽어 들여 코드 영역을 메모리에 할당
  * 초기화된 전역 변수 및 static 변수인 데이터 영역을 메모리에 할당
  * 힙과 스택의 초기 메모리 주소를 초기화
  * Queue에서 프로세스가 등록되고 운영체제가 CPU를 할당하기를 대기
* 문맥 교환(Context Switching)
  * CPU는 한번에 하나의 프로세스만 처리할 수 있어 여러 프로세스를 처리해야 하는 상황에서 현재 진행중인 Task(프로세스, 스레드)의 상태를 PCB에 저장하고 다음에 진행할 Task의 상태값을 읽어 적용하는 과정이 필요하고 이를 문맥 교환이라함
* CPU 스케줄링 기법
  * SRT(Shortest Remaining Time): 남은 시간이 가장 적은 프로세스를 실행
  * MLFQ(Multi Level Feedback Queue): 우선 순위 개수만큼 Queue가 있으며 최상위 단계의 Queue부터 실행 후 해당 큐의 할당량이 끝나면 하위 우선 순위 Queue를 실행하는 스케줄링 기법으로 처음 시작은 모든 프로세스가 가장 높은 우선 순위 Queue에 존재하나 할당된 Time Slice를 소진하면 우선 순위를 감소시켜서 우선 순위를 정해가고 일정 주기마다 모든 작업을 가장 높은 우선 순위 큐로 이동 시켜서 Starvation을 방지
  * Round Robin: 시간 조각(Time Slice)라고 하는 단위로 공평하게 프로세스 실행
* 메모리 영역에서 힙과 스택의 차이
  * 힙은 프로그램 코드에서 동적으로 할당하여 사용될 때 할당되는 메모리 영역
  * 스택은 함수를 호출할 때나 지역변수를 지정할 때 할당되는 메모리 영역
* 가상메모리와 가상메모리 사용 시의 장점
  * `프로그램에 실제 메모리 주소가 아닌 가상의 메모리 주소를 주는 방식`으로 프로그램 별로 사용 중인 메모리보다 큰 메모리를 사용하는 듯한 환상을 주는 기법
  * 실제 프로그램 전체를 적재하여 사용하지 않고 일부분만 적재하기 때문에 메모리 제약을 극복
  * 메모리의 실제 주소를 사용하지 않으므로 보안 상의 장점이 존재
* 세그멘테이션
  * 메모리 영역인 커널 영역, 스택 영역, 공유 라이브러리 영역, 힙 영역, 데이터 영역, 코드 영역 등으로 메모리를 세그먼트로 나누고 `세그먼트 테이블`에 각 세그먼트의 시작주소와 길이 정보를 운용하여 가상 메모리를 관리하는 기법
* 페이징
  * 페이지: `가상메모리`를 최소 단위로 쪼개어 만든 일정한 크기의 블럭
  * 프레임: `물리메모리`에 페이지 크기와 같은 블럭으로 나눈 블럭
  * 프로세스를 일정 크기인 페이지로 잘라서 가상 메모리에 적재하고 페이지 테이블을 이용하여 프레임으로 변환하여 가상 메모리를 관리하는 기법
* 페이지 교체 알고리즘
  * FIFO: 페이지 교체 시점에 들어온 페이지 순서대로 페이지를 교체하는 알고리즘으로 페이지 프레임의 개수를 늘리면 Page Fault 발생이 감소해야하나, 오히려 늘어나는 `Belady의 모순` 발생
  * LRU(Least-Recently-Used): 페이지 교체 시점에 가장 오랫동안 사용되지 않은 페이지를 선택하여 교체하는 알고리즘
  * LFU(Least Frequently Used): 페이지 교체 시점에 참조 횟수가 가장 적은 페이지를 교체하는 알고리즘
* 캐시의 지역성
  * 시간 지역성: 최근에 참조된 주소의 내용은 곧 다음에 다시 참조되는 특성
  * 공간 지역성: 대부분의 실제 프로그램이 참조된 주소와 인접한 주소의 내용이 다시 참조되는 특성
* 프로세스와 스레드의 차이
  * 프로세스는 프로그램의 실행 상태로 운영체제로부터 자원을 할당받아 실행하고 스레드는 경량 프로세스로서 프로세스 안에서 프로세스로부터 자원을 받아 실행
  * 프로세스는 `코드/데이터/스택/힙` 메모리 영역을 기반하지만, 스레드는 프로세스의 코드/데이터/힙 메모리 영역을 공유하고 `개별적인 스택`을 기반으로 함
* 멀티 스레딩
  * 멀티 코어 환경에서 병렬 처리를 하기 위한 방식으로 스레드를 기반으로함
  * 멀티 코어 환경은 공유 자원(Cirical Section)이 있을 시 동기화 매커니즘이 필요
  * 스레드 간은 Heap을 공유하므로 Shared Memory가 없어도 Heap을 통해 데이터를 주고 받을 수 있음
  * 멀티 스레드는 멀티 프로세스보다 적은 메모리 공간을 차지하고 스레드 간의 통신 비용이 적으며 문맥 교환 시에 비용이 적음
  * 하나의 스레드가 종료되면 전체 스레드가 종료될 수 있음
* 멀티 프로세싱
  * 멀티 코어 환경에서 병렬 처리를 하기 위한 방식으로 프로세스를 기반으로함
  * 멀티 코어 환경은 공유 자원(Cirical Section)이 있을 시 동기화 매커니즘이 필요
  * Shared Memory가 있어야 데이터를 주고 받을 수 있음 
  * 멀티 프로세스는 멀티 스레드보다 많은 메모리 공간을 차지하고 IPC라는 별도 매커니즘을 사용해야하여 프로세스 간의 통신 비용이 크며 문맥 교환 시에 비용이 큼
  * 하나의 프로세스가 죽더라도 다른 프로세스에는 영향을 끼치지 않고 정상적으로 수행
* 뮤텍스와 세마포어의 차이
  * 뮤텍스는 스레드 기반으로 공유 자원의 활용을 제어하는 매커니즘이고 세마포어는 프로세스 기반으로 공유 자원의 활용을 제어하는 매커니즘
  * 뮤텍스는 바이너리 세마포어와 비슷한 방식으로 동기화 대상이 1개 일 때 사용하고 세마포어는 동기화 대상이 하나 이상일 때 사용
* deadlock과 deadlock 해결 방법
  * 데드락이란 멀티 프로세스/스레딩 환경에서 잘못된 동기화 매커니즘 활용 때문에 프로세스/스레드가 `block`되어 다른 프로세스/스레드의 작업이 끝나기만을 기다리는 현상
  * lock을 잡는 순서를 모든 프로세스가 동일하게 코딩하는 방법 or `trylock`을 활용하여 lock을 선점한 프로세스/스레드가 없을 때만 락을 얻으려고 시도하는 방법을 통해 데드락을 해결
* 문맥 교환
  * 하나의 프로세스가 CPU를 사용 중인 상태에서 다른 프로세스가 CPU를 사용하도록 하기 위해, 이전의 프로세스의 상태(문맥)를 보관하고 새로운 프로세스의 상태를 적재하는 작업


### Network
* TCP와 UDP의 차이
  * TCP는 `신뢰성을 보장하는 연결형 프로토콜`로 `흐름제어, 혼잡제어, 오류제어`를 제공
  * UDP는 `신뢰성을 보장하지 않는 비연결형 프로토콜`로 흐름제어, 혼잡제어, 오류제어를 제공하지 않음 
* OSI 7계층와 각 계층 역할
  * Application - Application(7), Presentation(6), Session(5) 계층으로 분리
  * Application(7): 사용자에게 `실제 애플리케이션 서비스`를 제공하는 계층 / HTTP
  * Presentation(6): 애플리케이션의 `데이터 형태와 구조를 변환`시키는 계층
  * Session(5): 애플리케이션 간의 `TCP/IP 세션을 구축하고 관리하며 종료`시키는 계층
  * Transport(4): 통신 `양단 간의 신뢰성 있는 통신`을 보장하는 계층 / TCP와 UDP
  * Network(3): 목적지까지의 경로를 선택하고 `경로에 따라 패킷을 전달`해주는 계층 / IP
  * Link(2): 인접한 `피어 간의 신뢰성 있는 통신`을 보장하는 계층 / MAC
  * Physical(1): 전기적, 기계적, 기능적인 특성을 이용해서 통신 케이블로 데이터를 전송
* HTTP와 HTTPS의 차이
  * HTTP는 웹 브라우저와 웹 서버가 통신하기 위한 프로토콜이고 HTTPS는 HTTP Secure의 약자로 HTTP에 SSL/TLS 기반의 Secure Socket을 활용한 프로토콜
  * HTTP는 평문 통신이기 때문에 `도청`이 가능하고 `변조`가 가능하며 통신 상대를 특정하지 않기 때문에 `위장`이 가능
  * HTTPS는 웹 브라우저와 웹 서버가 각각 키를 갖고 있고 그 키를 통해 암호화/복호화하여 HTTP 통신하므로 클라이언트와 서버만이 데이터를 열람 가능
* HTTP 상태코드  
  * 2xx: 성공
  * 3xx: 리다이렉션
  * 4xx: 클라이언트 에러
  * 5xx: 서버 에러
* 공개키
  * 비공개키와 공개키 2개의 키로 쌍으로 암호화/복호화하는 기법으로 비공개키는 자신만이 소유하고 공개키는 타인에게 제공하는 방식으로 작동
* SSL/TLS 동작방식
  * 
* 쿠키와 세션이 무엇이고 차이가 뭔지
  * 쿠키는 `클라이언트 로컬`에 저장되는 키와 값이 들어있는 작은 데이터 파일
  * 세션은 일정 시간동안 같은 브라우저로 부터 들어오는 일련의 요구를 하나의 상태로 보고 그 상태를 `서버`에 저장하는 기술
  * 쿠키는 클라이언트 로컬에 파일로 저장하지만 세션은 서버에 저장하고 세션은 `sessionid`를 통해 데이터를 구분하여 처리하여 보안이 좋음
* TCP 3-way handshake가 언제 일어나고 어떤 과정인지
  * 서버와 클라이언트가 TCP `연결을 성립할 때` 사용
  * Client -> Server: SYN 전송
  * Server -> Client: SYN 전송 + ACK 전송
  * Client -> Server: ACK 전송
  * TCP는 양방향성 연결이기 때문에 클라이언트에서 서버에게 자신의 존재를 알리고 패킷을 보낼 수 있는 것처럼 서버에서도 클라이언트에세 자신의 존재를 알리고 패킷을 보낼 수 있다는 신호를 보내야함
* TCP 4-way handshake가 언제 일어나고 어떤 과정인지
  * 서버와 클라이언트가 TCP `연결을 종료할 때` 사용
  * Client -> Server : FIN 전송
  * Server -> Client : ACK 전송
  * Server -> Client : FIN 전송
  * Client -> Server : ACK 전송
* 웹 브라우저에 URL을 입력했을 때의 수행 과정
  * 사용자의 PC는 `DHCP 서버`에서 사용자 `자신의 IP 주소`, `가장 가까운 라우터의 IP 주소`, `가장 가까운 DNS 서버의 IP 주소`를 받는다.
  * `ARP`를 이용하여 IP 주소를 기반으로 가장 가까운 라우터의 MAC 주소를 받는다.
  * TCP Socket을 통해 웹 서버와 `3 way hand shaking`을 하여 연결한다.
  * `HTTP Request`가 TCP Socket을 통해 보내지고, 응답으로 웹페이지의 정보가 사용자의 PC에 전달
* 기타 네트워크 프로토콜과 기본 네트워크 주소들
  * DHCP: 호스트의 IP 주소 및 TCP/IP 설정을 클라이언트에 자동으로 제공하는 프로토콜
  * DNS: IP 주소와 도메인의 매핑정보를 관리하는 프로토콜
  * ARP: IP 주소를 물리적 네트워크 주소로 대응시키기 위해 사용되는 프로토콜
  * IP 주소: 컴퓨터 마다 부여된 고유의 주소
  * MAC 주소: NIC 카드 마다 부여된 네트워크 장비 고유의 주소
* HTTP GET 방식과 POST 방식의 차이
  * GET은 정보를 조회하기 위한 메소드이고 POST는 서버로 데이터를 전송하기 위해 설계된 메소드
  * 둘다 데이터를 서버에 전달할 수 있다는 것이 공통점이지만 GET은 URL의 파라미터로 이름과 데이터가 쌍으로 명시되어 전달되고, POST는 HTTP Request Message의 Body 부분에 데이터가 담겨있어 또한 URL의 길이는 제한적이기 때문에 GET으로는 많은 양의 데이터를 전송할 수도 없음
* CDN과 사용 시의 이점
  * CDN은 Contents Delivery Network의 약자로 지리, 물리적으로 떨어져 있는 사용자에게 컨텐츠를 더 빠르게 제공할 수 있는 기술


### Database
* DB를 사용하는 이유
  * 파일 시스템이 OS마다 다를 수 있기 때문에 OS에 종속적인 파일 시스템을 이용하는 것은 프로그램의 확장성을 해침
  * DB는 `원자적 갱신`, `동시성 제어`, `데이터 보호`, `백업 및 회복` 등의 여러 데이터 관리 기능을 두어 데이터 관리를 편하게 하기 때문에 파일 시스템을 활용하여 OS를 만듦
* 테이블
  * 행과 열로 이루어진 데이터의 집합
* 도메인
  * 데이터베이스 필드에 채워질 수 있는 값들의 집합
* 행
  * 테이블을 구성하는 데이터 셋으로 튜플이나 레코드라고 불림
* 열
  * 테이블을 구성하는 데이터 셋으로 속성이라고 불림
* 후보 키, 주 키, 외래 키
  * 후보 키: 릴레이션을 구성하는 속성들 중에서 Tuple을 `유일하게 식별`할 수 있는 속성들의 부분 집합
  * 주 키: 후보 키 중에서 선택한 Main Key
  * 외래 키: 참조되는 릴레이션의 주 키와 대응되어 릴레이션 간에 참조 관계를 표현하는 키
* 스키마와 테이블(릴레이션)의 차이
  * 스키마는 테이블(릴레이션)의 이름과 속성들의 나열로 테이블에서의 첫 행인 헤더이고 테이블은 행과 열로 구성된 테이블을 의미
* 조인
  * 두 개 이상의 테이블이나 데이터베이스를 연결하여 데이터를 검색하는 방법으로 적어도 하나의 칼럼을 서로 공유하고 있어야 하므로 이를 이용하여 데이터 검색에 활용
* Index 자료구조
  * B 트리
  * B+ 트리
  * 인덱싱에선 등호 연산 때문에 해시 테이블을 사용하면 성능이 떨어짐
* Index를 사용하는 이유와 장점 및 단점
  * 인덱스는 데이터베이스의 `검색 속도`를 위해 사용하는 추가적인 자료구조로 테이블 내의 칼럼의 값과 해당 레코드가 저장된 주소를 키와 값의 쌍으로 정의
  * 인덱스를 사용하면 검색이 빨리지지만 테이블의 데이터가 추가, 삭제, 수정이 자주되는 경우 인덱스도 변경해야 하여 성능이 오히려 저하될 수 있음
* 정규화
  * 
* 트랜잭션
  * 데이터베이스의 상태를 변화시킬 때 한번에 수행되어야하는 하나의 `원자적인` 작업의 단위
  * Lock과 유사한 기능을 하지만 Lock은 동일한 자원을 요청할 경우 한 시점에는 하나의 커넥션만 변경하는데에 반해 트랜잭션은 논리적인 작업의 쿼리의 개수와 관계없이 논리적인 작업 셋 자체가 100% 적용되거나 아무것도 적용되지 않아야 함을 보장
* Commit, Rollback
  * Commit: 작업의 논리적 단위가 성공적으로 끝났고, 데이터베이스가 다시 일관된 상태에 잇으며 이 트랜잭션이 행한 갱신 연산이 완료되어 하드 디스크에 저장된 것을 트랜잭션 관리자에게 알려주는 연산
  * Rollback: 트랜잭션의 실행을 취소하였음을 알리는 연산자로 트랜잭션이 수행한 결과를 원래의 상태로 원상 복귀시키는 연산
* 관계형 데이터베이스와 NoSQL의 차이
  * 관계형 데이터베이스는 엄격한 스키마 아래 행과 열로 구성된 테이블들의 관계로 데이터를 저장하는 데이터베이스이고 NoSQL은 스키마가 없거나 느슨한 스키마로 데이터를 저장하는 데이터베이스
  * 관계형 데이터베이스는 `속성(열)에 맞는 각각형 자료형에 따라` 데이터를 삽입해야하지만 NoSQL은 `key-value 구조`의 유연한 데이터 삽입 구조를 갖음
  * 관계를 맺고 있는 데이터가 자주 변경되거나 명확한 스키마가 있는 경우 SQL DB가 좋고 정확한 데이터 구조를 알 수 없거나 변경/확장이 쉡게 되어야하는 경우 NOSQL DB가 좋음
* Redis와 MongoDB
  * Redis는 No SQL 방식을 사용하는 인메모리 데이터베이스로 `Key-Value` 형식으로 데이터를 저장하며 주로 캐쉬로 사용
  * MongoDB는 NO SQL 방식을 사용하는 데이터베이스로 JSON같은 구조의 `Document` 형식으로 데이터를 저장하고 문서에 대한 ID를 키로 표현


### Datastructure
* 배열과 링크드 리스트 비교
  * 배열은 순차적으로 데이터를 저장하는 자료구조로 메모리 상에 연속적으로 할당한 자료구조이고 링크드 리스트는 따로 할당하고 이은 자료구조
  * 배열은 순서를 알고 있다면 탐색에서 O(1) 삽입 삭제에서 O(N)
  * 링크드 리스트는 탐색에서 O(N) 순서를 알고 있다면 삽입 삭제에서 O(N)
* 배열 리스트와 링크드 리스트 비교
  * 배열 리스트는 내부적으로는 배열을 활용하기 때문에 탐색에서 O(1) 삽입 삭제에서 O(N)
  * 링크드 리스트는 탐색에서 O(N) 순서를 알고 있다면 삽입 삭제에서 O(N)
  * 캐시의 특성 때문에 빈번한 삽입 삭제가 나지 않는 경우라면 배열 리스트를 사용할 때 일반 적으로 성능이 더 좋음
* 해쉬테이블
  * 배열과 리스트의 장점을 합친 자료구조로 key 값을 통해 해시 주소를 알아내어 탐색에 있어 O(1)을 보장하는 자료구조
  * `해시 충돌`이 나는 경우 그 다음 비어 있는 공간에 삽입하는 방식인 선형 조사법 또는 해시 주소로 관리되는 데이터를 연결 리스트로 관리하는 방식인 체이닝 기법을 통해서 해결
* Stack과 Queue
  * Stack은 LIFO 방식으로 삽입되고 제거되는 최근성에 포커싱된 자료구조이고 Queue는 FIFO 방식으로 삽입되고 제거되는 순차성에 포커싱된 자료구조
* Tree, Binary Tree, Full Binary Tree, Complete Binary Tree, Binary Search Tree 
  * 트리는 그래프의 스페셜 케이스로 사이클을 가지지 않는 그래프로 부모 자식 관계를 갖는 노드들의 집합으로 계층적 구조를 갖음
  * 이진 트리는 최대 2개의 자식 노드들만 가질 수 있는 트리
  * 포화 이진 트리는 각 레벨에 노드가 꽉 차있는 트리
  * 완전 이진 트리는 높이가 K인 트리에서 레벨 1~ 레벨 K-1까지 모두 채워져 있고 마지막 레벨에서는 왼쪽부터 순서대로 채워져 있는 트리
  * 이진 탐색 트리는 탐색을 위해 만들어진 자료구조로 부모 노드의 키 값이 왼쪽 자식 노드의 키값보다 크고 오른쪽 자식 노드의 키값보다 작거나 같은 구조
* 힙
  * 힙은 완전 이진 트리의 일종으로 우선 순위 큐를 구현하기 위해 만들어진 자료구조인데 이진 탐색 트리가 전체 노드를 탐색하기 위한 자료구조라면 힙은 최소값 또는 최대값을 쉽게 뽑아내기 위한 자료구조
  * 부모 노드의 키 값이 자식 노드의 키 값보다 항상 큰 완전 이진 트리로 힙은 자식 노드에도 구분 조건이 필요한 이진 탐색 트리보다 느슨한 정렬 상태를 유지
* Binary Search Tree의 최악의 시간복잡도와 최악의 시간복잡도를 유발하는 케이스
  * 밸런싱이 된 BST는 O(logN)이지만 밸런싱이 되지 않지 않고 한쪽으로만 삽입된 경우 O(N)
* Graph를 구현하는 두 가지 방법과 장점
  * 인접 행렬을 사용하는 방법: 인접 행렬의 해당하는 위치의 value 값을 통해서 vertex 간의 연결 관계를 `O(1`)으로 파악하는 방법으로 `장점의 개수^2`의 공간 복잡도를 갖으며 엣지가 많을 경우 사용
  * 인접 리스트를 사용하는 방법: 각 vertex의 adjacent list를 통해서 연결 관계를 `O(정점에 연결된 노드의 수)`로 파악하는 방법으로 `엣지의 개수+정점의 개수`의 공간 복잡도를 갖으며 엣지가 적을 경우 사용


### Algorithm
* 정렬 알고리즘에서 `stable` 하다는 것의 의미
  * 정렬 기준으로 봤을 때 값이 동일한 Element가 있어도 정렬 전의 순서와 정렬 후의 순서가 동일함을 보장하는 것
* 정렬 알고리즘의 가짓수가 많은 이유
  * 공간 복잡도에 따라 사용해야할 알고리즘이 다름 -> Merge Sort는 공간 복잡도는 Selection Sort와 Insertion Sort에 비해 큼
  * 안정 정렬이냐 불안정 정렬이냐에 따라 사용해야할 때가 다름
* Selection Sort
  * 선택 정렬은 가장 작은 값을 가지는 데이터를 찾아서 가장 작은 값을 앞에서부터 채워 나가면서 정렬하는 방식으로 동작하는 O(n^2) `불안정 정렬 알고리즘`으로 1번의 순환마다 맨 앞의 값이 고정
* Bubble Sort
  * 버블 정렬이란 처음부터 끝까지 현재 자신과 자신의 다음 데이터를 비교해가면서 큰 값을 맨 뒤로 보내는 방식으로 동작하는 O(n^2) `안정 정렬 알고리즘`으로 1번의 순환마다 맨 뒤의 값이 고정
* Merge Sort
  * 병합 정렬은 배열을 반으로 쪼개 가면서 하나의 원소를 가진 배열로 만든 이후에 쪼개진 각 배열을 정렬하면서 병합하여 최종 정렬된 배열을 완성하는 O(NlonN) `안정 정렬 알고리즘`
* Heap Sort
  * 완전 이진 트리를 기본으로 하는 힙에 데이터를 삽입하고 꺼내서 힙을 통해 정렬하는 O(NlogN) `불안정 정렬 알고리즘`
* Quick Sort
  * 분할 정복 알고리즘으로 `파티셔닝` 아이디어를 재귀적으로 활용
  * `파티셔닝`이란 pivot 원소를 기준으로 왼쪽은 pivot보다 작은 원소들로 모으고 오른쪽은 pivot보다 큰 원소로 모으는 것을 의미하는데 pivot을 기준으로 파티셔닝이 완료되면 pivot을 고정하고 재귀호출 하여 구현하는 O(NlonN) `불안정 정렬 알고리즘`
  * Quick Sort가 통상적으로 가장 빠른 정렬을 지원하지만 `Worst Case에서 O(n^2)`이므로 Tim Sort나 Heap Sort를 사용하기도 함
* 이분 탐색
  * 이분 탐색은 이미 정렬되어 있는 자료구조에서 특정 값을 탐색할 때 탐색 번위를 반으로 쪼개서 값을 찾아가는 알고리즘
  * O(logN)으로 순차 탐색보다 빠르지만 탐색을 위해 정렬을 하면 순차 탐색보다 더 높은 시간복잡도를 갖게 됨
* Fibonacci 공식을 재귀적인 방법과 동적 계획법을 이용했을 때 각각의 차이
  * 재귀적인 방법인 경우 재귀 호출 시에 중복되는 연산이 계속 수행되지만 동적 계획법의 경우 이전 값을 메모리제이션하기 때문에 중복 연산이 수행되지 않음
* DFS와 BFS
  * DFS는 스택이나 재귀호출로 구현할 수 있는 탐색 방법으로 한 정점으로부터 연결되어 있는 한 정점으로만 나아가는 방식
  * BFS는 큐를 통해서 구현할 수 있는 탐색 방법으로 한 정점으로부터 연결되어 있는 모든 정점을 나아가며 탐색하는 방식으로 BFS로 구한 경로는 최단 경로라는 장점이 존재


### Etc
* 객체지향 프로그래밍과 장점
  * 사물들을 객체라고 보고 그 객체의 특징들을 뽑아와 프로그래밍는 방식으로 `추상화`가 쉽고 상속을 통해 코드 `재산성성`을 높일 수 있으며 객체 단위 코드가 나눠져 있기 때문에 `디버깅과 유지보수`에 용이
* 객체지향 설계의 5원칙
  * `SRP(Single Responsibility Principle)`: 단일 책임 원칙, 클래스는 단 하나의 책임을 가져야 하며 클래스를 변경하는 이유는 단 하나의 이유이어야 한다.
  * `OCP(Open-Closed Principle)`: 개방-폐쇄 원칙, 확장에는 열려 있어야 하고 변경에는 닫혀 있어야 한다.
  * `LSP(Liskov Substitution Principle)`: 리스코프 치환 원칙, 상위 타입의 객체를 하위 타입의 객체로 치환해도 상위 타입을 사용하는 프로그램은 정상적으로 동작해야 한다.
  * `ISP(Interface Segregation Principle)`: 인터페이스 분리 원칙, 인터페이스는 그 인터페이스를 사용하는 클라이언트를 기준으로 분리해야 한다.
  * `DIP(Dependency Inversion Principle)`: 의존 역전 원칙, 고수준 모듈은 저수준 모듈의 구현에 의존해서는 안된다.
* 클래스와 인스턴스의 차이
  * 클래스는 객체를 만들기 위한 템플릿, 객체는 클래스라는 템플릿을 토대로 메모리에 할당한 실체
* 컴파일와 스크립트 언어의 차이
  * `컴파일 언어`는 컴파일러를 통해 사전에 컴파일 되어 기계어 상태로 실행되고 `스크립트 언어`는 컴파일 단계 없이 인터프리터에 의해 실행 단계해서 한 줄씩 기계어로 번역하여 실행
  * 일반적으로 컴파일 언어가 스크립트 언어에 비해 빠르고 안정적임
* 동기식과 비동기식의 차이
  * 동기식은 요청에 대한 응답을 기다린 후 응답이 오면 실행하는 방식이고 비동기식은 요청에 대한 응답을 기다리지 않고 실행하는 방식
  * 동기식은 구성이 단순하나 멀티태스킹이 불가능하고 비동기식은 멀티태스킹이 가능하나 요청량이 많아질 경우 부하 컨트롤과 데이터의 일관성 유지 등 추가적인 처리가 필요
* 블락킹과 논블락킹의 차이
  * 블락킹은 I/0 처리 함수가 끝날 때까지 기다리고 처리가 끝나면 결과를 리턴하는 방식이고 논블락킹은 I/0 처리 함수가 끝나지 않더라도 기다리지 않고 다른 작업을 처리하는 방식
* 블락킹과 비동기의 차이
  * 블락킹과 비동기 모두 응답을 기다리지 않는 공통점이 있지만, 재실행 시점이 비동기는 요청에 대한 응답이라는 관점이고 블락킹은 I/O처리(시스템 함수 호출의 리턴)이라는 관점에서 다름
* RESTful API
  * REST는 HTTP기반으로 필요한 자원에 접근하는 방식을 정해놓은 아키텍쳐로 RESTful API는 REST 기반의 규칙들을 지켜서 설계된 API
  * 기본 설계 원칙1. `/`를 계층관계를 나타내는데 사용하되 마지막 문자에 `/`를 포함하지 않음
  * 기본 설계 원칙2. 자원에 대한 정보는 명사로 표현하고 자원에 대한 행위는 HTTP 메소드로 표현
  * 기본 설계 원칙3. 소문자와 `-`를 사용
  * 기본 설계 원칙4. 브라우저는 form-data 형식의 submit 으로 보내고 서버에서는 json 형태로 보내는 식의 분리보다는 둘 다 form-data 형식으로 보내든 하나로 통일
* RESTful API 장단점
  * HTTP를 사용하므로 웹 인프라를 그대로 이용할 수 있고 MSA에 적합하여 재사용에서 이점이 존재
  * HTTP를 사용하므로 HTTP 통신 모델에 제약적이고 아키텍처가 복잡
* 디자인 패턴
  * 소프트웨어 코드 작성 시에 생기는 `공통적인 문제를 해결하는데 도움이 되는 코드 패턴`
* 디자인 패턴 중 싱글톤 패턴
  * 전체 프로그램에서 단 1개의 객체를 생생하고 공유하는 코드 패턴으로 한번의 객체 생성으로 재 사용이 가능하기 때문에 메모리 낭비를 방지하고 객체가 전역성을 띄기 때문에 공유가 용이
* 디자인 패턴 중 MVC 패턴
  * Model, View, Controller라고 하는 컴포넌트로 분리하여 비지니스 처리 로직과 사용자 인터페이스 요소를 분리시켜 서로 영향없이 개발 하기 수월 
* PostgresSQL과 ElasticSearch의 차이점
  * PostgresSQL은 관계형 데이터베이스이고 ElasticSearch는 검색 및 분석엔진으로 다르고 ES는 데이터 모델을 JSON으로 하고 있어 NoSQL처럼 사용할 수 있음
* TDD
  * 테스트 코드를 작성 한 후 그것을 통과하는 실행 코드를 작성하는 cycle로 개발을 해가는 방법으로 디버깅이 쉬워지고 코드의 신뢰성이 높아짐
* 크롬 탭은 프로세스인지 스레드인지
  * 크롬은 탭마다 PID를 가지고 있는 Process이며 각 Tab마다 랜더링 정보나 기타 데이터를 따로 관리, 그로 인해 메모리를 많이 잡아먹기도 하지만 하나의 Tab에 오류가 생겼다고 모든 Tab에 영향을 끼치진 않는 장점이 존재
* 함수형 프로그래밍
  * 함수형 프로그래밍은 계산을 수학적 함수의 조합으로 생각하는 방식
  * 1급 객체와 데이터 불변성 그리고 고차함수, 합성함수, 순수함수와 같은 다양한 함수 개념으로 구성


### Python
* Generator와 사용 시의 장점
  * Iterator를 생성해주는 루틴으로 `yield` 키워드를 통해서 만드는데, Generator는 한번에 모든 데이터를 메모리에 적재할 필요가 없어서 메모리 효율이 높고 계산 결과가 필요할 때 수행되므로 수행 시간을 꼭 필요한 시간까지 늦츨 수 있음
* Decorator와 사용 시의 장점
  * 기존의 코드에 여러 가지 기능을 추가하는 파이썬 구문으로 데코레이터를 함수나 클래스로 정의하고 수행하고자 하는 함수에 `@` 키워드를 통해서 삽입하여 실행시켜 생산성을 극대화할 수 있음
* Python Garbage Collection 동작 방식
  * 각각의 객체마다 `reference count`를 갖고 있고 몇 곳에서 객체를 참조하는지를 나타내는데 인터프리터가 계속 이를 확인하다가 이 count가 0이 되는 경우 그 객체를 삭제
*  GIL과 GIL을 보완하는 방법
  * 파이썬은 하나의 스레드만이 인터프리터의 제어권을 가질 수 있는 개념인 GIL(Global Interpreter Lock)은 멀티 코어 환경에서도 어느 시점에서나 1개의 스레드만 실행될 수 있기 때문에 `threading`이 아닌 `multiprocessing` 모듈을 통해 스레드 단위가 아닌 프로세스 별로 인터프리터 락을 잡아 보완해야함
* Duck Typing
  * 동적 타입을 가지는 프로그래밍 언어에서 많이 사용되는 개념으로, 객체의 실제 타입보다는 객체의 변수와 메소드가 그 객체의 적합성을 결정하는 것을 의미


### Java
* JVM과 Java 프로그램 실행 과정
  * JVM은 Java Virtual Machine의 약자로 자바 프로그램을 실행하는 역할을 하고 프로그램이 시작되면 컴파일러를 통해 바이트 코드로 변환하고 변환된 파일을 JVM에 로딩하여 실행
* Java에서 Garbage Collection이 필요한 이유에 대해서 설명
  * 자바는 메모리를 명시적으로 해제하지 않기 때문에 GC를 통해서 필요없는 객체를 지우는 작업을 수행
* JVM 메모리 영역 구조
  * 크게 `메소드 영역, JVM 스택, JVM 힙`으로 나뉘며 JVM 힙은 `Young Generation, Old Generation, Permanent Generation`으로 나뉘고 Young Generation은 `Eden, Survivor0, Survivor1`으로 나뉨
* Java Garbage Collection 동작 방식
  * 새롭게 생성된 객체는 Young의 Eden 영역으로 들어가게 되고 Eden 영역이 다 차면 Minor GC가 발생하여 참조 횟수에 따라 증가하는 `age bit`를 보고 불필요한 객체를 삭제하고 생존한 객체는 S0으로 이동
  * Minor GC가 발생할 때마다 각각 Young 영역의 객체들은 삭제와 이동을 하게되는데 (Eden -> S0 / S0 -> S1)
  * S1이 가득 차면 필요한 객체는 OLD 영역으로 이동하고 OLD 영역이 가득차면 Major GC를 통해서 값을 삭제
  * GC가 실행될 때마다 `STOP THE WORLD`가 발생하여 프로그램이 중지
* Overriding과 Overloading
  * 오버라이딩은 부모 클래스에 존재하는 메서드를 하위 클래스에서 재정의하는 것이고 오버로딩은 같은 메서드 이름을 갖게 하지만 시그니처가 다르게 정의하는 것
* 추상 클래스와 인터페이스
  * 추상 클래스는 반드시 구현해야하는 추상 메소드를 1개 이상 갖고 있는 클래스이고 인터페이스는 추상 메소드만 갖고 있는 개념으로 추상 클래스는 1번만 상속받을 수 있지만 인터페이스는 여러번 상속 가능
* Collection
  * List: 대표적인 구현체로는 ArrayList가 존재한다. 이는 기존에 있었던 Vector를 개선한 것이다.
  * Map: 대표적인 구현체로 HashMap이 존재한다. 해시테이블처럼 key-value의 구조로 이루어져 있으며 key를 기준으로 중복된 값을 저장하지 않으며 순서를 보장하지 않는다. 
  * Set: 대표적인 구현체로 HashSet이 존재한다. value에 대해서 중복된 값을 저장하지 않는다. 
  * Stack과 Queue: Stack은 직접 new 키워드로 사용할 수 있으며, Queue는 LinkedList에 new 키워드를 적용하여 사용
* Annotation
  * 어노테이션이란 본래 주석이란 뜻이지만, 자바에서는 인터페이스를 기반으로 한 문법으로 주석과 다른 점은 주석처럼 코드에 달아 클래스에 특별한 의미를 부여하거나 기능을 주입함
* Generic
  * 제네릭은 다양한 타입의 객체들을 다루는 메서드나 컬렉션 클래스에서 사용하는 것으로, 컴파일 과정에서 타입체크를 해주는 기능
* Access Modifier
  * public
  * protected
  * private
* final 키워드
  * final class: 다른 클래스에서 상속하지 못한다.
  * final method: 다른 메소드에서 오버라이딩하지 못한다.
  * final variable: 변하지 않는 상수값이 되어 새로 할당할 수 없는 변수가 된다.
* Wrapper class
  * 
* Synchronized
  * 
* ThreadLocal
  * 

### JavaScript


### Django


### Spring


### React


### Android


### IOS