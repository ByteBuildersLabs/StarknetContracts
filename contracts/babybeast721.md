# Guide to Compile, Declare, and Deploy BabyBeastNFT Contract  

This guide explains the steps required to compile, declare, and deploy the `BabyBeastNFT` contract on Starknet using the `sncast` tool.  

---

## Prerequisites  

Ensure the following dependencies are installed:  
- **Scarb**: Starknet's package manager and build system  
- **Starknet Foundry**: A testing and development tool for Starknet  
- **Move to the contracts directory**: `cd contracts/babybeast721`

---

## Steps  

### 1. Generate RPC URL  
Use the following RPC URL for the Starknet Sepolia testnet:  
`https://starknet-sepolia.g.alchemy.com/starknet/version/rpc/v0_7/cLCTETfGYLtswAlpQ-sbxOrmsy6sNW5w`

### 2. Create an Account  
Run the following command to create an account:  
```bash
sncast account create \
    --url https://starknet-sepolia.g.alchemy.com/starknet/version/rpc/v0_7/cLCTETfGYLtswAlpQ-sbxOrmsy6sNW5w \
    --name babybeastdeployer
```
Note: Before deploying the account, fund it with sepollia or mainet tokens.

### 3. Deploy the Account  
Deploy the created account using:  
```bash
sncast account deploy \
    --url https://starknet-sepolia.g.alchemy.com/starknet/version/rpc/v0_7/cLCTETfGYLtswAlpQ-sbxOrmsy6sNW5w \
    --name babybeastdeployer \
    --fee-token strk
```

### 4. Declare the Contract  
Declare the `BabyBeastNFT` contract:  
```bash
sncast --account babybeastdeployer \
    declare \
    --url https://starknet-sepolia.g.alchemy.com/starknet/version/rpc/v0_7/cLCTETfGYLtswAlpQ-sbxOrmsy6sNW5w \
    --contract-name BabyBeastNFT \
    --fee-token strk
```
Note: Copy the class hash and replace it in the next command.

### 5. Deploy the Contract  
Deploy the contract using its class hash:  
```bash
sncast \
    --account babybeastdeployer \
    deploy \
    --url https://starknet-sepolia.g.alchemy.com/starknet/version/rpc/v0_7/cLCTETfGYLtswAlpQ-sbxOrmsy6sNW5w \
    --class-hash 0x6e4615700e4481c8e5b5e32ebf6378c0a203fe24f6c0d87a06d2fab86fd3e28 \
    --fee-token strk
```

---

## Notes  

1. **Class Hash**: Ensure the provided class hash matches the one generated after declaring the contract.  
2. **Fee Token**: The `strk` token is used for transactions in the Sepolia testnet.  
3. **sncast Documentation**: For detailed information, refer to the [sncast repository](https://github.com/keep-starknet-strange/sncast).  

---

## Additional Resources  

- [Starknet Foundry Documentation](https://foundry-rs.github.io/starknet-foundry/index.html)  
- [Alchemy Starknet RPC Guide](https://www.alchemy.com/)  


### File Download
If you'd like, I can generate this as a `.md` file for you. Let me know!