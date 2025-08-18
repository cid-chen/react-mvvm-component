# react-mvvm-component

An efficient plugin that brings **"modern MVVM architecture"** to React.

Lightweight 6KB, supports React 17–19, integrates seamlessly with legacy projects and existing components.

High readability and easy maintenance for building more elegant, stable applications.
<br/><br/>

## Live Demo

- <a href="https://reactmvvm.org" target="_blank" rel="noopener">Demo and Document, English</a>

- <a href="https://reactmvvm.org/overview/v1/tw" target="_blank" rel="noopener">Demo and Document, 中文</a>
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
 
const App = ()=>{
  
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

## License

This project is partially open-source. It is free to use and can be used for commercial purposes.

For more details, please refer to the licensing terms below.

[Apache 2.0 (check this out)](LICENSE)
