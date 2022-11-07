# *There is a react code examples* 

### how to createElement in class components:

``` js
import React from "react";

const Hello = () => {
    // return ( 
    //     <div className="dummyClass">
    //         <h1>Hello world</h1>
    //     </div>
    // )
    return React.createElement(
        'div',
        {id: 'hello', className: 'dummyClass'},
        React.createElement('h1', null, "Hello world")
    )
}
 
export default Hello;
```

<!-- ============ ----- ============ -->

### Binding Event Handlers

``` js 
import React, { Component } from "react";

export class Hello extends Component {
  constructor(props) {
    super(props)

    this.state = {
        message: "Hello"
    }

    this.clickHandler = this.clickHandler.bind(this)
  }

  clickHandler = () => {
    this.setState({
        message: 'Goodbye!'
    })
    console.log(this);
  }
  render() {
    return <div>
        <h1>{this.state.message}</h1>        
        {/* <button onClick={this.clickHandler.bind(this)}>Click</button> */}
        {/* <button onClick={() => this.clickHandler()}>Click</button> */}
        <button onClick={this.clickHandler}>Click</button>
    </div>;
  }
}

export default Hello;
```