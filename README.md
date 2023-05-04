# Smart Contract Readme

This is a smart contract written in Solidity programming language for a purchase agreement. It includes the following functions:

1. `confirmPurchase()`: This function is used by the buyer to confirm the purchase by sending 2 times the value of the product. It transitions the state from `Created` to `Locked`.

2. `confirmReceived()`: This function is used by the buyer to confirm that the product has been received. It transitions the state from `Locked` to `Release` and transfers the value of the product to the buyer.

3. `paySeller()`: This function is used by the seller to receive payment from the buyer. It transitions the state from `Release` to `Inactive` and transfers 3 times the value of the product to the seller.

4. `abort()`: This function is used by the seller to abort the purchase agreement. It transitions the state from `Created` to `Inactive` and returns the funds to the seller.

The contract includes three custom modifiers: 

1. `inState(State state_)`: checks whether the current state matches the expected state.

2. `onlyBuyer()`: checks whether the caller is the buyer.

3. `onlySeller()`: checks whether the caller is the seller.

The contract also includes three custom errors that can be raised by the modifiers: 

1. `InvalidState()`: This error is raised when the function is called at the wrong state.

2. `OnlyBuyer()`: This error is raised when the function is called by someone other than the buyer.

3. `OnlySeller()`: This error is raised when the function is called by someone other than the seller.

The license for this smart contract is GPL-3.0. This contract is compatible with Solidity version 0.8.11 and lower than 0.9.0.
