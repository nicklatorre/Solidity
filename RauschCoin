pragma solidity ^0.4.0;

contract RauschCoin {
    address public minter; 
    mapping (address => uint) public balance; 
    event Sent(address from, address to, uint amount);
    function RauschCoin() {
        minter = msg.sender;
    }
    function mint(address receiver, uint amount) {
        if (msg.sender != minter) return; 
        balance [receiver] += amount; 
    }
    function send(address receiver, uint amount) {
        if (balance[msg.sender] <  amount) return; 
        balance [msg.sender] -= amount; 
        balance [receiver] += amount; 
        Sent(msg.sender, receiver, amount); 
    }
}
