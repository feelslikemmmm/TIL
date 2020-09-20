async와 defer의 차이점
---

- **head tag 안에 script  tag 작성하는 방법**

```jsx
<!DOCTYPE html>
<html lang="ko">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>async vs defer</title>
    <script src="main.js"></script>
  </head>
  <body></body>
</html>

위와 같은 html 문서가있고 브라우저는 제일 위부터 순서대로 하나씩 해석해 나간다.

그래서 head안에 script를 포함하게 되면 브라우저가 문서를 읽다가

script태그를 다운받아야 한다고 이해하게 된다.

이럴때 다운받아야 하는 js파일이 크기가 매우 크다면 사용자가 웹사이트를 보는데

많은 시간이 소요가 된다. 그래서 좋은 방법이 아니다.
```

---

- **body tag 아래에 script tag 작성하는 방법**

```jsx
<!DOCTYPE html>
<html lang="ko">
  	<head>
    	<meta charset="UTF-8" />
    	<meta name="viewport" content="width=device-width, initial-			scale=1.0" />
    	<title>async vs defer</title>
  </head>
  <body>
    <div></div>
    <script src="main.js"></script>
  </body>
</html>

이 방법은 script태그를 body태그 끝부분에 작성해주는건데 html문서를 다 읽고

페이지가 로드되고나서 script태그를 해석하게 된다.

이 방법은 사용자가 웹문서를 빨리 볼 수 있다는 장점은 있지만 단점도 있다

단점은 만약에 웹사이트가 js에 굉장히 의존적인 아이라면 즉,

사용자가 의미있는 컨텐츠를 보기 위해서는 js를 이용해서 서버에 있는 데이터를 받아온다던지

DOM요소를 더 예쁘게 꾸며준다던지 그런식으로 동작하는 웹사이트라면

사용자가 정상적인 페이지를 보기 전 까지는 서버에서 Javascript를 받아오는 시간도 기다려야 하고

실행하는 시간도기다려야 하는 단점이 있다.
```

---

- **asyn라는 속성 값을 쓰는 방법**

    ```jsx
    <!DOCTYPE html>
    <html lang="ko">
     <head>
       <meta charset="UTF-8" />
       <meta name="viewport" content="width=device-width, initial-scale=1.0" />
       <title>async vs defer</title>
       <script asyn src="main.js"></script>
     </head>
     <body>
       <div></div>
     </body>
    </html>

    asyn는 booleen type의 속성값이기 때문에 선언하는 것 만으로도 

    true로 설정이 되어서 asyn 옵션을 사용할 수 있다.

    asyn을 사용하게 되면 브라우저가 html을 다운로드 받아서 parsing을 하다가

    asyn가 있는것을 보고 그러면 병렬로 js파일을 다운로드 받자! 라고 명령만 해놓고

    다시 parsing을 하다가 js파일이 다운로드가 완료가 되면 그때 parsing 하는것을

    멈추고 다운로드 된 js파일을 실행하게 된다.

    이렇게 실행을 다 하고 나서 나머지 html을 parsing하게 된다

    이렇게 하면 장단점이 무엇일까?

    body끝에 사용하는 것 보다는 fetching이 

    parsing하는 동안 병렬적으로 일어나기 때문에 다운로드 받는 시간을 절약할 수 있다

    하지만 자바스크립트가 html이 parsing되기도 전에 실행이 되기 때문에

    만약 js파일에서 쿼리셀렉터를 이용해서 dom요소를 조작한다면 조작하려는 시점에

    html이 우리가 원하는 요소가 아직 정의되어있지 않을수가 있다

    그래서 그 부분이 조금 위험할수도 있고 html을 parsing하는 동안에 언제든지

    js를 실행하기위해서 멈출 수 있기 때문에 사용자가 page를 보는데 시간이

    조금 더 걸릴 수 있는 단점이 있다.
    ```

    ---

- **defer를 사용하는 방법**

    ```jsx
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>async와 defer의 차이점</title>
        <script defer src="main.js"></script>
    </head>
    <body>
        <div></div>
    </body>
    </html>

    defer를 사용하게되면 브라우저가 parsing을 하다가 script defer가 있네? 그러면

    우리 얘를 다운로드 받자 라고 명령만 실행시켜 놓고 나머지 html을 끝까지

    parsing하게 된다 그리고 parsing이 끝나고 나서 다운로드 된 js를 실행하게 된다

    defer가 가장 좋은 옵션이다. html을 parsing하는 동안 필요한 js를 다 다운받아놓고

    html을 parsing해서 사용자에게 page를 보여주고 나서 js를 실행하기 때문이다
    ```
