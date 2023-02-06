---
title: "정규식을 통한 문자 검출"  
excerpt: "문자열의 검사를 위해서는 정규식을 써야한다."


categories:
  - Javascript

tags:
  - Javascript,Text Control

last_modified_at: 2023-02-06
---

문자열의 검사를 위해서는 정규식을 써야한다.

- 일반적인 include 함수

```js
'abc'.include('a', 1);
//true
'abc'.include('a', 2);
//false
```

- inclde 함수는 활용성이 떨어짐  
그래서 아래의 정규식을 활용함

```js
/[a-z]/.test('aabbcc');
//a~z까지의 영문 소문자 검사
//true

/[a-zA-Z]/.test('aabbcc');
//모든 영문자 확인(대, 소)
//true

/[ㄱ-ㅎ가-힣]/.test('테스트');
//모든 한글 검사
//true

/[0-9]/.test('test');
//숫자 검사
//false

/\S/.test('test');
//입력된 값이 있는지 검사
//true

/^a/.test('test');
//a로 시작하는지 검사
//false

/a$/.test('test');
//a로 끝나는지 검사
//false

/a|b/.test('test');
//a or b 있는지 검사
//false
```

- 이메일 체크 정규식

```js
const regExp = /^[0-9a-zA-Z]([-_\.]?[0-9a-zA-Z])*@[0-9a-zA-Z]([-_\.]?[0-9a-zA-Z])*\.[a-zA-Z]{2,3}$/i;
//상용으로 쓰이는 정규식이라고 함
//너무 복잡한데?

const regExp = /\S+@\S+.\S+/
//일단은 이정도만...
```
