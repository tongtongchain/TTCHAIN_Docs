
Basic interface
=========================================


Access wallet login function through rpc request
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:
1.In the ttchain platform data directory, config relevant rpc server parameters in config.json.
2.Start the ttchain platform
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "username", 
	        "password"
	    ], 
	    "id": "1", 
	    "method": "login"
	}

Request method: login

Request parameter: rpc user, rpc password
	

Response Result:

::

	{
	    "id": "1", 
	    "result": true
	}

Return value:

null: 



Display the version number and the relevant information of the client
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": 2.0, 
	    "params": [], 
	    "id": "1", 
	    "method": "about"
	}

Request method : about

Request parameter : null
	

Response Result:

::

	{
	    "id": "2", 
	    "result": {
	        "fc_revision_age": "46 years ago", 
	        "blockchain_name": "TTCHAIN",
	        "ttc_revision_age": "64 weeks ago",
	        "boost_version": "1.55", 
	        "openssl_version": "OpenSSL 1.0.1g 7 Apr 2014", 
	        "compile_date": "compiled on Mar 28 2016 at 11:50:01", 
	        "build": "win32 64-bit", 
	        "ttc_revision": "1.2",
	        "fc_revision": "0", 
	        "client_version": "", 
	        "blockchain_description": "The Future of Banking"
	    }
	}

Return value:

blockchain_name: blockchain name

blockchain_description: blockchain description

client_version: client version

ttc_revision: ttchain version

fc_revision: fc version

fc_revision_age: fc revision time

compile_date: compile date

boost_version: boost version

openssl_version: openssl version

build: compile platform



Get the current blockchain and wallet basic data
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "2", 
	    "method": "get_info"
	}

Request method : get_info 

Request parameter : null
	

Response Result:

::

	{
	    "id": "2", 
	    "result": {
	        "blockchain_head_block_timestamp": "2016-03-28T07:43:00", 
	        "blockchain_average_delegate_participation": "1.46017699115044250", 
	        "wallet_unlocked": true, 
	        "wallet_next_block_production_time": null, 
	        "blockchain_share_supply": "10000578600000", 
	        "network_num_connections": "0", 
	        "blockchain_next_round_timestamp": "2016-03-29T02:25:40", 
	        "ntp_time_error": "-0.10100400000000000", 
	        "blockchain_random_seed": "fca3b1dd8ad99aee1451fcb8426185af01769942", 
	        "blockchain_next_round_time": "550", 
	        "wallet_block_production_enabled": false, 
	        "network_num_connections_max": "200", 
	        "wallet_last_scanned_block_timestamp": "2016-03-28T07:43:00", 
	        "wallet_next_block_production_timestamp": null, 
	        "wallet_unlocked_until_timestamp": "1911-10-30T20:53:40", 
	        "wallet_open": true, 
	        "blockchain_head_block_num": "5786", 
	        "blockchain_confirmation_requirement": "1", 
	        "network_chain_downloader_blocks_remaining": null, 
	        "network_chain_downloader_running": false, 
	        "client_data_dir": "e:/alptest/3", 
	        "blockchain_head_block_age": "66810", 
	        "blockchain_blocks_left_in_round": "55", 
	        "wallet_unlocked_until": "999997526", 
	        "ntp_time": "2016-03-29T02:16:30", 
	        "wallet_scan_progress": "1.00000000000000000", 
	        "client_version": "", 
	        "blockchain_head_block_id": "a8b1ce125f3cbb4e3454a532ca9360bbe9f9dfa4"
	    }
	}

Return value:

blockchain_head_block_num: head block number

blockchain_head_block_age: head block age

blockchain_head_block_timestamp: head block timestamp

blockchain_head_block_id: head block id

blockchain_average_delegate_participation: delegate participation rate

blockchain_confirmation_requirement: block confirmation time

blockchain_share_supply: TTC supply

blockchain_blocks_left_in_round: number of rounds of the remaining round

blockchain_next_round_time: next round remaining time

blockchain_next_round_timestamp: next round timestamp

blockchain_random_seed: Current rounds

client_data_dir: Local client data storage path

client_version: client version

network_num_connections: current number of connections

network_num_connections_max: maximum number of current client connections

network_chain_downloader_running: current high-speed synchronization mode open

network_chain_downloader_blocks_remaining: number of currently remaining unsynchronized blocks

ntp_time: NTP timestamp

ntp_time_error: NTP time correction parameter

wallet_open: is wallet open

wallet_unlocked: is wallet unlock

wallet_unlocked_until: wallet unlock time

wallet_unlocked_until_timestamp: wallet lock timestamp

wallet_last_scanned_block_timestamp: wallet last scan time 

wallet_scan_progress: number of wallet scan threads

wallet_block_production_enabled: is wallet produce block

wallet_next_block_production_time: next round produce block time

wallet_next_block_production_timestamp: next round produce block timestamp


Verify whether the input public key is valid
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "public_key"
	    ], 
	    "id": "2", 
	    "method": "validate_address"
	}

Request method : validate_address

Request parameter : Input public key
	

Response Result:

::

	{
	    "id": "2", 
	    "result": {
	        "isvalid": true
	    }
	}

Return value:

isvalid: is valid public key



Temporarily set the login user name for rpc
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:Need to use the 'rpc_start_server' directive to make this directive effective
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "username"
	    ], 
	    "id": "2", 
	    "method": "rpc_set_username"
	}

Request method : rpc_set_username

Request parameter : 	rpc login user name
	

Response Result:

::

	{
	    "id": "2", 
	    "result": "null"
	}

Return value:

null: 



Temporary settings rpc login user password
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:Need to use the 'rpc_start_server' directive to make this directive effective
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "password"
	    ], 
	    "id": "2", 
	    "method": "rpc_set_password"
	}

Request method : rpc_set_password

Request parameter : rpc login user password
	

Response Result:

::

	{
	    "id": "3", 
	    "result": "null"
	}

Return value:

null: 



Temporarily start the client rpc mode
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:Need to disconnect the rpc link, re-rpc link to see the effect of API implementation
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "port"
	    ], 
	    "id": "2", 
	    "method": "rpc_start_server"
	}

Request method : rpc_start_server

Request parameter : rpc service port
	

Response Result:

::

	{
	    "id": "4", 
	    "result": "null"
	}

Return value:

null:



Update NTP time
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "2", 
	    "method": "ntp_update_time"
	}

Request method : ntp_update_time

Request parameter : null
	

Response Result:

::

	{
	    "id": "5", 
	    "result": "null"
	}

Return value:

null:



Displays the hard disk space occupied by the current data
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "2", 
	    "method": "disk_usage"
	}

Request method : disk_usage

Request parameter : null
	

Response Result:

::

	{
	    "id": "2", 
	    "result": {
	        "logs": "4085001", 
	        "mail_client": null, 
	        "blockchain": "3482597", 
	        "wallets": {
	            ".backups": "3237", 
	            "op": "402051"
	        }, 
	        "network_peers": "289497", 
	        "dac_state": "7642885", 
	        "mail_server": null, 
	        "total": "16171905"
	    }
	}

Return value:

blockchain:  chain data space

dac_state: Local data space

logs: The log space

mail_client: Reserved field

mail_server: Reserved field

network_peers: Network connection pool space

wallets: Wallet folder, the following item is related to your local wallet

.backups: Backup space

op:  wallet named op occupied space

total: Total occupancy space


Gets all the detailed transaction information for the specified block
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "block"
	    ], 
	    "id": "2", 
	    "method": "blockchain_get_block_transactions"
	}

Request method : blockchain_get_block_transactions

Request parameter : block id or block number
	

Response Result:

::

	{
	    "id": "2", 
	    "result": [
	        [
	            "7e8b7797d42d1ed8f8b1beb3e92f77ae6842c6a3", 
	            {
	                "withdraws": [
	                    [
	                        "0", 
	                        "10000001000"
	                    ]
	                ], 
	                "imessage_length": "0", 
	                "deltas": [
	                    [
	                        "0", 
	                        [
	                            [
	                                "0", 
	                                "-10000001000"
	                            ]
	                        ]
	                    ], 
	                    [
	                        "1", 
	                        [
	                            [
	                                "0", 
	                                "10000000000"
	                            ]
	                        ]
	                    ]
	                ], 
	                "required_fees": {
	                    "asset_id": "0", 
	                    "amount": "0"
	                }, 
	                "alt_fees_paid": {
	                    "asset_id": "0", 
	                    "amount": "0"
	                }, 
	                "deposits": [
	                    [
	                        "0", 
	                        "10000000000"
	                    ]
	                ], 
	                "yield": [], 
	                "trx": {
	                    "ttc_inport_asset": {
	                        "asset_id": "0", 
	                        "amount": "10000000000"
	                    }, 
	                    "operations": [
	                        {
	                            "type": "withdraw_op_type", 
	                            "data": {
	                                "claim_input_data": "", 
	                                "amount": "10000001000", 
	                                "balance_id": "TTCQJ2gaD8RiKpiWRcT3AAEj4vr5eAJpXj52"
	                            }
	                        }, 
	                        {
	                            "type": "deposit_op_type", 
	                            "data": {
	                                "amount": "10000000000", 
	                                "condition": {
	                                    "asset_id": "0", 
	                                    "slate_id": "0", 
	                                    "type": "withdraw_signature_type", 
	                                    "data": {
	                                        "owner": "TTC6b7RN33FnT5MHPNwXqwWZBFZ17ArA3wm3"
	                                    }
	                                }
	                            }
	                        }
	                    ], 
	                    "signatures": [
	                        "2004f4f30c748da49ddf94468fcfbff02c72f9ac5784d56b9db5efc1d5470182034a8eb3866f42ca84013b218193bf4f3dfb079e1c605ff1939df2a5750ee72401"
	                    ], 
	                    "expiration": "2016-03-28T08:00:48", 
	                    "ttc_account": "TTC6b7RN33FnT5MHPNwXqwWZBFZ17ArA3wm3fffffffffffffffffffffffffffffff1"
	                }, 
	                "signed_keys": [], 
	                "chain_location": {
	                    "trx_num": "0", 
	                    "block_num": "5533"
	                }, 
	                "delegate_vote_deltas": [], 
	                "balance": [
	                    [
	                        "0", 
	                        "1000"
	                    ]
	                ]
	            }
	        ]
	    ]
	}

Return value:

Before trx data, no data name: trade order number

trx: Structure type name

signed_keys: Reserved field

deposits: Accounting for assets

withdraws:Out of assets

yield: Reserved parameter

deltas: Reserved parameter

required_fees: Reserved parameter

alt_fees_paid: Reserved parameter

balance: Reserved parameter

delegate_vote_deltas: Reserved parameter

imessage_length: Remarks length

chain_location: Transaction location structure



Gets the account details for the specified account name or ID
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "account"
	    ], 
	    "id": "2", 
	    "method": "blockchain_get_account"
	}

Request method : blockchain_get_account

Request parameter : account name, account id, account address or account public key 
	

Response Result:

::

	{
	    "id": "2", 
	    "result": {
	        "owner_key": "TTC8KkneVfc6iaR9grBpRij5wqhPK5XwxS7ohNhJ5tH8DEoL77j32",
	        "name": "TTC1",
	        "registration_date": "2015-05-31T16:00:00", 
	        "last_update": "2015-05-31T16:00:00", 
	        "delegate_info": {
	            "pay_balance": "20090309", 
	            "total_burned": "0", 
	            "blocks_missed": "810", 
	            "pay_rate": "100", 
	            "votes_for": "20090309", 
	            "blocks_produced": "58", 
	            "last_block_num_produced": "5782", 
	            "total_paid": "20090309", 
	            "signing_key_history": [
	                [
	                    "0", 
	                    "TTC8KkneVfc6iaR9grBpRij5wqhPK5XwxS7ohNhJ5tH8DEoL77j32"
	                ]
	            ], 
	            "next_secret_hash": "7e7f255f175ffaf52397084f6ca747674088f176"
	        }, 
	        "public_data": null, 
	        "id": "2", 
	        "active_key_history": [
	            [
	                "2015-05-31T16:00:00", 
	                "TTC8KkneVfc6iaR9grBpRij5wqhPK5XwxS7ohNhJ5tH8DEoL77j32"
	            ]
	        ]
	    }
	}

Return value:

id: Account ID

name: account name

public_data: public data added when registering the account

owner_key: Owner public key

active_key_history: Active public key history

registration_date: Registration time

last_update:  Last updated account information

delegate_info: delegate  information structure

meta_data: Reserved field



Query blockchain information and parameters
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "1", 
	    "method": "blockchain_get_info"
	}

Request method : blockchain_get_info

Request parameter : null
	

Response Result:

::

	{
	    "id": "1", 
	    "result": {
	        "db_version": "201", 
	        "symbol_size_min": "3", 
	        "block_interval": "10", 
	        "max_delegate_pay_issued_per_block": "507977", 
	        "memo_size_max": "51", 
	        "symbol_size_max": "8", 
	        "statistics_enabled": false, 
	        "max_pending_queue_size": "1000", 
	        "genesis_timestamp": "2015-05-31T16:00:00", 
	        "delegate_num": "99", 
	        "name_size_max": "63", 
	        "symbol": "TTC",
	        "short_symbol_asset_reg_fee": "50000000000", 
	        "data_size_max": "65536", 
	        "address_prefix": "TTC",
	        "max_trx_per_second": "100", 
	        "asset_shares_max": "1000000000000000", 
	        "long_symbol_asset_reg_fee": "50000000", 
	        "blockchain_id": "94beaf23764844cae3e1f368273d0dddc8bc06c575c0cf6578bcb1f2012e7694", 
	        "name": "TTCs",
	        "max_delegate_reg_fee": "122181818", 
	        "relay_fee": "1000"
	    }
	}

Return value:

blockchain_id: Genesis id number

name: blockchain name

symbol: asset symbol

address_prefix: address prefix

db_version: blockchain database version

genesis_timestamp: Creation time of cGenesis

block_interval: Block time interval

delegate_num: number of delegate

max_delegate_pay_issued_per_block: maximum number of TTCs delegate can receive

max_delegate_reg_fee: The cost of registration as delegate

name_size_max: maximum length limit of user name

memo_size_max: Remarks length limit

data_size_max: The maximum length of the user's public data

symbol_size_max: The maximum length of the asset symbol

symbol_size_min: The minimum length of the asset symbol

asset_shares_max: The maximum number of assets issued

short_symbol_asset_reg_fee: Minimum registration symbol registration fee

long_symbol_asset_reg_fee: Maximum registration symbol registration fee

statistics_enabled: is open the statistical mode

relay_fee: The required fee

max_pending_queue_size: Area queue maximum length

max_trx_per_second: Maximum number of transactions per second



Returns a snapshot of the current underlying asset allocation
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "filename"
	    ], 
	    "id": "2", 
	    "method": "blockchain_generate_snapshot"
	}

Request method : blockchain_generate_snapshot

Request parameter : Export the location where the asset document is stored
	

Response Result:

::

	{
	    "id": "2", 
	    "result": null
	}

Return value:

null:



Returns whether or not the local block chain has been synchronized with the network
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "2", 
	    "method": "blockchain_is_synced"
	}

Request method : blockchain_is_synced

Request parameter : null
	

Response Result:

::

	{
	    "id": "2", 
	    "result": true
	}

Return value:

result: Whether it is in sync(Synchronized blocks within two days are not synchronized)



Query block number
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "2", 
	    "method": "blockchain_get_block_count"
	}

Request method : blockchain_get_block_count

Request parameter : null
	

Response Result:

::

	{
	    "id": "2", 
	    "result": "5534"
	}

Return value:

result: The current block number of blocks



Gets the balance record under the specified balance_id
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:balance_id can be viewed from the 'withdraw_op_type' of the generated transaction when it is transferred
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "balance_id"
	    ], 
	    "id": "2", 
	    "method": "blockchain_get_balance"
	}

Request method : blockchain_get_balance

Request parameter : The balance id to be queried
	

Response Result:

::

	{
	    "id": "2", 
	    "result": {
	        "deposit_date": "2016-06-20T05:32:35", 
	        "snapshot_info": {
	            "original_address": "TTCL34D5qcbMU56mRRByLFVvDVVEvZe9sVn6",
	            "original_balance": "1000000000000"
	        }, 
	        "last_update": "2016-06-20T06:21:30", 
	        "meta_data": "null", 
	        "balance": "196009", 
	        "condition": {
	            "asset_id": "0", 
	            "slate_id": "0", 
	            "type": "withdraw_signature_type", 
	            "data": {
	                "owner": "TTCL34D5qcbMU56mRRByLFVvDVVEvZe9sVn6"
	            }
	        }
	    }
	}

Return value:

condition: Amount information structure

balance: Balance quantity

snapshot_info: Creation of asset structure

deposit_date: Balance increase time

last_update: The most recent update time

meta_data: Reserved field



List the balance that is owned by the specified public key
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "public_key"
	    ], 
	    "id": "2", 
	    "method": "blockchain_list_key_balances"
	}

Request method : blockchain_list_key_balances

Request parameter : The public key to query the balance
	

Response Result:

::

	{
	    "id": "2", 
	    "result": [
	        [
	            "TTCNXWy8jSAkuWRoxLDKU7JL7CT6k7kP7Afc",
	            {
	                "deposit_date": "1970-01-01T00:04:50", 
	                "snapshot_info": {
	                    "original_address": "TTC5iSiYMm1fkUtTcW7dQSVNDFZEGXNgj4fy",
	                    "original_balance": "1000000000000"
	                }, 
	                "last_update": "2016-03-28T06:58:50", 
	                "meta_data": null, 
	                "balance": "1000000200000", 
	                "condition": {
	                    "asset_id": "0", 
	                    "slate_id": "0", 
	                    "type": "withdraw_signature_type", 
	                    "data": {
	                        "owner": "TTC5iSiYMm1fkUtTcW7dQSVNDFZEGXNgj4fy"
	                    }
	                }
	            }
	        ]
	    ]
	}

Return value:

In all data before the data, there is no data name for the field: balanceid

condition: Amount information structure

balance: Balance quantity

snapshot_info: Creation of asset structure

deposit_date: Balance increase time

last_update: The most recent update time

meta_data: Reserved field



Return current trustee information of current round in the order of the signed blocks
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:More content, may use ordinary tools no way to receive all the return.
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "start_num", 
	        "limit_num"
	    ], 
	    "id": "2", 
	    "method": "blockchain_list_active_delegates"
	}

Request method : blockchain_list_active_delegates

Request parameter : Start sequence number, return quantity
	

Response Result:

::

	{
	    "id": "2", 
	    "result": [
	        {
	            "owner_key": "TTC8XfYBVvdxrSFbW2Ehtzhf1vAQNq21nTiMpyE6QGvoydtY2aXcZ",
	            "name": "TTC42",
	            "registration_date": "2015-05-31T16:00:00", 
	            "last_update": "2015-05-31T16:00:00", 
	            "delegate_info": {
	                "pay_balance": "19586615", 
	                "total_burned": "0", 
	                "blocks_missed": "809", 
	                "pay_rate": "100", 
	                "votes_for": "19586615", 
	                "blocks_produced": "57", 
	                "last_block_num_produced": "5737", 
	                "total_paid": "19586615", 
	                "signing_key_history": [
	                    [
	                        "0", 
	                        "TTC8XfYBVvdxrSFbW2Ehtzhf1vAQNq21nTiMpyE6QGvoydtY2aXcZ"
	                    ]
	                ], 
	                "next_secret_hash": "7bf4dcb7b7e7887053638b5ac9d637930a91a535"
	            }, 
	            "public_data": null, 
	            "id": "43", 
	            "active_key_history": [
	                [
	                    "2015-05-31T16:00:00", 
	                    "TTC8XfYBVvdxrSFbW2Ehtzhf1vAQNq21nTiMpyE6QGvoydtY2aXcZ"
	                ]
	            ]
	        }
	    ]
	}

Return value:

id: Account ID

name: account name

public_data: Public data added when registering the account

owner_key: Owner public key

active_key_history: Active public key history

registration_date: Registration time

last_update:  Last updated account information

delegate_info: delegate  information structure



Returns the registered account name, starting with the specified account name until the maximum number of available limits
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "first", 
	        "limit"
	    ], 
	    "id": "2", 
	    "method": "blockchain_list_accounts"
	}

Request method : blockchain_list_accounts

Request parameter : n fact, find the first letter, the default is "a". find the number, the default is 20
	

Response Result:

::

	{
	    "id": "2", 
	    "result": [
	        {
	            "owner_key": "TTC6vBWNEsnNS5rMXSHsXLDxp3mMyBZd5M9gAgtMbvLevHQVrCgYY",
	            "name": "TTC0",
	            "registration_date": "2015-05-31T16:00:00", 
	            "last_update": "2015-05-31T16:00:00", 
	            "delegate_info": {
	                "pay_balance": "20288476", 
	                "total_burned": "0", 
	                "blocks_missed": "804", 
	                "pay_rate": "100", 
	                "votes_for": "20288476", 
	                "blocks_produced": "64", 
	                "last_block_num_produced": "5645", 
	                "total_paid": "20288476", 
	                "signing_key_history": [
	                    [
	                        "0", 
	                        "TTC6vBWNEsnNS5rMXSHsXLDxp3mMyBZd5M9gAgtMbvLevHQVrCgYY"
	                    ]
	                ], 
	                "next_secret_hash": "4e549122f53e486cd2f5741965bcb030f6c714bc"
	            }, 
	            "public_data": null, 
	            "id": "1", 
	            "active_key_history": [
	                [
	                    "2015-05-31T16:00:00", 
	                    "TTC6vBWNEsnNS5rMXSHsXLDxp3mMyBZd5M9gAgtMbvLevHQVrCgYY"
	                ]
	            ]
	        }
	    ]
	}

Return value:

id: Account ID

name : account name

public_data: Public data added when registering the account

owner_key: Owner public key

active_key_history: Active public key history

registration_date: Registration time

last_update:  Last updated account information

delegate_info: delegate  information structure

meta_data: Reserved field



Returns a transaction list message that has not yet been taken into the block
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "2", 
	    "method": "blockchain_list_pending_transactions"
	}

Request method : blockchain_list_pending_transactions

Request parameter : null
	

Response Result:

::

	{
	    "id": "2", 
	    "result": [
	        {
	            "ttc_inport_asset": {
	                "asset_id": "0", 
	                "amount": "100000"
	            }, 
	            "operations": [
	                {
	                    "type": "withdraw_op_type", 
	                    "data": {
	                        "claim_input_data": "", 
	                        "amount": "101000", 
	                        "balance_id": "TTC5wSdtt5BF3oDXAYXoRJdWnw6Dzr8pc9vC"
	                    }
	                }, 
	                {
	                    "type": "deposit_op_type", 
	                    "data": {
	                        "amount": "100000", 
	                        "condition": {
	                            "asset_id": "0", 
	                            "slate_id": "0", 
	                            "type": "withdraw_signature_type", 
	                            "data": {
	                                "owner": "TTC5iSiYMm1fkUtTcW7dQSVNDFZEGXNgj4fy"
	                            }
	                        }
	                    }
	                }
	            ], 
	            "signatures": [
	                "205c194f49a821cc7f9884356c89117332c3867967f09d22f0920a2deccf0a64a84c5252b0dde7972dfc905d407a3c8a7e74cf2f4dcad3741f3d63694541d741bf"
	            ], 
	            "expiration": "2016-03-28T08:43:34", 
	            "ttc_account": "TTC5iSiYMm1fkUtTcW7dQSVNDFZEGXNgj4fyffffffffffffffffffffffffffff0011"
	        }
	    ]
	}

Return value:

expiration: Transaction expiration time

ttc_account: Transaction credited party

ttc_inport_asset: Transaction crediting structure

operations: Operating structure

signatures: signatures



Get a detailed transaction on a block chain transfer
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "transaction_id_prefix", 
	        "exact"
	    ], 
	    "id": "2", 
	    "method": "blockchain_get_transaction"
	}

Request method : blockchain_get_transaction

Request parameter : Transaction id, Whether to find out exactly, the default is false
	

Response Result:

::

	{
	    "id": "2", 
	    "result": [
	        "66294adf274750ba2cd312b13aa81cc0bee71ba6", 
	        {
	            "withdraws": [
	                [
	                    "0", 
	                    "100000001000"
	                ]
	            ], 
	            "imessage_length": "0", 
	            "deltas": [
	                [
	                    "0", 
	                    [
	                        [
	                            "0", 
	                            "-100000001000"
	                        ]
	                    ]
	                ], 
	                [
	                    "1", 
	                    [
	                        [
	                            "0", 
	                            "100000000000"
	                        ]
	                    ]
	                ]
	            ], 
	            "required_fees": {
	                "asset_id": "0", 
	                "amount": "0"
	            }, 
	            "alt_fees_paid": {
	                "asset_id": "0", 
	                "amount": "0"
	            }, 
	            "deposits": [
	                [
	                    "0", 
	                    "100000000000"
	                ]
	            ], 
	            "yield": [], 
	            "trx": {
	                "ttc_inport_asset": {
	                    "asset_id": "0", 
	                    "amount": "0"
	                }, 
	                "operations": [
	                    {
	                        "type": "withdraw_op_type", 
	                        "data": {
	                            "claim_input_data": "", 
	                            "amount": "100000001000", 
	                            "balance_id": "TTCMPUsyR4Qiomu2r6GvGNFyNxoZQB7oJXfr"
	                        }
	                    }, 
	                    {
	                        "type": "deposit_op_type", 
	                        "data": {
	                            "amount": "100000000000", 
	                            "condition": {
	                                "asset_id": "0", 
	                                "slate_id": "0", 
	                                "type": "withdraw_signature_type", 
	                                "data": {
	                                    "owner": "TTCGb4Dbh82jY8Q5JrvNmCcsjgdZcawCD5Ex"
	                                }
	                            }
	                        }
	                    }
	                ], 
	                "signatures": [
	                    "1f109eaf6f4e95914b6a51bb5c8cbf67992ed3b9d575da7a34ed1f63aa1b0eeea7571ce2cebf18c253d1e4208de1f30f7c61d2cfcdbe772e2856e1a4f0d791b66e"
	                ], 
	                "expiration": "2016-03-22T08:11:00", 
	                "ttc_account": ""
	            }, 
	            "signed_keys": [], 
	            "chain_location": {
	                "trx_num": "0", 
	                "block_num": "1277"
	            }, 
	            "delegate_vote_deltas": [], 
	            "balance": [
	                [
	                    "0", 
	                    "1000"
	                ]
	            ]
	        }
	    ]
	}

Return value:

trx_id: Transaction id

trx: Detailed transaction data

signed_keys: signature

deposits: Accounting for assets

withdraws:Out of assets

yield: Reserved parameter

deltas: Reserved parameter

required_fees: Reserved field

alt_fees_paid: Reserved field

balance: Reserved field

delegate_vote_deltas: Reserved parameter

imessage_length: Remarks length

chain_location: Transaction location structure



Query the details of the specified delegate agent
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "first", 
	        "count"
	    ], 
	    "id": "26", 
	    "method": "blockchain_list_delegates"
	}

Request method : blockchain_list_delegates

Request parameter : The starting agent rank number, the number of entries returned
	

Response Result:

::

	{
	    "id": "17", 
	    "result": [
	        {
	            "owner_key": "TTC7zcWtxPx252gZhjYmj5nyKKZ6agzkVVc8E4HKBVDiiswZ2syS3",
	            "name": "alp4",
	            "last_update": "2015-05-31T16:00:00", 
	            "delegate_info": {
	                "pay_balance": "557579636", 
	                "total_burned": "0", 
	                "blocks_missed": "4865", 
	                "pay_rate": "100", 
	                "votes_for": "1030973384311", 
	                "blocks_produced": "5195", 
	                "last_block_num_produced": "494448", 
	                "total_paid": "587328636", 
	                "signing_key_history": [
	                    [
	                        "0", 
	                        "TTC7zcWtxPx252gZhjYmj5nyKKZ6agzkVVc8E4HKBVDiiswZ2syS3"
	                    ]
	                ], 
	                "next_secret_hash": "feab43c718df5bb693b3a54b855ecd7bd834c4a7"
	            }, 
	            "public_data": "null", 
	            "registation_date": "2015-05-31T16:00:00", 
	            "id": "5", 
	            "active_key_history": [
	                [
	                    "2015-05-31T16:00:00", 
	                    "TTC7zcWtxPx252gZhjYmj5nyKKZ6agzkVVc8E4HKBVDiiswZ2syS3"
	                ]
	            ]
	        }
	    ]
	}

Return value:

id: Account ID

name: account name

public_data: Public data added when registering the account

owner_key: Owner public key

active_key_history: Active public key history

registration_date: Registration time

last_update:  Last updated account information

delegate_info: delegate  information structure

meta_data: Reserved field



Returns the details of the specified range of blocks
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "max_block_num", 
	        "limit"
	    ], 
	    "id": "26", 
	    "method": "blockchain_list_blocks"
	}

Request method : blockchain_list_blocks

Request parameter : When the block number is displayed, the number of entries is returned
	

Response Result:

::

	{
	    "latency": "0", 
	    "user_transaction_ids": [
	        "f7f984386f2cee6cb806e06ab1a5e955c04273a3", 
	        "f7f8b372d625c99267b5e7e04c42ac004885b102", 
	        "f7f0d80434c1f7618a084c5423e29bbd2ce49a1e", 
	        "f7ee970b029dde86ca053ce0976e3bc6112a0c78", 
	        "f7eac3727f9c4c0d49ee9d8116cfe0e7f5092254", 
	        "f7eab200cdee190c92a794253318ae533ca901d0", 
	        "f7e547f8bce59018a8fe504fae182548d560770b", 
	        "f7e03864045770f8a2eca96b2680a5cd7953a0b4", 
	        "f7db395033d208ba338391edb9f027c9a396dd48", 
	        "f7db2bbe686d4eb8682ad828a8f0e7e060e3b523", 
	        "f7dad29228c81987496edc3b3413cfc825b409e4", 
	        "f7c6af7fe6f9422b137af95cbf869dff89027cce", 
	        "f0b3bffd483f2a243502f83b143e1baa90833013", 
	        "cb896307d7cc7651a3e1f3853b65d254b2958b20", 
	        "975f8398135d3b90c9662a516d323a2e06b82fd1", 
	        "876de39d1f96f493788fa946d95a86c330d40669", 
	        "86ce132074b4735cfa7fdc89b3440527818c7b27", 
	        "6c56aa35222d8fb891ab0a073a80a14ffaf6360f", 
	        "6049c81451031be300a9eb5b928f3b9369955cec", 
	        "534c39ed29294e00e73262b56311cc7f715817a0", 
	        "48f1ef67e7806cb5d8550cc7bc94fdd9d871ba00", 
	        "3852885967c249ea3f52b25a71e7b62e3093ffe9", 
	        "127b092d5df103a3bb5a185d48269befabcb5108", 
	        "01628269891f5293672b038a3e9f681211650490"
	    ], 
	    "delegate_signature": "206631beee6020ee31c99c93e16171db60560263acbaa38d81c2cef2a79989d4ea53a019ba35f213a81eb66f07b250c9ac3e53b284ad32737f56309d8fa05889ee", 
	    "signee_fees_collected": "0", 
	    "processing_time": "0", 
	    "timestamp": "2016-03-11T08:32:20", 
	    "signee_shares_issued": "0", 
	    "block_num": "1020", 
	    "previous_secret": "f0f100f90dc73c2ef9d0bd398e9513d65b2f51a7", 
	    "next_secret_hash": "b37d87e09b6d112c220a9651db24edd475c9f465", 
	    "signee_fees_destroyed": "0", 
	    "transaction_digest": "bdaae5cf29f597a1ec84435377e7e30f351c44abd553f4394dc7febf6b7139ce", 
	    "random_seed": "0000000000000000000000000000000000000000", 
	    "block_size": "3886", 
	    "id": "699a6bd96d6df589a63bc61621ad3a82a8016081", 
	    "previous": "87f4ffd55d673ebb99d9d377afb957ccb35cb0ac"
	}

Return value:

previous: The hash of the previous block

block_num: block number of the current block

timestamp: Block release time

transaction_digest: All blocks in the Transaction id hash

next_secret_hash: The next round out of the certificate

previous_secret: This round out of the certificate

delegate_signature: delegate signature

user_transaction_ids: The block contains the set of IDs for all transactions

id: Block ID

block_size: block size

latency: Reserved field

signee_shares_issued: Reserved field

signee_fees_collected: Reserved field

signee_fees_destroyed: Reserved field

random_seed: Reserved field

processing_time: Reserved field



Query who is the signature agent for the specified block
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "block"
	    ], 
	    "id": "26", 
	    "method": "blockchain_get_block_signee"
	}

Request method : blockchain_get_block_signee

Request parameter : Block hash or block height
	

Response Result:

::

	{
	    "id": "26", 
	    "result": "alp4"
	}

Return value:

account_name: delegate name



Add or remove a node's connection
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "node", 
	        "command"
	    ], 
	    "id": "1", 
	    "method": "network_add_node"
	}

Request method : network_add_node

Request parameter : Add or remove the ip and port number, for the operation of the node
	

Response Result:

::

	{
	    "id": "1", 
	    "result": "null"
	}

Return value:

null:



Gets the current number of nodes for the node
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "1", 
	    "method": "network_get_connection_count"
	}

Request method : network_get_connection_count

Request parameter : null
	

Response Result:

::

	{
	    "id": "1", 
	    "result": "1"
	}

Return value:

result field after the colon: the number of current node connections



Returns the information of each node that has been connected
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:Returns a set of data
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "hide_firewalled_nodes"
	    ], 
	    "id": "1", 
	    "method": "network_get_peer_info"
	}

Request method : network_get_peer_info

Request parameter : Whether to output only the firewall after the node, the default false
	

Response Result:

::

	{
	    "id": "2", 
	    "result": [
	        {
	            "lastsend": "1466573207", 
	            "ttchain_git_revision_sha": "1.2 (same as ours)",
	            "conntime": "2016-06-22T05:22:33", 
	            "addrlocal": "10.23.3.161:60555", 
	            "ttchain_git_revision_age": "1 years6 months ago (same as ours)",
	            "fc_git_revision_age": "46 years ago (same as ours)", 
	            "current_head_block_number": "689", 
	            "fc_git_revision_sha": "0 (same as ours)", 
	            "pingwait": "", 
	            "current_head_block": "1dea351ba0d6fc22958ebc1e45ba9c68c7e20333", 
	            "addr": "119.254.161.28:60555", 
	            "ttchain_git_revision_unix_timestamp": "2015-01-08T18:02:32",
	            "lastrecv": "1466573207", 
	            "platform": "win32", 
	            "firewall_status": "firewalled", 
	            "pingtime": "", 
	            "bytesrecv": "7696", 
	            "bytessent": "2288", 
	            "startingheight": "", 
	            "inbound": false, 
	            "version": "", 
	            "current_head_block_time": "2016-06-22T05:26:50", 
	            "services": "00000001", 
	            "subver": "ttchain_client",
	            "syncnode": "", 
	            "fc_git_revision_unix_timestamp": "1970-01-01T00:00:00", 
	            "banscore": ""
	        }
	    ]
	}

Return value:

addr: Connection of the node's ip and port

addrlocal: he local node's ip and port

services: Reserved field

lastsend: Last send time

lastrecv: Last receive time

bytessent: send bytes

bytesrecv: receive bytes

conntime: Connection time

pingtime: Reserved field

pingwait: Reserved field

version: version

subver: Reserved field

inbound: Reserved field

firewall_status: Firewall status

startingheight: Reserved field

banscore: Reserved field

syncnode: Reserved field

ttchain_git_revision_sha: git version

ttchain_git_revision_unix_timestamp: git timestamp

ttchain_git_revision_age: length of git version

fc_git_revision_sha: The version of the fc library

fc_git_revision_unix_timestamp:  fc library git timestamp

fc_git_revision_age: length of fc git version

platform: platform

current_head_block_number: The height of the current block

current_head_block:  current block hash

current_head_block_time: current block time



Get the current network information
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "26", 
	    "method": "network_get_info"
	}

Request method : network_get_info

Request parameter : null
	

Response Result:

::

	{
	    "id": "26", 
	    "result": {
	        "listening_on": "0.0.0.0:60696", 
	        "node_public_key": "03dafc378c8a22d136b338a3913bb0acbe551f970d0af1d0955861a7103eb17252", 
	        "node_id": "6819fe268e09df3ce4a90ab543fb98cc42390a986e5f5037921e911b437b06b23b", 
	        "firewalled": "firewalled"
	    }
	}

Return value:

listening_on: The client listens on the address and port

node_public_key: The public key used by the encrypted communication between the node and the node (the program starts up for the first time)

node_id: Each time you start the client, you will regenerate one, so that you can connect to the same node multiple times

firewalled: Whether it is behind a firewall



Gets a list of potential connection points
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "26", 
	    "method": "network_list_potential_peers"
	}

Request method : network_list_potential_peers

Request parameter : null
	

Response Result:

::

	{
	    "id": "26", 
	    "result": [
	        {
	            "endpoint": "59.108.127.182:60666", 
	            "last_connection_attempt_time": "2016-06-22T02:17:47", 
	            "last_error": {
	                "message": "unspecified", 
	                "code": "0", 
	                "name": "exception", 
	                "stack": [
	                    {
	                        "data": {
	                            "message": "?????????????(Ð­??/??????/???)??????????Î¡?"
	                        }, 
	                        "context": {
	                            "thread_name": "asio", 
	                            "level": "error", 
	                            "timestamp": "2016-06-21T04:16:03", 
	                            "hostname": "", 
	                            "file": "asio.cpp", 
	                            "line": "60", 
	                            "method": "fc::asio::detail::error_handler"
	                        }, 
	                        "format": "${message} "
	                    }
	                ]
	            }, 
	            "number_of_failed_connection_attempts": "5", 
	            "last_seen_time": "2016-06-22T05:18:17", 
	            "last_connection_disposition": "last_connection_succeeded", 
	            "number_of_successful_connection_attempts": "10"
	        }, 
	        {
	            "endpoint": "119.254.161.28:60666", 
	            "last_connection_attempt_time": "2016-06-22T02:17:49", 
	            "last_error": {
	                "message": "unspecified", 
	                "code": "0", 
	                "name": "exception", 
	                "stack": [
	                    {
	                        "data": {
	                            "peer": "119.254.161.28:60666", 
	                            "status": "connecting", 
	                            "timeout": "10", 
	                            "sent": "0", 
	                            "received": "0"
	                        }, 
	                        "context": {
	                            "thread_name": "p2p", 
	                            "level": "warn", 
	                            "timestamp": "2016-06-20T06:55:21", 
	                            "hostname": "", 
	                            "file": "Node.cpp", 
	                            "line": "1256", 
	                            "method": "ttchain::net::detail::NodeImpl::terminate_inactive_connections_loop"
	                        }, 
	                        "format": "Terminating handshaking connection due to inactivity of ${timeout} seconds.  Negotiating status: ${status}, bytes sent: ${sent}, bytes received: ${received}"
	                    }
	                ]
	            }, 
	            "number_of_failed_connection_attempts": "5", 
	            "last_seen_time": "2016-06-22T05:18:17", 
	            "last_connection_disposition": "last_connection_succeeded", 
	            "number_of_successful_connection_attempts": "10"
	        }
	    ]
	}

Return value:

endpoint: Potential node IP

last_seen_time: last ocurance node time

last_connection_disposition: Last connection status

last_connection_attempt_time: Last attempt Connection time

number_of_successful_connection_attempts: Number of successful connections

number_of_failed_connection_attempts: Number of failed connections

last_error: Reserved field



Query UPNP basic information
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "26", 
	    "method": "network_get_upnp_info"
	}

Request method : network_get_upnp_info

Request parameter : null
	

Response Result:

::

	{
	    "id": "26", 
	    "result": {
	        "external_ip": "0.0.0.0", 
	        "upnp_enabled": true, 
	        "mapped_port": "0"
	    }
	}

Return value:

upnp_enabled: is start upnp

external_ip: Local monitoring IP

mapped_port: Map port



Create a wallet with the specified name
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "wallet_name", 
	        "password", 
	        ""
	    ], 
	    "id": "3", 
	    "method": "wallet_create"
	}

Request method : wallet_create

Request parameter : wallet name and wallet password
	

Response Result:

::

	{
	    "id": "1", 
	    "result": "null"
	}

Return value:

null:



Get wallet information
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "1", 
	    "method": "wallet_get_info"
	}

Request method : wallet_get_info

Request parameter : null
	

Response Result:

::

	{
	    "id": "1", 
	    "result": {
	        "scan_progress": "1.00000000000000000", 
	        "data_dir": "e:/alptest/3/wallets", 
	        "name": "op", 
	        "unlocked": true, 
	        "last_scanned_block_num": null, 
	        "open": true, 
	        "transaction_expiration_secs": "3600", 
	        "unlocked_until_timestamp": "2016-03-28T07:29:49", 
	        "automatic_backups": true, 
	        "version": "109", 
	        "transaction_scanning_enabled": false, 
	        "transaction_fee": {
	            "asset_id": "0", 
	            "amount": "1000"
	        }, 
	        "num_scanning_threads": "4", 
	        "unlocked_until": "3598", 
	        "last_scanned_block_timestamp": null
	    }
	}

Return value:

data_dir: file path

num_scanning_threads: Number of scan threads

open: Is wallet open

name: wallet name

automatic_backups: whether turn on automatic backup

transaction_scanning_enabled: Whether the transaction scan is on

last_scanned_block_num: last scanned block number

last_scanned_block_timestamp: last scanned block timestamp

transaction_fee: default transaction fee

transaction_expiration_secs: transaction expiration time

unlocked: whether wallet unlock

unlocked_until:  number of seconds left in the wallet unlock state

unlocked_until_timestamp: timestamp re-lock the wallet

scan_progress: Scan the process

version: wallet version



If the current wallet is open to close it
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "6", 
	    "method": "wallet_close"
	}

Request method : wallet_close

Request parameter : null
	

Response Result:

::

	{
	    "id": "6", 
	    "result": "null"
	}

Return value:

null:

If the current wallet is unlock to lock it
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "6", 
	    "method": "wallet_lock"
	}

Request method : wallet_lock

Request parameter : null
	

Response Result:

::

	{
	    "id": "6", 
	    "result": "null"
	}

Return value:

null:

Open the wallet with the specified name
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:The wallet name of the currently specified name already exists
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "wallet_name"
	    ], 
	    "id": "2", 
	    "method": "wallet_open"
	}

Request method : wallet_open 

Request parameter : wallet name
	

Response Result:

::

	{
	    "id": "6", 
	    "result": "null"
	}

Return value:

null:



Unlock the private key in the wallet to enable the payment operation
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:wallet open
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "timeout", 
	        "password"
	    ], 
	    "id": "17", 
	    "method": "wallet_unlock"
	}

Request method : wallet_unlock

Request parameter : Unlock expiration time, password
	

Response Result:

::

	{
	    "id": "4", 
	    "result": "op"
	}

Return value:

null:



Import the private key into the local wallet and return the actual account it imported
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:The wallet is open and the wallet is unlocked
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "wif_key_to_import", 
	        "account_name", 
	        "create_account", 
	        "wallet_rescan_blockchain"
	    ], 
	    "id": "5", 
	    "method": "wallet_import_private_key"
	}

Request method : wallet_import_private_key 

Request parameter : The private key to import, the name of the imported account, whether you need to create a new account, whether to rescan the new wallet
	

Response Result:

::

	{
	    "id": "5", 
	    "result": "aa"
	}

Return value:

result Colors Field: Import account name



Export the current wallet data as a JSON file
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:wallet open
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "filename"
	    ], 
	    "id": "7", 
	    "method": "wallet_backup_create"
	}

Request method : wallet_backup_create 

Request parameter : Backup storage path
	

Response Result:

::

	{
	    "id": "6", 
	    "result": "null"
	}

Return value:

null:



Use the backup JSON file to create (restore) a new wallet
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:null
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "filepath", 
	        "wallet_name", 
	        "password"
	    ], 
	    "id": "8", 
	    "method": "wallet_backup_restore"
	}

Request method : wallet_backup_restore

Request parameter : Wallet backup file path, wallet name, backup wallet secret password
	

Response Result:

::

	{
	    "id": "8", 
	    "result": "null"
	}

Return value:

null:



Set the wallet to open the automatic backup function and return to the state after the set
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:Wallet open, when you create an account, if automatic backup opened, it will automatically create a backup
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "enabled"
	    ], 
	    "id": "9", 
	    "method": "wallet_set_automatic_backups"
	}

Request method : wallet_set_automatic_backups

Request parameter : Whether to enable automatic backup function
	

Response Result:

::

	{
	    "id": "9", 
	    "result": false
	}

Return value:

result after the colon field:  the state of the current backup of the wallet is automatically open



Set the Transaction expiration time and return the expiration time after the setting
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:wallet open
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "per_sec"
	    ], 
	    "id": "10", 
	    "method": "wallet_set_transaction_expiration_time"
	}

Request method : wallet_set_transaction_expiration_time

Request parameter : timeout counted in seconds
	

Response Result:

::

	{
	    "id": "10", 
	    "result": "3600"
	}

Return value:

result after the colon field: the current transaction timeout



List the transaction history of the specified account
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:Open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "account_name", 
	        "asset_symbol", 
	        "limit", 
	        "start_block_num", 
	        "end_block_num"
	    ], 
	    "id": "11", 
	    "method": "wallet_account_transaction_history"
	}

Request method : wallet_account_transaction_history

Request parameter : The default value for the account name is empty, the default value of the asset is empty, The default value of upper limit is 0, the block number of starting query, default value is 0, the defualt value of the block number which ended query is -1, represents a transaction that returns to the current block
	

Response Result:

::

	{
	    "id": "26", 
	    "result": [
	        {
	            "is_market": false, 
	            "fee": {
	                "asset_id": "0", 
	                "amount": "1000"
	            }, 
	            "is_confirmed": true, 
	            "is_market_cancel": false, 
	            "timestamp": "2016-06-21T03:20:20", 
	            "is_virtual": false, 
	            "block_num": "462950", 
	            "ledger_entries": [
	                {
	                    "from_account": "alp6", 
	                    "amount": {
	                        "asset_id": "0", 
	                        "amount": "10000000000"
	                    }, 
	                    "running_balances": [
	                        [
	                            "sy234", 
	                            [
	                                [
	                                    "0", 
	                                    {
	                                        "asset_id": "0", 
	                                        "amount": "10000000000"
	                                    }
	                                ]
	                            ]
	                        ]
	                    ], 
	                    "memo": "", 
	                    "to_account": "sy234"
	                }
	            ], 
	            "trx_id": "78d148258f0488e12c7ad59d02a5700cd7cf194a", 
	            "expiration_timestamp": "2016-06-21T04:20:06"
	        }
	    ]
	}

Return value:

is_virtual: reserved field

is_confirmed: Whether the transaction is confirmed

is_market: reserved field

is_market_cancel: reserved field

trx_id: trasaction ID

block_num: The block where the transaction is confirmed

ledger_entries: Trading parsing

fee: Transaction fee

timestamp: Transaction create time 

expiration_timestamp: Transaction dead time



Check the transaction history according to the entry account
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "account_name", 
	        "asset_symbol", 
	        "limit", 
	        "transaction_type"
	    ], 
	    "id": "26", 
	    "method": "wallet_transaction_history_splite"
	}

Request method : wallet_transaction_history_splite

Request parameter : user name, asset identification, number limit,  tradeã€€type
	

Response Result:

::

	{
	    "id": "26", 
	    "result": [
	        {
	            "is_market": false, 
	            "fee": {
	                "asset_id": "0", 
	                "amount": "1000"
	            }, 
	            "is_confirmed": true, 
	            "is_market_cancel": false, 
	            "timestamp": "2016-06-21T03:20:20", 
	            "is_virtual": false, 
	            "block_num": "462950", 
	            "ledger_entries": [
	                {
	                    "from_account": "alp6", 
	                    "amount": {
	                        "asset_id": "0", 
	                        "amount": "10000000000"
	                    }, 
	                    "running_balances": [
	                        [
	                            "sy234", 
	                            [
	                                [
	                                    "0", 
	                                    {
	                                        "asset_id": "0", 
	                                        "amount": "10000000000"
	                                    }
	                                ]
	                            ]
	                        ]
	                    ], 
	                    "memo": "", 
	                    "to_account": "sy234"
	                }
	            ], 
	            "trx_id": "78d148258f0488e12c7ad59d02a5700cd7cf194a", 
	            "expiration_timestamp": "2016-06-21T04:20:06"
	        }
	    ]
	}

Return value:

is_virtual: reserved field

is_confirmed: Whether the transaction is confirmed

is_market: reserved field

is_market_cancel: reserved field

trx_id: trasaction ID

block_num: he block where the transaction is confirmed

ledger_entries: Trading parsing

fee: Transaction fee

timestamp: Transaction create time 

expiration_timestamp: Transaction dead time 



Get all error records in the current pending area
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite: open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "filepath"
	    ], 
	    "id": "26", 
	    "method": "wallet_get_pending_transaction_errors"
	}

Request method : wallet_get_pending_transaction_errors 

Request parameter : file path
	

Response Result:

::

	{
	    "id": "26", 
	    "result": [
	        [
	            "d128986f41ada51d4937171047acc33781c8f321", 
	            {
	                "message": "expired transaction", 
	                "code": "31010", 
	                "name": "expired_transaction", 
	                "stack": [
	                    {
	                        "data": {
	                            "_current_state->now()": "2016-06-23T09:07:50", 
	                            "trx_arg": {
	                                "ttc_inport_asset": {
	                                    "asset_id": "0", 
	                                    "amount": "0"
	                                }, 
	                                "operations": [
	                                    {
	                                        "type": "withdraw_op_type", 
	                                        "data": {
	                                            "claim_input_data": "", 
	                                            "amount": "101000", 
	                                            "balance_id": "TTC5Bf23THE4RoWzQqWAKn7PkmzJdgUWHDJV"
	                                        }
	                                    }, 
	                                    {
	                                        "type": "deposit_op_type", 
	                                        "data": {
	                                            "amount": "100000", 
	                                            "condition": {
	                                                "asset_id": "0", 
	                                                "slate_id": "0", 
	                                                "type": "withdraw_signature_type", 
	                                                "data": {
	                                                    "owner": "TTCM3rr9yc2MB5GQRdBVY2Q5baF1FRBU8gG6"
	                                                }
	                                            }
	                                        }
	                                    }
	                                ], 
	                                "signatures": [
	                                    "2044d58b6e469f0f075a2faade9d806477aaa134f749a1b9bce25e3455ab8b9f6015bcaa40cf74276fdcf084c6c76dc7e9918e20d5380bcf7591eb1db3ef21dc9f"
	                                ], 
	                                "expiration": "2016-06-23T09:03:43", 
	                                "ttc_account": ""
	                            }, 
	                            "expired_by_sec": "247"
	                        }, 
	                        "context": {
	                            "thread_name": "th_a", 
	                            "level": "error", 
	                            "timestamp": "2016-06-23T09:07:51", 
	                            "hostname": "", 
	                            "file": "TransactionEvaluationState.cpp", 
	                            "line": "152", 
	                            "method": "ttchain::blockchain::TransactionEvaluationState::evaluate"
	                        }, 
	                        "format": ""
	                    }, 
	                    {
	                        "data": {
	                            "trx_arg": {
	                                "ttc_inport_asset": {
	                                    "asset_id": "0", 
	                                    "amount": "0"
	                                }, 
	                                "operations": [
	                                    {
	                                        "type": "withdraw_op_type", 
	                                        "data": {
	                                            "claim_input_data": "", 
	                                            "amount": "101000", 
	                                            "balance_id": "TTC5Bf23THE4RoWzQqWAKn7PkmzJdgUWHDJV"
	                                        }
	                                    }, 
	                                    {
	                                        "type": "deposit_op_type", 
	                                        "data": {
	                                            "amount": "100000", 
	                                            "condition": {
	                                                "asset_id": "0", 
	                                                "slate_id": "0", 
	                                                "type": "withdraw_signature_type", 
	                                                "data": {
	                                                    "owner": "TTCM3rr9yc2MB5GQRdBVY2Q5baF1FRBU8gG6"
	                                                }
	                                            }
	                                        }
	                                    }
	                                ], 
	                                "signatures": [
	                                    "2044d58b6e469f0f075a2faade9d806477aaa134f749a1b9bce25e3455ab8b9f6015bcaa40cf74276fdcf084c6c76dc7e9918e20d5380bcf7591eb1db3ef21dc9f"
	                                ], 
	                                "expiration": "2016-06-23T09:03:43", 
	                                "ttc_account": ""
	                            }
	                        }, 
	                        "context": {
	                            "thread_name": "th_a", 
	                            "level": "warn", 
	                            "timestamp": "2016-06-23T09:07:51", 
	                            "hostname": "", 
	                            "file": "TransactionEvaluationState.cpp", 
	                            "line": "192", 
	                            "method": "ttchain::blockchain::TransactionEvaluationState::evaluate"
	                        }, 
	                        "format": ""
	                    }
	                ]
	            }
	        ], 
	        [
	            "ecc6cfb278e2f10e0d77f122fa840f2160dedcc4", 
	            {
	                "message": "expired transaction", 
	                "code": "31010", 
	                "name": "expired_transaction", 
	                "stack": [
	                    {
	                        "data": {
	                            "_current_state->now()": "2016-06-23T09:07:50", 
	                            "trx_arg": {
	                                "ttc_inport_asset": {
	                                    "asset_id": "0", 
	                                    "amount": "0"
	                                }, 
	                                "operations": [
	                                    {
	                                        "type": "withdraw_op_type", 
	                                        "data": {
	                                            "claim_input_data": "", 
	                                            "amount": "101000", 
	                                            "balance_id": "TTC5Bf23THE4RoWzQqWAKn7PkmzJdgUWHDJV"
	                                        }
	                                    }, 
	                                    {
	                                        "type": "deposit_op_type", 
	                                        "data": {
	                                            "amount": "100000", 
	                                            "condition": {
	                                                "asset_id": "0", 
	                                                "slate_id": "0", 
	                                                "type": "withdraw_signature_type", 
	                                                "data": {
	                                                    "owner": "TTCM3rr9yc2MB5GQRdBVY2Q5baF1FRBU8gG6"
	                                                }
	                                            }
	                                        }
	                                    }
	                                ], 
	                                "signatures": [
	                                    "1f4892d2720a119b861560422ed5bab49875e8d8a4cdca3fe40ab51e54ec9449c712fc54c34bc90976e94146975601e80adef099f7b3bfd974e31a192ff27f4c72"
	                                ], 
	                                "expiration": "2016-06-23T09:03:34", 
	                                "ttc_account": ""
	                            }, 
	                            "expired_by_sec": "256"
	                        }, 
	                        "context": {
	                            "thread_name": "th_a", 
	                            "level": "error", 
	                            "timestamp": "2016-06-23T09:07:51", 
	                            "hostname": "", 
	                            "file": "TransactionEvaluationState.cpp", 
	                            "line": "152", 
	                            "method": "ttchain::blockchain::TransactionEvaluationState::evaluate"
	                        }, 
	                        "format": ""
	                    }, 
	                    {
	                        "data": {
	                            "trx_arg": {
	                                "ttc_inport_asset": {
	                                    "asset_id": "0", 
	                                    "amount": "0"
	                                }, 
	                                "operations": [
	                                    {
	                                        "type": "withdraw_op_type", 
	                                        "data": {
	                                            "claim_input_data": "", 
	                                            "amount": "101000", 
	                                            "balance_id": "TTC5Bf23THE4RoWzQqWAKn7PkmzJdgUWHDJV"
	                                        }
	                                    }, 
	                                    {
	                                        "type": "deposit_op_type", 
	                                        "data": {
	                                            "amount": "100000", 
	                                            "condition": {
	                                                "asset_id": "0", 
	                                                "slate_id": "0", 
	                                                "type": "withdraw_signature_type", 
	                                                "data": {
	                                                    "owner": "TTCM3rr9yc2MB5GQRdBVY2Q5baF1FRBU8gG6"
	                                                }
	                                            }
	                                        }
	                                    }
	                                ], 
	                                "signatures": [
	                                    "1f4892d2720a119b861560422ed5bab49875e8d8a4cdca3fe40ab51e54ec9449c712fc54c34bc90976e94146975601e80adef099f7b3bfd974e31a192ff27f4c72"
	                                ], 
	                                "expiration": "2016-06-23T09:03:34", 
	                                "ttc_account": ""
	                            }
	                        }, 
	                        "context": {
	                            "thread_name": "th_a", 
	                            "level": "warn", 
	                            "timestamp": "2016-06-23T09:07:51", 
	                            "hostname": "", 
	                            "file": "TransactionEvaluationState.cpp", 
	                            "line": "192", 
	                            "method": "ttchain::blockchain::TransactionEvaluationState::evaluate"
	                        }, 
	                        "format": ""
	                    }
	                ]
	            }
	        ]
	    ]
	}

Return value:

transactionID: Transaction ID

Exception: reserved field, abnormal trading



Modify password
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:unlock the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "old_passphrase", 
	        "passphrase"
	    ], 
	    "id": "26", 
	    "method": "wallet_change_passphrase"
	}

Request method : wallet_change_passphrase

Request parameter : old password of wallet, new password of wallet
	

Response Result:

::

	{
	    "id": "26", 
	    "result": "null"
	}

Return value:

none: 



Determine if the password is correct
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:unlock the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "123456789"
	    ], 
	    "id": "19", 
	    "method": "wallet_check_passphrase"
	}

Request method : wallet_check_passphrase

Request parameter : Pending password
	

Response Result:

::

	{
	    "id": "19", 
	    "result": true
	}

Return value:

result: whether the password is correct



Determine if an address is legal
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:none
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "TTC5iSiYMm1fkUtTcW7dQSVNDFZEGXNgj4fy"
	    ], 
	    "id": "20", 
	    "method": "wallet_check_address"
	}

Request method : wallet_check_address 

Request parameter : The address to be checked
	

Response Result:

::

	{
	    "id": "19", 
	    "result": true
	}

Return value:

result: whether the address is correct



Create an account
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:unlock the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "test"
	    ], 
	    "id": "22", 
	    "method": "wallet_account_create"
	}

Request method : wallet_account_create 

Request parameter : The user name to be created
	

Response Result:

::

	{
	    "id": "22", 
	    "result": "TTCQJDzx3AzQWGhCBucE6zLj3mkFo6KG9qSw"
	}

Return value:

addr: Create account addressã€€



Set support account
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:none
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "alp0", 
	        "1"
	    ], 
	    "id": "23", 
	    "method": "wallet_account_set_approval"
	}

Request method : wallet_account_set_approval 

Request parameter : Support account, agree or not
	

Response Result:

::

	{
	    "id": "3", 
	    "result": "1"
	}

Return value:

Result: whether support or not


Transfer to an address
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:unlock the walletï¼Œthe wallet the wallet which has account
	

Request:

::

	{
	    "jsonrpc": 2.0, 
	    "params": [
	        "amount_to_transfer", 
	        "asset_symbol", 
	        "from_account_name", 
	        "to_address", 
	        "memo_message", 
	        "strategy"
	    ], 
	    "id": "1", 
	    "method": "wallet_transfer_to_address"
	}

Request method : wallet_transfer_to_address

Request parameter : transfer amountã€type of transfer assetã€account of withdraw money, transfer to the account addressã€note, the state of voteï¼ˆvote_none:no voteï¼Œvote_all:vote all people,the maximum number of people is 108,
vote_radom:random voteï¼Œthe number of people who choose a certain number of votes from their supporters is no more than 36ï¼Œvote_recommended:vote according to selected votersï¼Œif the chosen voter's publish_data has other voting strategies to add to its own voting strategyï¼‰
	 

Response Result:

::

	{
	    "id": "26", 
	    "result": {
	        "index": "0", 
	        "is_market": false, 
	        "fee": {
	            "asset_id": "0", 
	            "amount": "1000"
	        }, 
	        "is_confirmed": false, 
	        "ledger_entries": [
	            {
	                "from_account": "TTC5eLFrZG5gvc5g5xqEU6J3GELp5WcQYoqhz4JBPT7BVgTpqqxbN",
	                "amount": {
	                    "asset_id": "0", 
	                    "amount": "100000"
	                }, 
	                "memo": "aa"
	            }
	        ], 
	        "received_time": "2016-06-01T08:32:20", 
	        "is_virtual": false, 
	        "block_num": "0", 
	        "trx": {
	            "ttc_inport_asset": {
	                "asset_id": "0", 
	                "amount": "0"
	            }, 
	            "operations": [
	                {
	                    "type": "withdraw_op_type", 
	                    "data": {
	                        "claim_input_data": "", 
	                        "amount": "101000", 
	                        "balance_id": "TTCJEk1wuT9Vix4vQRidmAafz5hCWrS48un2"
	                    }
	                }, 
	                {
	                    "type": "deposit_op_type", 
	                    "data": {
	                        "amount": "100000", 
	                        "condition": {
	                            "asset_id": "0", 
	                            "slate_id": "0", 
	                            "type": "withdraw_signature_type", 
	                            "data": {
	                                "owner": "TTC5iSiYMm1fkUtTcW7dQSVNDFZEGXNgj4fy"
	                            }
	                        }
	                    }
	                }, 
	                {
	                    "type": "imessage_memo_op_type", 
	                    "data": {
	                        "imessage": "aa"
	                    }
	                }
	            ], 
	            "signatures": [
	                "203abaffeaa2735b4f9c79bedae77143ac5da1451c92fd7390c1ae502b53578ef47b2751afa034ff7e0232e37f8fb755f677e9ef566dfc2f7f3d2da1f4cb44476b"
	            ], 
	            "expiration": "2016-06-01T09:32:19", 
	            "ttc_account": ""
	        }, 
	        "entry_id": "0ba68a7e9945f9119cb151a2ef5ff110e4d15925", 
	        "created_time": "2016-06-01T08:32:20", 
	        "extra_addresses": [
	            "TTC5iSiYMm1fkUtTcW7dQSVNDFZEGXNgj4fy"
	        ]
	    }
	}

Return value:

index: reserved field

entry_id: transaction ID

block_num: the number of block

is_virtual: reserved field

is_confirmed: whether to confirm

is_market: reserved field

trx: name of struct type 



Transfer to an account
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:unlock the walletï¼Œthe walletã€€that has accounts
	

Request:

::

	{
	    "jsonrpc": 2.0, 
	    "params": [
	        "amount_to_transfer", 
	        "asset_symbol", 
	        "from_account_name", 
	        "to_account_name", 
	        "memo_message", 
	        "strategy"
	    ], 
	    "id": "1", 
	    "method": "wallet_transfer_to_public_account"
	}

Request method : wallet_transfer_to_public_account

Request parameter : transfer amountã€type of transfer assetã€account of withdraw money, transfer to the account addressã€note, the state of voteï¼ˆvote_none:no voteï¼Œvote_all:vote all people,the maximum number of people is 108,
vote_radom:random voteï¼Œthe number of people who choose a certain number of votes from their supporters is no more than 36ï¼Œvote_recommended:vote according to selected votersï¼Œif the chosen voter's publish_data has other voting strategies to add to its own voting strategyï¼‰
	

Response Result:

::

	{
	    "id": "26", 
	    "result": {
	        "index": "0", 
	        "is_market": false, 
	        "fee": {
	            "asset_id": "0", 
	            "amount": "1000"
	        }, 
	        "is_confirmed": false, 
	        "ledger_entries": [
	            {
	                "from_account": "TTC5eLFrZG5gvc5g5xqEU6J3GELp5WcQYoqhz4JBPT7BVgTpqqxbN",
	                "amount": {
	                    "asset_id": "0", 
	                    "amount": "100000"
	                }, 
	                "memo": "aa"
	            }
	        ], 
	        "received_time": "2016-06-01T08:32:20", 
	        "is_virtual": false, 
	        "block_num": "0", 
	        "trx": {
	            "ttc_inport_asset": {
	                "asset_id": "0", 
	                "amount": "0"
	            }, 
	            "operations": [
	                {
	                    "type": "withdraw_op_type", 
	                    "data": {
	                        "claim_input_data": "", 
	                        "amount": "101000", 
	                        "balance_id": "TTCJEk1wuT9Vix4vQRidmAafz5hCWrS48un2"
	                    }
	                }, 
	                {
	                    "type": "deposit_op_type", 
	                    "data": {
	                        "amount": "100000", 
	                        "condition": {
	                            "asset_id": "0", 
	                            "slate_id": "0", 
	                            "type": "withdraw_signature_type", 
	                            "data": {
	                                "owner": "TTC5iSiYMm1fkUtTcW7dQSVNDFZEGXNgj4fy"
	                            }
	                        }
	                    }
	                }, 
	                {
	                    "type": "imessage_memo_op_type", 
	                    "data": {
	                        "imessage": "aa"
	                    }
	                }
	            ], 
	            "signatures": [
	                "203abaffeaa2735b4f9c79bedae77143ac5da1451c92fd7390c1ae502b53578ef47b2751afa034ff7e0232e37f8fb755f677e9ef566dfc2f7f3d2da1f4cb44476b"
	            ], 
	            "expiration": "2016-06-01T09:32:19", 
	            "ttc_account": ""
	        }, 
	        "entry_id": "0ba68a7e9945f9119cb151a2ef5ff110e4d15925", 
	        "created_time": "2016-06-01T08:32:20", 
	        "extra_addresses": [
	            "TTC5iSiYMm1fkUtTcW7dQSVNDFZEGXNgj4fy"
	        ]
	    }
	}

Return value:

index: reserved field

entry_id: transaction ID

block_num: block number

is_virtual: reserved field

is_confirmed: whether to confirm

is_market: reserved field

trx: the name of struct type



Rescan the block to extract the relevant transactions to the wallet
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:unlock the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "29", 
	    "method": "wallet_rescan_blockchain"
	}

Request method : wallet_rescan_blockchain

Request parameter : none
	

Response Result:

::

	{
	    "id": "29", 
	    "result": "null"
	}

Return value: none 



Cancel scanning the current block
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:unlock the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "30", 
	    "method": "wallet_cancel_scan"
	}

Request method : wallet_cancel_scan

Request parameter : none
	

Response Result:

::

	{
	    "id": "30", 
	    "result": "null"
	}

Return value: none 



Query transaction information
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "transaction_id_prefix"
	    ], 
	    "id": "26", 
	    "method": "wallet_get_transaction"
	}

Request method : wallet_get_transaction

Request parameter : trasaction ID
	

Response Result:

::

	{
	    "id": "26", 
	    "result": {
	        "index": "24", 
	        "is_market": false, 
	        "fee": {
	            "asset_id": "0", 
	            "amount": "1000"
	        }, 
	        "is_confirmed": true, 
	        "ledger_entries": [
	            {
	                "from_account": "TTC7zZSxzHsgSzmcdcMsYV9DZqAro71WrL5HnePJH5YbdQGfJRFKy",
	                "amount": {
	                    "asset_id": "0", 
	                    "amount": "100000"
	                }, 
	                "memo": "To: TTC8XLL7...",
	                "to_account": "TTC7VpiEMUB9LSYxk3APqJg7PPi256M8TSC9vzCEQhokjYYWHQmKx"
	            }
	        ], 
	        "received_time": "2016-06-28T01:42:26", 
	        "is_virtual": false, 
	        "block_num": "477920", 
	        "trx": {
	            "ttc_inport_asset": {
	                "asset_id": "0", 
	                "amount": "0"
	            }, 
	            "operations": [
	                {
	                    "type": "withdraw_op_type", 
	                    "data": {
	                        "claim_input_data": "", 
	                        "amount": "101000", 
	                        "balance_id": "TTC5Bf23THE4RoWzQqWAKn7PkmzJdgUWHDJV"
	                    }
	                }, 
	                {
	                    "type": "deposit_op_type", 
	                    "data": {
	                        "amount": "100000", 
	                        "condition": {
	                            "asset_id": "0", 
	                            "slate_id": "0", 
	                            "type": "withdraw_signature_type", 
	                            "data": {
	                                "owner": "TTC8XLL78anJzHw1qeMqzHsq5Hh447wuvYro"
	                            }
	                        }
	                    }
	                }
	            ], 
	            "signatures": [
	                "1f34cfc2598fe247a81926b7814d0a8bb1929bd9d3278143b7422fe334677a19d851f6c4e71792d60c15c8b227f93717d81ab19f7ea1b60d1e0b735bfc91157db9"
	            ], 
	            "expiration": "2016-06-28T01:42:28", 
	            "ttc_account": ""
	        }, 
	        "entry_id": "58bae775e828049429e3a26b7e625072d63da374", 
	        "created_time": "2016-06-28T01:42:26", 
	        "extra_addresses": [
	            "TTC8XLL78anJzHw1qeMqzHsq5Hh447wuvYro"
	        ]
	    }
	}

Return value:

index: reserved field

entry_id: transaction ID

block_num: block number

is_virtual: reserved field

is_confirmed: whether to confirm

is_market: reserved field

trx: the name of struct type 



Account registration
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:unlock the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "account_name", 
	        "pay_from_account", 
	        "public_data", 
	        "delegate_pay_rate", 
	        "account_type"
	    ], 
	    "id": "26", 
	    "method": "wallet_account_register"
	}

Request method : wallet_account_register

Request parameter : the name of the account to be registeredã€account for this registration fee, open data, agency trustee rate, account type(reserved field)
	

Response Result:

::

	{
	    "id": "26", 
	    "result": {
	        "index": "0", 
	        "is_market": false, 
	        "fee": {
	            "asset_id": "0", 
	            "amount": "1000"
	        }, 
	        "is_confirmed": false, 
	        "ledger_entries": [
	            {
	                "from_account": "TTC6e57Ms177rEGt4Db8rmjYMFveXQYVunsYjjmvma73tAg1XsHxx",
	                "amount": {
	                    "asset_id": "0", 
	                    "amount": "0"
	                }, 
	                "memo": "register sy234", 
	                "to_account": "TTC6e57Ms177rEGt4Db8rmjYMFveXQYVunsYjjmvma73tAg1XsHxx"
	            }
	        ], 
	        "received_time": "2016-06-28T02:56:56", 
	        "is_virtual": false, 
	        "block_num": "0", 
	        "trx": {
	            "ttc_inport_asset": {
	                "asset_id": "0", 
	                "amount": "0"
	            }, 
	            "operations": [
	                {
	                    "type": "register_account_op_type", 
	                    "data": {
	                        "owner_key": "TTC6e57Ms177rEGt4Db8rmjYMFveXQYVunsYjjmvma73tAg1XsHxx",
	                        "name": "sy234", 
	                        "active_key": "TTC7zZSxzHsgSzmcdcMsYV9DZqAro71WrL5HnePJH5YbdQGfJRFKy",
	                        "meta_data": {
	                            "type": "titan_account", 
	                            "data": ""
	                        }, 
	                        "public_data": "", 
	                        "delegate_pay_rate": "255"
	                    }
	                }, 
	                {
	                    "type": "withdraw_op_type", 
	                    "data": {
	                        "claim_input_data": "", 
	                        "amount": "1000", 
	                        "balance_id": "TTC5Bf23THE4RoWzQqWAKn7PkmzJdgUWHDJV"
	                    }
	                }
	            ], 
	            "signatures": [
	                "204f4cb30eef8da006f74eb81a3991a45882117a63d9847b21cd992c82543f0a60647a0a2b4269c4baac2eb8c41d14d0115cdba45fd1e4b723c47dd1d2044568f9"
	            ], 
	            "expiration": "2016-06-28T02:56:58", 
	            "ttc_account": ""
	        }, 
	        "entry_id": "d29cee8715b8c53001a7f0b4b1f30eea781090ca", 
	        "created_time": "2016-06-28T02:56:56", 
	        "extra_addresses": []
	    }
	}

Return value:

index: reserved field

entry_id: transaction ID

block_num: block number

is_virtual: reserved field

is_confirmed: whether to confirm

is_market: reserved field

trx: the name of struct type 



Check all relevant account information in the wallet
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "26", 
	    "method": "wallet_list_accounts"
	}

Request method : wallet_list_accounts

Request parameter : no params
	

Response Result:

::

	{
	    "id": "26", 
	    "result": [
	        {
	            "index": "25", 
	            "owner_key": "TTC6pZUWPujhRUEPaoSBuKgwPVY3Ay3VYwfLZ33EnSreCLWRHyZ6M",
	            "name": "alp1", 
	            "block_production_enabled": false, 
	            "registration_date": "2015-05-31T16:00:00", 
	            "last_update": "2015-05-31T16:00:00", 
	            "private_data": null, 
	            "delegate_info": {
	                "pay_balance": "71063974", 
	                "total_burned": "0", 
	                "blocks_missed": "4481", 
	                "pay_rate": "100", 
	                "votes_for": "1136147884", 
	                "blocks_produced": "5045", 
	                "last_block_num_produced": "479440", 
	                "total_paid": "571302974", 
	                "signing_key_history": [
	                    [
	                        "0", 
	                        "TTC6pZUWPujhRUEPaoSBuKgwPVY3Ay3VYwfLZ33EnSreCLWRHyZ6M"
	                    ]
	                ], 
	                "next_secret_hash": "abe20661166e5e00a583d2dccdc23a25a706b190"
	            }, 
	            "last_used_gen_sequence": "0", 
	            "is_favorite": false, 
	            "public_data": null, 
	            "id": "2", 
	            "is_my_account": false, 
	            "approved": "1", 
	            "active_key_history": [
	                [
	                    "2015-05-31T16:00:00", 
	                    "TTC6pZUWPujhRUEPaoSBuKgwPVY3Ay3VYwfLZ33EnSreCLWRHyZ6M"
	                ]
	            ]
	        }, 
	        {
	            "index": "27", 
	            "owner_key": "TTC7d6PWo9bJWbGkv1naudu9CCm8jvvpcVNevE8nXS4QmrnHTCRbn",
	            "name": "alp2", 
	            "block_production_enabled": false, 
	            "registration_date": "2015-05-31T16:00:00", 
	            "last_update": "2015-05-31T16:00:00", 
	            "private_data": null, 
	            "delegate_info": {
	                "pay_balance": "539997745", 
	                "total_burned": "0", 
	                "blocks_missed": "4499", 
	                "pay_rate": "100", 
	                "votes_for": "1436524291", 
	                "blocks_produced": "5029", 
	                "last_block_num_produced": "479448", 
	                "total_paid": "569642745", 
	                "signing_key_history": [
	                    [
	                        "0", 
	                        "TTC7d6PWo9bJWbGkv1naudu9CCm8jvvpcVNevE8nXS4QmrnHTCRbn"
	                    ]
	                ], 
	                "next_secret_hash": "b1b022fb4831605311d5a96275332ef023f8f7fc"
	            }, 
	            "last_used_gen_sequence": "0", 
	            "is_favorite": false, 
	            "public_data": null, 
	            "id": "3", 
	            "is_my_account": false, 
	            "approved": "1", 
	            "active_key_history": [
	                [
	                    "2015-05-31T16:00:00", 
	                    "TTC7d6PWo9bJWbGkv1naudu9CCm8jvvpcVNevE8nXS4QmrnHTCRbn"
	                ]
	            ]
	        }, 
	        {
	            "index": "14", 
	            "owner_key": "TTC6e57Ms177rEGt4Db8rmjYMFveXQYVunsYjjmvma73tAg1XsHxx",
	            "name": "sy234", 
	            "block_production_enabled": false, 
	            "registration_date": "2016-06-28T02:56:50", 
	            "meta_data": {
	                "type": "titan_account", 
	                "data": ""
	            }, 
	            "last_update": "2016-06-28T02:56:50", 
	            "private_data": null, 
	            "last_used_gen_sequence": "0", 
	            "is_favorite": false, 
	            "public_data": "", 
	            "id": "177", 
	            "is_my_account": true, 
	            "approved": "0", 
	            "active_key_history": [
	                [
	                    "2016-06-28T02:56:50", 
	                    "TTC7zZSxzHsgSzmcdcMsYV9DZqAro71WrL5HnePJH5YbdQGfJRFKy"
	                ]
	            ]
	        }, 
	        {
	            "index": "33", 
	            "owner_key": "TTC5aRA9JVFD1R8TvLJpKzjXrJUCG8Wg6BWKLnHpSYpGH9qPicPMd",
	            "name": "sy345", 
	            "block_production_enabled": false, 
	            "registration_date": "2016-06-28T03:59:40", 
	            "meta_data": {
	                "type": "titan_account", 
	                "data": ""
	            }, 
	            "last_update": "2016-06-28T03:59:40", 
	            "private_data": null, 
	            "last_used_gen_sequence": "0", 
	            "is_favorite": false, 
	            "public_data": "jjjjjjjjjjjjjjjjjjjjfdsfsadjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjjddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddddd", 
	            "id": "178", 
	            "is_my_account": true, 
	            "approved": "0", 
	            "active_key_history": [
	                [
	                    "2016-06-28T03:59:40", 
	                    "TTC6gUVodY7jnmSWk2Vkp8RKvSrmPgxpnpsXMWpodKxbDBww9Wwzt"
	                ]
	            ]
	        }, 
	        {
	            "index": "38", 
	            "owner_key": "TTC6uC6kdWehzhJV7e6MkowZvw8V2tjT5GU9CKoVrsb3REp7oT4s8",
	            "name": "sy678", 
	            "block_production_enabled": false, 
	            "registration_date": "1970-01-01T00:00:00", 
	            "last_update": "2016-06-28T06:07:18", 
	            "private_data": null, 
	            "last_used_gen_sequence": "0", 
	            "is_favorite": false, 
	            "public_data": null, 
	            "id": "0", 
	            "is_my_account": true, 
	            "approved": "0", 
	            "active_key_history": [
	                [
	                    "2016-06-28T06:07:18", 
	                    "TTC5R7s2UhnG97xrtKEmFpx2iq6VxV3aDpNvJn3DvtYB9tQmFzfxR"
	                ]
	            ]
	        }, 
	        {
	            "index": "41", 
	            "owner_key": "TTC5YWupJFNhc6SAw33UGvBwK4cKtqC5UbZC18dwXLL1WSRimHY1s",
	            "name": "sy6789", 
	            "block_production_enabled": false, 
	            "registration_date": "1970-01-01T00:00:00", 
	            "last_update": "2016-06-28T06:08:32", 
	            "private_data": null, 
	            "last_used_gen_sequence": "0", 
	            "is_favorite": false, 
	            "public_data": null, 
	            "id": "0", 
	            "is_my_account": true, 
	            "approved": "0", 
	            "active_key_history": [
	                [
	                    "2016-06-28T06:08:32", 
	                    "TTC6V7YdCqxvS4cRWzQ2YSzGwN6A15ZaNfHoZHB9AALxZB13riWrw"
	                ]
	            ]
	        }
	    ]
	}

Return value:

index: entry ID of wallet database

id: account ID

name : account name

public_data: Open data added to a registered account

owner_key: owner public key

active_key_history: the history of active public key

registration_date: regist time

last_update: the last updated of account information 

delegate_info: Agent information structure

is_my_account: whether have private key

approved: Support for the account

is_favorite: reserved field

block_production_enabled: Whether to open the production block function

last_used_gen_sequence: reserved field

private_data: reserved field



Check all unregistered accounts in wallet
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "26", 
	    "method": "wallet_list_unregistered_accounts"
	}

Request method : wallet_list_unregistered_accounts

Request parameter : none
	

Response Result:

::

	{
	    "id": "26", 
	    "result": [
	        {
	            "index": "38", 
	            "owner_key": "TTC6uC6kdWehzhJV7e6MkowZvw8V2tjT5GU9CKoVrsb3REp7oT4s8",
	            "name": "sy678", 
	            "block_production_enabled": false, 
	            "registration_date": "1970-01-01T00:00:00", 
	            "last_update": "2016-06-28T06:07:18", 
	            "private_data": null, 
	            "last_used_gen_sequence": "0", 
	            "is_favorite": false, 
	            "public_data": null, 
	            "id": "0", 
	            "is_my_account": true, 
	            "approved": "0", 
	            "active_key_history": [
	                [
	                    "2016-06-28T06:07:18", 
	                    "TTC5R7s2UhnG97xrtKEmFpx2iq6VxV3aDpNvJn3DvtYB9tQmFzfxR"
	                ]
	            ]
	        }, 
	        {
	            "index": "41", 
	            "owner_key": "TTC5YWupJFNhc6SAw33UGvBwK4cKtqC5UbZC18dwXLL1WSRimHY1s",
	            "name": "sy6789", 
	            "block_production_enabled": false, 
	            "registration_date": "1970-01-01T00:00:00", 
	            "last_update": "2016-06-28T06:08:32", 
	            "private_data": null, 
	            "last_used_gen_sequence": "0", 
	            "is_favorite": false, 
	            "public_data": null, 
	            "id": "0", 
	            "is_my_account": true, 
	            "approved": "0", 
	            "active_key_history": [
	                [
	                    "2016-06-28T06:08:32", 
	                    "TTC6V7YdCqxvS4cRWzQ2YSzGwN6A15ZaNfHoZHB9AALxZB13riWrw"
	                ]
	            ]
	        }
	    ]
	}

Return value:

index: entry ID of wallet database

id: account ID

name : account name

public_data: Open data added to a registered account

owner_key: owner public key

active_key_history: the history of active public key

registration_date: regist time

last_update: the last updated of account information 

is_my_account: whether have private key

approved: Support for the account

is_favorite: reserved field

block_production_enabled: Whether to open the production block function

last_used_gen_sequence: reserved field

private_data: reserved field



List all accounts that has private key in wallet
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "40", 
	    "method": "wallet_list_my_accounts"
	}

Request method : wallet_list_my_accounts

Request parameter : none
	

Response Result:

::

	{
	    "id": "17", 
	    "result": [
	        {
	            "index": "11", 
	            "owner_key": "TTC5VoZWa93vxBF9DudYMhtdDdDjJvcqpk9WJpczFAMLcJ6H7mp8a",
	            "name": "alphzk1", 
	            "block_production_enabled": false, 
	            "registration_date": "1970-01-01T00:00:00", 
	            "last_update": "2016-06-28T02:20:11", 
	            "private_data": "null", 
	            "last_used_gen_sequence": "0", 
	            "is_favorite": false, 
	            "public_data": "null", 
	            "id": "0", 
	            "is_my_account": true, 
	            "approved": "0", 
	            "active_key_history": [
	                [
	                    "2016-06-28T02:20:11", 
	                    "TTC5VoZWa93vxBF9DudYMhtdDdDjJvcqpk9WJpczFAMLcJ6H7mp8a"
	                ]
	            ]
	        }
	    ]
	}

Return value:

index: entry ID of wallet database

id: account ID

name : account name

public_data: Open data added to a registered account

owner_key: owner public key

active_key_history: the history of active public key

registration_date: regist time

last_update: the last updated of account information 

delegate_info: Agent information structure

is_my_account: whether have private key

approved: Support for the account

is_favorite: reserved field

block_production_enabled: Whether to open the production block function

last_used_gen_sequence: reserved field

private_data: reserved field



Get the address of a local wallet or register an account in the chain
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "account"
	    ], 
	    "id": "43", 
	    "method": "wallet_get_account_public_address"
	}

Request method : wallet_get_account_public_address

Request parameter : account name
	

Response Result:

::

	{
	    "id": "43", 
	    "result": "TTCFuj3UjtwsMxZsebUjb6kGFLYWT43GQwkyffffffffffffffffffffffffffffffff"
	}

Return value:

addr:account address



Rename an unregistered account
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "currentaccount", 
	        "newaccount"
	    ], 
	    "id": "45", 
	    "method": "wallet_account_rename"
	}

Request method : wallet_account_rename

Request parameter : current account name, new account name
	

Response Result:

::

	{
	    "id": "29", 
	    "result": "null"
	}

Return value:

none: 



Get the specified account balance
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "account"
	    ], 
	    "id": "49", 
	    "method": "wallet_account_balance"
	}

Request method : wallet_account_balance

Request parameter : account name
	

Response Result:

::

	{
	    "id": "49", 
	    "result": [
	        [
	            "alp0", 
	            [
	                [
	                    "0", 
	                    "999999696000"
	                ]
	            ]
	        ]
	    ]
	}

Return value:

account: account

asset_id: Asset types

balance: current balance


Lists all the balance record ids for the specified account
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "account_name"
	    ], 
	    "id": "50", 
	    "method": "wallet_account_balance_ids"
	}

Request method : wallet_account_balance_ids

Request parameter : The user name of the query account
	

Response Result:

::

	{
	    "id": "50", 
	    "result": [
	        [
	            "alp0", 
	            [
	                "TTC6P1pnNuJR4SW7mbiAy1ibfmJwZSZZLZWC",
	                "TTCG7NGwoYicogH7bpZ5MDghBaTAUGzwd53Z"
	            ]
	        ]
	    ]
	}

Return value:

Fields without TTC: account name

The data that inside "[]" after he account name: The balanceid of the account



The interface that trustee receives the transfer salary 
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:unlock the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "delegate_name", 
	        "to_account_name", 
	        "amount_to_withdraw"
	    ], 
	    "id": "52", 
	    "method": "wallet_delegate_withdraw_pay"
	}

Request method : wallet_delegate_withdraw_pay

Request parameter : The name of the agent receiving the wage, the name of the account to be received, the amount of salary received
	

Response Result:

::

	{
	    "id": "26", 
	    "result": {
	        "index": "0", 
	        "is_market": false, 
	        "fee": {
	            "asset_id": "0", 
	            "amount": "1000"
	        }, 
	        "is_confirmed": false, 
	        "ledger_entries": [
	            {
	                "from_account": "TTC5eLFrZG5gvc5g5xqEU6J3GELp5WcQYoqhz4JBPT7BVgTpqqxbN",
	                "amount": {
	                    "asset_id": "0", 
	                    "amount": "100000"
	                }, 
	                "memo": "aa"
	            }
	        ], 
	        "received_time": "2016-06-01T08:32:20", 
	        "is_virtual": false, 
	        "block_num": "0", 
	        "trx": {
	            "ttc_inport_asset": {
	                "asset_id": "0", 
	                "amount": "0"
	            }, 
	            "operations": [
	                {
	                    "type": "withdraw_op_type", 
	                    "data": {
	                        "claim_input_data": "", 
	                        "amount": "101000", 
	                        "balance_id": "TTCJEk1wuT9Vix4vQRidmAafz5hCWrS48un2"
	                    }
	                }, 
	                {
	                    "type": "deposit_op_type", 
	                    "data": {
	                        "amount": "100000", 
	                        "condition": {
	                            "asset_id": "0", 
	                            "slate_id": "0", 
	                            "type": "withdraw_signature_type", 
	                            "data": {
	                                "owner": "TTC5iSiYMm1fkUtTcW7dQSVNDFZEGXNgj4fy"
	                            }
	                        }
	                    }
	                }, 
	                {
	                    "type": "imessage_memo_op_type", 
	                    "data": {
	                        "imessage": "aa"
	                    }
	                }
	            ], 
	            "signatures": [
	                "203abaffeaa2735b4f9c79bedae77143ac5da1451c92fd7390c1ae502b53578ef47b2751afa034ff7e0232e37f8fb755f677e9ef566dfc2f7f3d2da1f4cb44476b"
	            ], 
	            "expiration": "2016-06-01T09:32:19", 
	            "ttc_account": ""
	        }, 
	        "entry_id": "0ba68a7e9945f9119cb151a2ef5ff110e4d15925", 
	        "created_time": "2016-06-01T08:32:20", 
	        "extra_addresses": [
	            "TTC5iSiYMm1fkUtTcW7dQSVNDFZEGXNgj4fy"
	        ]
	    }
	}

Return value:

index: reserved field

entry_id: transaction ID

block_num: block number

is_virtual: reserved field

is_confirmed: whether to confirm

is_market: reserved field

trx: the name of struct type 



The query of trustee salary
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:unlock the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "account_name"
	    ], 
	    "id": "53", 
	    "method": "wallet_delegate_pay_balance_query"
	}

Request method : wallet_delegate_pay_balance_query

Request parameter : The user name of the query agent
	

Response Result:

::

	{
	    "id": "53", 
	    "result": {
	        "pay_balance": "1300000", 
	        "total_balance": "1300000"
	    }
	}

Return value:

total_balance: total wages

pay_balance: Available wage



Gets the state of the broker in the wallet
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "account_name"
	    ], 
	    "id": "54", 
	    "method": "wallet_get_delegate_statue"
	}

Request method : wallet_get_delegate_statue

Request parameter : The user name of the query agent
	

Response Result:

::

	{
	    "id": "54", 
	    "result": false
	}

Return value:

The field after the result colon:  The state of a block in the current wallet



Delete your local wallet account
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:unlock the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "account_name"
	    ], 
	    "id": "36", 
	    "method": "wallet_account_delete"
	}

Request method : wallet_account_delete

Request parameter : The name of the account to be deleted
	

Response Result:

::

	{
	    "id": "36", 
	    "result": true
	}

Return value:

The field after the result colon: return trueã€€all time



Set local transfer fee
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "fee"
	    ], 
	    "id": "36", 
	    "method": "wallet_set_transaction_fee"
	}

Request method : wallet_set_transaction_fee

Request parameter : the handling charge that will be set
	

Response Result:

::

	{
	    "id": "36", 
	    "result": {
	        "asset_id": "0", 
	        "amount": "100"
	    }
	}

Return value:

Asset: current fee



Obtain current local transfer fee
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "symbol"
	    ], 
	    "id": "36", 
	    "method": "wallet_get_transaction_fee"
	}

Request method : wallet_get_transaction_fee

Request parameter : the asset id to be queried
	

Response Result:

::

	{
	    "id": "36", 
	    "result": {
	        "asset_id": "0", 
	        "amount": "100"
	    }
	}

Return value:

Asset: current fee



Set the local wallet to enable scanning
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "enable"
	    ], 
	    "id": "36", 
	    "method": "wallet_set_transaction_scanning"
	}

Request method : wallet_set_transaction_scanning

Request parameter : whether to start the scan
	

Response Result:

::

	{
	    "id": "36", 
	    "result": true
	}

Return value:

The field after the result colon: return current status



Obtain the private key according to the address of the local owned account or public key
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:unlock the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "addr"
	    ], 
	    "id": "61", 
	    "method": "wallet_dump_private_key"
	}

Request method : wallet_dump_private_key

Request parameter : address/public key
	

Response Result:

::

	{
	    "id": "61", 
	    "result": "5JfeSoRUiosgA9kzcPTwmUZs6rEnYPz4iSqGHc9uKcscdjc96g9"
	}

Return value:

private_key: address



The production of a block is enabled or disabled for a specific trustee account
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:open the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "delegate_name", 
	        "enabled"
	    ], 
	    "id": "67", 
	    "method": "wallet_delegate_set_block_production"
	}

Request method : wallet_delegate_set_block_production

Request parameter : the name of the trustee account, whether to enable
	

Response Result:

::

	{
	    "id": "67", 
	    "result": "null"
	}

Return value:

none: 



Get specify private key of account from local wallet
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:unlock the wallet
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "account", 
	        "key_type"
	    ], 
	    "id": "62", 
	    "method": "wallet_dump_account_private_key"
	}

Request method : wallet_dump_account_private_key

Request parameter : account name, private key type
	

Response Result:

::

	{
	    "id": "61", 
	    "result": "5JfeSoRUiosgA9kzcPTwmUZs6rEnYPz4iSqGHc9uKcscdjc96g9"
	}

Return value:

private_key: address



To specify the block by block number or ID, and obtain the header information of its block
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:no param
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "blocknum"
	    ], 
	    "id": "2", 
	    "method": "blockchain_get_block"
	}

Request method : blockchain_get_block

Request parameter : block number
	

Response Result:

::

	{
	    "id": "2", 
	    "result": {
	        "latency": "0", 
	        "user_transaction_ids": [], 
	        "delegate_signature": "2002db1a3aa58e3768c794fd5295aa4a58691a294b650f6956c4edbea299df72bc282e54d762a6374765287bf7fad734ddc2a00b39775fe256e977b37d27ca7359", 
	        "signee_fees_collected": "0", 
	        "processing_time": "0", 
	        "timestamp": "2016-03-21T05:16:40", 
	        "signee_shares_issued": "0", 
	        "block_num": "1000", 
	        "previous_secret": "7976c83635b5bc21cac6d4d762b789f97797681d", 
	        "next_secret_hash": "64159580b455cd4b95a4d22670745454f3693c1d", 
	        "signee_fees_destroyed": "0", 
	        "transaction_digest": "c8cf12fe3180ed901a58a0697a522f1217de72d04529bd255627a4ad6164f0f0", 
	        "random_seed": "0000000000000000000000000000000000000000", 
	        "block_size": "166", 
	        "id": "2df402a360d9956d51749428815ed671cc40ea5c", 
	        "previous": "5071675dc378fe85a9e4e76cb90651471bb47380"
	    }
	}

Return value:

previous: previous hash

block_num: block_num

timestamp: block create time 

transaction_digest: All transaction signatures

next_secret_hash:All transaction signatures

previous_secret: Next round of block credentialsã€€ã€€


delegate_signature: allograph

user_transaction_ids: contains all ID of transaction

id: block id 

block_size: block_size

latency: The production block and local synchronization to block time difference

signee_shares_issued: reserve param

signee_fees_collected: handling fee of the statistics in the block

signee_fees_destroyed: Handling fee for destruction in block

random_seed: random seed

processing_time: Local processing time



Get the proxy setting parameters
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite: none
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [], 
	    "id": "36", 
	    "method": "delegate_get_config"
	}

Request method : delegate_get_config

Request parameter : none
	

Response Result:

::

	{
	    "id": "36", 
	    "result": {
	        "transaction_blacklist": [], 
	        "transaction_min_fee": "1000", 
	        "network_min_connection_count": "4", 
	        "block_max_transaction_count": "4294967295", 
	        "transaction_max_size": "1024000", 
	        "operation_blacklist": [], 
	        "transaction_canonical_signatures_required": false, 
	        "block_max_size": "1024000", 
	        "block_max_production_time": "3000000", 
	        "transaction_imessage_max_soft_length": "40", 
	        "transaction_imessage_min_fee_coe": "100"
	    }
	}

Return value:

network_min_connection_count: the minimum connection count of network

block_max_transaction_count:  the maximum transaction count of block

block_max_size: block_max_size

block_max_production_time: The maximum block time of a block

transaction_max_size: The maximum size of a transaction

transaction_canonical_signatures_required: reserved field

transaction_min_fee: Minimum transaction fee

transaction_imessage_max_soft_length: Remark maximum length

transaction_imessage_min_fee_coe: Remark the cost of per byte

transaction_blacklist: reserved field

operation_blacklist: reserved field



Sets the minimum number of connections needed for the current broker
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:none
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "count"
	    ], 
	    "id": "36", 
	    "method": "delegate_set_network_min_connection_count"
	}

Request method : delegate_set_network_min_connection_count

Request parameter : Minimum number of connections required
	

Response Result:

::

	{
	    "id": "36", 
	    "result": "null"
	}

Return value:

none: 



Sets the maximum number of transactions for the current broker
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:none
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "count"
	    ], 
	    "id": "36", 
	    "method": "delegate_set_block_max_transaction_count"
	}

Request method : delegate_set_block_max_transaction_count

Request parameter : Limit the maximumã€€number of local transactions
	

Response Result:

::

	{
	    "id": "36", 
	    "result": "null"
	}

Return value:

none: 



The maximum value of a block set by the agent property
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:You can verify the success through the 73 instructions
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "blocksize"
	    ], 
	    "id": "2", 
	    "method": "delegate_set_block_max_size"
	}

Request method : delegate_set_block_max_size

Request parameter : the size of block
	

Response Result:

::

	{
	    "id": "36", 
	    "result": "null"
	}

Return value:

none: 



The proxy property sets the maximum size of a transaction
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:You can verify the success through the 73 instructions
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "trx_size"
	    ], 
	    "id": "2", 
	    "method": "delegate_set_transaction_max_size"
	}

Request method : delegate_set_transaction_max_size

Request parameter : the size of trade
	

Response Result:

::

	{
	    "id": "36", 
	    "result": "null"
	}

Return value:

none: 



Set the minimum transaction fee that the agent acknowledges
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Prerequisite:You can verify the success through the 73 instructions
	

Request:

::

	{
	    "jsonrpc": "2.0", 
	    "params": [
	        "transaction"
	    ], 
	    "id": "2", 
	    "method": "delegate_set_transaction_min_fee"
	}

Request method : delegate_set_transaction_min_fee

Request parameter : The agent recognizes the amount of serviceã€€fee that can be put into its own buffer
	

Response Result:

::

	{
	    "id": "36", 
	    "result": "null"
	}

Return value: none



Broadcast a transaction
-------------------------------------------------------------------------------------------------------------------
Prerequisite: none
	
	
Request:

::

	{
		"expiration": "2017-09-19T02:58:38",
		"alp_account": "",
		"alp_inport_asset": {
			"amount": 0,
			"asset_id": 0
		},
		"operations": [
			{
				"type": "withdraw_op_type",
				"data": {
					"balance_id": "TTCEYUEpKd67WmFVuwrbXdAGquhJVrUmsPN7",
					"amount": 20001000,
					"claim_input_data": ""
				}
			},
			{
				"type": "deposit_op_type",
				"data": {
					"amount": 20000000,
					"condition": {
						"asset_id": 0,
						"slate_id": 0,
						"type": "withdraw_signature_type",
						"balance_type": "withdraw_common_type",
						"data": {
							"owner": "TTC3pUa2TtwBBjmuy2QDQSxRNk49Xzrn4Wom"
						}
					}
				}
			}
		],
		"result_trx_type": "origin_transaction",
		"result_trx_id": "0000000000000000000000000000000000000000",
		"signatures": [
			"1f5ef9a4a28cf2f3c8994b9229edc300d3cf7e21b233d507aa0f88bee7d50d32cb6e9ed8bdd60d07c0124f4e61273e7dde0bb656d106b03974001c8e4ab0842518"
		]
	}

Request method : network_broadcast_transaction

Request parameter : the information of broadcasting a transaction
	

Response Result:

::

	{
		"id": 69,
		"result": "8f612b365d4de8fb7b260c1f385040512d352d12"	ori_trx_id
	}

Return value: 

result: original trade id  ori_trx_id



Get block number and result_trx_id of a transacion
---------------------------------------------------
Prerequisite: none
	

Request:

::


Request method : blockchain_get_contrttc_result

Request parameter: ori_trx_id
	

Response Result:

::

	{
		"id": "84",
		"result": {
			"block_num": 172067,
			"trx_id": "7af0e28ae15aa6d2e2c9a4a3c5161b26d85e37b9"	
		}
	}

Return value: 

result: result_trx_id, block_num



Get result from a contract transaction emit
--------------------------------------
Prerequisite: none
	

Request:

::


Request method : blockchain_get_events

Request parameter: block_num, result_trx_id
	

Response Result:

::

	{
		"id": "72",
		"result": [
			{
				"id": "TTCBGzSXPfG3ddgzvv3vsf5jqTWqhgRTRrxW",
				"event_type": "change_fee_success",	
				"event_param": "0.025000",
				"is_truncated": false							
			}
		]
	}

Return value: 

result: contract ID, event_type, event_param



Test for calling a contract function emit locally, which won't cost any TTC
--------------------------------------------------------------------------------
Prerequisite: none
	

Request:

::


Request method : call_contrttc_local_emit

Request parameter: contrttc_id, caller, method, param 
	

Response Result:

::

	{
		"id": "72",
		"result": [
			{
				"id": "TTCBGzSXPfG3ddgzvv3vsf5jqTWqhgRTRrxW",
				"event_type": "change_fee_success",
				"event_param": "0.025000",
				"is_truncated": false							
			}
		]
	}

Return value: 

result: contract id, event_type, event_param



Return Transaction Infomation after signing
--------------------------------------------
Prerequisite: none
	

Request:

::

Request method : create_transfer_transaction

Request parameter: amount_to_transfer, asset_symbol, from_account_name, to_address, memo_message, strategy
	

Response Result:

::

	{
		"expiration": "2017-09-19T02:58:38",
		"alp_account": "",
		"alp_inport_asset": {
			"amount": 0,
			"asset_id": 0
		},
		"operations": [
			{
				"type": "withdraw_op_type",
				"data": {
					"balance_id": "TTCEYUEpKd67WmFVuwrbXdAGquhJVrUmsPN7",
					"amount": 20001000,
					"claim_input_data": ""
				}
			},
			{
				"type": "deposit_op_type",
				"data": {
					"amount": 20000000,
					"condition": {
						"asset_id": 0,
						"slate_id": 0,
						"type": "withdraw_signature_type",
						"balance_type": "withdraw_common_type",
						"data": {
							"owner": "TTC3pUa2TtwBBjmuy2QDQSxRNk49Xzrn4Wom"
						}
					}
				}
			}
		],
		"result_trx_type": "origin_transaction",
		"result_trx_id": "0000000000000000000000000000000000000000",
		"signatures": [
			"1f5ef9a4a28cf2f3c8994b9229edc300d3cf7e21b233d507aa0f88bee7d50d32cb6e9ed8bdd60d07c0124f4e61273e7dde0bb656d106b03974001c8e4ab0842518"
		]
	}

Return value: 

result: 
