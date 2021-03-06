
Local Script
=========================================

Compile local script
------------------------------------
Prerequisite: none

Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "compile_script",
        "params": [
            "C:/Users/hasee/Desktop/test.glua"
        ]
    }
Request method: compile_script

Request parameter: full path of script

Response Result:

::
    
    {
        "id": "1",
        "result": "C:/Users/hasee/Desktop/test.script"
    }
Response parameters: 

full path of bytecode file generated by compilation


Search Specified Local Script Information
------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "get_script_info",
        "params": [
            "SCRARHqLKbP7Sigkme6X5cjHUjxBh9UKFQd8"
        ]
    }
Request method: get_script_info

Request parameter: script id

Response Result:

::
    
    {
        "id": "1",
        "result": {
            "id": "SCRARHqLKbP7Sigkme6X5cjHUjxBh9UKFQd8",
            "enable": true,
            "code_printable": {
                "abi": [
                    
                ],
                "offline_abi": [
                    
                ],
                "events": [
                    
                ],
                "printable_code": "1b4c7561530019930d0a1a0a040804080878560000000000000000000000287740012140433a2f55736572732f68617365652f4465736b746f702f746573742e6c756100000000000000000002020100000026008000000000000100000001000000000001000000010000000000000001000000055f454e56",
                "code_hash": "93924b0b4dd7435704f079f6b93e4744b01a17fb"
            },
            "description": "this is my first script",
            "register_time": "2016-09-28T08:41:23"
        }
    }

response parameters:

id:script id

enable: enable state

code_printable: bytecode info

description : description of script  

register_time : time of register a script


List all the local scripts in wallet
------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "list_scripts",
        "params": [
            
        ]
    }

Request method: list_scripts

Request parameter: none

Response Result:

::
    
    {
        "id": "1",
        "result": [
            {
                "id": "SCRARHqLKbP7Sigkme6X5cjHUjxBh9UKFQd8",
                "enable": true,
                "code_printable": {
                    "abi": [
                        
                    ],
                    "offline_abi": [
                        
                    ],
                    "events": [
                        
                    ],
                    "printable_code": "1b4c7561530019930d0a1a0a040804080878560000000000000000000000287740012140433a2f55736572732f68617365652f4465736b746f702f746573742e6c756100000000000000000002020100000026008000000000000100000001000000000001000000010000000000000001000000055f454e56",
                    "code_hash": "93924b0b4dd7435704f079f6b93e4744b01a17fb"
                },
                "description": "this is my first script",
                "register_time": "2016-09-28T08:41:23"
            }
        ]
    }

Response parameters: script infomation array




Add New Local Script
------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "add_script",
        "params": [
            "C:/Users/hasee/Desktop/test.script",
            "this is my first script"
        ]
    }

Request method: add_script

Request parameter: full path of scriptï¼Œdescription of script 

Response Result:

::
    
    {
        "id": "1",
        "result": "SCRARHqLKbP7Sigkme6X5cjHUjxBh9UKFQd8"
    }
Response parameters: 
script id


Delet Local Script
------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks

Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "remove_script",
        "params": [
            "SCRARHqLKbP7Sigkme6X5cjHUjxBh9UKFQd8"
        ]
    }
Request method: remove_script

Request parameter: script id

Response Result:

::
    
    {
        "id": "1",
        "result": null
    }

Response parameters: none



Disable A Local Script
------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks

Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "disable_script",
        "params": [
            "SCRARHqLKbP7Sigkme6X5cjHUjxBh9UKFQd8"
        ]
    }
    
Request method: disable_script

Request parameter: script id

Response Result:

::
    
    {
        "id": "1",
        "result": null
    }

Response parameters: none


Enable A Local Script
------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "enable_script",
        "params": [
            "SCRARHqLKbP7Sigkme6X5cjHUjxBh9UKFQd8"
        ]
    }
Request method: enable_script

Request parameter: script id

Response Result:

::
    
    {
        "id": "1",
        "result": null
    }

Response parameters: none


Query the local script associated with the Event in the contract
------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "list_event_handler",
        "params": [
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE",
            "event_type1"
        ]
    }
Request method: list_event_handler

Request parameter: contract id, event type

Response Result:

::
    
    {
        "id": "1",
        "result": [
            "SCRARHqLKbP7Sigkme6X5cjHUjxBh9UKFQd8"
        ]
    }

Response parameters: script id array


Add a related local script to the Event in the contract
------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "add_event_handler",
        "params": [
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE",
            "event_type1",
            "SCRARHqLKbP7Sigkme6X5cjHUjxBh9UKFQd8",
            "0"
        ]
    }
Request method: add_event_handler

Request parameter: contract id, event type,script, sequence location of triggering script 


Response Result:

::
    
    {
        "id": "1",
        "result": null
    }
Response parameters: none


Remove a related local script from the Event in the contract
------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "delete_event_handler",
        "params": [
            "CONJuXHfWSGo51cGbD3dXVpQs8B5v7MrFZcE",
            "event_type1",
            "SCRARHqLKbP7Sigkme6X5cjHUjxBh9UKFQd8"
        ]
    }

Request method: delete_event_handler

Request parameter: contract id,event type, script id

Response Result:

::
    
    {
        "id": "1",
        "result": null
    }
Response parameters: none


Export the local script library and the relationship library with the Event
------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "export_script_db",
        "params": [
            "F:/script_db"
        ]
    }
Request method: export_script_db

Request parameter: The location of export

Response Result:

::

    {
        "id": "1",
        "result": null
    }

Response parameters: none


Import the local script library and the relationship library with the Event
-----------------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks


Request:

::
    
    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": "import_script_db",
        "params": [
            "F:/script_db"
        ]
    }
Request method: import_script_db

Request parameter: location of the source data 

Response Result:

::
    
    {
        "id": "1",
        "result": null
    }

Response parameters: none


Query the script binding contract and event according to script id
--------------------------------------------
Prerequisite: RPC login authentication successfully, wallet opens, wallet unlocks

Request:

::

    {
        "jsonrpc": "2.0",
        "id": "1",
        "method": " get_events_bound ",
        "params": ["SCRARHqLKbP7Sigkme6X5cjHUjxBh9UKFQd8"]
    }
    
Request method: get_events_bound

Request parameter: script id

Response Result:

::

    {
        "id":1,
        "result": [
            {"CON5KWRaxfL7iF7CCnrYviUSKkXKr7Um7QGc,printt"},
            {"CON5KWRaxfL7iF7CCnrYviUSKkXKr7Um7QGc,testevent"}
        ]
    }
Response parameters: element is an array in form of {contract id, event type}



