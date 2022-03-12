
### Additional questions


<details>
    <summary>저장되는 데이터의 순서를 고려하지 않는 데이터 타입은 어떤 것이 있나요?</summary>
    * mapping 방식의 dictionary
    * 집합을 표현하는 set
    * 직접 데이터를 표현하는 int, float 등
</details>

<details>
    <summary>dictionary의 원리는 무엇이죠?(hashing). Hashing을 간단하게 구현해주세요</summary>
</details>

<details>
    <summary> mutable과 immutable한 데이터 타입에 대한 예를 들어주세요.</summary>

</details>

<details>
    <summary> python 에서 a = 1로 정수형을 선언했습니다. 정수형은 immutable임에도 불구하고 a += 1 로 할 경우 a 변수는 2를 가지게 됩니다.
    어떤 과정이 발생하는건지 설명해주세요. </summary>

</details>

<details>
    <summary> iterator 프로토콜이 어떤 것인가요? </summary>
    * 참고 : https://shoark7.github.io/programming/python/iterable-iterator-generator-in-python
</details>

<details>
    <summary> custom iterable과 iterator를 만들고 싶습니다. 어떤 메소드가 필요할까요? </summary>
    * 참고 : https://shoark7.github.io/programming/python/iterable-iterator-generator-in-python
</details>

<details>
    <summary> 파이썬에서 키워드나 식별자는 어떤 것인가요? </summary>
    * 참고 : https://www.delftstack.com/ko/tutorial/python-3-basic-tutorial/keywords-and-identifiers/#:~:text=%EB%8C%80%ED%95%B4%20%EC%84%A4%EB%AA%85%ED%95%A9%EB%8B%88%EB%8B%A4.-,%ED%8C%8C%EC%9D%B4%EC%8D%AC%20%ED%82%A4%EC%9B%8C%EB%93%9C,33%20%EA%B0%9C%EC%9D%98%20%ED%82%A4%EC%9B%8C%EB%93%9C%EA%B0%80%20%EC%9E%88%EC%8A%B5%EB%8B%88%EB%8B%A4.
    * 참고 : https://velog.io/@davkim1030/Python-101-2%EC%9E%A5.-%EC%98%88%EC%95%BD%EC%96%B4-%ED%82%A4%EC%9B%8C%EB%93%9C-%EB%B3%80%EC%88%98-%EC%83%81%EC%88%98-%EC%83%81%EC%88%98-%EB%A6%AC%ED%84%B0%EB%9F%B4
</details>


<details>
    <summary> readline과 readlines의 차이는 무엇인가요? </summary>
    * readline : 파일을 한줄씩 읽는다.
    * readlines : 파일을 한번에 읽어 리스트로 반환
</details>

<details>
    <summary> readline은 generator인가요? </summary>
    * Nope.
    * 참고 : https://jdridgeway.com/python-3-generators/#:~:text=Note%3A%20both%20readline(size),are%20used%20for%20example%20purposes.
</details>

<details>
    <summary> lazy implementation 이란 어떤 것인가요? </summary>
    * 참고 : https://www.delftstack.com/ko/tutorial/python-3-basic-tutorial/keywords-and-identifiers/#:~:text=%EB%8C%80%ED%95%B4%20%EC%84%A4%EB%AA%85%ED%95%A9%EB%8B%88%EB%8B%A4.-,%ED%8C%8C%EC%9D%B4%EC%8D%AC%20%ED%82%A4%EC%9B%8C%EB%93%9C,33%20%EA%B0%9C%EC%9D%98%20%ED%82%A4%EC%9B%8C%EB%93%9C%EA%B0%80%20%EC%9E%88%EC%8A%B5%EB%8B%88%EB%8B%A4.
    * 참고 : https://velog.io/@davkim1030/Python-101-2%EC%9E%A5.-%EC%98%88%EC%95%BD%EC%96%B4-%ED%82%A4%EC%9B%8C%EB%93%9C-%EB%B3%80%EC%88%98-%EC%83%81%EC%88%98-%EC%83%81%EC%88%98-%EB%A6%AC%ED%84%B0%EB%9F%B4
</details>

<details>
    <summary> 일반적으로 함수가 끝나는 상황은 어떤 경우가 있나요? </summary>
    * return을 만나거나
    * exception을 만나거나
    * 함수의 끝을 만나거나( return None의 형태가 되겠지)
</details>

<details>
    <summary> return과 yield의 차이는? </summary>
    * yield는 함수의 끝나고 다시 시작되는 control 기능을 합니다.
</details>

<details>
    <summary> 함수의 구성 요소는 어떤 것이 있고 어떤 차이가 있나요? </summary>
    - 매개변수(parameter) : 함수의 정의에서 전달받은 인수를 함수 내부로 전달하기 위해 사용하는 변수
    - 인수(argument) : 함수가 호출될 때 함수로 값을 전달해주는 값
</details>

<details>
    <summary> 함수의 구성 요소는 어떤 것이 있고 어떤 차이가 있나요? </summary>
    - 매개변수(parameter) : 함수의 정의에서 전달받은 인수를 함수 내부로 전달하기 위해 사용하는 변수
    - 인수(argument) : 함수가 호출될 때 함수로 값을 전달해주는 값
</details>

<details>
    <summary> 고위 함수는 무엇인가요? </summary>
    - 참고 : https://velog.io/@shchoice/First-class-Function%EC%9D%BC%EA%B8%89-%ED%95%A8%EC%88%98-Higher-order-Function%EA%B3%A0%EC%9C%84-%ED%95%A8%EC%88%98
</details>