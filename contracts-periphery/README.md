# Umbra periphery contracts

Smart contracts that integrate with [Umbra](../README.md), but are not part of the [core protocol contracts](../contracts-core/).

## Contracts

Below is a list of contracts contained in this package:

- `UmbraBatchSend`: Aggregate multiple `Umbra` sends into a single transaction.

## Development

This repo uses [Foundry](https://github.com/gakonst/foundry).

### How to use the DeployBatchSend Script

1. Inside `contracts-periphery` folder, run `cp .env.example .env` and fill out all fields.
2. In your terminal use command

- `cast nonce <Deployer's address> --rpc-url <URL>` to find your nonce.

4. Change `EXPECTED_NONCE` of `DeployBatchSend` script to match your nonce.
5. To make sure the script test passes, run

- `forge test --mc DeployBatchSendTest --sender <Deployer's address>`

6. Pass in the `private key` to dry run deploying the contract across the networks you've specified. You should see gas estimates for each network, otherwise there could be a mismatch between deployer's nonce and the specified expected nonce, or there's already code at the expected contract address.

- `forge script DeployBatchSend --private-key <Private Key> `

7. Execute the deploy by broadcasting the deploy transactions.

- `forge script DeployBatchSend --private-key <Private Key> --broadcast`
