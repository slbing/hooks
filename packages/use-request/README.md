# useRequest

Production-ready React Hook to manage asynchronous data.

**Core Characteristics**

* Auto-triggered request and Manually-triggered Request
* SWR(stale-while-revalidate)
* Cache / Preload
* Refresh On Window Focus
* Polling
* Debounce
* Throttle
* Concurrent Request
* Dependent Request
* Loading Delay
* Pagination
* Load more, data recovery and scroll position recovery
* ......

## Installing

Inside your React project directory, run the following:

yarn add @ahooksjs/use-request

```bash
yarn add @ahooksjs/use-request
```

Or with npm:

```bash
npm install @ahooksjs/use-request
```

## Example

```javascript
import useRequest from '@ahooksjs/use-request';

const { data, error, loading, run } = useRequest('/api/user');
```

## Documentation

https://ahooks.js.org/hooks/async

## kim更新

```js
//样例
const queryAction = useRequest<API.PageAiCustomerEnterpriseVo>(()=>queryEnterprise({...pageAble},{...searchCondition}),{refreshDeps:[pageAble,searchCondition],manual:true})
```

refreshDeps 与 manual 可以同时使用，不在互斥，设置manual在声明的时候不会自动制定，refreshDeps的state被set的时候能够正常出发请求，相当于用新的参数调用接口，同步引起页面渲染
