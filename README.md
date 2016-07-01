# React Komposer Specs

## Installation

```
npm i --save react-komposer-specs
```

## Full APIs

### `getContext`

```
import { getContext } from 'react-komposer-plus';
import { PropTypes } from 'react';

const ComposedClock = getContext({
  time: PropTypes.string,
})(Clock);
```

### `withHandlers`

```
import { withHandlers } from 'react-komposer-plus';

const Clock = ({ handleClick }) => (
  <button onClick={handleClick}>Clock</button>
);

const ComposedClock = withHandlers({
  handleClick: (props, event) {
    console.log(props);
    console.log(event);
  },
})(Clock);
```

### `withState`

```
import { withState } from 'react-komposer-plus';

const Counter = ({ state }) => (
  <div>{state.counter}</div>  // displays 1
);

const ComposedCounter = withState({
  counter: 1,
})(Counter);
```

### `withLifecycle`

```
import { withLifecycle } from 'react-komposer-plus';

const ComposedCounter = withLifecycle({
  componentWillMount() {
    console.log('component will mount');
  },
  componentDidMount() {
    console.log('component mounted');
  },
})(Counter);
```
