# React hook to detect click or touch events

React hook `useClickAway()` that reacts to clicks outside the bound element, and calls the expression that is passed in when this event is detected.

Suppose you're working on a Modal component that renders a dialog box, and you wish to close the modal if the user clicks away this is the ideal scenario for `useClickAway()` custom hook.

## Installation

Using `npm`:

```bash
npm i use-click-away --save
```

[Check the live DEMO](https://reactmoviestore.netlify.app/).

## Usage

Import the hook:

```javascript
import { useClickAway } from "use-click-away";
```

### Full example

```
export default () => {
  const [modal, setModal] = React.useState(false);
  const clickRef = React.useRef("");

  useClickAway(clickRef, () => {
    setModal(false);
  });

  return (
    <div ref={clickRef} className="container">
      <button onClick={() => setModal(true)}>Show Modal</button>
      {modal && <Modal>Modal Content</Modal>}
    </div>
  );
}

```

## Specification

### `useClickAway()` input

- `clickRef: element` - The dom element to bind our hook.
- `callback: function` - The callback that runs after user click


## Built With

- [React](https://reactjs.org/) - A JavaScript library for building user interfaces

## License

MIT Licensed. Copyright (c) George Bardi 2020.
