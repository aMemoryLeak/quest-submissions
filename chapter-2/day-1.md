## Chapter 2 Day 1 Quest

```cadence
pub contract JacobTucker{
  pub let is: String
  
  init(){
    self.is = "the best!"
  }
}
```

```cadence
import JacobTucker from 0x03

pub fun main(): String{
  return JacobTucker.is
}
```
:arrow_backward: [Go Back](README.md)
