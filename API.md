# API 기능명세서

## API 프로토콜

- 요청
  요청은 메소드, 파라이터, 쿼리, 바디를 통해 구분됩니다.
  메소드: 요청 처리 방법을 구분합니다.
  파라미터: 요청 처리 위치를 선택합니다.
  쿼리: 요청 처리 옵션을 선택합니다.
  바디: 요청 처리 시 필요한 데이터를 담습니다. JSON 을 사용합니다.
  ```jsx
  async function APIRequest(method, body) {
    const res = await fetch(url, {
      method: method,
      headers: {
        "Content-Type": "application/json"
      }
      body
    }).catch((error) => {})
    const json = await res.json();
    return json;
  }
  ```
- 응답
  응답 바디는 JSON 으로 구성됩니다. 요청 처리 중 오류가 발생한 경우에는 `error` 필드가 추가되여 응답합니다. 응답 예시는 다음과 같습니다.
  - `200` 정상 처리
    ```jsx
    {
    	message: "OK",
    	data: {...}
    }
    ```
  - `404` 일반 오류
    ```jsx
    {
    	message: "존재하지 않는 무언가입니다.",
    	data: {},
    	error: {}
    }
    ```
  - `400` 요청 바디가 있는 오류 (요청 바디 값 관련 오류일 떄)
    ```jsx
    {
    	message: "이미 존재하는 이름입니다.",
    	data: {},
    	error: {
    		field: "name"
    	}
    }
    ```

## API 테이블

- `/fridge`
  - `/subpage`
    - `GET` 요청에 대한 설명
    - `POST` 또다른 설명
- `/recipies`
  - `/recommand`
    - `GET` 레시피 추천 받기
-

### `METHOD` `/test/test/test` 요청에 대한 설명

- 요청
  - 쿼리
    - page: 요청 페이지
  - 헤더
    ```jsx
    {
      Auth: 'asdsadasdad';
    }
    ```
  - 바디
    ```jsx
    {
      test: 'test';
      object: {
      }
    }
    ```
- 응답
  - `200` 성공
    - 바디
      ```jsx
      {
      	js object 형태로 잘 적기
      }
      ```
  - `400` 오류 토드에 맞는 오류 설명 적기
  - `403` 님 권한 없는거임
  - `404` 그냥 뭘 요청한거임 그런거 몰라요

### `GET` `/recipies/recommands` 레시피 추천 받기

- 요청
- 응답
  - `200` 성공
    - 바디
      ```jsx
      {
      	js object 형태로 잘 적기
      }
      ```
  - `400` 오류 토드에 맞는 오류 설명 적기
  - `403` 님 권한 없는거임
  - `404` 그냥 뭘 요청한거임 그런거 몰라요
