redux-extend-reducer
===============

Extend redux reducer with other reducers.

```
npm install --save redux-extend-reducer
```

## Example

```js

const init = { field: 1 }

const root = (prev = init, curr) => ({...prev, field: prev.field + curr})
const some = (prev = init, curr) => ({...prev, field: prev.field + curr})

const reducer = extendReducer(root, { some })

// state structure
const state = {
  field: 1,
  some: {
    field: 1,
  },
}

const next = reducer(state, 3)

// result
// { field: 4,
//   some: {
//     field: 4,
//   },
// }
```

## Why?

Sometimes we need to add some Redux reducer as a key to another core reducer. Also it fill uncovered with combineReducer and reduceReducers cases.
