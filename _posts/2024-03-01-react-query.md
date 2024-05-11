---
title: React-query
author: parklego
date: 2024-03-01
category: til
layout: post
---

## 환경설정

```jsx
import { QueryClient, QueryClientProvider } from "react-query";

const client = new QueryClient({
  defaultOptions: {},
});

ReactDOM.createRoot(document.getElementById("root")!).render(
  <React.StrictMode>
    <QueryClientProvider client={client}>
        <App />
    </QueryClientProvider>
  </React.StrictMode>
);

```

## useQuery

```jsx
const { data, isLoading, error } = useQuery(queryKey, queryFn, options);
```

- queryKey

  키값에 따라 데이터를 캐싱처리 한다.

  ```jsx
  // 문자열
  useQuery('todos', ...)

  // 배열
  useQuery(['todos'], ...)
  ```

- queryFn

  fetching 함수를 넘기면 된다.

  ```jsx
  useQuery(["todos"], () => somethingfetching() ));
  ```

## useInfiniteQuery

continue

---

도움되는 링크

https://github.com/ssi02014/react-query-tutorial
