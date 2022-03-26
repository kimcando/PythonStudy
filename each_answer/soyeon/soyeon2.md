* GIL은 무엇인가요?
  * 파이썬 객체의 접근을 막는 뮤텍스입니다. 뮤텍스는 멀티 쓰레드에서 쓰레드 간 자원을 공유할 때 여러개가 동시에 데이터에 접근하면 생길 수 있는 문제를 해결하기 위해 데이터를 한 번에 하나의 프로세스(쓰레드)만 접근할 수 있도록 하는 동기화 방식입니다.
  * 즉 스레드들의 실행시간이 서로 겹치지 않고 각각 단독으로 실행되게 mutual exclusion 하는 것입니다.
  * 파이썬은 모든것이 객체라 객체마다 mutex가 필요하나 이걸 다 관리하면 성능도 떨어지고 엔지니어도 힘듭니다.
  * 따라서 파이썬은 객체마다 mutex를 두어 보호하는 대신 파이썬 인터프리터 자체를 잠궈 한 쓰레드가 모든 공유 자원을 독점하는 방식을 사용합니다.
  * 추가로 알아볼 것 -> [뮤텍스, 세마포어](https://chelseashin.tistory.com/40)
  * [추가 설명](https://m.blog.naver.com/alice_k106/221566619995)
* GIL은 왜 느린가요?
  * 질문이 [cpu-bound multirheaded process에서 GIL 때문에 느려지는 이유](https://www.reddit.com/r/learnpython/comments/9i6kwk/eli5_why_does_the_gil_slow_down_cpubound/)라고 변경돼야할 것 같다.
  * 파이썬이 느린 이유 중 하나-GIL : 한 스레드가 자원 독점하기 위해 인터프리터 자체를 잠그고, 한 스레드만 파이썬 코드가 실행되기 때문에 실제로 멀티스레드 해도 진짜 멀티 스레드가 안됨.
      - [ ] 근데 정확히 이해되지가 않는다. [인터프리터를 락해서 다른 코드가 실행안된다](https://velog.io/@sawol/GILGlobal-Interpreter-Lock)는게 무슨 말이지 정확히?
  * 참고
      * [thread-safe](https://8iggy.tistory.com/241) 
      * [외국사이트 참고](https://medium.com/hackernoon/why-is-python-so-slow-e5074b6fe55b) 

* 파이썬은 왜 꼬리 재귀를 제공하지 않나요?
  - [ ] 일단 꼬리 재귀부터 이해해야겠다. 함수가 반복문으로 변경되어 스택이 쌓이지 않는다라?
* 파이썬의 메모리 관리 전략은 어떤 것이 있나요? (Garbage collection)
  * 크게 reference counting 방법으로 작동하고, cycle reference 있는 경우 tracing하는 방법이 있다.
* Reference counting의 작동에 대해서 자세하게 설명해주세요.
  * 모든 객체는 참조당할 때 레퍼런스 카운터가 증가되고, 참조가 없어지면 감소됩니다.
  * 이때 카운터 값이 0이 되면 객체가 메모리에서 해제됩니다.
  * 간단하지만 space oeverhead, execution overhead가 존재하며, 객체가 스스로를 참조할 경우 이 방식이 적용되기 어렵습니다.
  * 이를 해결하는것이 trace-based 방식의 generational garbagage collection 방법입니다.
  * 해당 관리 방법은 모든 객체는 빨리 사라진다라는 기조로 generation을 관리하는 리스트와 threshold를 사용해 유지하고 버릴 객체를 관리합니다.
  * 참고
    * [trace-based 자세한 사항](https://blog.winterjung.dev/2018/02/18/python-gc)
    
* 힙 메모리, 스택 메모리의 차이점은 무엇인가요? 파이썬의 객체는 어느 영역에서 관리되나요?
  * 스택 메모리는 지역변수와 매개변수 저장 공간. 함수의 호출과 함께 할당되며 함수가 종료되면 해제
  * 힙 메모리는 사용자의 동적 할당으로 생성되는 공간으로 사용자가 공간의 크기를 직접 관리할 수 있으나, 파이썬은 메모리 memory management가 있어서 신경쓰지 않아도 됨
  * 보통 객체는 힙 메모리, 참조(변수)는 스택메모리에 저장
  - [ ] 힙 메모리/스택 메모리 + 메모리 안의 데이터 영역과 stack 영역의 차이?
  * 참고
    * [영상](https://www.youtube.com/watch?v=arxWaw-E8QQ)
* local, global variable의 차이점은 무엇인가요? 어느 영역에 저장되나요?
  * local variable은 함수 내부에서 생성된 변수로 함수 내부에서 사용 가능
  * global variable은 함수 외부에서 전역적으로 사용가능한 변수
  * global variable은 메모리안의 데이터 영역에, local variable은 stack에 저장 
