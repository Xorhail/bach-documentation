---
id: bachredux-withselector
title: withSelector
---

Allows you to extract data from the Redux store state, using a selector function.

## Helper Signature

| Parameter    | Type             | Description                                                                                     |
| ------------ | ---------------- | ----------------------------------------------------------------------------------------------- |
| selectorName | string           | the name of the value in the props passed to the wrapped component                              |
| fn           | js function      | the function that returns the desired value from the store                                      |
| conditions   | array of strings | names of the properties on the props object react should restrict the firing of the function to |

## Example

```
import React from 'react';
import {compose} from '@truefit/bach';
import {withSelector} from '@truefit/bach-redux';

const WithSelector = ({todos}) => (
  <div>
    <h1>withSelector</h1>
    <ul>
      {todos.map(todo => (
        <li key={todo}>{todo}</li>
      ))}
    </ul>
  </div>
);

export default compose(
  withSelector('todos', (state, props) => state.features.bachRedux.todo),
)(WithSelector);
```

## React-Redux Hook

[useSelector](https://react-redux.js.org/next/api/hooks#useselector)