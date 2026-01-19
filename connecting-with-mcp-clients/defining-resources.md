For this part, we want to add new features like letting users mention a document by writing out @doc_name:
- Typing @ should show a list of all the available documents
- When the document is mentioned, its contents should be injected into the prompt automatically

For this, we are going to use, resources.

## Resources
The allow the MCP server to expose data to the client. They are also similar to a GET request handler in a HTTP server. Theyll be able to retunr any type of data, it can either be JSON, strings, binary information...
For this, we can set the `mime_type` so that the client gets a hint as to what type of data we are returning. We will also have two types, a direct and templated.
- Direct resource: URI does not contain any params
- Templated Resource: URI contains one or more paramns. Our Python SDK will parse these and pass them as arguments to our function.

Our client will have to manage sending this request to the MCP server through a tool call to `ReadResourceRequest` we are going to include the URI of the resource. The MCP server will look at the URI and run the function and send the result back through a `ReadResourceResult`.

After writing such functionality we can test again.
```bash
uv run mcp dev mcp_server.py
```