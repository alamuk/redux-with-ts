# Redux and typescripts 
A JS library for predictable and maintainable global state management: - 
[Redux-sites](https://redux.js.org/tutorials/essentials/part-1-overview-concepts)
- we set up a global data Storage 
- then we dispatch an actions to that Storage from any component we want.
- those actions trigger reducer function `not created by reducer hook` but instated manage by Redux. 
- and that will update the state. 
- we can also select the data from the Store inside our component. 
- see image in Public folder-how-redux-works



### Command line: 
- ~ npm i @reduxjs/toolkit
- ~ npm i react-redux
- import {configureStore} 

### ! = explanation mark in ts
- if anything shows null, but we know its exit, we can use `!` to show it is not null in typescripts 

### configureStore()
import {configureStore}
then call the configureStore to create the store. `store = configureStore()`
- it wants an object as an argument. 
- this object tells redux how the store should be setup. 
- Also, it needs a reducer which creates the store type of data it will manage in this reducer object. 


### slice
import {createSlice} 
then call back to create the slices `createSlice()`
- the overall store is a combination of multiple state slices that are grouped together make the store. e.g. `card-slice`
- this `createSlice()` take object as an argument. 
- in the `createSlice({})` object we need three things, 
1. name of the slice 
2. initialState 
3. reducers: {} object where we any method we want manipulated the state. 
`export const cardSlice = createSlice({
   name: 'card',
   initialState: initialState,
   reducers: {
   addToCard() {},
   removeFromCard() {},
   },
   });`


### reducer 
- in the reduced object, we provide all the slice - like a - key value pairs. 
- `card: cardSlice.reducer` in here we need to get the property of the reducer of card slice. 


### Provider component 
- this component helps to use the data from redux store. 
- it is wrap the components where those states will be used. or change. 
- it needs a store Prop to bring our store as a prop. 
- `<Provider store={store}>  </Provider>`
- it makes the redux store available to other components.

### how to use those actions in slice reducer. 
- we need to use a Redux action object in the `slice` file where the methods of action created. 
`export const { addToCard, removeFromCard } = cardSlice.actions` 
- And use those methods in the components where it is necessary by importing them through `useDispatch` hook
- `useDispatch` hook has dispatch function which needs with this,
`const dispath = useDispatch`
then use this in the local function.
`function handleAddtoCard(){ dispatch() }`



### Note: 
extra type safety when working with `thunks` -
action creators that perform some (async) action before the actual action is created & dispatch. 

### we need to create our own:
1. useDispatch hook
2. useSelector hook
``` 
to be clear: we DON'T need to re-create these hooks for each of the our store-Sclice. 
we only create one of them once -
hence we might also want to call them useAppDispatch and useAppSelector. 
```
we also need to import from redux: type TypedUseSelectorHook— for 
better typescript support once we start selecting data from the store. 


### export type RootState = ReturnType<typeof store.dispatch>;
ReturnType<> is part of the typescript. 