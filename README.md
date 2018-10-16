# test-prism

## html

```html
<h2 id="look-ma-a-header">
  <a href="#look-ma-a-header">#</a>
  Look ma, a header!
</h2>
```

## JavaScript & JSX

```jsx
// a quick example

const { Provider, Consumer } = createContext('red')

const Blue = () => (
  <Provider value='blue'>
    <Consumer>{color => <h1>{color}</h1>}</Consumer>
  </Provider>
)

const Red = () => (
  <Consumer>{color => <h1>{color}</h1>}</Consumer>
)
```

## React

```jsx
// src/components/Chat.js

class Chat extends Component {

  // ...

  render() {
    const { currentMessage, messages } = this.state;
    const { updateCurrentMessage, add } = this

    return (
      <div>
        <h1>Chatroom</h1>
        <Messages messages={messages} />
        <Input 
          value={currentMessage} 
          onChange={updateCurrentMessage} 
        />
        <Button onClick={add} />
      </div>
    )
  }
}
```

```jsx
import { Form } from 'semantic-ui-react'

const Usage = () => (
  <Form>
    <Form.Group>
      <Form.Input />
      <Form.Select />
      <Form.Button />
    </Form.Group>
  </Form>
)
```

## CSS

```css
.filter {

  /* define structure */

  width: 500px;
  height: 200px;
  border-radius: 100px;
  background: #373b56;



  /* allows for absolute positioning of 
     the .filter__switch element */

  position: relative;



  /* flex styles to align .filter__item elements */

  display: flex;
  justify-content: space-between;
  align-items: center;

}


.filter__item {

  width: 33.33%;
  z-index: 2;

}


.filter__switch {

  /* define structure */

  height: calc(100% - 10px);
  width: calc(33.33% - 10px);
  border-radius: 100px;
  background: #5a6be8;

  

  /* absolute positioning provides
     the ability to place the switch wherever
     we want it */

  position: absolute;
  top: 5px;
  left: 5px;

}
```
