### Aggregated Answers

* Python에서 sequence에 대해서 설명해주세요.
    * 파이썬에서 데이터 구조를 나눌 때, 저장되는 **데이터의 순서를 고려**하는 데이터 타입입니다. 리스트,튜플, 스트링이있습니다.

* Python 자료 구조에서 리스트와 튜플의 차이점을 설명해주세요.
    * 공통점은 데이터의 순서가 존재하는 것입니다.
    * 차이점은 mutable, 튜플은 immutable한 것입니다.

* mutable과 immutable에 대해서 설명해주세요.
    * reference가 가리키는 메모리에 저장된 실제값을 바꿀 수 있다면 mutable. 수정하지 못한다면 immutable입니다.
    * mutable은 리스트, 딕셔너리, 셋이 있고 imutable은 int, str, 튜플이 있습니다.

* iterable과 iterator에 대해 설명해주세요.
    * iterable은 순회할 수 있는 모든 객체입니다. 쉬운 예로는 for 문에 넣을 수 있는 모든 객체로 리스트, 딕셔너리, 셋이 대표적입니다.
    * iterator는 상태를 유지하며 반환할 수 있는 마지막 값까지 원소를 필요할 때마다 하나씩 반환하는 객체이다.
    * 둘의 생성관계로는 iterable에 iter 함수를 적용했을 때 iterator가 반환되며, iterator는 next를 통해 한 요소씩 반환된다.
    
- [ ] iterator와 generator의 차이점은? 
    * generator는 iterator의 특별한 케이스입니다. iterator는 클래스로, generator는 `yield`를 사용한 함수로 구현 가능하며, generator는 iterable과 iterator의 기능을 모두 가지고 있다.
    * iterator는 마지막까지 반환하면 재사용할 수 없고 StopIteration 예외를 일으키지만 generator는 무한으로 데이터 생성이 가능합니다.(?표현이 맞나)
    * yield가 next 기능을 갖고 있는 것은 아님!(https://anandology.com/python-practice-book/iterators.html)
    * [여기](https://shoark7.github.io/programming/python/iterable-iterator-generator-in-python)의 5번째 section 참고
    * 추가 참고: https://medium.com/@er.26yashiagarwal/iterators-generators-and-list-comprehension-in-python-7ad314c7b919

- [ ] list comprehension을 사용할 때와 generator를 설명해주세요.
    * eager loading
    * lazy evaluation
    
* yield키워드 설명과 generator와 관련해 설명해주세요.
    * yield 는 함수가 불리더라도 그 함수 내의 local variable 상태를 변환 시키지 않으면서 값을 반환해주는 것입니다.
    * yield는 제너레이터를 반환하게 되는데, 이를 통해 일반적인 iterator 구현을 위한 `__iter__`와 `__next__` 메소드 대신 `yield`를 이용해 generator 구현 가능합니다.
  
- [ ] **Q.iterator 클래스도 상태를 기억할텐데 정확하게 어떻게 작동되는 것인지는 확인해봐야할 듯!**

* labmda와 def 의 주된 차이점은 무엇인가요?
    * def는 이름을 갖는 함수, lambda는 이름을 갖지 않는 익명의 함수이다.
    * def는 명령문(statement)이고, lambda는 표현식(expression)이다.
    * def는 재사용 가능, Lambda는 기능의 일회성 구현을 위해 사용가능하고 편리하다.(리스트, 딕셔너리에서 바로 로직 만들어서 넣기 가능)
    * def는 메모리 stack 메모리에 할당됩니다. 
    * 반면, lambda는 heap에 생성되고, 변수에 저장될 경우 증발하지 않지만, 함수의 인자값이나 함수 내부에서 사용될 경우 함수 종료 시 바로 메모리 영역에서 증발된다.
        * https://newbiecs.tistory.com/332
    
* reduce, map, filter function은 어떤 것인가요?
    * reduce: `iterable`의 각 요소를 왼쪽부터 오른쪽 방향으로 function을 적용하여 하나의 값으로 합쳐준다. ****reduce(function, iterable[, initializer])형태이다.****
    * map: `iterable`에 있는 모든 요소에 `function` 을 적용하여 그 결과를 반환한다. 수행한 결과는 map object로 반환되므로, 이를 list나 tuple로 바꾸는 작업이 필요하다. ****map(function, iterable, …) 형태이다.****
    * filter: `iterable`의 각 요소에 대해 `function`이 True를 반환하는 요소의 iterator라고 한다. 수행한 결과는 filter object로 반환되므로, 이를 list나 tuple로 바꾸는 작업이 필요하다. ****filter(function, iterable) 형태이다.****
   
* pass by value, pass by reference, pass by object에 대해서 설명. 파이썬은 어떤 로직을 따르는지? 
    * "call by", "pass by" 는 함수가 호출될 때 전달되는 매개 변수가 어떻게 전달되는지를 설명하는 것입니다. 
    * call by value: 값에 의한 호출로 변수에 할당된 값을 복사해서 함수의 인자로 넘기는 것입니다. 따라서 함수 내에서 해당 변수 값을 변경하면 함수 내에서만 적용됩니다.
    * call by reference: 참조에 의한 호출로 변수의 참조(메모리 주소)를 함수의 인자로 넘기게 됩니다.(맞나?) 따라서 함수 내에서 해당 변수를 변경하면 함수 외부에서도 변경한 상태가 반영됩니다.
    * call by object: 파이썬은 어떤 객체가 함수에 넘겨지느냐에 따라 call by reference, call by value로 달라지기 때문에 call by object입니다.
    - [ ] "pass by, call by~" 이 함수에 넘겨주는 때에만 한정되게 사용하는건지? 
        * https://codingdog.tistory.com/entry/call-by-value-%EA%B0%92%EC%9D%84-%EB%B3%B5%EC%82%AC%ED%95%9C%EB%8B%A4
    
* shallow copy와 deep copy에 대해서 설명해주세요.
    * 얕은 복사 : 리스트는 복사되어 새로운 객체가 만들어지지만 요소들은 같은 주소값을 공유한다.즉, 같다.
    * 갚은 복사 :  리스트는 복사되어 새로운 객체도 만들고, 각 객체에 대한 주소값도 변한다. 즉, 복합객체에 대해 모든 요소가 재귀적으로 복사된다.
    * 얕은 복사는 `[:]` 또는 `copy.copy` 로 가능하고, 깊은 복사는 `copy.deepcopy`로 가능하다.
    * 얕은 복사와 깊은 복사의 차이는 복합 객체일 때이다. (e.g, List(list)) 
    * 주소값을 '복사' 한다는 것이 같다는 것인지 다르다는 것인지 의미가 모호해서 같다, 다르다로 정리함!
    * slicing은 shallow copy : https://stackoverflow.com/questions/19068707/does-a-slicing-operation-give-me-a-deep-or-shallow-copy
    
* variable scope란 무엇인가. 파이썬의 관점에서 설명해주세요.
    * 파이썬에서 변수가 값을 참조할 때 따르는 규칙입니다.(LEGB: local, enclosed function locals, global, built-in) 
    * local : 함수 내부에서 생성된 변수 
    * enclosed function locals : 내부 함수에서 자신의 외부 함수의 범위, 자유변수 
    * global : 함수 외부에서 선언된 변수. 전역변수 
    * built-in : 내장 함수 영역
    
* Context manager란 무엇이고 어떤 때 사용?
    * 원하는 타이밍에 리소스를 할당 및 제공하고, 반환하는 역할 (자원의 낭비를 막을 수 있음)하는 것
    * 구현은 함수(decorator)나 클래스로 가능하다.
    ```python
    import contextlib
    @contextlib.contextmanager
    ```
    
* 일급 객체란 무엇인가요?
    * 일급 객체 : 변수 혹은 데이터 구조를 안에 담을 수 잇고, 매개변수로 전달할 수 있고, 리턴값으로 사용될 수 있는 객체의 성질을 만족하는 객체입니다. 
    * 파이썬에서 함수는 일급 객체이다.(함수를 데이터 다루듯이 다룰 수 있다는 뜻)
    
* 파이썬의 클로저는 무엇이고 어떤 때 사용하나요?
    * 내부 함수가 메모리에 존재하지 않는 경우에도 호출될 때 주변 환경을 기억하는 것이다.
    * 함수의 스코프를 지어놓음으로써 각 변수가 섞여서 불필요한 충돌을 방지할 수 있으며 사용 환경에 맞게 임의대로 내부구조를 조정할 수 있다.
    
* 파이썬의 데코레이터는 무엇이고 어떤 때 사용하나요?
    * 기존의 함수에 여러가지 기능을 추가하는 것입니다.
    * 로깅, 성능 테스트, 유효성 체크 등 공통 기능을 데코레이터로 만들어서 다른 함수와 조합하여 사용하기 용이합니다.
    
* 언더스코어 사용처는 무엇인가요?
    * 무시하고 싶은 값, 특별한 네이밍(메소드, 변수), 인터프리터에서의 마지막값, 숫자 리터러의 자릿수를 구분할 때 사용합니다. 
    
* getter, setter, hasattr은 어떤 것인가요?
    * 인스턴스 내부의 데이터에 안전하게 접근하기 위한 키워드입니다.
    - getter : 데이터를 읽어주는 메서드
    - setter : 데이터를 변경해주는 메서드
    - hasattr: 인스턴스 내부의 속성 존재를 확인