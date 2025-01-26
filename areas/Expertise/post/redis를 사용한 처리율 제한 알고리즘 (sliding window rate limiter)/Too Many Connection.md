Too Many Connection은 status code 429로 사용자가 지정된 시간 안에 너무 많은 request를 보냈음을 나타냅니다.

response에는 처리율 제한을 처리하는 조건을 명시해야하며 `Retry-After`를 포함하는 것을 권장합니다.

response 예시는 아래와 같습니다.
```
   HTTP/1.1 429 Too Many Requests
   Content-Type: text/html
   Retry-After: 3600

   <html>
      <head>
         <title>요청이 너무 많음</title>
      </head>
      <body>
         <h1>요청이 너무 많음</h1>
         <p>시간당 50개의 요청만 허용합니다. 잠시 후에 다시 시도해주세요.</p>
      </body>
   </html>
```

처리율 제한 알고리즘에 대해서는 선택적으로 사용할 수 있습니다.
1. 개별 api resource 마다 요청 수 제한
2. 전체 서버에 대해 요청 수 제한

> [!important]
> 429 status code를 가진 response는 캐시에 저장되면 안됩니다.

참고문서 
- https://datatracker.ietf.org/doc/html/rfc6585
