
### Drafts of questions

<details>
    <summary>Python에서 sequence에 대해서 설명해주세요.</summary>
    * 파이썬에서 데이터 구조를 나눌 때, 저장되는 데이터의 순서를 고려하는 데이터 타입입니다. 리스트,튜플, 스트링이있습니다.
</details>


<details>
    <summary>Python 자료 구조에서 리스트와 튜플의 차이점을 설명해주세요.</summary>
    * 둘 데이터 타입 모두 순서는 존재하지만 리스트는 mutable, 튜플은 immutable합니다.
</details>

<details>
    <summary> mutable과 immutable에 대해서 설명해주세요</summary>
    * reference가 가리키는 메모리에 저장된 실제값을 바꿀 수 있다면 mutable. 수정하지 못한다면 immutable입니다.
</details>

<details>
    <summary> iterable과 iterator에 대해 설명해주세요.</summary>
    * iterable : 자료구조에 저장돼있는 요소값(멤버)를 하나씩 반환할 수 있는 객체로 for 문에 넣을 수 있는 모든 객체를 예로 들 수 있습니다.(e.g, 리스트, 셋 등등)
    * iterator : next()함수를 통해 데이터를 순차적으로 호출할 수 있는 객체입니다. 즉, 객체는 자신의 상태를 유지하면서(.?) 자신이 가지고 있는 마지막 값까지 필요할 때마다 하나씩 반환할 수 있는 객체입니다.
    * 꼭 읽어보면 좋을 [자료](https://shoark7.github.io/programming/python/iterable-iterator-generator-in-python)
    * 짧은 답변을 위해 만든 [자료](https://kkamikoon.tistory.com/entry/Python-Iterator%EB%9E%80-Python-Iterable%EC%9D%B4%EB%9E%80)
</details>

<details>
    <summary> iterator와 generator의 차이점은? 메모리 관점에서 설명한다면? </summary>
    * generator는 iterator의 특별 케이스입니다. 엄밀하게 말하자면 generator는 iterator지만 iterator는 generator가 아닙니다.
    * iterator로 동작할 수 있는 구현 방식이 다른데, 일단 generator를 구현할 시 클래스가 아니라 함수로 정의합니다.
    * iterator의 경우 `__iter__`와 `__next__` 메소드를 만들어야하지만, generator는 `yield` 키워드 인자로 구현할 수 있습니다.
</details>

<details>
    <summary> yield 키워드 설명과 generator와 관련되 설명해주세요. </summary>
    * yield 는 함수가 불리더라도 그 함수 내의 local variable 상태를 변환 시키지 않으면서 값을 반환해주는 것입니다.
    * 일반적으로 함수가 값을 반환할 때 return 키워드를 사용하는데, `yield`는 제너레이터를 반환하게 됩니다.
    * 일반적인 iterator 구현을 위한 `__iter__`와 `__next__` 메소드 대신 `yield`를 이용할 경우 아래와 같이 구현 가능합니다.
    ```
    from random import randint
    def random_number_generator(n):
        count = 0
        while count < n:
            yield randint(1, 100)
            count += 1
    g = random_number_generator(5)
    print(g)
    # <generator object random_number_generator at 0x7f0801e15e08>
    print(next(g))
    print(next(g))
    print(next(g))
    # 72
    # 90
    # 3
    ```
    * yield의 짧은 [정의](https://www.geeksforgeeks.org/python-yield-keyword/#:~:text=Yield%20is%20a%20keyword%20in,is%20what%20makes%20a%20generator.)
    * yield 전반적 [설명1](https://kkamikoon.tistory.com/90) , [설명2](https://tech.ssut.me/what-does-the-yield-keyword-do-in-python/)
    * 쉬운 yield 사용 예제 [설명](https://www.daleseo.com/python-yield/)
</details>

<details>
    <summary> labmda와 def 의 주된 차이점은 무엇인가요? </summary>
    * 두 가지 모두 파이썬에서 함수를 선언하는 방법입니다.
    * def는 이름을 갖는 함수고, lambda는 이름을 갖지 않는 익명의 함수입니다.
    * def는 명령문(statement, 소스코드에서 작동하는 줄) 이고, lambda는 표현식(expression,identifiers, literals, operator만으로 표현되고 나중에 어떤 값으로 표현)입니다.
    * lambda는 메모리 saving이 될 수 있고 특정 함수에서 용이하게 작동할 수 있지만, 긴 표현과 정밀한 기능 구현을 위해서는 `def` 를 이용하는 것이 좋습니다.
    * 추가 [참고](https://stackoverflow.com/questions/25327629/when-is-a-lambda-function-better-than-defining)
</details>

<details>
    <summary> reduce, map, filter function은 어떤 것인가요? </summary>
    * map은 iter의 원소를 하나씩 사전에 정의한 함수에 전달하고 결과값을 리스트에 담아 리턴합니다.
    * seq의 원소를 순서대로 사전에 정의한 함수에 누적하며 적용시킵니다.
    * seq에서 정의한 함수를 통해 걸러진 결과값만을 리스트에 넣어 반환합니다. 즉, 함수의 조건을 만족해 True인 값들만 반환합니다.
</details>

<details>
    <summary> pass by value, pass by reference, pass by object에 대해서 설명해주세요. 파이썬은 어떤 로직을 따르나요? </summary>
    * call by ~, pass by~ 는 함수가 호출될 때 전달되는 매개 변수가 어떻게 전달되는지를 설명하는 것입니다.
    * call by value: 값에 의한 호출로 변수에 할당된 값을 복사해서 함수의 인자로 넘기는 것입니다. 따라서 함수 내에서 해당 변수 값을 변경하면 함수 내에서만 적용됩니다.
    * call by reference: 참조에 의한 호출로 변수의 참조(메모리)를 함수의 인자로 넘기게 됩니다.(맞나?) 따라서 함수 내에서 해당 변수를 변경하면 함수 외부에서도 변경한 상태가 반영됩니다.
    * call by object: 파이썬은 어떤 객체가 함수에 넘겨지느냐에 따라 call by reference, call by value로 달라지기 때문에 call by object입니다.
        * 즉, immutable object 가 함수 argument로 넘어가면 call by value로 넘어가며
        * mutable object가 함수 argument로 넘어가면 call by reference로 넘어가고 실제 메모리가 가리키는 값을 바꿀 수 있습니다.
</details>

<details>
    <summary> shallow copy와 deepcopy에 대해서 설명해주세요. </summary>
    * 파이썬에서 새로운 변수에 값을 줄 수 있는 경우는 할당과 얕은 복사, 깊은 복사가 있습니다.
    * 할당 경우 단순 참조를 하며 사본을 만들지 않습니다. `b=a`로 할당 후 a의 변화는 b에 반영됩니다.
    * 얕은 복사는 객체의 주소값을 복사합니다. 즉, 객체는 새로 만들어지고, 새로 만들어진 객체를 가리킵니다. 하지만, 그 내부 요소는 원래 객체가 가리키는 요소를 참조합니다. 복사한 객체의 요소 값을 변경하거나 더해도 원래 객체에 영향을 주지 않습니다.
    * 깊은 복사는 새 복합 객체(한 객체가 다른 객체를 포함하는 것)를 만들고 원본 객체에 대한 복사를 재귀적으로 삽입합니다. 즉, 내부 객체들까지 모두 복사 2차원 3차원 리스트에 대해 원본 객체에 대한 참조를 다 만들어주는 것입니다.
    * 혹시 [참고](https://blockdmask.tistory.com/576)
</details>

<details>
    <summary> Variable scope은 무엇인가요? 파이썬의 관점에서 설명한다면? </summary>
    * 파이썬에서 변수가 값을 참조할 때 따르는 규칙입니다.(LEGB: local, enclosed function locals, global, built-in)
    * local : 함수 내부에서 생성된 변수
    * enclosed function locals : 내부 함수에서 자신의 외부 함수의 범위, 자유변수
    * global : 함수 외부에서 선언된 변수. 전역변수
    * built-in : 내장 함수 영역(import할 필요 없는 함수들. 파이썬 인터프린터 시작할 떄 자동으로 로드되는 print, len 같은 것들)
</details>

<details>
    <summary> Context manager는 무엇이고 어떤 때 사용하나요? </summary>
    * 한정된 하드웨어 소스를 사용하면서 데이터베이스 작업, file I/O 등 이용 시 할당된 자원이 제때 반환되지 않음으로 인한 성능 저하를 막기 위해 원하는 타이밍에 정확하게 리소스 할당 및 제공할 수 있도록 하는 것으로 함수나 클래스로 구현될 수 있습니다.
    * 추가 [참고](https://hello-cruiser.tistory.com/entry/Python-Context-Manager#:~:text=context%20manager%EB%9E%80%20with%20statement,%ED%96%89%EC%9C%84%EB%A1%9C%20%EB%B3%BC%20%EC%88%98%20%EC%9E%88%EC%8A%B5%EB%8B%88%EB%8B%A4.)
    * 추가 [참고2](https://www.geeksforgeeks.org/context-manager-in-python/)
</details>

<details>
    <summary> 일급함수란 무엇인가요?  </summary>
    * 일급 객체 : 변수 혹은 데이터 구조를 안에 담을 수 잇고, 매개변수로 전달할 수 있고, 리턴값으로 사용될 수 있는 객체의 성질을 만족하는 객체입니다.
    * 일급 함수 : 프로그래밍 언어가 함수를 일급 객체로 취급한다는 것입니다. 
    * 파이썬에서 함수는 일급 함수로서, 함ㅅ를 변수나 자료구조에 저장할 수 있고 함수의 매개변수에 다른 함수를 인수로 전달할 수 있고 함수의 반환값을 다른 함수에 전달할 수 있습니다.
    * [정의참고](https://tibetsandfox.tistory.com/8)
    * [정의 참고2](https://velog.io/@shchoice/First-class-Function%EC%9D%BC%EA%B8%89-%ED%95%A8%EC%88%98-Higher-order-Function%EA%B3%A0%EC%9C%84-%ED%95%A8%EC%88%98)
</details>

<details>
    <summary> 파이썬의 클로저는 무엇이고 어떤 때 사용하나요? </summary>
    * https://tibetsandfox.tistory.com/9#:~:text=%ED%81%B4%EB%A1%9C%EC%A0%80(Closure)%EB%9E%80%3F,%ED%95%98%EB%8A%94%20%ED%95%A8%EC%88%98%EB%A5%BC%20%EC%9D%98%EB%AF%B8%ED%95%A9%EB%8B%88%EB%8B%A4.
    * https://shoark7.github.io/programming/python/closure-in-python
    * https://schoolofweb.net/blog/posts/%ED%8C%8C%EC%9D%B4%EC%8D%AC-%ED%81%B4%EB%A1%9C%EC%A0%80-closure/
</details>

<details>
    <summary> 파이썬의 데코레이터는 무엇이고 어떤 때 사용하나요? </summary>
    * https://schoolofweb.net/blog/posts/%ED%8C%8C%EC%9D%B4%EC%8D%AC-%EB%8D%B0%EC%BD%94%EB%A0%88%EC%9D%B4%ED%84%B0-decorator/
    * 함수를 장식한다는 의미로서, 구체적으로는 함수를 수정하지 않은 상태에서 추가 기능을 구현할 때 사용합니다.
    * 사용법 : https://engineer-mole.tistory.com/181
</details>

<details>
    <summary> 언더스코어 사용처 </summary>
    * 무시하고 싶은 값, 특별한 네이밍(메소드, 변수), 인터프리터에서의 마지막값, 숫자 리터러의 자릿수를 구분할 때 사용합니다.
    * [참고](https://tibetsandfox.tistory.com/20)
</details>

<details>
    <summary> getter, setter, hasattr 은 어떤 것이죠? </summary>
    Answer
</details>