# DSLA Submission
Repo with option factory that can be used for various DSLA's including  
Hedge against diminishing staking returns and yields
Hedge against stablecoin and synthetic assets losing their peg


Main Contracts 

Option Factory (optionFactory.sol)
- This allows users to create call / put options with desired strike price + amount of collateral lock 
- creates contract following "OptionVaultSimple.sol" pattern -> this has collateral locked in escrow as needed if options are executed + can also allocated lock funds to a vault to earn yield
- mints buyerERC20.sol tokens (in derivatesPool.sol file) which are sold through sales contract (SaleContract.sol) holders of these tokens can exercise options
- by entering correct inputs DSLA's covering various risks can be created 
- Additionally to solve the problem of capital efficiency the contract which holds these funds in Escrow can deploy them to a vault for example a new stable coin USDX may want to sell users options allowing them to trade 1 USDX for 0.99 USDC in the future. When this option is created a certain amount of USDC would be locked in escrow. However if this coverage were to last say 3 months there is significant opportunity cost. The OptionVaultSimple.sol contract allows for the owner to deploy funds in escrow to a yield bearing vault i.e. a Yearn Vault while holders of the option can still execute a trade of 1 USDX to USDC at any time. 
