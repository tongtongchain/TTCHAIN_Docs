
Sandbox
=========================================

Open Sandbox
------------------------------------
Prerequisite:  RPC login authentication successfully, wallet opens, wallet unlocks

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "sandbox_open",
        "params": [
            
        ]
    }
Request method: sandbox_open

Request parameter: none

Response Result:

::

    {
        "id": "1",
        "result": null
    }
Response parameters: none


Close Sandbox
------------------------------------
Prerequisite:  RPC login authentication successfully, wallet opens, wallet unlocks, sandbox opens

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "sandbox_close",
        "params": [
            
        ]
    }
Request method: sandbox_close

Request parameter: none

Response Result:

::

    {
        "id": "1",
        "result": null
    }
Response parameters: none

Compile a contract in sandbox
----------------------------------------
Prerequisite:  RPC login authentication successfully, wallet opens, wallet unlocks, sandbox opens


Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "sandbox_compile_contract",
        "params": [
            "C:/Users/hasee/Desktop/test.glua"
        ]
    }
Request method: sandbox_compile_contract

Request parameter: path of contract source


Response Result:

::

    {
        "id": "1",
        "result": "C:/Users/hasee/Desktop/test.gpc"
    }

Response parameters: generated contract bytecode file path


Register a contract in sandbox (sandbox)
------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks, sandbox opens

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "sandbox_register_contract",
        "params": [
            "test01",
            "C:/Users/hasee/Desktop/test1.gpc",
            "TTC",
            "0.1"
        ]
    }

Request method: sandbox_register_contract

Request parameter: registrant, bytecode file path, asset id, and execution cost ceiling

Response Result:

::

    {
        "id": "1",
        "result": "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE"
    }

Response parameters: contract id


Register a contract in sandbox: (sandbox testing)
------------------------------------
Prerequisite:  RPC login authentication successfully, wallet opens, wallet unlocks, sandbox opens

Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "sandbox_register_contract_testing",
        "params": [
            "test01",
            "C:/Users/hasee/Desktop/test1.gpc"
        ]
    }
Request method: sandbox_register_contract_testing

Request parameter: registrant, contract bytecode file

Response Result:

::
    
    {
        "id": "1",
        "result": [
            {
                "amount": 1000,
                "asset_id": 0
            },
            {
                "amount": 10000000,
                "asset_id": 0
            },
            {
                "amount": 473,
                "asset_id": 0
            },
            {
                "amount": 100,
                "asset_id": 0
            }
        ]
    }

Response parameters: 
transaction fee, contract security, execution expense, bytecode cost, registered execution cost



Call a contract in sandbox (sandbox)
------------------------------------
Prerequisite:  RPC login authentication successfully, wallet opens, wallet unlocks, sandbox opens


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "0",
        "method": "sandbox_call_contract",
        "params": [
            "CONMR24hkhmuJ8X6eiEhdT2vqV1FvCcS5vDf",
            "alp0",
            "print",
            "",
            "TTC",
            "1"
        ]
    }

Request method: sandbox_call_contract

Request parameter: contract id, initiator of calling, method of calling, parameter of calling, asset symbol, and execution cost ceiling


Response Result:

::
    
    {
        "id": "0",
        "result": {
            "index": 0,
            "entry_id": "d57f3b339a40eb1d9a72359d1a3c9d9e67434673",
            "block_num": 0,
            "is_virtual": false,
            "is_confirmed": false,
            "is_market": false,
            "trx": {
                "expiration": "2016-11-21T06:53:19",
                "ttc_account": "",
                "ttc_inport_asset": {
                    "amount": 0,
                    "asset_id": 0
                },
                "operations": [
                    {
                        "type": "call_contract_op_type",
                        "data": {
                            "caller": "TTC8CqTJMSBzgqFxudU5TWzQyVDgmqrqax3ApNDGDwEZV7uXKTND2",
                            "balances": [
                                [
                                    "TTCJqWqjsVdAXCK99knVmeCE7EpAuFdTmFux",
                                    101000
                                ]
                            ],
                            "contract": "TTCMR24hkhmuJ8X6eiEhdT2vqV1FvCcS5vDf",
                            "costlimit": {
                                "amount": 100000,
                                "asset_id": 0
                            },
                            "method": "print",
                            "args": ""
                        }
                    }
                ],
                "signatures": [
                    "2030cd70eadf10532a4b27613252c3c2c5bd61ccd5f22911c18727676625cae9411ffed0f6383efdd48568ed9559d9819ccd45d6ab2318528108fec1ea7ba17bab"
                ]
            },
            "ledger_entries": [],
            "fee": {
                "amount": 1000,
                "asset_id": 0
            },
            "created_time": "2016-11-21T05:53:19",
            "received_time": "2016-11-21T05:53:19",
            "extra_addresses": []
        }
    }

Response parameters: transaction history


Call a contract in sandbox (sandbox testing)
------------------------------------
Prerequisite:  RPC login authentication successfully, wallet opens, wallet unlocks, sandbox opens


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "sandbox_call_contract_testing",
        "params": [
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE",
            "test01",
            "function_not_exist",
            ""
        ]
    }

Request method: sandbox_call_contract_testing

Request parameter: contract id, initiator of calling, method of calling, parameter of calling

Response Result:

::
    
    {
        "id": "1",
        "result": [
            {
                "amount": 1000,
                "asset_id": 0
            },
            {
                "amount": 103,
                "asset_id": 0
            }
        ]
    }

Response parameters: transaction fee, execution cost

Upgrade contract in sandbox (sandbox)
------------------------------------
Prerequisite:  RPC login authentication successfully, wallet opens, wallet unlocks, sandbox opens


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "sandbox_upgrade_contract",
        "params": [
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE",
            "test01",
            "my_contract_1",
            "this is my first contract"
            "TTC"
            "10"
        ]
    }

Request method: sandbox_upgrade_contract

Request parameter: contract idï¼Œinitiator of callingï¼Œnew contract nameï¼Œdescription of contractï¼Œasset symbolï¼Œexecution cost ceiling

Response Result:

::
    
    {
        "id": "1",
        "result": {
            "index": 0,
            "entry_id": "1a6f38c365c7b14d4d24a263c74c9d80f0296394",
            "block_num": 0,
            "is_virtual": false,
            "is_confirmed": false,
            "is_market": false,
            "trx": {
                "expiration": "2016-09-28T06:44:46",
                "ttc_account": "",
                "ttc_inport_asset": {
                    "amount": 0,
                    "asset_id": 0
                },
                "operations": [
                    {
                        "type": "upgrade_contract_op_type",
                        "data": {
                            "id": "TTCJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE",
                            "name": "my_contract_1",
                            "desc": "this is my first contract",
                            "balances": [
                                [
                                    "TTCPe9u4ZmBj38D5GzPPSz9LLe8J3LpM89o8",
                                    1000
                                ]
                            ]
                        }
                    }
                ],
                "signatures": [
                    "2027fbcf936eeb898593fade96c26bef189462d60b1e60a8fb95f73cbfd0e6632423346678f5691a9f7f5e20681656b7d3b0aa9f262a91ccadcb5c52bcf531566c"
                ]
            },
            "ledger_entries": [
                {
                    "amount": {
                        "amount": 0,
                        "asset_id": 0
                    },
                    "memo": ""
                }
            ],
            "fee": {
                "amount": 10001000,
                "asset_id": 0
            },
            "created_time": "2016-09-28T05:44:46",
            "received_time": "2016-09-28T05:44:46",
            "extra_addresses": [
                "TTCJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE"
            ]
        }
    }

Response parameters: transaction history
    

Upgrade a contract in sandbox (sandbox testing)
------------------------------------
Prerequisite:  RPC login authentication successfully, wallet opens, wallet unlocks, sandbox opens


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "sandbox_upgrade_contract_testing",
        "params": [
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE",
            "test01",
            "my_contract_1",
            "this is my first contract"
        ]
    }

Request method: sandbox_upgrade_contract_testing

Request parameter: contract idï¼Œinitiator of callingï¼Œnew contract nameï¼Œdescription of contract

Response Result:

::

    {
        "id": "1",
        "result": [
            {
                "amount": 1000,
                "asset_id": 0
            },
            {
                "amount": 16,
                "asset_id": 0
            },
            {
                "amount": 1000000,
                "asset_id": 0
            }
        ]
    }

Response parameters: transaction feeï¼Œexecution costï¼Œcash deposit


Delete a contract in sandbox(sandbox)
------------------------------------
Prerequisite:  RPC login authentication successfully, wallet opens, wallet unlocks, sandbox opens

Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "sandbox_destroy_contract",
        "params": [
            "CONPZdkAuyDthiftdDzp8Hg7PqyK9MiTnL2q",
            "test01"
            "TTC"
            "10"
        ]
    }

Request method: sandbox_destroy_contract

Request parameter: contract idï¼Œdeletion initiatorï¼Œasset id, execution expense ceiling

Response Result:

::
    
    {
        "id": "1",
        "result": {
            "index": 0,
            "entry_id": "111eae250a783bba4d9f5e8bee56af762b447dfe",
            "block_num": 0,
            "is_virtual": false,
            "is_confirmed": false,
            "is_market": false,
            "trx": {
                "expiration": "2016-09-28T07:02:06",
                "act_account": "",
                "act_inport_asset": {
                    "amount": 0,
                    "asset_id": 0
                },
                "operations": [
                    {
                        "type": "destroy_contract_op_type",
                        "data": {
                            "id": "TTCPZdkAuyDthiftdDzp8Hg7PqyK9MiTnL2q",
                            "balances": [
                                [
                                    "TTCPe9u4ZmBj38D5GzPPSz9LLe8J3LpM89o8",
                                    1000
                                ]
                            ]
                        }
                    }
                ],
                "signatures": [
                    "1f4d9614000a6000940b98186d28f1e28faa0326f912b234ed31822c10140889b72183551449b0b18da4c9f4c355b3453c9c54fa23dab09cd4ba2136912b26f71f"
                ]
            },
            "ledger_entries": [
                {
                    "amount": {
                        "amount": 0,
                        "asset_id": 0
                    },
                    "memo": ""
                }
            ],
            "fee": {
                "amount": 1000,
                "asset_id": 0
            },
            "created_time": "2016-09-28T06:02:06",
            "received_time": "2016-09-28T06:02:06",
            "extra_addresses": [
                "TTCPZdkAuyDthiftdDzp8Hg7PqyK9MiTnL2q"
            ]
        }
    }

Response parameters: transaction history


Delete a contract in sandbox (sandbox testing)
------------------------------------
Prerequisite:  RPC login authentication successfully, wallet opens, wallet unlocks, sandbox opens

Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "sandbox_destroy_contract_testing",
        "params": [
            "CONPZdkAuyDthiftdDzp8Hg7PqyK9MiTnL2q",
            "test01"
        ]
    }

Request method: sandbox_destroy_contract_testing

Request parameter: contract idï¼Œinitiator of deletion

Response Result:

::

    {
        "id": "1",
        "result": [
            {
                "amount": 1000,
                "asset_id": 0
            },
            {
                "amount": 16,
                "asset_id": 0
            }
        ]
    }

Response parameters: transaction feeï¼Œexecution cost

Transfer to contract in sandbox (sandbox)
------------------------------------
Prerequisite:  RPC login authentication successfully, wallet opens, wallet unlocks, sandbox opens


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "sandbox_transfer_to_contract",
        "params": [
            "10",
            "TTC",
            "test01",
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE",
            "1"
        ]
    }
Request method: sandbox_transfer_to_contract

Request parameter: transfer amountï¼Œasset symbolï¼Œtransfer accountsï¼Œcontract idï¼Œexecution cost ceiling

Response Result:

::
    
    {
        "id": "1",
        "result": {
            "index": 0,
            "entry_id": "1003bfb6f006509eadaa0567152b995aca63db1b",
            "block_num": 0,
            "is_virtual": false,
            "is_confirmed": false,
            "is_market": false,
            "trx": {
                "expiration": "2016-09-28T07:34:09",
                "act_account": "",
                "act_inport_asset": {
                    "amount": 0,
                    "asset_id": 0
                },
                "operations": [
                    {
                        "type": "transfer_contract_op_type",
                        "data": {
                            "from": "TTC785tCDTiTNu2FxDkzKazkTvFbVeJ4bAo9A1VuJV7yBdB7J7UbB",
                            "costlimit": {
                                "amount": 100000,
                                "asset_id": 0
                            },
                            "transfer_amount": {
                                "amount": 1000000,
                                "asset_id": 0
                            },
                            "balances": [
                                [
                                    "TTCPe9u4ZmBj38D5GzPPSz9LLe8J3LpM89o8",
                                    1101000
                                ]
                            ],
                            "contract_id": "TTCJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE"
                        }
                    }
                ],
                "signatures": [
                    "1f0acbf0ab2c3338e478157e02bcd770e22a832b85ace93bb58cc7e9c3f241b59e7029f1c7a029417d3753dc508712e934debfcb4538846a9112836085f804ef48"
                ]
            },
            "ledger_entries": [
                {
                    "from_account": "TTC785tCDTiTNu2FxDkzKazkTvFbVeJ4bAo9A1VuJV7yBdB7J7UbB",
                    "amount": {
                        "amount": 1000000,
                        "asset_id": 0
                    },
                    "memo": ""
                }
            ],
            "fee": {
                "amount": 1000,
                "asset_id": 0
            },
            "created_time": "2016-09-28T06:34:09",
            "received_time": "2016-09-28T06:34:09",
            "extra_addresses": [
                "TTCJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE"
            ]
        }
    }

Response parameters: transaction history

Transfer to contract in sandbox (sandbox testing)
------------------------------------
Prerequisite:  RPC login authentication successfully, wallet opens, wallet unlocks, sandbox opens

Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "sandbox_transfer_to_contract_testing",
        "params": [
            "10000",
            "TTC",
            "test01",
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE"
        ]
    }

Request method: sandbox_transfer_to_contract_testing

Request parameter: transfer amountï¼Œasset symbolï¼Œtransfer accountsï¼Œcontract id

Response Result:

::
    
    {
        "id": "1",
        "result": [
            {
                "amount": 1000,
                "asset_id": 0
            },
            {
                "amount": 1000000000,
                "asset_id": 0
            },
            {
                "amount": 0,
                "asset_id": 0
            }
        ]
    }
Response parameters: transaction feeï¼Œtransfer amountï¼Œexecution cost


Query a contract info in sandbox
------------------------------------
Prerequisite:  RPC login authentication successfully, wallet opens, wallet unlocks, sandbox opens


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "sandbox_get_contract_info",
        "params": [
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE"
        ]
    }

Request method: sandbox_get_contract_info

Request parameter: contract id

Response Result:

::
    
    {
        "id": "1",
        "result": {
            "contract_name": "my_contract_1",
            "id": "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE",
            "level": "forever",
            "owner": "TTC785tCDTiTNu2FxDkzKazkTvFbVeJ4bAo9A1VuJV7yBdB7J7UbB",
            "state": "valid",
            "description": "this is my first contract",
            "code_printable": {
                "abi": [
                    "init",
                    "start"
                ],
                "offline_abi": [],
                "events": [],
                "printable_code": "1b4c7561530019930d0a1a0a040804080878560000000000000000000000287740012140453a5c476f6f70616c332e305c6175746f746573745c74657374312e6c75610000000000000000000202070000000b0000006c0000000a4000806c4000000a4080802600000126008000020000000405696e697404067374617274010000000100020000000003000000050000000100030400000046004000814000006440000126008000020000000407707072696e740405696e6974010000000000000000000400000004000000040000000400000005000000010000000573656c66000000000400000001000000055f454e560007000000090000000200060700000086004000c1400000068140004001800024010001a440000026008000030000000407707072696e74041973746172742063616c6c6564207769746820706172616d200409746f6e756d626572010000000000000000000700000008000000080000000800000008000000080000000800000009000000020000000573656c660000000007000000076e756d737472000000000700000001000000055f454e560700000001000000050000000300000009000000070000000b0000000b00000001000000024d010000000700000001000000055f454e56",
                "code_hash": "df6d3e2343718599ac6343ba2bd3d4e7cc7e7347"
            },
            "trx_id": "ccb1c3cdadfb6a0883863d5b2c9605cd3ba9ab99"
        }
    }
Response parameters: 

contract_name: contract name

id: contract id

level: temporary contracts or permanent contracts

owner: contract registrant

state: initialization state

description: description of contract

code_printable: bytecode info

trx_id: The transaction id of the registered contract




Query the balance of a contract in sandbox
------------------------------------
Prerequisite:  RPC login authentication successfully, wallet opens, wallet unlocks, sandbox opens

Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "sandbox_get_contract_balance",
        "params": [
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE"
        ]
    }

Request method: sandbox_get_contract_balance

Request parameter: contract id

Response Result:

::
    
    {
        "id": "1",
        "result": [
            {
                "condition": {
                    "asset_id": 0,
                    "slate_id": 0,
                    "type": "withdraw_signature_type",
                    "data": {
                        "owner": "TTCJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE"
                    }
                },
                "balance": 1000000,
                "deposit_date": "2016-09-28T06:34:00",
                "last_update": "2016-09-28T06:34:00",
                "meta_data": null
            },
            {
                "condition": {
                    "asset_id": 0,
                    "slate_id": 0,
                    "type": "withdraw_signature_type",
                    "data": {
                        "owner": "TTCJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE"
                    }
                },
                "balance": 0,
                "deposit_date": "2016-09-26T09:08:40",
                "last_update": "2016-09-28T05:44:40",
                "meta_data": null
            }
        ]
    }
Response parameters: cash deposit balance of contractï¼Œbalance of contract


Query the balance of a contract in sandbox
------------------------------------
Prerequisite:  RPC login authentication successfully, wallet opens, wallet unlocks, sandbox opens


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "sandbox_account_balance",
        "params": [
            "test01"
        ]
    }
Request method: sandbox_account_balance

Request parameter: account name

Response Result:

::
    
    {
        "id": "1",
        "result": [
            [
                "test01",
                [
                    [
                        0,
                        28981277
                    ]
                ]
            ]
        ]
    }

Response parameters: account nameï¼Œbalance record array


