## Chapter 2 Day 4 Quest
1. Contract with Struct (Now 88% more organic!)
```cadence
pub contract Cameras {
    
    pub struct Camera {
        pub var manufacturer: String
        pub var model: String
        pub var year: UInt64
        pub var totalSupply: UInt64
        pub var cameraTouchedThroughFence: Bool

        pub fun changeManufacturer(newManufacturer: String){
            self.manufacturer = newManufacturer
        }

        pub fun touchCameraThroughTheFence(wasCameraTouched: Bool){
            self.cameraTouchedThroughFence = wasCameraTouched
        }

        init(
            manufacturer: String,
            model: String,
            year: UInt64,
            totalSupply: UInt64,
            cameraTouchedThroughFence: Bool
        ){
            self.manufacturer = manufacturer
            self.model = model
            self.year = year
            self.totalSupply = totalSupply
            self.cameraTouchedThroughFence = cameraTouchedThroughFence
        }
    }
}
```

:arrow_backward: [Go Back](README.md)
