## 基础 
``` javascript
const a = <p>a</p>
const b = <p>b</b>
// render 需要return null
const warnDemo = ({warn}) => {
  if (!warn) {
    return null
  }
  return <p>warning</p>
}
class Demo extend React.Component {
  constructor(props) {
    super(props)
    this.name = props.name 
    this.state = {
      tickets: props.tickets || [{id: 1, name: '111'}, {id: 2, name: '222'}]
    }
  }
  fn = (...params, e) => {
    e.stopDefault()
  }
  render() {
    const tickets = this.state.tickets
    return (
      <div>
        <a onClick={e => this.fn('a', 'b', e)}>demo</a>
        <p onClick={this.fn.bind(this, 'a', 'b')}>demo</p>
        {this.name ? a : b}
        {this.name && a}
        <ul>
          {tickets.map(item => (
            <li key={item.id}>{item.name}</li>
          ))}
        </ul>
      </div>
    )
  }
}
// 对checkout, a标签之类 event.stopDefault()
// 阻止事件传播 event.stopPropagation()
```

``` javascript
// 受控组件, <input>, <textarea>, <select>
// 非受控组件, <input type="file">
class CustomInput extend React.Component {
  constructor(props) {
    super(props)
    this.ref = React.createRef()
  }
  
  focusInput = () => {
    this.ref.current.focus()
  }

  render() {
    return (
      <div>
        <input ref={this.ref}/>
        <button onClick={this.focusInput}>focus input</button>
      </div>
    )
  }
}
```

ref -> this.ref = React.createRef() -> this.ref.current.focus

context -> const Context = React.createContent(defaultValue) 
-> const { Provider }= Context
1. static contextType = ThemeContext; -> this.context
2. const { Consumer } = Context -> <Consumer>{value => </>}</Consumer>