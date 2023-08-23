# Substrate Node Template

This serves as a working example of [rbac-pallet](https://github.com/ozgunozerk/substrate-node-rbac)

# Build:
`cargo build --release`

# Run:
`${path to target executable} --dev`
(this will start the node)

# FUN PART:
1. ensure your node is working fine
   example output:
   ```
    2021-11-03 15:32:14 Substrate Node
    2021-11-03 15:32:14 ✌️  version 3.0.0-monthly-2021-09+1-bf52814-x86_64-macos
    2021-11-03 15:32:14 ❤️  by Substrate DevHub <https://github.com/substrate-developer-hub>, 2017-2021
    2021-11-03 15:32:14 📋 Chain specification: My Custom Testnet
    2021-11-03 15:32:14 🏷 Node name: MyNode01
    2021-11-03 15:32:14 👤 Role: AUTHORITY
    2021-11-03 15:32:14 💾 Database: RocksDb at /tmp/node01/chains/local_testnet/db
    2021-11-03 15:32:14 ⛓  Native runtime: node-template-100 (node-template-1.tx1.au1)
    2021-11-03 15:32:15 🔨 Initializing Genesis block/state (state: 0x2bde…8f66, header-hash: 0x6c78…37de)
    2021-11-03 15:32:15 👴 Loading GRANDPA authority set from genesis on what appears to be first startup.
    2021-11-03 15:32:15 ⏱  Loaded block-time = 6s from block 0x6c78abc724f83285d1487ddcb1f948a2773cb38219c4674f84c727833be737de
    2021-11-03 15:32:15 Using default protocol ID "sup" because none is configured in the chain specs
    2021-11-03 15:32:15 🏷 Local node identity is: 12D3KooWLmrYDLoNTyTYtRdDyZLWDe1paxzxTw5RgjmHLfzW96SX
    2021-11-03 15:32:15 📦 Highest known block at #0
    2021-11-03 15:32:15 〽️ Prometheus exporter started at 127.0.0.1:9615
    2021-11-03 15:32:15 Listening for new connections on 127.0.0.1:9945.
    2021-11-03 15:32:20 💤 Idle (0 peers), best: #0 (0x6c78…37de), finalized #0 (0x6c78…37de), ⬇ 0 ⬆ 0
  ```
2. open a browser and go to this location: https://polkadot.js.org/apps/?rpc=ws://127.0.0.1:9944#/explorer (this is connecting to your local dev net)
3. go to `Developer` -> `Extrinsics`
4. select Bob as the account
5. try to `createAccessControl` (any values would do)
    1. should get an error for `AccessDenied`
6. select Alice as the account (she has the only one with permission)
7. grantAccess to Bob
    1. values should be
        1. AccessControl
        2. create_access_control
8. should get a success message
9. select Bob again
10. try to `createAccessControl` again, with any values
11. should succeed now 🥂
