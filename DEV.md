## 1. 初始化项目

```shell
$ npm install -g @graphprotocol/graph-cli

$ graph init easyfaucet-subgraph
```

> 注意：每次修改 `scheam.graphql` 和 abi 文件后都需要执行 `graph codegen` 命令重新生成代码。

## 2. 认证

```
$ graph auth 13af...e0de
```

## 3. 部署到不同的链

原理：执行 `graph build --network <chain_name>` 命令根据 `networks.json` 配置文件为不同的链生成特定的 `subgraph.yaml` 文件。

> 注意：只有 `dataSources[].netowrk` `dataSources[].source.address` `dataSources[].source.startBlock` 这 3 个属性会被自动更新，其他的内容需要手动维护!

#### 3.1 部署到 chapel

```
$ graph build --network chapel

$ graph deploy easyfaucet-bnbtestnet --network chapel
```

#### 3.2 部署到 sepolia

```
$ graph build --network sepolia

$ graph deploy easyfaucet-sepolia --network sepolia
```
