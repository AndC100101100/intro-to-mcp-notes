projects either are the implementation of a server or the implementation of a client

In our mcp_client file, we will find the implementation of the `class MCPClient`, which will wrap the client session, responsible of making the connection to our MCP server.
In our project, this sessions is part of the MCP python SDK. In our use case, through the Client we are exposing some functionality that belongs to the server to the rest of our code base.

In many cases, this will probably look like our CLI code using the cleint to get a list of tools to pass to Claude, or our CLI code using the client to call a tool.
