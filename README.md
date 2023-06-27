# ERC-20_simple_contract
Replace the symbol and name with your own:
62 symbol = "QKC";

63 name = "Name";

set the decimal (value in which tokens can be divided, 0to8 decimal units can be used) and establish a total supply value as you wish:

64 decimals = 2;
65 _totalSupply = 100000;

Please change YOUR_METAMASK_WALLET_ADDRESS to your own wallet address (same wallet you specified to obtain test currency):

66 balances[YOUR_METAMASK_WALLET_ADDRESS] = _totalSupply;

67 emit Transfer(address(0), YOUR_METAMASK_WALLET_ADDRESS, _totalSupply);

Note: The total supply value must have additional trailing zeros as specified by the decimals field. For example, the decimals value in this contract is 2 and we need a total supply of 1000 tokens, so we’ll have to set the total supply variable to 100000 (simply because it won’t allow a decimal point).

Explanation of the code above:

Line 1: Declaring the solidity version

Line 3-4: Calling the Safe Math interface to use math functions in our contract.

Line 29-41: Calling the ERC-20 Interface to implement its functions.

Line 44-48: A Contract function to receive approval and execute a function in one call.

Line 52-56: Starting our QKCToken contract, creating a variable symbol of string type to hold our token’s symbol, a variable name of string type to hold our token’s name, variable decimals of unsigned integer type to hold the decimal value for the token division.

Line 58-59: Creating two mapping functions that will grant users the ability to spend these tokens.

Line 61-68: Initializing the constructor, setting symbol, name, decimals, and total supply value for our token. Declaring the total supply of the token to be equal to your wallet’s balance for this token.

Line 70-72: Function totalSupply which will govern the total supply of our token.

Line 74-76: Function balanceOf which will check the balance of a wallet address.

Line 78-83: Function transfer which will execute the transfer of tokens from the total supply to users.

Line 85-89: Function approve which will check if the total supply has the amount of token which needs to be allocated to a user.

Line 91-97: Function transferFrom which will facilitate the transfer of token between users.

Line 99-101: Function allowance which will check if a user has enough balance to perform the transfer to another user.

Line 103-108: Function approveAndCall which executes the transactions of buying and spending of tokens.

Line 110-112: Fallback function to prevent accounts from directly sending ETH to the contract, this prevents the users from spending gas on transactions in which they forget to mention the function name.

Compile the smart-contract and deploy it using injected Web3 (make sure to select Ropsten testnet on Metamask before compiling the contract). Approve the transaction from metamask.
