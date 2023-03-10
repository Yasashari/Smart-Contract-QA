# Smart-Contract-QA

#### MISSING ZERO ADDRESS CHECKS

#### NON-LIBRARY/INTERFACE FILES SHOULD USE FIXED COMPILER VERSIONS, NOT FLOATING ONES
    File: /src/ERC20/ERC20PermitPermissionedMint.sol
    2 pragma solidity ^0.8.0;
    
#### UNUSED IMPORTS
    import "openzeppelin-contracts/contracts/token/ERC20/ERC20.sol";
    
#### Don’t use extra parenthesis
    return (deposit(assets, receiver));
    return (mint(shares, receiver));
   
#### Missed space
    for (uint i = 0; i < minters_array.length; i++){

    File: /src/ERC20/ERC20PermitPermissionedMint.sol
    63 \n
    
    File: /src/frxETH.sol
    34 \n
    42 \n
    
#### EVENT IS MISSING INDEXED FIELDS
    Index event fields make the field more quickly accessible to off-chain tools that parse events. However, note that each index field costs extra gas 
    during emission, so it’s not necessarily best to index the maximum allowed per event (three fields). Each event should use three indexed fields if 
    there are three or more fields, and gas usage is not particularly of concern for the events in question. If there are fewer than three fields, 
    all of the fields should be indexed.
  
    205    event EmergencyEtherRecovered(uint256 amount);
    206    event EmergencyERC20Recovered(address tokenAddress, uint256 tokenAmount);

#### Use camel case for all functions, parameters and variables and snake case for constants

    26    address _timelock_address,
    53    function minter_burn_from(address b_address, uint256 b_amount) public onlyMinters {
    
          https://docs.soliditylang.org/en/v0.8.15/style-guide.html#order-of-functions
          
          https://www.notion.so/Solidity-Style-44daebebfbd645b0b9cbad7075ba42fe


#### Solidity natspec comments 
        https://docs.soliditylang.org/en/v0.8.16/natspec-format.html
 
#### NATSPEC IS INCOMPLETE
        /// @audit Missing: '@param bytes32'
        
       546:      function acceptRandomSeed(bytes32, uint256 randomness) external {
       
        /// @audit Missing: '@return'

        693:      function tokenURI(uint256 gobblerId) public view virtual override returns (string memory) {
        
#### NOT USING THE NAMED RETURN VARIABLES ANYWHERE IN THE FUNCTION IS CONFUSING

        File: src/utils/token/GobblersERC1155B.sol
        /// @audit owner
        55:       function ownerOf(uint256 id) public view virtual returns (address owner) {
        
#### STATE VARIABLE VISIBILITY IS NOT SET
        address immutable token;

#### INCORRECT COMMENTS
#### USE MODIFIER FOR BETTER READABILITY AND CODE REUSE
        https://code4rena.com/reports/2022-07-fractional#n-03-use-modifier-for-better-readability-and-code-reuse

#### Not to use Assembly
Even though assembly code was used for gas optimization, it reduces the readability (and future updatability) of the code.
https://code4rena.com/reports/2022-07-fractional#n-04-assembly-within-supplysol-and-transfersol

#### Code does not follow the checks-effects-interactions pattern
     Eventhough it doesn't have the opportunity for reentrancy here, the best coding practice is to follow the check-effects-interaction pattern

    There is 1 instance of this issue:

    File: src/FERC1155.sol

    85           _mint(_to, _id, _amount, _data);
    86:          totalSupply[_id] += _amount;
    
#### constants should be defined rather than using magic numbers

    https://github.com/code-423n4/2022-07-fractional/blob/e2c5a962a94106f9495eb96769d7f60f7d5b14c9/src/modules/Migration.sol#L199
    
    For more read....
        https://github.com/code-423n4/2022-07-fractional-findings/issues/506

        
