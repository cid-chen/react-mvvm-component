![React 17‑19 Support](https://img.shields.io/badge/React%20Support-17%E2%80%9319-blue)
![bundlephobia](https://img.shields.io/bundlephobia/min/@gratefuljs/react-mvvm-component)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE.txt)

# react-mvvm-component v1.2.0

React is a library, not a state manager. That’s why `"React MVVM Component"` comes in.

Frustrated with complex local state flow or debugging hooks and effects?
<br/>
<br/>

**React MVVM Component = React Function Component + MVVM Options API**
<br/>
<br/>

Using this new hook plugin, you can manage **"in-component state"** more clearly and intuitively.

`Lightweight 6KB`, `supports React 17–19` and `the essence of Function Components remains unchanged`.

**Seamlessly compatible with native components, existing projects and React ecosystem !**


## Live Demo

- <a href="https://reactmvvm.org" target="_blank" rel="noopener">MVVM Component Overview</a>

- <a href="https://reactmvvm.org/event/v1/en" target="_blank" rel="noopener">MVVM Component Basic Usage</a>

- <a href="https://reactmvvm.org/render/v1/en" target="_blank" rel="noopener">If / Loop with JSX</a>

- <a href="https://reactmvvm.org/lifecycle/v1/en" target="_blank" rel="noopener">Well-defined Lifecycle</a>

- <a href="https://reactmvvm.org/watch/v1/en" target="_blank" rel="noopener">Data Watch</a>

- <a href="https://reactmvvm.org/filecomponent/v1/en" target="_blank" rel="noopener">Single-File Componont, SFC module</a>
<br/><br/>

## Live Demo (zh-TW)

- <a href="https://reactmvvm.org/overview/v1/tw" target="_blank" rel="noopener">MVVM 元件簡介</a>

- <a href="https://reactmvvm.org/event/v1/tw" target="_blank" rel="noopener">MVVM 元件使用案例</a>

- <a href="https://reactmvvm.org/render/v1/tw" target="_blank" rel="noopener">JSX 內的 If / Loop 判斷</a>

- <a href="https://reactmvvm.org/lifecycle/v1/tw" target="_blank" rel="noopener">明確的元件生命週期</a>

- <a href="https://reactmvvm.org/watch/v1/tw" target="_blank" rel="noopener">Data Watch 監聽器</a>

- <a href="https://reactmvvm.org/filecomponent/v1/tw" target="_blank" rel="noopener">Single-File Componont, SFC 模組化</a>
<br/><br/>


## MVVM component is still a React function component !

MVVM component is not intended to replace existing tools, but rather to **extend their functionality** with a complementary architectural pattern that may be more suitable in certain scenarios.

Therefore, the MVVM component is **still a function component, so you can use it directly in your existing project**.

It works seamlessly with other function components, please refer to demo: [Entitly](https://reactmvvm.org/entitly/v1/en), [Parent-Child](https://reactmvvm.org/methodapi/v1/en), and [Example8_1's original syntax](https://reactmvvm.org/lifecycle/v1/en) for more information.
<br/><br/>

## Installation

```
npm install @gratefuljs/react-mvvm-component
```

or

```
pnpm install @gratefuljs/react-mvvm-component
```

## Basic Example

Built on React, this plugin is easy to set up — just plug it into your project and enjoy the extended functionality:

```js
import ReactDOM from 'react-dom/client';
import React from 'react';
import { useRespectVue } from '@gratefuljs/react-mvvm-component';
 
const App = ()=>{ // The MVVM component is still a React function component
  
  const [MVVMComponent, VMmethodsAPI] = useRespectVue(React, {
    view : ({$VM, methods, refDOM}) => (
      <div>
        <p>Count: { $VM('count') }</p>
 
        <button onClick={methods.plus}>+</button>
        &nbsp;
        <button onClick={methods.minus}>-</button>
      </div>),
    methods : ({$VM, getMethods, memoBox, $DOM, nextTick}) => ({
      plus : function(){
 
        const cnt = $VM('count');
 
        cnt.val( cnt.now()+1 );
      },
      minus : function(){
 
        const cnt = $VM('count');
 
        cnt.val( cnt.now()-1 );
      },
    }),
    data : {
      count: 0,
    },
  });
 
  return (<>{MVVMComponent}</>);
};
 
 
const root = ReactDOM.createRoot(document.getElementById('app'));
root.render(<React.StrictMode>
    <App />
</React.StrictMode>);
```

## Bug Report 

If you discover a bug or security vulnerability, please report it by opening an issue or contacting us directly.  
Your help in improving this project is greatly appreciated!

If possible, please include a detailed description of the error along with screenshots or screen recordings.
It would also be very helpful if you can provide a reproducible example using CodePen, JSFiddle, JSBin, or similar tools.
Thank you.

[Email](mailto:cid.chen.mail@gmail.com)

[X(Twitter)](https://x.com/cid_chen)

No other contact methods are available apart from those listed above.
<br/><br/>

## Change Log

[CHANGELOG.md](CHANGELOG.md)
<br/><br/>

## License

This project is partially open-source. It is free to use and can be used for commercial purposes.

For more details, please refer to the licensing terms below.

[Apache 2.0 (check this out)](LICENSE.txt)
<br/><br/>

If you find this package helpful in your React projects,

please consider supporting it by making a donation <a href="https://ko-fi.com/O4O21IE7IA"><img style="border: 0px none; height: 34px;" src="https://storage.ko-fi.com/cdn/kofi6.png?v=6" alt="Buy Me a Coffee at ko-fi.com" height="34" border="0"></a> or giving it a star ⭐️. 

Your support helps keep the project going. Thank you!
