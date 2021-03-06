---
id: bachrecompose-mapprops
title: mapProps
---

Allows you to transform the props from that point in the composition into a new map of props.

_Note: this can be a dangerous utility as it completely replaces the props object that has been built to this point. Consider that when writing your mapping logic_

## Helper Signature

| Parameter | Type        | Description                                                                            |
| --------- | ----------- | -------------------------------------------------------------------------------------- |
| fn        | js function | accepts a js object "props" and returns a js object to be used as "props" from then on |

## Example

```
import React from 'react';
import {compose} from '@truefit/bach';
import {mapProps} from '@truefit/bach-recompose';

const ChildContent = ({message}) => (
  <div>
    <h1>mapProps</h1>
    <h2>Message: {message}</h2>
  </div>
);

const Child = compose(
  mapProps(({note, ...props}) => ({message: note, ...props})),
)(ChildContent);

export default () => <Child note="Hello World" />;
```
