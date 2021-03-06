# provideStore
### signature: `provideStore(reducer: any, initialState?: any)`

`provideStore` is to be invoked during bootstrap, configuring and returning an array of providers for Store related services.

#### Arguments

1. `reducer : ActionReducer | [key:string]: ActionReducer` - Reducer or map of reducer functions. If multiple reducers are supplied reducers are 
automatically combined to create root reducer.

2. `initialState? : any` : Initial state for given reducer(s). This can be useful if supplying initial state from another service, 
or when using store in universal applications.

#### Returns
([*`Provider[]`*](store.md)): Provider[] registering Store and related services

#### Example
```ts
import { bootstrap } from '@angular/platform-browser-dynamic';
import { provideStore } from '@ngrx/store';
import { App } from './myapp';
import { counterReducer } from './counter';

bootstrap(App, [
	provideStore({ counter: counterReducer })
]);
```

> :file_folder: [https://github.com/ngrx/store/blob/master/src/ng2.ts](https://github.com/ngrx/store/blob/master/src/ng2.ts)