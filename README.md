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

        
