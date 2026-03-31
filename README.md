# Token-Sale-ICO-Mini-
Token Sale (ICO Mini)
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/IERC20.sol";

contract TokenSale {
    IERC20 public token;
    uint256 public rate = 1000; // 1 ETH = 1000 tokens

    constructor(address _token) {
        token = IERC20(_token);
    }

    function buy() public payable {
        uint256 amount = msg.value * rate;
        token.transfer(msg.sender, amount);
    }
}
