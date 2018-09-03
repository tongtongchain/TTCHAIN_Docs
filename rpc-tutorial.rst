RPC Tutorial
===============


Support for JsonRpc
---------------

Support 2 JsonRpc modes

- Tcp-JsonRpc mode
- Http-JsonRpc mode


How to enable the RPC server listener
----------------------------------------

- Start Tcp-JsonRpc mode

::

    TTCHAIN --rpcuser RPCusername --rpcpassword RPCpassword --rpcport port --server --data-dir dataDirectory
    

Example : 
::

    TTCHAIN --rpcuser admin --rpcpassword 123456 --rpcport 10086 --server --data-dir chain_data
    

- Start Http-JsonRpc Mode

::

    TTCHAIN --rpcuser RPCusername --rpcpassword RPCpassword --httpdendpoint ListenEndpoint --server --data-dir dataDirectory
    

Example : 
::

    TTCHAIN --rpcuser admin --rpcpassword 123456 --httpdendpoint 127.0.0.1:8080 --server --data-dir chain_data
    


How to build RPC interaction
--------------------------------------------------

- In Tcp-JsonRpc mode

1. Initiate a TCP connection.

#. Send the RPC login request as a way of data flow, then receive the correct RPC response.

#. Interact with RPC.

#. Disconnect.


- In Http-JsonRpc Mode

1. Initiate  http headerï¼Œset the key and the content value as Authorization and 6 random bytes + base64(rpcuser:rpcpassword) seperately.

#. Fill the  RPC requests in HTTP body, then combine the header and send HTTP POST. 

#. Get HTTP response, the content of body is RPC response.


Simple DEMO
------------------------------------------

Python 2.7 Simple demo

- In Tcp-JsonRpc mode

SimpleTcpJsonRpc.py

::

    #!/usr/bin/env python 
    # encoding: utf-8
    
    
    import socket
    
    def is_receive_complete(data):
        if data is None or data == '':
            return False
        json_start = False
        json_tag_count = 0
        for c in data:
            if c == '{':
                if not json_start:
                    json_start = True
                json_tag_count += 1
            elif c == '}':
                json_tag_count -= 1
            if json_start and json_tag_count == 0:
                return True
        return False
    
    def recv_until_json_complete(sd):
        left_data = ""
        while not is_receive_complete(left_data):
            data = sd.recv(4096)
            left_data += data
        return left_data
    
    
    login_payload = ''' { "jsonrpc": "2.0", "params": [ "admin", "123456" ], "id": "1", "method": "login" } '''
    get_info_payload = ''' { "jsonrpc": "2.0", "params": [], "id": "2", "method": "get_info" } '''
    
    RpcServerEndpoint = "127.0.0.1:10086"
    conn_tuple = RpcServerEndpoint.split(":")
    endpoint_tuple = (conn_tuple[0], int(conn_tuple[1]))
    
    sd = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    sd.connect(endpoint_tuple)
    
    sd.sendall(login_payload)
    recv_data = recv_until_json_complete(sd)
    print recv_data
    
    sd.sendall(get_info_payload)
    recv_data = recv_until_json_complete(sd)
    print recv_data
    
    sd.close()



- In Http-JsonRpc Mode

SimpleHttpJsonRpc.py

::

    #!/usr/bin/env python 
    # encoding: utf-8
    
    
    import base64
    from requests import Request, Session
    
    get_info_payload = {"jsonrpc": "2.0", "params": [], "id": "2", "method": "info"}
    
    rpc_auth = "000000" + base64.b64encode("%s:%s" % ("admin", "123456"))
    auth_headers = {'Content-Type': 'application/json', 'Authorization': rpc_auth}
    post_url = "http://127.0.0.1:8080/rpc"
    
    s = Session()
    req = Request('POST', post_url, json=get_info_payload, headers=auth_headers)
    prepped = req.prepare()
    resp = s.send(prepped)
    
    print resp.text
