
## Chapter 2 Day 1 Quest
![image](https://user-images.githubusercontent.com/80992246/167930523-606628d1-51f4-4e02-9472-8bed87bd2ac9.png)

![image](https://user-images.githubusercontent.com/80992246/167930374-ce9d5e70-5c22-4f49-81fd-f360ed9e91ea.png)

## Chapter 2 Day 2 Quest
1. A script would not be able to call changeGreeting because that function is modifying the state of the blockchain.
   We need to call the function in a transaction.
2. AuthAccount is the account that will pay for the transaction. This is also the place where we have access to the
   authorizing users storage space. The execute statement does not have this level of access.
3. The ```prepare``` phase is where we can check to make sure we have everything we need from the account that is paying.
   For example, does the AuthAccount meet the prerequisites to complete the transaction. In the event of failure to meet
   these prerequisites, the transaction will fail with a transaction status that != 4, meaning the transaction was not 
   commited to the blockchain.
   The ```execute``` phase of the transaction is where the work to update the state of the blockchain actually happens.
   [source]: https://docs.onflow.org/fcl/reference/api/#transaction-statuses
4. 
Contract
```cadence
pub contract HelloWorld {

    //data
    pub var greeting: String
    pub var myNumber: Int

    //functions that interact with that data
    pub fun changeGreeting(newGreeting: String){
        self.greeting = newGreeting
    }

    pub fun updateMyNumber(newNumber: Int){
        self.myNumber = newNumber
    }

    init(){
        self.greeting = "Yo!"
        self.myNumber = 0
    }
}

```
Script
```cadence
import HelloWorld from 0x01

pub fun main(): Int{
    return HelloWorld.myNumber
}
```
Transaction
```cadence
import HelloWorld from 0x01

transaction(myNewNumber: Int){
    prepare(signer: AuthAccount){}
    
    execute{
        HelloWorld.updateMyNumber(newNumber: myNewNumber)
        log("myNumber was ")
    }
}
```
