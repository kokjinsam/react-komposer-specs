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

const Counter = ({
  state,
  setState,
}) => (
  <div>
    <span>{state.counter}</span>  // displays 1
    <button onClick={() => setState({ counter: state.counter + 1 })}>+ 1</button>
  </div>
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
