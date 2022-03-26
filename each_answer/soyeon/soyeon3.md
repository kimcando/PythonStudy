* 멀티 프로세스, 멀티 스레드, 멀티 테스크, 멀티 프로그래밍에 대해 짧게 설명하고 비교해주세요.(CS 일반)
  * 멀티 프로세싱 : 여러개의 프로세서가 협력적으로 일을 처리하는 것. 컴퓨터 1개인데 프로세서(CPU)는 2개 이상인 경우가 많음. 멀티 코어 시스템 포함
  * 멀티 프로그래밍 : 하나의 프로세서가 여러 프로그램 수행가능한 것. 프로세서가 한 프로그램에서 입출력 작업이 끝날 때까지 대기하면 자원낭비. 따라서 하나의 프로세서에서 둘 이상의 프로그램을 수행할 수 있도록 하는 것. 
    * 따라서 CPU가 항상 한 개 이상의 프로그램을 돌려서 CPU 이용률 증가
    * 목적이 CPU가 쉬지 않고 계속 작업을 할 수 있게 하는 것
  * 멀티 태스킹: 여러개의 작업을 운영체제 스케줄링에 의해 번갈아가며 수행되도록 하는 것. CPU가 여러 프로세스를 전환하며 프로세스를 실행하는 것이고 전환이 아주 빨라서 사용자에게 빠른 응답 시간 제공. 그래서 우리는 여러 프로그램이 동시에 실행되는 것처럼 보임
    * 원래 한 개의 프로세서는 특정 순간에 한 개의 작업만 수행 가능하지만 실제로 여러가지 프로그램을 우리가 쓸 수 있게 하는 것.
    * 동시에 여러 프로그램이 돌아가는 것처럼 보여주는 방법
  * 멀티 스레딩 : 하나의 프로세스를 여러 실행하는 단위고 여러개의 스레드는 자원을 공유하는 것
    * 멀티 테스킹과 멀티 스레딩 차이 : 하나의 프로그램이 하나의 프로세스로 실행도 가능하나 여러개의 프로세스로 나누어 동시에 실행되게 할 수 잇고, 이때 주 프로세스와 동시에 실행되는 부수적인 것을 스레드로 볼 수 있음. 
      * 동시에 여러개의 프로세스가 실행되는 것 같아보이나, 멀티 태스킹은 OS 스케쥴링에 의해 여러 개의 프로그램을 실행시키는 것이고(물론 실제로는 분할이지만), 멀티 스레드는 하나의 프로그램을 여러개의 기능으로 나누어 이를 동시에 실행히시킴.
  * 참고
    * [전체 설명](https://velog.io/@chy0428/OS-%EB%A9%80%ED%8B%B0%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-%EB%A9%80%ED%8B%B0%ED%94%84%EB%A1%9C%EC%84%B8%EC%8B%B1)
    * [전체 설명2](https://sorjfkrh5078.tistory.com/56)
    * [멀티 프로그래밍 vs 멀티 태스킹](https://luv-n-interest.tistory.com/430)
    * [멀티 테스킹 vs 멀티 스레딩](https://skmagic.tistory.com/261)  
    
* IO bound 와 CPU bound에 대해 설명해주세요.(CS 일반)
  * 프로세스 명령어 해석하는 수학 연산, 이미지/비디오 프로세싱같이 CPU 성능과 관련된 경우 CPU bound 됐다고 함
  * CPU와 상관없이 peripheral 시스템(인풋, 아웃풋, 네트워크)과 관련된 경우 IO bound 됐다고 함
  
* python의 multiprocess, multithread 기능에 대해 설명해주세요.
  * 여러개의프로세스를 동시에 실행시키는 parallel execution(병렬성) 을 위한 라이브러리 `from concurrent.futures import ThreadPoolExecutor`이 있고 또는 `multiprocessing` 모듈의 Pool 클래스 사용 가능
  * 한 프로세스가 여러 thread를 실행 히시큰 concorrent execution(동시성)을 위한 라이브러리 `from concurrent.futures import ThreadPoolExecutor` 또는 `Threading`의 Thread 클래스 사용
* IO bound와 CPU bound 작업일 때 파이썬의 어떤 식으로 처리하면 효율적일까요?
  * cpu bound는 multi process를 사용,
  * io bound에는 multi thread를 사용하는 것이 좋으나(메모리 공유 때문에 context switching 시간 감소) multi process를 쓰더라도 속도 이득을 얻을 수 있습니다.
  * 참고
    *  [참고](https://hhj6212.github.io/programming/python/2021/04/18/python-multi.html#:~:text=%EC%9D%B4%EC%97%90%20%EB%94%B0%EB%A5%B4%EB%A9%B4%2C%20multithreading%20%EC%9D%80%20%EC%97%AC%EB%9F%AC,%ED%95%98%EB%8A%94%20%EA%B2%83%EC%9D%84%20%EB%A7%90%ED%95%A9%EB%8B%88%EB%8B%A4%20(parallelism).)
    *  [사용 참고](https://monkey3199.github.io/develop/python/2018/12/04/python-pararrel.html)
* 병렬성과 동시성에 대해 설명해주세요(CS일반)
 * 병렬성 : 여러 프로세스에서 각 테스크를 실행함으로 실제로 동시에 여러 작업이 처리됩니다.
 * 동시성 : 하나의 프로세스에서 여러 테스크를 수행하는데, 실제로는 동시에 처리되는게 아니지만 time slicing을 이용해 마치 여러개의 테스크가 수행되는 것 같은 것입니다.
* blocking 과 non blocking에 대해 설명해주세요(CS일반)
  * 두 개는 함수의 리턴 시점과 제어권에 따른 차이로 여러개의 작업이 처리돼야할 때, 한 작업이 처리되는 동안 다른 작업이 처리될 수 있느냐의 의미입니다.
  * blocking 경우 요청한 일이 끝날 때까지 계속 기다려야하는 것이고
  * non blocking은 A가 B함수에게 일을 요청한 후 뒤에 있는 다른 일을 이어서 수행할 수 있습니다.
* synchronous 과 asynchronous 에 대해 설명해주세요(CS일반)
  *  작업의 완료 여부를 계속 확인하는지 안하는지에 따라 나눌 수 있습니다.
  *  동기 경우 함수 A가 B를 호출한 후 A가 계속 B의 완료 여부를 확인하지만
  *  비동기는 함수 A가 신경쓰지 않고 B가 끝나면 알아서 A한테 전달해줍니다.
* 파이썬의 시리얼라이제이션에 대해 설명해주세요. 관련된 모듈이 있나요? 어떤 때 써보셨나요?
  * pickle : 객체를 아예 저장해준다. 
