
Contract Related
=========================================


Compile a contract
----------------------------------------
Prerequisite: none


Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "compile_contract",
        "params": [
            "C:/Users/hasee/Desktop/test.glua"
        ]
    }

Request method: compile_contract

Request parameter: contract source path


Response Result:

::

    {
        "id": "1",
        "result": "C:/Users/hasee/Desktop/test.gpc"
    }

Response parameters: generated contract bytecode file path


Register a contract on the chain
----------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "register_contract",
        "params": [
            "test01",
            "C:/Users/hasee/Desktop/test1.gpc",
            "TTC",
            "0.1"
        ]
    }

Request method: register_contract

Request parameter: registrant, bytecode file path, asset symbol, execution expense ceiling

Response Result:

::

    {
        "id": "1",
        "result": "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE"
    }

Response parameters: contract id


Register a contract testing
----------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "register_contract_testing",
        "params": [
            "test01",
            "C:/Users/hasee/Desktop/test1.gpc"
        ]
    }
Request method: register_contract_testing

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
transaction fee, contract cash deposit, execution expense, bytecode cost, execution expense


Upgrade a contract on the chain
----------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks


Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "upgrade_contract",
        "params": [
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE",
            "test01",
            "my_contract_1",
            "this is my first contract"
            "TTC"
            "10"
        ]
    }
Request method: upgrade_contract

Request parameter: contract id, upgrade initiator, new contract name, description of contract, asset symbole, execution expense ceiling

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
                "act_account": "",
                "act_inport_asset": {
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


Upgrading contract testing
----------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks


Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "upgrade_contract_testing",
        "params": [
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE",
            "test01",
            "my_contract_1",
            "this is my first contract"
        ]
    }

Request method: upgrade_contract_testing

Request parameter: contract, upgrade initiator, new contract name, description of contract

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

Response parameters: transaction fee, execution expense, cash deposit

Delete a contract on the chain
----------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "destroy_contract",
        "params": [
            "CONPZdkAuyDthiftdDzp8Hg7PqyK9MiTnL2q",
            "test01"
            "TTC"
            "10"
        ]
    }

Request method: destroy_contract

Request parameter: contract id, deletion initiator, asset id, execution cost ceiling   

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

Delete a contract testing
----------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "destroy_contract_testing",
        "params": [
            "CONPZdkAuyDthiftdDzp8Hg7PqyK9MiTnL2q",
            "test01"
        ]
    }

Request method: destroy_contract_testing

Request parameter: contract id deletion initiator    

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
    
Response parameters: transaction fee, execution expense

Call a contract on the chain 
----------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks


Request:

::

    {
        "jsonrpc": "2.0",
        "id": "0",
        "method": "call_contract",
        "params": [
            "CONMR24hkhmuJ8X6eiEhdT2vqV1FvCcS5vDf",
            "alp0",
            "print",
            "",
            "TTC",
            "1"
        ]
    }

Request method: call_contract

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
                "act_account": "",
                "act_inport_asset": {
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


Call a contract testing 
----------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks


Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "call_contract_testing",
        "params": [
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE",
            "test01",
            "function_not_exist",
            ""
        ]
    }

Request method: call_contract_testing

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

Response parameters: transaction fee, execution expense


Transfer to a contract on the chain 
----------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks


Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "wallet_transfer_to_contract",
        "params": [
            "10",
            "TTC",
            "test01",
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE",
            "1"
        ]
    }

Request method: wallet_transfer_to_contract

Request parameter: transfer amount, asset symbol, transfer account, contract id, execution expense ceiling

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

Transfer to a contract testing 
----------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "wallet_transfer_to_contract_testing",
        "params": [
            "10000",
            "TTC",
            "test01",
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE"
        ]
    }

Request method: wallet_transfer_to_contract_testing

Request parameter: transfer amount, asset symbol, transfer account, contract id

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

Response parameters: transaction fee, transfer amount, execution expense


Query contract information
---------------------------------------
Prerequisite: none


Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "get_contract_info",
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
            "owner_address": "TTCLMSC5rhePQeVgLQrjqVMdC9pmB97451CG",
            "owner_name": ""
            "state": "valid",
            "description": "this is my first contract",
            "code_printable": {
                "abi": [
                    "init",
                    "start"
                ],
                "offline_abi": [],
                "events": [],
                "printable_storage_properties": [],
                "printable_code": "1b4c7561530019930d0a1a0a040804080878560000000000000000000000287740012140453a5c476f6f70616c332e305c6175746f746573745c74657374312e6c75610000000000000000000202070000000b0000006c0000000a4000806c4000000a4080802600000126008000020000000405696e697404067374617274010000000100020000000003000000050000000100030400000046004000814000006440000126008000020000000407707072696e740405696e6974010000000000000000000400000004000000040000000400000005000000010000000573656c66000000000400000001000000055f454e560007000000090000000200060700000086004000c1400000068140004001800024010001a440000026008000030000000407707072696e74041973746172742063616c6c6564207769746820706172616d200409746f6e756d626572010000000000000000000700000008000000080000000800000008000000080000000800000009000000020000000573656c660000000007000000076e756d737472000000000700000001000000055f454e560700000001000000050000000300000009000000070000000b0000000b00000001000000024d010000000700000001000000055f454e56",
                "code_hash": "df6d3e2343718599ac6343ba2bd3d4e7cc7e7347"
            },
            "trx_id": "ccb1c3cdadfb6a0883863d5b2c9605cd3ba9ab99"
        }
    }

Response parameters: 

contract_name : contract name

id : contract id

level : temporary or permanent

owner : contract registrant

state : enabling state

description:description of contract

code_printable : bytecode information

trx_id: trade id of the registered contract


Query contract balance
---------------------------------------
Prerequisite: none


Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "get_contract_balance",
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

Response parameters: contract cash deposit balance, contract balance


Open/close the local interpreter
---------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "blockchain_set_node_vm_enabled",
        "params": [
            "true"
        ]
    }

Request method: blockchain_set_node_vm_enabled

Request parameter: true/false, enable vm or not

Response Result:

::

    {
        "id": "1",
        "result": null
    }

Response parameters: none

Gets switch whether to open the local interpreter validation
---------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "blockchain_get_node_vm_enabled",
        "params": [
            
        ]
    }

Request method: blockchain_get_node_vm_enabled

Request parameter: none

Response Result:

::

    {
        "id": "1",
        "result": true
    }

Response parameters: vm enabling state


Export the contract to the file
--------------------------------------------
Prerequisite: none


Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "load_contract_to_file",
        "params": [
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE",
            "D:/contract_to_export.gpc"
        ]
    }

Request method: load_contract_to_file

Request parameter: contract id, å¯¼å‡ºçš„æ–‡ä»¶çš„è·¯å¾„

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
                "offline_abi": [
                    
                ],
                "events": [
                    
                ],
                "printable_code": "1b4c7561530019930d0a1a0a040804080878560000000000000000000000287740012140453a5c476f6f70616c332e305c6175746f746573745c74657374312e6c75610000000000000000000202070000000b0000006c0000000a4000806c4000000a4080802600000126008000020000000405696e697404067374617274010000000100020000000003000000050000000100030400000046004000814000006440000126008000020000000407707072696e740405696e6974010000000000000000000400000004000000040000000400000005000000010000000573656c66000000000400000001000000055f454e560007000000090000000200060700000086004000c1400000068140004001800024010001a440000026008000030000000407707072696e74041973746172742063616c6c6564207769746820706172616d200409746f6e756d626572010000000000000000000700000008000000080000000800000008000000080000000800000009000000020000000573656c660000000007000000076e756d737472000000000700000001000000055f454e560700000001000000050000000300000009000000070000000b0000000b00000001000000024d010000000700000001000000055f454e56",
                "code_hash": "df6d3e2343718599ac6343ba2bd3d4e7cc7e7347"
            },
            "trx_id": "ccb1c3cdadfb6a0883863d5b2c9605cd3ba9ab99"
        }
    }

Response parameters: 

contract_name : contract name

id : contract id

level : temporary contracts or permanent contracts

owner : contract registrant

state : enabling state

description: description of contract

code_printable : bytebode information

trx_id: trade id of the registered contract


Get the contract result trading hash
--------------------------------------------
Prerequisite: none


Request:

::

    {
        "jsonrpc": "2.0",
        "id": "0",
        "method": "get_result_trx_id",
        "params": [
            "84f277e2097b9039b75bb66b85d09fa2e97381f6"
        ]
    }

Request method: get_result_trx_id

Request parameter: orginal trade id

Response Result:

::

    {
        "id": "0",
        "result": "94201d7b852e887b165c93458fe13ba48bd6f57e"
    }

Response parameters: final trade id


Get contract address according to the original transaction hash that created the contract
--------------------------------------------
Prerequisite: none


Request:

::

    {
        "jsonrpc": "2.0",
        "id": "0",
        "method": "get_contract_registered_in_transaction",
        "params": [
            "8bfce6f1d70f6b61a98d62910c18c25b2b8a8154"
        ]
    }

Request method: get_contract_registered_in_transaction

Request parameter: contract id

Response Result:

::

    {
        "id": "0",
        "result": "CON8wiH4jjovUC9c6FG7B15kwD6eqaVLVBJw"
    }

Response parameters: contract id


Get the original transaction hash that created the contract according to contract address
--------------------------------------------
Prerequisite: none

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "0",
        "method": "get_transaction_id_contract_registered",
        "params": [
            "CONWyvc7YvfGxs74aMuGY4cb4bX9RyxTJWw"
        ]
    }

Request method: get_transaction_id_contract_registered

Request parameter: contract id

Response Result:

::

    {
        "id": "0",
        "result": "10c14b782d5574b4d0e4a70eeff788eb07dd7a3f"
    }

Response parameters: trade id
    

Get all contract information on the chain
--------------------------------------------
Prerequisite: none

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "blockchain_get_all_contracts",
        "params": [ ]
    }

Request method: blockchain_get_all_contracts

Request parameter: none

Response Result:

::

    { 
        "id":1,
        "result":
        ["CON9dAKb5nDttSvH3T9oEuTdu3WeScKt8vcv","CONCs5JotmSyYK696nafFcYAX6iPZh7Xbh2u"]
    }

Response parameters: array of contract address



Get all the permanent contract information on the chain
--------------------------------------------
Prerequisite: none

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "blockchain_get_forever_contracts",
        "params": [ ]
    }

Request method: blockchain_get_forever_contracts

Request parameter: none
Response Result:

::

    {
        "id":1,"
        "result":[["TTC9dAKb5nDttSvH3T9oEuTdu3WeScKt8vcv","wens"]]
    }

Response parameters: array of contract name


Get the contract information for the account in wallet
--------------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "wallet_get_contracts",
        "params": ["account_name"] (If not given, the default is to obtain the contract information for all accounts in the wallet
)
    }

Request method: wallet_get_contracts

Request parameter: account name

Response Result:

::

    {
        "id":1,
        "result":["CON9dAKb5nDttSvH3T9oEuTdu3WeScKt8vcv","CONCs5JotmSyYK696nafFcYAX6iPZh7Xbh2u"]
    }

Request parameter: contract id array


Scan the contract information for all accounts in wallet
--------------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "wallet_scan_contracts",
        "params": [""]
    }

Request method: wallet_scan_contracts

Request parameter: none

Response Result:

::

    {
        "id":1,
        "result":null
    }

Response parameters: none


