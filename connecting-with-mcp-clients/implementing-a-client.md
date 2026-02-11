Projects either are the implementation of a server or the implementation of a client

In our mcp_client file, we will find the implementation of the `class MCPClient`, which will wrap the client session, responsible of making the connection to our MCP server.
In our project, this sessions is part of the MCP python SDK. In our use case, through the Client we are exposing some functionality that belongs to the server to the rest of our code base.

In many cases, this will probably look like our CLI code using the cleint to get a list of tools to pass to Claude, or our CLI code using the client to call a tool.

## Clients
In this code, it uses the client to:
- Get a list of available tools to send to Claude
- Execute tools when Claude requests them.

## Core Functionalities.
In the case of this implementation, we are defining the `list_tools()` function found in [mcp_client.py](../cli_project/mcp_client.py).
This function gets all the available tools from the MCP server. We access our session which is our connection to the server and call the built in list_tools() method, to then return the tools from the result.

We then have the `call_tool()` fucntion, which executes a specific tool on the server, we pass the toolname and inputa parameters to the server and return the result.

## testing
we can then test the client by running 
```bash
uv run mcp_client.py
```