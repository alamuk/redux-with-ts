# Redux and typescripts 
A JS library for predictable and maintainable global state management: - 
[Redux-sites](https://redux.js.org/tutorials/essentials/part-1-overview-concepts)
- we set up a global data Storage 
- then we dispatch an actions to that Storage from any component we want.
- those actions trigger reducer function `not created by reducer hook` but instated manage by Redux. 
- and that will update the state. 
- we can also select the data from the Store inside our component. 
- see image in Public folder-how-redux-works



### command line: 
- ~ npm i @reduxjs/toolkit
- ~ npm i react-redux

### ! = explanation mark in ts
- if anything shows null, but we know its exit, we can use `!` to show it is not null in typescripts 