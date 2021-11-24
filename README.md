# DojimaDao
Repo for Token + Treasury Maintenance 

Main Contracts 

Option Factory (optionFactory.sol)
- This allows users to create call / put options with desired strike price + amount of collateral lock 
- creates contract following "OptionVaultSimple.sol" pattern -> this has collateral locked in escrow as needed if options are executed + can also allocated lock funds to a vault to earn yield
- mints buyerERC20.sol tokens (in derivatesPool.sol file) which are sold through sales contract (SaleContract.sol) holders of these tokens can exercise options

Lend Factory (lendFactory.sol)
- Allows users to lock collateral to create p2p lending contract which anyone can choose to borrow to specificies terms of loan etc

lendNFT (lendNFT.sol)
- abilitiy to create loan using NFT as collateral (also will be pointed to by lendFactoryNFT.sol) for now only using IERC721 

Treasury 
(lots to do but theoretically will own liquidity and can offer call / put options, collect fees from above contracts + can deploy ttreasury funds to vaults to earn yield)
