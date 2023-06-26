# SmartContract_DutchAuction

This is a Solidity contract for a basic Dutch auction. A Dutch auction is a type of auction where the price starts high and decreases over time until someone places a bid.
The contract has several public state variables:
* reservePrice: the minimum price at which the item can be sold.
* numBlocksAuctionOpen: the number of blocks for which the auction will be open.
* offerPriceDecrement: the amount by which the offer price decreases each block.
* auctionCloseBlock: the block number at which the auction will close.
* sellerAccountAddr: the address of the seller’s account.
* auctionEnd: a boolean indicating whether or not the auction has ended.
* buyer: the address of the buyer.
The contract also has a constructor that takes in three arguments: _reservePrice, _numBlocksAuctionOpen, and _offerPriceDecrement. These values are used to initialize the corresponding state variables. The constructor also sets the startingBlock to the current block number, calculates the auctionCloseBlock, and sets the sellerAccountAddr and sellerAccount to the address of the account that deployed the contract.
The contract has a bid function that allows users to place bids. This function checks that the auction has not ended and that the current block number is less than auctionCloseBlock. It also checks that the value sent with the transaction is greater than or equal to the current bid price, as determined by calling the getCurrentBidPrice function. If these conditions are met, it calls the finalize function and returns true.
The getCurrentBidPrice function calculates and returns the current minimum bid price based on the current block number, reservePrice, numBlocksAuctionOpen, and offerPriceDecrement.
The finalize function transfers the value of the bid to the seller’s account, sets auctionEnd to true, and sets buyer to the address of the account that placed the winning bid.

Live Site : https://cold-lake-4291.on.fleek.co/frontend/build/
