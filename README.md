# test-prism

```javascript
document.querySelector('.filter').addEventListener('click', e => {
  e.stopPropagation()

  const el = e.target

  if (el.classList.contains('filter__item') && !el.classList.contains('filter__item--active')) {
    const filterItemData = el.getBoundingClientRect()
    const switchData = document.querySelector('.filter__switch').getBoundingClientRect()

    const midPoint = filterItemData.x + (filterItemData.width / 2)
    const newSwitchX = midPoint - (switchData.width / 2)

    const keyframes = [
      { transform: `translateX(${switchData.x}px)`},
      { transform: `translateX(${newSwitchX}px)`}
    ]
  }
})
```


## jsx

```jsx
import React from 'react'
import { Subscribe } from 'unstated'
import ColorContainer from '../containers/ColorContainer'
import { Outer, Inner, Button } from './styled'

const App = () => (
  <Subscribe to={[ColorContainer]}>
    {color => {
      const active = color.active()
      return (
        <Outer bg={active}>
          <Inner>
            <h1>{active}</h1>
            <Button onClick={color.make}>Another one!</Button>
          </Inner>
        </Outer>
      )
    }}
  </Subscribe>
)

export default App
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
