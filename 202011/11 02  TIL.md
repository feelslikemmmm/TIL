# 알고리즘 isSubsetOf
# Problem

두 개의 배열(base, sample)을 입력받아 sample이 base의 부분집합인지 여부를 리턴해야 합니다.

## 입력

- 인자 1 : base
  -  number 타입을 요소로 갖는 임의의 배열 (base.length <= 100 )
- 인자 2 : sample
   - number 타입을 요소로 갖는 임의의 배열 (sample.length <= 100 )


## 출력

- boolean 타입을 리턴해야 합니다.


## 제한 사항

- base, sample 내에 중복되는 요소는 없다고 가정합니다.

## 입출력 예시

![carbon (26)](https://user-images.githubusercontent.com/67893516/97959322-765c8c80-1df2-11eb-9f2d-be9d0144fce9.png)

# 해결 방법

배열의 every method를 이용해서 간단하게 풀었다

every 함수는 배열의 모든 요소가 callbackFunction 에서 true를 리턴해야 true를 리턴,

하나라도 false가 떨어지면 false를 리턴한다.




# 코드 구현
![carbon (27)](https://user-images.githubusercontent.com/67893516/97959324-76f52300-1df2-11eb-96df-787c19369efc.png)