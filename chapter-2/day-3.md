

## Chapter 2 Day 3 Quest
1. script
```cadence
pub fun main(){
    var dbs: [String] = ["Gohan", "Trunks", "Gotrunks"]
    log(dbs)
}
```
2. script
```cadence
pub fun main(){
    var socials: {String: UInt64} = {"Facebook":6, "Instagram": 3, "Twitter":4,"YouTube":1, "Reddit":2, "LinkedIn" :5}
}
```
3. The force unwrap operator ```!``` works by "asking" a variable if it is initialized or ```nil```
  - Example:
  ```cadence
pub fun main(): Fix64 {
    var example: {String: Fix64} = {"pi":3.14159, "e": 2.71828, "root2":1.41421,"root3":1.73205, "i^2":-1.0}
    return example["i^2"]!
}
  ```
4. 
  - The type that the function is returning is not what the function expected to return.
  - The definition of main is expecting a ```String``` return type. Main is returning type ```String?``` 
    causing the mismatched types error.
  - On line 3, use the force unwrap operator ```!``` on the return statement to return the value for the key that was provided.

:arrow_backward: [Go Back](README.md)
