# 알고리즘 firstNonRepeatedCharacter
# Problem

임의의 문자열을 입력받아 문자열 내에서 한 번만 등장하는 문자를 리턴해야 합니다.


## 입력

- 인자 1 : str 
  -  string 타입의 공백이 없는 문자열


## 출력

- string 타입을 리턴해야 합니다.


## 제한 사항

- 조건을 만족하는 문자 중 가장 먼저 위치한 문자를 리턴해야 합니다.
- 조건을 만족하는 문자가 없는 경우, null을 리턴해야 합니다.

## 입출력 예시

![carbon (23)](https://user-images.githubusercontent.com/67893516/97958582-d3efd980-1df0-11eb-9179-9cec4505db8f.png)

# 해결 방법

객체를 하나 선언하고, str.length만큼 포문으로 순회한다

이때 선언한 객체의 prop으로 str[i]를 넣어주고, str[i]가 있을때마다  ++ 해준다

예를 들어 str이 aab라면 이런 구조이다

```jsx
let count = {
  a : 2  //a가 2번 들어오기 때문에 ++가 두번 된다 그래서 2
  b : 1 //b가 1번 들어오기 때문에 ++ 되서 1
}
```

다시 for문으로 str.length 만큼 순회하며 선언한 객체의 prop str[i]의 value가 1이라면

1개 밖에 없는 단어이기 때문에 해당 단어를 리턴

나머지 경우에는 null을 리턴해준다.

# 코드 구현
![carbon (25)](https://user-images.githubusercontent.com/67893516/97958586-d5210680-1df0-11eb-824b-c31fba48d6b9.png)
