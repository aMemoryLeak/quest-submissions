## Chapter 3 Day 1 Quest

### Answers 
- Structs are diffrent from resources because:
  1. Structs can be copied therefore, uniqueness is not required or enforced.
  2. Structs are containers for data.
  3. Structs are not meant to be used to represent ownership of assets.

- It makes sense to use a resource instead of a struct in cases where 

- The ```create``` keyword is used to create a new resource.

- Resources cannot be created outside of contracts and result in an error in a script and transaction.

- The resource is of type ```Jacob```

- "ISpied"
```cadence
pub contract Test {


    pub resource Jacob {
        pub let rocks: Bool
        init() {
            self.rocks = true
        }
    }

    pub fun createJacob(): @Jacob { // there was 1 here
        let myJacob <- create Jacob() // there were 2 here
        return <- myJacob // there was 1 here
    }
}
```

:arrow_backward: [Go Back](README.md)
