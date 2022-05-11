# Multisender_Dividends
Multisender and dividends functionality 

Smart Contract deployed on Kovan testnet:
https://kovan.etherscan.io/address/0xD84c73E9A874397C72293aB547ACDdC6Bae67703#code

NOTES!!!

*Before using the multisender function, user has to make the transfer from his account to the contract and send the whole sum of the tokens he wants to multisend.

*We have to remember about specifics of the security tokens and give all necessary allowances (whitelist, setTransferLimit etc)

READ CONTRACT

owner

Returns the address of the current owner

WRITE CONTRACT

function renounceOwnership()

Leaves the contract without owner. It will not be possible to call onlyOwner functions anymore. Can only be called by the current owner.
NOTE: Renouncing ownership will leave the contract without an owner, thereby removing any functionality that is only available to the owner.


function sendTokensToUsers( address token, address[] memory users, uint[] memory amounts)

token - address of the token, which you want to multisend 
users - the array of addresses of recipients  
amounts - the array of the amounts to send to recipients
Multisender function. Creates the data (list address-amount) and send it in one transaction from this contract.


function transferOwnership(address newOwner)

newOwner - the address of new owner of the contract
Sets the new owner of the contract.


function withdrawTokens(address token, uint256 amount)

token - the address of the token to send  
amount - the amount to send

Function allows to transfer amount of tokens from the contract to the msg.sender.
It can help to return the tokens from the contract to user.
