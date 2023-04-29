Thin React.js wrapper for coil-lang

Example:

```
import {component, use_state} from "@coil-lang/react"

@component
fn SimpleCounter({initial_value}) {
  let value = use_state(initial_value)

  fn clear = value.set!(0)
  fn decrement = value.update!(_ - 1 #(Math.max(& 0)))
  fn increment = value.update!(_ + 1)

  return ~:div[
    ~:button{onClick: clear, children: "Clear"}
    ~:button{onClick: decrement, children: "-1"}
    ~:span["Value: " value]
    ~:button{onClick: increment, children: "+1"}
  ]
}
```
