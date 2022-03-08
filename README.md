# pseudorandom.sol

```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >0.8.0;

contract Pseudorandom {

   /**
   * generates a pseudorandom number
   * @return a pseudorandom value
   */
  function random() public view returns (uint256) {
    // require(msg.sender == tx.origin, "no smart contracts allowed");
    return uint256(keccak256(abi.encodePacked(
      tx.origin,
      blockhash(block.number - 1),
      block.timestamp
    )));
  }

}
```
