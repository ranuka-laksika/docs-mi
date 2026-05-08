# Generative AI Module Reference

This documentation provides a reference guide for the Generative AI Module.  
The Generative AI Module enables you to perform various operations such as chat, RAG chat, agent-based interactions, retrieving information from a knowledge base, and adding new entries to the knowledge base.  

## Connection Configurations

### LLM Connection

LLM (Large Language Model) connections are used to connect to various LLM providers. These connections are essential for enabling the Generative AI Module to interact with different LLM services.

<img src="{{base_path}}/assets/img/integrate/connectors/ai/llm-connections.png" title="LLM Provider Connections" width="700" alt="LLM Provider Connections"/>

The WSO2 MI Generative AI Module supports multiple LLM providers, allowing seamless integration with llm models.

- **Anthropic**  

- **Mistral AI**  

- **Open AI**  

- **Azure Open AI**  

- **Deepseek**  

#### Connection Configuration Parameters
The connection configuration parameters are used to establish a connection with the LLM provider. These parameters are needed to provide based on the provider you are using.
??? note "Anthropic"
    <table>
        <tr>
            <th> Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>name</td>
            <td>Connection Name</td>
            <td>Name of the connection.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>apiKey</td>
            <td>OpenAI Key</td>
            <td>API key used to authenticate with the OpenAI service.</td>
            <td>Yes</td>
        </tr>
    </table>

??? note "Mistral AI" 
    <table>
        <tr>
            <th>Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>name</td>
            <td>Connection Name</td>
            <td>Name of the connection.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>apiKey</td>
            <td>MistralAI Key</td>
            <td>API key used to authenticate with the Mistral AI service.</td>
            <td>Yes</td>
        </tr>
    </table>

??? note "Open AI" 
    <table>
        <tr>
            <th>Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>name</td>
            <td>Connection Name</td>
            <td>Name of the connection.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>apiKey</td>
            <td>OpenAI Key</td>
            <td>API key used to authenticate with the OpenAI service.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>baseUrl</td>
            <td>Base Url</td>
            <td>Base URL of the OpenAI service.</td>
            <td>Yes</td>
        </tr>
    </table>

??? note "Azure Open AI"
    <table>
        <tr>
            <th>Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>name</td>
            <td>Connection Name</td>
            <td>Name of the connection.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>apiKey</td>
            <td>Azure OpenAI Key</td>
            <td>API key used to authenticate with the Azure OpenAI service.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>deploymentName</td>
            <td>Deployment Name</td>
            <td>Name of the deployment in Azure OpenAI.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>endpoint</td>
            <td>Endpoint</td>
            <td>Endpoint URL of the Azure OpenAI service.</td>
            <td>Yes</td>
        </tr>
    </table>

??? note "Deepseek"
    <table>
        <tr>
            <th>Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>name</td>
            <td>Connection Name</td>
            <td>Name of the connection.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>apiKey</td>
            <td>Deepseek API Key</td>
            <td>API key used to authenticate with the Deepseek service.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>baseUrl</td>
            <td>Base Url</td>
            <td>Base URL of the Deepseek service.</td>
            <td>Yes</td>
        </tr>
    </table>

### Embedding Model Connection

Embedding model connections are used to connect to various embedding model providers. These connections are essential for enabling the Generative AI Module to interact with different embedding model services.

<img src="{{base_path}}/assets/img/integrate/connectors/ai/embedding-connections.png" title="Embedding Model Provider Connections" width="250" alt="Embedding Model Provider Connections"/>

The WSO2 MI Generative AI Module supports Open AI embedding model provider.

#### Connection Configuration Parameters
The connection configuration parameters are used to establish a connection with the Embedding model provider. These parameters are needed to provide based on the provider you are using.
??? note "Open AI"
    <table>
        <tr>
            <th> Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>name</td>
            <td>Connection Name</td>
            <td>Name of the connection.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>apiKey</td>
            <td>OpenAI Key</td>
            <td>API key used to authenticate with the OpenAI service.</td>
            <td>Yes</td>
        </tr>
    </table>

### Vector Database (Knowledgebase) Connection

Vector database connections are used to connect to various vector database providers. These connections are essential for enabling the Generative AI Module to interact with different vector database services.

<img src="{{base_path}}/assets/img/integrate/connectors/ai/vector-store-connections.png" title="Vector Store Connections" width="700" alt="Vector Store Connections"/>

The WSO2 MI Generative AI Module supports multiple vector stores.  

- **Chroma DB**  
    Chroma is an open-source vector database designed for AI applications, enabling efficient storage and retrieval of embeddings.

- **Postgres DB**  
    Postgres DB is a powerful, open-source relational database that can be used as a vector store for managing embeddings.

    !!! note
        To use Postgres DB as a vector store, ensure the `pgvector` extension is installed on the machine where the Postgres DB is running.  
        After installation, execute the following SQL command in your Postgres database to enable the creation of vector columns:

        ```sql
        CREATE EXTENSION vector;
        ```
        
- **Pinecone DB**  
    Pinecone is a managed vector database service that provides high-performance and scalable storage for embeddings.

- **MI Vector Store**  
    MI Vector Store is an in-memory vector database offered by WSO2 MI which will persist the data in the MI resources.  

    !!! info
        MI Vector Store is designed specifically for testing purposes and is not recommended for production use. Please use other vector stores for production scenarios.

#### Connection Configuration Parameters
The connection configuration parameters are used to establish a connection with the vector store. These parameters are needed to provide based on the store you are using.
??? note "Chroma DB"
    <table>
        <tr>
            <th> Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>name</td>
            <td>Connection Name</td>
            <td>Name of the connection.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>url</td>
            <td>Base URL</td>
            <td>Base URL of the Chroma service.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>collection</td>
            <td>Collection</td>
            <td>Name of the collection in Chroma.</td>
            <td>Yes</td>
        </tr>
    </table>

??? note "Postgres DB"
    <table>
        <tr>
            <th> Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>name</td>
            <td>Connection Name</td>
            <td>Name of the connection.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>host</td>
            <td>Host</td>
            <td>Host name of the Postgres DB.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>port</td>
            <td>Port</td>
            <td>Port number of the Postgres DB.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>database</td>
            <td>Database</td>
            <td>Name of the database in Postgres DB.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>user</td>
            <td>User</td>
            <td>User name to connect to the Postgres DB.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>password</td>
            <td>Password</td>
            <td>Password to connect to the Postgres DB.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>table</td>
            <td>Table</td>
            <td>Name of the table in Postgres DB.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>dimension</td>
            <td>Dimension of embeddings</td>
            <td>Dimension of the embeddings used in the Postgres DB.</td>
            <td>Yes</td>
        </tr>
    </table>

??? note "Pinecone DB"
    <table>
        <tr>
            <th> Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>name</td>
            <td>Connection Name</td>
            <td>Name of the connection.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>apiKey</td>
            <td>API Key</td>
            <td>API key used to authenticate with the Pinecone service.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>index</td>
            <td>Index</td>
            <td>Name of the index in Pinecone.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>namespace</td>
            <td>Namespace</td>
            <td>Namespace of the index in Pinecone.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>cloud</td>
            <td>Cloud</td>
            <td>Cloud provider of the Pinecone service.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>region</td>
            <td>Region</td>
            <td>Region of the Pinecone service.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>dimension</td>
            <td>Dimension of embeddings</td>
            <td>Dimension of the embeddings used in the Pinecone service.</td>
            <td>Yes</td>
        </tr>
    </table>

??? note "MI Vector Store"
    <table>
        <tr>
            <th> Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>name</td>
            <td>Connection Name</td>
            <td>Name of the connection.</td>
            <td>Yes</td>
        </tr>
    </table>

### Chat Memory Connection

Chat memory connections are used to connect to various chat memory providers. Chat memory is essential for enabling the Generative AI Module to manage chat history and context.  

<img src="{{base_path}}/assets/img/integrate/connectors/ai/chat-memory-connections.png" title="Chat Memory Connections" width="500" alt="Chat Memory Connections"/>

The WSO2 MI Generative AI Module supports multiple chat memory providers.

- **Postgres DB**  
    Postgres DB is a powerful, open-source relational database that can be used as a chat memory provider for managing chat history.

- **File Memory**  
    File memory is a simple file-based storage solution for managing chat history. It persists chat data within the MI resources, storing the memory file at `<MI_SERVER_HOME>/registry/governance/ai/chat-memory/<CONNECTION_NAME>.json`.

    !!! info
        File memory is designed specifically for testing purposes and is not recommended for production use. Please use other chat memory providers for production scenarios.

#### Connection Configuration Parameters
The connection configuration parameters are used to establish a connection with the chat memory database. These parameters are needed to provide based on the database you are using.
??? note "Postgres DB"
    <table>
        <tr>
            <th> Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>name</td>
            <td>Connection Name</td>
            <td>Name of the connection.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>host</td>
            <td>Host</td>
            <td>Host name of the Postgres DB.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>port</td>
            <td>Port</td>
            <td>Port number of the Postgres DB.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>database</td>
            <td>Database</td>
            <td>Name of the database in Postgres DB.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>user</td>
            <td>User</td>
            <td>User name to connect to the Postgres DB.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>password</td>
            <td>Password</td>
            <td>Password to connect to the Postgres DB.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>table</td>
            <td>Table</td>
            <td>Name of the table in Postgres DB.</td>
            <td>Yes</td>
        </tr>
    </table>  

??? note "File Memory"
    <table>
        <tr>
            <th> Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>name</td>
            <td>Connection Name</td>
            <td>Name of the connection.</td>
            <td>Yes</td>
        </tr>
    </table>

## Tools

Tools enable AI agents to interact with external systems, retrieve data, and perform actions. When you configure an agent with tools, the AI model can determine when and how to use them based on the user's query and the tool descriptions you provide.

### Tool types

The Generative AI Module supports the following tool types:

- **HTTP tools**: Enable the agent to make HTTP requests (GET, POST, PUT, DELETE, PATCH) to external APIs or services.

- **AI operation tools**: Enable the agent to use AI module operations such as `getFromKnowledge` to retrieve information from vector stores.

- **MCP tools**: Enable the agent to connect to Model Context Protocol (MCP) servers and use the tools they provide.

### How tools work with agents

When you add tools to an agent operation, the AI model analyzes the user's query and the available tools. If the query requires external data or actions, the model selects the appropriate tool, generates the necessary arguments, and executes the tool. The tool's response is then used to formulate the agent's final response to the user.

For example, if a user asks "What is the weather in New York?", an agent configured with a weather API tool can:

1. Identify that weather information is needed.
2. Select the appropriate weather tool.
3. Generate the required arguments (location: "New York").
4. Execute the tool to fetch weather data.
5. Use the retrieved data to respond to the user.

### Tool configuration parameters

All tools share common configuration parameters:

<table>
    <tr>
        <th>Parameter name</th>
        <th>Display name</th>
        <th>Description</th>
        <th>Required</th>
    </tr>
    <tr>
        <td>name</td>
        <td>Tool Name</td>
        <td>Unique identifier for the tool. The AI model uses this name to reference the tool.</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>description</td>
        <td>Tool Description</td>
        <td>Clear description of what the tool does. The AI model uses this description to determine when to use the tool. Be specific and include the purpose and expected behavior.</td>
        <td>Yes</td>
    </tr>
</table>

### HTTP tools

HTTP tools allow the agent to make HTTP requests to external APIs. Each HTTP method (GET, POST, PUT, DELETE, PATCH) has specific configuration parameters.

#### HTTP tool configuration parameters

In addition to the common tool parameters, HTTP tools require the following configuration:

<table>
    <tr>
        <th>Parameter name</th>
        <th>Display name</th>
        <th>Description</th>
        <th>Required</th>
    </tr>
    <tr>
        <td>connection</td>
        <td>HTTP Connection</td>
        <td>HTTP connection that defines the base URL and authentication for the target API.</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>relativePath</td>
        <td>Relative Path</td>
        <td>Path to append to the base URL defined in the connection.</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>requestBody</td>
        <td>Request Body</td>
        <td>Request payload for POST, PUT, and PATCH methods. You can mark this field as an AI-populated argument by clicking the magic button, allowing the AI to generate the appropriate request body dynamically.</td>
        <td>No</td>
    </tr>
    <tr>
        <td>headers</td>
        <td>Headers</td>
        <td>HTTP headers to include in the request.</td>
        <td>No</td>
    </tr>
    <tr>
        <td>queryParameters</td>
        <td>Query Parameters</td>
        <td>Query parameters to include in the request URL. You can mark parameters as AI-populated arguments.</td>
        <td>No</td>
    </tr>
</table>

**Sample HTTP POST tool configuration**

```xml
<tool name="CustomerInfoTool" template="http_post_tool_1" resultExpression="${vars.http_post_tool.payload}" description="Get customer information from the internal database">
    <http.post>
        <connection>BANK_API_CONN</connection>
        <relativePath>/customerInfo</relativePath>
        <requestBody aiPopulated="true" description="Provide the customer ID in the following format: {userID: 'C567'}"/>
    </http.post>
</tool>
```

### AI operation tools

AI operation tools enable the agent to use AI module operations as tools. Currently, the `getFromKnowledge` operation is supported as a tool, allowing agents to retrieve information from vector stores.

#### Get from knowledge tool configuration parameters

In addition to the common tool parameters, the `getFromKnowledge` tool requires the following configuration:

<table>
    <tr>
        <th>Parameter name</th>
        <th>Display name</th>
        <th>Description</th>
        <th>Required</th>
    </tr>
    <tr>
        <td>embeddingConfigKey</td>
        <td>Embedding Model Connection</td>
        <td>Connection to the embedding model provider. Refer to the <a href="#embedding-model-connection">Embedding Model Connection</a> section for more details.</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>vectorStoreConfigKey</td>
        <td>Vector Store Connection</td>
        <td>Connection to the vector store provider. Refer to the <a href="#vector-database-knowledgebase-connection">Vector Database Connection</a> section for more details.</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>input</td>
        <td>Input</td>
        <td>Search query to retrieve relevant information from the knowledge base. You can mark this field as an AI-populated argument.</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>embeddingModel</td>
        <td>Embedding Model</td>
        <td>Name of the embedding model to use for generating embeddings from the input query.</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>maxResults</td>
        <td>Max Results</td>
        <td>Maximum number of results to retrieve from the vector store.</td>
        <td>No</td>
    </tr>
    <tr>
        <td>minScore</td>
        <td>Min Score</td>
        <td>Minimum similarity score threshold for the results.</td>
        <td>No</td>
    </tr>
</table>

**Sample get from knowledge tool configuration**

```xml
<tool name="GetBankDocumentsTool" template="ai_getFromKnowledge_tool_1" resultExpression="${vars.ai_getFromKnowledge_tool.payload}" description="Retrieve PineValley Bank documents from the knowledge base">
    <ai.getFromKnowledge>
        <connections>
            <embeddingConfigKey>EMBEDDING_CONN</embeddingConfigKey>
            <vectorStoreConfigKey>VECTOR_STORE_CONN</vectorStoreConfigKey>
        </connections>
        <input aiPopulated="true" description="Search query to find relevant bank documents"/>
        <embeddingModel>text-embedding-3-small</embeddingModel>
        <maxResults>5</maxResults>
        <minScore>0.75</minScore>
    </ai.getFromKnowledge>
</tool>
```

### MCP tools

Model Context Protocol (MCP) tools enable the agent to connect to MCP servers and use the tools they provide. MCP is a standardized protocol for connecting AI models to external data sources and tools.

#### MCP connection configuration

To use MCP tools, you must first create an MCP connection.

<img src="{{base_path}}/assets/img/get-started/build-first-ai-integration/agent/add_mcp_connection.jpeg" title="MCP Connection Configuration" width="700" alt="MCP Connection Configuration"/>

**MCP connection parameters:**

<table>
    <tr>
        <th>Parameter name</th>
        <th>Display name</th>
        <th>Description</th>
        <th>Required</th>
    </tr>
    <tr>
        <td>name</td>
        <td>Connection Name</td>
        <td>Name of the MCP connection.</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>url</td>
        <td>MCP Server URL</td>
        <td>URL of the MCP server that provides the tools.</td>
        <td>Yes</td>
    </tr>
    <tr>
        <td>authConfig</td>
        <td>Authentication Configuration</td>
        <td>Authentication credentials required to connect to the MCP server (if authentication is enabled).</td>
        <td>No</td>
    </tr>
</table>

#### Adding MCP tools to an agent

Once you have created an MCP connection, you can add MCP tools to your agent. When you select an MCP connection, the available tools from that MCP server are automatically listed, allowing you to select which tools to include.

<img src="{{base_path}}/assets/img/get-started/build-first-ai-integration/agent/select_mcp_tools.jpeg" title="Select MCP Tools" width="700" alt="Select MCP Tools"/>

**Sample agent configuration with MCP tools**

```xml
<ai.agent>
    <connections>
        <llmConfigKey>LLM_CONN</llmConfigKey>
        <memoryConfigKey>MEMORY_CONN</memoryConfigKey>
    </connections>
    <sessionId>{${payload.sessionId}}</sessionId>
    <role>Customer Service Agent</role>
    <instructions>Assist customers with their queries using available tools.</instructions>
    <prompt>${payload.query}</prompt>
    <responseVariable>ai_agent_1</responseVariable>
    <overwriteBody>false</overwriteBody>
    <modelName>gpt-4o</modelName>
    <tools>
        <tool name="MCPTool1" template="mcp_tool_1" resultExpression="${vars.mcp_tool_1.payload}" description="Description of MCP tool functionality"/>
        <tool name="MCPTool2" template="mcp_tool_2" resultExpression="${vars.mcp_tool_2.payload}" description="Description of another MCP tool"/>
    </tools>
</ai.agent>
```

### Best practices for tool configuration

When configuring tools for your AI agent, follow these best practices:

- **Write clear tool descriptions**: The AI model relies on tool descriptions to determine when to use each tool. Be specific about what the tool does, what data it retrieves, and when it should be used.

- **Use meaningful tool names**: Choose descriptive names that clearly indicate the tool's purpose (for example, `GetCustomerInfo` instead of `Tool1`).

- **Mark appropriate fields as AI-populated**: Use the AI-populated argument feature for fields that the AI should fill dynamically based on the user's query.

- **Provide argument descriptions**: When marking a field as AI-populated, include a clear description that explains what information the AI should provide and in what format.

- **Test tool execution**: Verify that each tool works correctly in isolation before adding it to the agent.

- **Limit the number of tools**: While agents can work with multiple tools, providing too many tools can reduce the AI model's accuracy in selecting the right tool. Start with essential tools and add more as needed.

For a complete tutorial on using tools with AI agents, see the [Build an AI Agent]({{base_path}}/get-started/build-first-ai-integration/first-integration-ai-agent/) tutorial.

## Operations
    
??? note "chat"
    The chat operation sends a message to the LLM and receives a response.  
    **Connection Parameters:**
    <table>
        <tr>
            <th>Parameter Name</th>
            <th>Connection Category</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>llmConfigKey</td>
            <td>LLM Connection</td>
            <td>Connection to the LLM provider. Refer to the [LLM Connection](#llm-connection) section for more details.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>memoryConfigKey</td>
            <td>Chat Memory Connection</td>
            <td>Connection to the chat memory provider. Refer to the [Chat Memory Connection](#chat-memory-connection) section for more details.</td>
            <td>No</td>
        </tr>
    </table>  
    **Operation Parameters:**
    <table>
        <tr>
            <th>Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>modelName</td>
            <td>Model Name</td>
            <td>Name of the model to use for the chat operation.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>sessionId</td>
            <td>Session ID</td>
            <td>Unique identifier for the chat session.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>prompt</td>
            <td>User Query/Prompt</td>
            <td>Message to send to the LLM.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>attachments</td>
            <td>Attachments</td>
            <td>
                Attachments to send along with the message to the LLM. The attachments should be in the following format:  
                <code>[{"type":"application/pdf", "content":"base64 content"}]</code>.  
                Supported types include:
                <ul>
                    <li><code>application/pdf</code></li>
                    <li><code>image/png</code></li>
                    <li><code>image/jpeg</code></li>
                    <li><code>text/plain</code></li>
                    <li><code>text/html</code></li>
                    <li><code>text/csv</code></li>
                    <li><code>text/xml</code></li>
                </ul>
                The content must be base64 encoded.
            </td>
            <td>No</td>
        </tr>
        <tr>
            <td>outputType</td>
            <td>Output Type</td>
            <td>Type of output to return. The supported types are: <code>string</code>, <code>integer</code>, <code>float</code>, <code>boolean</code>. The default is <code>string</code>.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>maxHistory</td>
            <td>Max chat history</td>
            <td>Maximum number of chat history entries to send to the LLM.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>system</td>
            <td>System Prompt</td>
            <td>System prompt to set the context for the conversation.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>maxTokens</td>
            <td>Max Tokens</td>
            <td>Maximum number of tokens to generate in the response.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>temperature</td>
            <td>Temperature</td>
            <td>Sampling temperature to use for the response. The default is 0.7.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>topP</td>
            <td>Top P</td>
            <td>Top P sampling to use for the response. The default is 1.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>frequencyPenalty</td>
            <td>Frequency Penalty</td>
            <td>Frequency penalty to use for the response. The default is 0.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>seed</td>
            <td>Seed</td>
            <td>Specifies the random seed value to ensure reproducibility of the response. The default value is 0.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>responseVariable</td>
            <td>Output Variable Name</td>
            <td>Name of the variable to store the response.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>overwriteBody</td>
            <td>Overwrite Body</td>
            <td>Whether to overwrite the message body with the response. The default is false.</td>
            <td>No</td>
        </tr>
    </table>

    **Sample configuration**
    
    ```xml
    <ai.chat>
        <connections>
            <llmConfigKey>LLM_CONN</llmConfigKey>
            <memoryConfigKey>MEMORY_CONN</memoryConfigKey>
        </connections>
        <sessionId>{${payload.sessionId}}</sessionId>
        <system>You are a helpful AI assistant</system>
        <prompt>${payload.content}</prompt>
        <outputType>string</outputType>
        <responseVariable>ai_chat_1</responseVariable>
        <overwriteBody>false</overwriteBody>
        <modelName>gpt-4o</modelName>
        <temperature>0.7</temperature>
        <maxTokens>4069</maxTokens>
        <topP>1</topP>
        <frequencyPenalty>0</frequencyPenalty>
        <maxHistory>10</maxHistory>
    </ai.chat>
    ```
    
    **Sample response**
    
    The response received will be stored in the variable `ai_chat_1` as a JSON object. The following is a sample response.
    
    ```json
    {
    "content": "WSO2 Micro Integrator is a comprehensive integration solution designed to simplify digital transformation. It facilitates connectivity among applications, services, data, and the cloud through a user-friendly, low-code graphical design experience. The Micro Integrator offers deployment options in both microservices and ESB styles, providing greater flexibility.",
    "tokenUsage": {
        "inputTokensDetails": {
        "cachedTokens": 0
        },
        "outputTokensDetails": {
        "reasoningTokens": 0
        },
        "inputTokenCount": 41,
        "outputTokenCount": 459,
        "totalTokenCount": 500
    },
    "sources": [],
    "finishReason": "STOP",
    "toolExecutions": []
    }
    ```  


??? note "ragChat"
    The `ragChat` operation sends a message to the LLM and retrieves a response, leveraging a Retrieval-Augmented Generation (RAG) approach.  
    **Connection Parameters:**
    <table>
        <tr>
            <th>Parameter Name</th>
            <th>Connection Category</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>embeddingConfigKey</td>
            <td>Embedding model Connection</td>
            <td>Connection to the embedding model provider. Refer to the [Embedding Model Connection](#embedding-model-connection) section for more details.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>vectorStoreConfigKey</td>
            <td>Vector Store Connection</td>
            <td>Connection to the vector store provider. Refer to the [Vector Store Connection](#vector-store-connection) section for more details.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>llmConfigKey</td>
            <td>LLM Connection</td>
            <td>Connection to the LLM provider. Refer to the [LLM Connection](#llm-connection) section for more details.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>memoryConfigKey</td>
            <td>Memory Connection</td>
            <td>Connection to the chat memory provider. Refer to the [Chat Memory Connection](#chat-memory-connection) section for more details.</td>
            <td>No</td>
        </tr>
    </table>  

    **Operation Parameters:**
    <table>
        <tr>
            <th>Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>sessionId</td>
            <td>Session ID</td>
            <td>Unique identifier for the chat session.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>prompt</td>
            <td>User Query/Prompt</td>
            <td>Message to send to the LLM.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>embeddingModel</td>
            <td>Embedding Model</td>
            <td>Name of the embedding model to use for the RAG operation.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>maxResults</td>
            <td>Max Results</td>
            <td>Maximum number of results to retrieve from the vector store.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>minScore</td>
            <td>Min Score</td>
            <td>Minimum score threshold for the results retrieved from the vector store.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>modelName</td>
            <td>Model Name</td>
            <td>Name of the model to use for the chat operation.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>outputType</td>
            <td>Output Type</td>
            <td>Type of output to return. The supported types are: <code>string</code>, <code>integer</code>, <code>float</code>, <code>boolean</code>. The default is <code>string</code>.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>maxHistory</td>
            <td>Max chat history</td>
            <td>Maximum number of chat history entries to send to the LLM.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>system</td>
            <td>System Prompt</td>
            <td>System prompt to set the context for the conversation.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>maxTokens</td>
            <td>Max Tokens</td>
            <td>Maximum number of tokens to generate in the response.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>temperature</td>
            <td>Temperature</td>
            <td>Sampling temperature to use for the response. The default is 0.7.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>topP</td>
            <td>Top P</td>
            <td>Top P sampling to use for the response. The default is 1.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>frequencyPenalty</td>
            <td>Frequency Penalty</td>
            <td>Frequency penalty to use for the response. The default is 0.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>seed</td>
            <td>Seed</td>
            <td>Specifies the random seed value to ensure reproducibility of the response. The default value is 0.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>responseVariable</td>
            <td>Output Variable Name</td>
            <td>Name of the variable to store the response.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>overwriteBody</td>
            <td>Overwrite Body</td>
            <td>Whether to overwrite the message body with the response. The default is false.</td>
            <td>No</td>
        </tr>
    </table>

    **Sample configuration**
    
    ```xml
    <ai.ragChat>
        <connections>
            <llmConfigKey>LLM_CONN</llmConfigKey>
            <memoryConfigKey>MEMORY_CONN</memoryConfigKey>
            <embeddingConfigKey>EMBEDDING_CONN</embeddingConfigKey>
            <vectorStoreConfigKey>VECTOR_STORE_CONN</vectorStoreConfigKey>
        </connections>
        <sessionId>{${payload.sessionId}}</sessionId>
        <prompt>${payload.content}</prompt>
        <outputType>string</outputType>
        <responseVariable>ai_ragChat_1</responseVariable>
        <overwriteBody>false</overwriteBody>
        <embeddingModel>text-embedding-3-small</embeddingModel>
        <maxResults>5</maxResults>
        <minScore>0.75</minScore>
        <modelName>gpt-4o</modelName>
        <temperature>0.7</temperature>
        <maxTokens>4069</maxTokens>
        <topP>1</topP>
        <frequencyPenalty>0</frequencyPenalty>
        <seed>0</seed>
        <system></system>
        <maxHistory>10</maxHistory>
    </ai.ragChat>
    ```
    
    **Sample response**
    
    The response received will be stored in the variable `ai_ragChat_1` as a JSON object. The following is a sample response.
    
    ```json
    {
    "content": "WSO2 Micro Integrator is a comprehensive integration solution designed to simplify digital transformation. It facilitates connectivity among applications, services, data, and the cloud through a user-friendly, low-code graphical design experience. The Micro Integrator offers deployment options in both microservices and ESB styles, providing greater flexibility.",
    "tokenUsage": {
        "inputTokensDetails": {
        "cachedTokens": 0
        },
        "outputTokensDetails": {
        "reasoningTokens": 0
        },
        "inputTokenCount": 99,
        "outputTokenCount": 62,
        "totalTokenCount": 161
    },
    "sources": [
        {
        "textSegment": {
            "text": "WSO2 Micro Integrator is a comprehensive integration solution that simplifies your digital transformation journey. The Micro Integrator streamlines connectivity among applications, services, data, and the cloud using a user-friendly, low-code graphical design experience. Deployment options include both microservices and ESB styles for greater flexibility.",
            "metadata": {
            "index": "0"
            }
        },
        "metadata": {}
        }
    ],
    "finishReason": "STOP",
    "toolExecutions": []
    }
    ```  

??? note "agent"
    The chat operation sends a message to the LLM and receives a response.  
    **Connection Parameters:**
    <table>
        <tr>
            <th>Parameter Name</th>
            <th>Connection Category</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>llmConfigKey</td>
            <td>LLM Connection</td>
            <td>Connection to the LLM provider. Refer to the [LLM Connection](#llm-connection) section for more details.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>memoryConfigKey</td>
            <td>Chat Memory Connection</td>
            <td>Connection to the chat memory provider. Refer to the [Chat Memory Connection](#chat-memory-connection) section for more details.</td>
            <td>No</td>
        </tr>
    </table>  
    **Operation Parameters:**
    <table>
        <tr>
            <th>Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>sessionId</td>
            <td>Session ID</td>
            <td>Unique identifier for the chat session.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>modelName</td>
            <td>Model Name</td>
            <td>Name of the model to use for the chat operation.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>role</td>
            <td>Role</td>
            <td>The specific function or responsibility assigned to the agent, defining its purpose and scope of operation.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>instructions</td>
            <td>Instructions</td>
            <td>Specific instructions or guidelines for the agent to follow during its operation.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>prompt</td>
            <td>User Query/Prompt</td>
            <td>Message to send to the LLM.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>attachments</td>
            <td>Attachments</td>
            <td>
                Attachments to send along with the message to the LLM. The attachments should be in the following format:  
                <code>[{"type":"application/pdf", "content":"base64 content"}]</code>.  
                Supported types include:
                <ul>
                    <li><code>application/pdf</code></li>
                    <li><code>image/png</code></li>
                    <li><code>image/jpeg</code></li>
                    <li><code>text/plain</code></li>
                    <li><code>text/html</code></li>
                    <li><code>text/csv</code></li>
                    <li><code>text/xml</code></li>
                </ul>
                The content must be base64 encoded.
            </td>
            <td>No</td>
        </tr>
        <tr>
            <td>outputType</td>
            <td>Output Type</td>
            <td>Type of output to return. The supported types are: <code>string</code>, <code>integer</code>, <code>float</code>, <code>boolean</code>. The default is <code>string</code>.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>maxHistory</td>
            <td>Max chat history</td>
            <td>Maximum number of chat history entries to send to the LLM.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>system</td>
            <td>System Prompt</td>
            <td>System prompt to set the context for the conversation.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>maxTokens</td>
            <td>Max Tokens</td>
            <td>Maximum number of tokens to generate in the response.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>temperature</td>
            <td>Temperature</td>
            <td>Sampling temperature to use for the response. The default is 0.7.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>topP</td>
            <td>Top P</td>
            <td>Top P sampling to use for the response. The default is 1.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>frequencyPenalty</td>
            <td>Frequency Penalty</td>
            <td>Frequency penalty to use for the response. The default is 0.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>seed</td>
            <td>Seed</td>
            <td>Specifies the random seed value to ensure reproducibility of the response. The default value is 0.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>responseVariable</td>
            <td>Output Variable Name</td>
            <td>Name of the variable to store the response.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>overwriteBody</td>
            <td>Overwrite Body</td>
            <td>Whether to overwrite the message body with the response. The default is false.</td>
            <td>No</td>
        </tr>
    </table>

    **Sample configuration**
    
    ```xml
    <ai.agent>
        <connections>
            <llmConfigKey>LLM_CONN</llmConfigKey>
            <memoryConfigKey>MEMORY_CONN</memoryConfigKey>
        </connections>
        <sessionId>{${payload.sessionId}}</sessionId>
        <role>Customer Assistance Agent</role>
        <instructions>Assist customers by providing accurate and helpful responses to their queries, ensuring a positive user experience.</instructions>
        <prompt>${payload.content}</prompt>
        <outputType>string</outputType>
        <responseVariable>ai_agent_1</responseVariable>
        <overwriteBody>false</overwriteBody>
        <modelName>gpt-4o</modelName>
        <temperature>0.7</temperature>
        <maxTokens>4069</maxTokens>
        <topP>1</topP>
        <frequencyPenalty>0</frequencyPenalty>
        <maxHistory>10</maxHistory>
    </ai.agent>
    ```
    
    **Sample response**
    
    The response received will be stored in the variable `ai_agent_1` as a JSON object. The following is a sample response.
    
    ```json
    {
    "content": "Hello John Doe! I can help you explore various investment options offered by PineValley Bank. Since your investment goal is long-term growth, let's consider some of the products that might align with your objectives:\n\n1. **Qtrade Guided Portfolios**: These are professionally managed portfolios designed to help achieve long-term growth with a balanced risk approach. They might be suitable for you if you prefer a hands-off approach but still want expert management.\n\n2. **TFSAs (Tax-Free Savings Accounts)**: A TFSA allows your investments to grow tax-free, which is beneficial for long-term growth. You can invest in various assets within a TFSA, including stocks and ETFs.\n\n3. **RRSPs (Registered Retirement Savings Plans)**: An RRSP provides tax-deferred growth, which can be advantageous for long-term retirement planning. Contributions are tax-deductible, and the funds grow without being taxed until withdrawal.\n\n4. **Direct Investing (Stocks, ETFs)**: If you prefer more control over your investments, you can consider direct investing in stocks and ETFs. This approach requires more involvement but can be rewarding if you want to actively manage your portfolio.\n\n5. **GICs (Guaranteed Investment Certificates)**: While generally more conservative, GICs offer guaranteed returns, making them a stable component of a diversified portfolio.\n\nSince I couldn't retrieve detailed brochures or documents this time, I recommend considering these options and contacting PineValley Bank for specific product brochures and more detailed guidance. If you have any questions about these products or need help with the onboarding process, feel free to ask!",
    "tokenUsage": {
        "inputTokenCount": 1995,
        "outputTokenCount": 374,
        "totalTokenCount": 2369
    },
    "finishReason": "STOP",
    "toolExecutions": [
        {
        "request": {
            "id": "call_4MZwbJiAOJPUuuJFpcKSXneV",
            "name": "http_post_tool_0",
            "arguments": "{\"requestBodyJson\":\"{\\\"userID\\\": \\\"C567\\\"}\"}"
        },
        "result": "{\"userID\":\"C567\",\"name\":\"John Doe\",\"age\":30,\"investmentGoal\":\"Long-term growth\"}"
        },
        {
        "request": {
            "id": "call_XBFZADsSZsSzl3UBArT60H1O",
            "name": "ai_getFromKnowledge_tool_0",
            "arguments": "{\"input\":\"investment products offered by PineValley Bank\"}"
        },
        "result": "[]"
        }
    ]
    }
    ```  

??? note "addToKnowledge"
    The `ragChat` operation sends a message to the LLM and retrieves a response, leveraging a Retrieval-Augmented Generation (RAG) approach.  
    **Connection Parameters:**
    <table>
        <tr>
            <th>Parameter Name</th>
            <th>Connection Category</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>embeddingConfigKey</td>
            <td>Embedding model Connection</td>
            <td>Connection to the embedding model provider. Refer to the [Embedding Model Connection](#embedding-model-connection) section for more details.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>vectorStoreConfigKey</td>
            <td>Vector Store Connection</td>
            <td>Connection to the vector store provider. Refer to the [Vector Store Connection](#vector-store-connection) section for more details.</td>
            <td>Yes</td>
        </tr>
    </table>  
    **Operation Parameters:**
    <table>
        <tr>
            <th>Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>input</td>
            <td>Input</td>
            <td>Input to be added to the knowledge base.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>needParse</td>
            <td>Parse</td>
            <td>Whether to parse the input.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>parseType</td>
            <td>Type</td>
            <td>Type of parsing to be done. The supported types are: <code>pdf-to-text</code>, <code>markdown-to-text</code>, <code>html-to-text</code>, <code>doc-to-text</code>, <code>docx-to-text</code>, <code>xls-to-text</code>, <code>xlsx-to-text</code>, <code>ppt-to-text</code>, <code>pptx-to-text</code>. The default is <code>pdf-to-text</code>.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>needSplit</td>
            <td>Split</td>
            <td>Whether to split the input into smaller chunks.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>splitStrategy</td>
            <td>Strategy</td>
            <td>Strategy to be used for splitting the input. The supported strategies are: <code>Recursive</code>, <code>ByParagraph</code>, <code>BySentence</code>. The default is <code>Recursive</code>.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>maxSegmentSize</td>
            <td>Max Segment Size</td>
            <td>Maximum size of each segment after splitting. The default is 1000.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>maxOverlapSize</td>
            <td>Max Overlap Size</td>
            <td>Maximum overlap size between segments. The default is 200.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>needEmbedding</td>
            <td>Embedding</td>
            <td>Whether to generate embeddings for the input.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>embeddingModel</td>
            <td>Embedding Model</td>
            <td>Name of the embedding model to use for the RAG operation.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>responseVariable</td>
            <td>Output Variable Name</td>
            <td>Name of the variable to store the response.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>overwriteBody</td>
            <td>Overwrite Body</td>
            <td>Whether to overwrite the message body with the response. The default is false.</td>
            <td>No</td>
        </tr>
    </table>

    **Sample configuration**
    
    ```xml
    <ai.addToKnowledge>
        <connections>
            <embeddingConfigKey>EMBEDDING_CONN</embeddingConfigKey>
            <vectorStoreConfigKey>VECTOR_STORE_CONN</vectorStoreConfigKey>
        </connections>
        <input>{${payload.input}}</input>
        <needParse>true</needParse>
        <parseType>pdf-to-text</parseType>
        <needSplit>true</needSplit>
        <splitStrategy>Recursive</splitStrategy>
        <maxSegmentSize>1000</maxSegmentSize>
        <maxOverlapSize>200</maxOverlapSize>
        <needEmbedding>true</needEmbedding>
        <embeddingModel>text-embedding-3-small</embeddingModel>
        <responseVariable>ai_addToKnowledge_1</responseVariable>
        <overwriteBody>false</overwriteBody>
    </ai.addToKnowledge>
    ```
    
    **Sample response**
    
    The response received will be stored in the variable `ai_addToKnowledge_1` as a JSON object. The following is a sample response.
    
    ```json
    {
    "success": true
    }
    ```  

??? note "getFromKnowledge"
    The `ragChat` operation sends a message to the LLM and retrieves a response, leveraging a Retrieval-Augmented Generation (RAG) approach.  
    **Connection Parameters:**
    <table>
        <tr>
            <th>Parameter Name</th>
            <th>Connection Category</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>embeddingConfigKey</td>
            <td>Embedding model Connection</td>
            <td>Connection to the embedding model provider. Refer to the [Embedding Model Connection](#embedding-model-connection) section for more details.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>vectorStoreConfigKey</td>
            <td>Vector Store Connection</td>
            <td>Connection to the vector store provider. Refer to the [Vector Store Connection](#vector-store-connection) section for more details.</td>
            <td>Yes</td>
        </tr>
    </table>  
    **Operation Parameters:**
    <table>
        <tr>
            <th>Parameter Name</th>
            <th>Display Name</th>
            <th>Description</th>
            <th>Required</th>
        </tr>
        <tr>
            <td>input</td>
            <td>Input</td>
            <td>Input to be searched from the knowledge base.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>needEmbedding</td>
            <td>Embed Input</td>
            <td>Specifies whether to generate embeddings for the input. If the embedding vector is already provided by the user, this can be disabled. However, if the input is a raw string, embeddings must be generated.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>embeddingModel</td>
            <td>Embedding Model</td>
            <td>Name of the embedding model to use for the RAG operation.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>maxResults</td>
            <td>Max Results</td>
            <td>Maximum number of results to retrieve from the vector store.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>minScore</td>
            <td>Min Score</td>
            <td>Minimum score threshold for the results retrieved from the vector store.</td>
            <td>No</td>
        </tr>
        <tr>
            <td>responseVariable</td>
            <td>Output Variable Name</td>
            <td>Name of the variable to store the response.</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>overwriteBody</td>
            <td>Overwrite Body</td>
            <td>Whether to overwrite the message body with the response. The default is false.</td>
            <td>No</td>
        </tr>
    </table>

    **Sample configuration**
    
    ```xml
    <ai.getFromKnowledge>
        <connections>
            <embeddingConfigKey>EMBEDDING_CONN</embeddingConfigKey>
            <vectorStoreConfigKey>VECTOR_STORE_CONN</vectorStoreConfigKey>
        </connections>
        <input>{${payload.input}}</input>
        <needEmbedding>true</needEmbedding>
        <embeddingModel>text-embedding-3-small</embeddingModel>
        <maxResults>5</maxResults>
        <minScore>0.75</minScore>
        <responseVariable>ai_getFromKnowledge_1</responseVariable>
        <overwriteBody>false</overwriteBody>
    </ai.getFromKnowledge>
    ```
    
    **Sample response**
    
    The response received will be stored in the variable `email_list_1` as a JSON object. The following is a sample response.
    
    ```json
    [
    {
        "score": 0.9066269765264976,
        "embeddingId": "1fd2ccb4-4317-4c3e-a598-1cbcce4ae5ab",
        "embedding": [
            ...
        ],
        "embedded": {
        "text": "WSO2 Micro Integrator is a comprehensive integration solution that simplifies your digital transformation journey. The Micro Integrator streamlines connectivity among applications, services, data, and the cloud using a user-friendly, low-code graphical design experience. Deployment options include both microservices and ESB styles for greater flexibility.",
        "metadata": {
            "index": "0"
        }
        }
    }
    ]
    ```  

Click on the **Go to Tutorial** button below to learn how to build your first AI integration using the above operations. The tutorial will guide you through the process of creating a simple integration that utilizes the AI capabilities of WSO2 Micro Integrator.

<div style="display: flex; justify-content: center; align-items: center; gap: 20px; margin-top: 20px;">
  <a href="{{base_path}}/get-started/build-first-ai-integration/" class="md-button md-button--primary">Go to Tutorial →</a>
</div>
