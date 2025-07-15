# 오늘도 썩는 중 API 명세서

## 요청 방식

REST + JSON (in fetch)

```js
async function APIRequest(method, body) {
  const res = await fetch(url, {
    method: "",
    headers: {
      "Content-Type": "application/json"
    }
    body
  }).catch((error) => {})
  const json = await res.json();
  return json;
}
```

## API 테이블

- [`GET` /test/test]()

### `GET` /test/test

응답

```json
{
  "example": "test"
}
```
