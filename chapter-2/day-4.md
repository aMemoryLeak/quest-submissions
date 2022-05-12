## Chapter 2 Day 4 Quest
1-3. Contract with Struct (Now with a dictionary and user defined functions!)
```cadence
pub contract Products {
    
    pub var myCameras: {Address: Camera}

    pub fun addCamera(
        manufacturer: String,
        model: String,
        year: UInt64,
        owner: Address,
        cameraTouchedThroughFence: Bool
        ){
            self.myCameras.insert(key: owner, Camera(
            manufacturer: manufacturer,
            model: model,
            year: year,
            owner: owner,
            cameraTouchedThroughFence: cameraTouchedThroughFence
            ))
        }

    pub struct Camera {
        pub var manufacturer: String
        pub var model: String
        pub var year: UInt64
        pub var owner: Address
        pub var cameraTouchedThroughFence: Bool

        init(
            manufacturer: String,
            model: String,
            year: UInt64,
            owner: Address,
            cameraTouchedThroughFence: Bool
        ){
            self.manufacturer = manufacturer
            self.model = model
            self.year = year
            self.owner = owner
            self.cameraTouchedThroughFence = cameraTouchedThroughFence
        }
    }

    init(){
        self.myCameras = {}
    }
}
```

4. Transaction
```cadence
import Products from 0x02

transaction (manufacturer: String, model: String, year: UInt64, owner: Address, cameraTouchedThroughFence: Bool){
    prepare(acct: AuthAccount){
    
    }

    execute{
        Products.addCamera(
            manufacturer: manufacturer,
            model: model,
            year: year,
            owner: owner,
            cameraTouchedThroughFence: cameraTouchedThroughFence)
        log("camera added")
    }
    
}
```

5. Script
```cadence
import Products from 0x02

pub fun main(): Products.Camera {
    return Products.myCameras[0x01]!
}
```
:arrow_backward: [Go Back](README.md)
