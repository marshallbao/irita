<!--
order: 1
-->

# 权限管理

IRITA 管理员可以通过控制台进行链的管理操作，主要管理功能有：

- [权限管理](#权限管理)
  - [assign-roles](#assign-roles)
    - [增加权限示例](#增加权限示例)
  - [unassign-roles](#unassign-roles)
    - [移除权限示例](#移除权限示例)
  - [block-account](#block-account)
    - [加入黑名单示例](#加入黑名单示例)
  - [unblock-account](#unblock-account)
    - [移出黑名单示例](#移出黑名单示例)
  - [block-contract](#block-contract)
    - [加入黑名单示例](#合约加入黑名单示例)
  - [unblock-contract](#unblock-contract)
    - [移出黑名单示例](#合约移出黑名单示例)

## assign-roles

IRITA 管理员可以为指定账户增加相应的操作权限。

```bash
irita tx perm assign-roles [address] [roles]
```

**参数：**

| 名称      | 类型    | 必须 | 默认          | 描述                                                                     |
| ---------------- | ------- | ---- | ------------- | ------------------------------------------------------------------------ |
| address  | string  | 是   |             | 账户地址 |
| roles  | string  | 是   |             | 权限值，可用值包括：PermAdmin，BlacklistAdmin，NodeAdmin，ParamAdmin，PowerUser, IDAdmin, BaseM1Admin, RelayerUser |

### 增加权限示例

```bash
irita tx perm assign-roles iaa18up8anyjpal8rncm8rd4ukp5f7etga795gp33q PermAdmin --from=node0 --chain-id=irita-test -b=block -o=json --indent -y --home=testnet/node0/iritacli
```

结果

```json
{
  "height": "329",
  "txhash": "8104DB91B083EB18F64CA4CC418FC54D4453AEA691C578EE64A22128FF724EC3",
  "raw_log": "<raw-log>",
  "logs": [
    {
      "msg_index": 0,
      "log": "",
      "events": [
        {
          "type": "assign-roles",
          "attributes": [
            {
              "key": "account",
              "value": "iaa18up8anyjpal8rncm8rd4ukp5f7etga795gp33q"
            }
          ]
        },
        {
          "type": "message",
          "attributes": [
            {
              "key": "action",
              "value": "assign-roles"
            },
            {
              "key": "module",
              "value": "perm"
            },
            {
              "key": "sender",
              "value": "iaa12v3r0unp6nprp9zur0fn446n832dfag5l3w38e"
            }
          ]
        }
      ]
    }
  ],
  "gas_wanted": "200000",
  "gas_used": "42088"
}
```

## remove-roles

IRITA 管理员可以移除指定账户的操作权限。

```bash
irita tx perm unassign-roles [address] [roles] [flags]
```

**参数：**

| 名称      | 类型    | 必须 | 默认          | 描述                                                                     |
| ---------------- | ------- | ---- | ------------- | ------------------------------------------------------------------------ |
| address  | string  | 是   |             | 账户地址 |
| roles  | string  | 是   |             | 权限值，可用值包括：PermAdmin，BlacklistAdmin，NodeAdmin，ParamAdmin，PowerUser, IDAdmin, BaseM1Admin, RelayerUser |

### 移除权限示例

```bash
irita tx perm unassign-roles iaa18up8anyjpal8rncm8rd4ukp5f7etga795gp33q PermAdmin --from=node0 --chain-id=irita-test -b=block -o=json --indent -y --home=testnet/node0/iritacli
```

结果

```json
{
  "height": "365",
  "txhash": "F298C81F1760503E1E7699EBBE57F5B8230DA3093BDF481FD7BF146A2240D416",
  "raw_log": "<raw-log>",
  "logs": [
    {
      "msg_index": 0,
      "log": "",
      "events": [
        {
          "type": "message",
          "attributes": [
            {
              "key": "action",
              "value": "unassign-roles"
            },
            {
              "key": "module",
              "value": "perm"
            },
            {
              "key": "sender",
              "value": "iaa12v3r0unp6nprp9zur0fn446n832dfag5l3w38e"
            }
          ]
        },
        {
          "type": "unassign-roles",
          "attributes": [
            {
              "key": "account",
              "value": "iaa18up8anyjpal8rncm8rd4ukp5f7etga795gp33q"
            }
          ]
        }
      ]
    }
  ],
  "gas_wanted": "200000",
  "gas_used": "42052"
}
```

## block-account

IRITA 管理员可以将指定账户加入黑名单。

```bash
irita tx perm block-account [address] [flags]
```

**参数：**

| 名称      | 类型    | 必须 | 默认          | 描述                                                                     |
| ---------------- | ------- | ---- | ------------- | ------------------------------------------------------------------------ |
| address  | string  | 是   |             | 账户地址 |

### 加入黑名单示例

```bash
irita tx perm block-account iaa18up8anyjpal8rncm8rd4ukp5f7etga795gp33q --from=node0 --chain-id=irita-test -b=block -o=json --indent -y --home=testnet/node0/iritacli
```

结果

```json
{
  "height": "388",
  "txhash": "F266F1734DDE56A8C4A5676BD929C414F0E9C874131856AF362762E4474B489D",
  "raw_log": "<raw-log>",
  "logs": [
    {
      "msg_index": 0,
      "log": "",
      "events": [
        {
          "type": "block_account",
          "attributes": [
            {
              "key": "account",
              "value": "iaa18up8anyjpal8rncm8rd4ukp5f7etga795gp33q"
            }
          ]
        },
        {
          "type": "message",
          "attributes": [
            {
              "key": "action",
              "value": "block_account"
            },
            {
              "key": "module",
              "value": "perm"
            },
            {
              "key": "sender",
              "value": "iaa12v3r0unp6nprp9zur0fn446n832dfag5l3w38e"
            }
          ]
        }
      ]
    }
  ],
  "gas_wanted": "200000",
  "gas_used": "41058"
}
```

## unblock-account

IRITA 管理员可以将指定账户从黑名单移出。

```bash
irita tx perm unblock-account [address] [flags]
```

**参数：**

| 名称      | 类型    | 必须 | 默认          | 描述                                                                     |
| ---------------- | ------- | ---- | ------------- | ------------------------------------------------------------------------ |
| address  | string  | 是   |             | 账户地址 |

### 移出黑名单示例

```bash
irita tx perm unblock-account iaa18up8anyjpal8rncm8rd4ukp5f7etga795gp33q --from=node0 --chain-id=irita-test -b=block -o=json --indent -y --home=testnet/node0/iritacli
```

结果

```json
{
  "height": "403",
  "txhash": "92BE6F2E8867288208D6DC68F0F99F179A8B6AA93253CEC64142B96EA724AA0F",
  "raw_log": "<raw-log>",
  "logs": [
    {
      "msg_index": 0,
      "log": "",
      "events": [
        {
          "type": "message",
          "attributes": [
            {
              "key": "action",
              "value": "unblock_account"
            },
            {
              "key": "module",
              "value": "perm"
            },
            {
              "key": "sender",
              "value": "iaa12v3r0unp6nprp9zur0fn446n832dfag5l3w38e"
            }
          ]
        },
        {
          "type": "unblock_account",
          "attributes": [
            {
              "key": "account",
              "value": "iaa18up8anyjpal8rncm8rd4ukp5f7etga795gp33q"
            }
          ]
        }
      ]
    }
  ],
  "gas_wanted": "200000",
  "gas_used": "39004"
}
```

## block-contract

IRITA 管理员可以将指定合约加入黑名单。

```bash
irita tx perm block-contract [address] [flags]
```

**参数：**

| 名称      | 类型    | 必须 | 默认          | 描述                                                                     |
| ---------------- | ------- | ---- | ------------- | ------------------------------------------------------------------------ |
| contractAddress  | string  | 是   |             | 账户地址 |

### 合约加入黑名单示例

```shell
irita tx perm block-contract 0x38f5c8f6B1c66c6DEf5C01E37453FBE68FF1B626 --from=node0 --chain-id=irita-test -b=block -o=json --indent -y --home=testnet/node0/iritacli
```

```json
{
  "height":"85",
  "txhash":"BFF9770A2C1245495514A754F7759D27E95A454653E10A58B80B93C655EF583C",
  "codespace":"",
  "code":0,
  "data":"0A210A1F2F69726974616D6F642E7065726D2E4D7367426C6F636B436F6E7472616374",
  "raw_log":"[{\"events\":[{\"type\":\"block_contract\",\"attributes\":[{\"key\":\"contract\",\"value\":\"0x38f5c8f6B1c66c6DEf5C01E37453FBE68FF1B626\"}]},{\"type\":\"message\",\"attributes\":[{\"key\":\"action\",\"value\":\"/iritamod.perm.MsgBlockContract\"},{\"key\":\"module\",\"value\":\"perm\"},{\"key\":\"sender\",\"value\":\"iaa19famjucwp47c28j6q79gyswvykrek8dusv260v\"}]}]}]",
  "logs":[
    {
      "msg_index":0,
      "log":"",
      "events":[
        {
          "type":"block_contract",
          "attributes":[
            {
              "key":"contract",
              "value":"0x38f5c8f6B1c66c6DEf5C01E37453FBE68FF1B626"
            }
          ]
        },
        {
          "type":"message",
          "attributes":[
            {
              "key":"action",
              "value":"/iritamod.perm.MsgBlockContract"
            },
            {
              "key":"module",
              "value":"perm"
            },
            {
              "key":"sender",
              "value":"iaa19famjucwp47c28j6q79gyswvykrek8dusv260v"
            }
          ]
        }
      ]
    }
  ],
  "info":"",
  "gas_wanted":"200000",
  "gas_used":"52700",
  "tx":null,
  "timestamp":""
}
```

## unblock-contract

IRITA 管理员可以将指定合约从黑名单移出。

```bash
irita tx perm unblock-contract [address] [flags]
```

**参数：**

| 名称      | 类型    | 必须 | 默认          | 描述                                                                     |
| ---------------- | ------- | ---- | ------------- | ------------------------------------------------------------------------ |
| contractAddress  | string  | 是   |             | 账户地址 |

### 合约移出黑名单示例

```shell
irita tx perm unblock-contract 0x38f5c8f6B1c66c6DEf5C01E37453FBE68FF1B626 --from=node0 --chain-id=irita-test -b=block -o=json --indent -y --home=testnet/node0/iritacli
```

```json
{
    "height":"109",
    "txhash":"D0E125DDBF2273AB2FC54B1E5BD6898B1F7145EA3384633E38AD922AF248EE0A",
    "codespace":"",
    "code":0,
    "data":"0A230A212F69726974616D6F642E7065726D2E4D7367556E626C6F636B436F6E7472616374",
    "raw_log":"[{\"events\":[{\"type\":\"message\",\"attributes\":[{\"key\":\"action\",\"value\":\"/iritamod.perm.MsgUnblockContract\"},{\"key\":\"module\",\"value\":\"perm\"},{\"key\":\"sender\",\"value\":\"iaa19famjucwp47c28j6q79gyswvykrek8dusv260v\"}]},{\"type\":\"unblock_contract\",\"attributes\":[{\"key\":\"contract\",\"value\":\"0x38f5c8f6B1c66c6DEf5C01E37453FBE68FF1B626\"}]}]}]",
    "logs":[
        {
            "msg_index":0,
            "log":"",
            "events":[
                {
                    "type":"message",
                    "attributes":[
                        {
                            "key":"action",
                            "value":"/iritamod.perm.MsgUnblockContract"
                        },
                        {
                            "key":"module",
                            "value":"perm"
                        },
                        {
                            "key":"sender",
                            "value":"iaa19famjucwp47c28j6q79gyswvykrek8dusv260v"
                        }
                    ]
                },
                {
                    "type":"unblock_contract",
                    "attributes":[
                        {
                            "key":"contract",
                            "value":"0x38f5c8f6B1c66c6DEf5C01E37453FBE68FF1B626"
                        }
                    ]
                }
            ]
        }
    ],
    "info":"",
    "gas_wanted":"200000",
    "gas_used":"51666",
    "tx":null,
    "timestamp":""
}
```