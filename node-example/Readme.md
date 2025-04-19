# Run a XVI Validator
## Setting up a node
1. Git clone https://github.com/XAILESFINANCE/XVI-Network.git

2. Copy source form node-example to root folder
```
cp -r XVI-Network/node-example/XVI  /root/
```
3. Create an Account

```
cd /root/XVI
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to node.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake XVI coin, all you should do is sending your XVI coin to the XVI Consensus contract address over the XVI network from the validator address.
    The XVI Consensus contract address: 0xCCdA55cbA46237dcb62B4c483FB326b1cECA0577
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to XVI and send the XVI coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /XVI/nodes/validator/keys/XVI/UTC--xxxx
    /XVI/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
