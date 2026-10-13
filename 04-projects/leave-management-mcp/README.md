# Leave Management MCP Server

**Objective:** Build your first MCP (Model Context Protocol) server that exposes leave-management tools.

**Level:** Intermediate  
**Original source:** `bode_casics_aigen/GenAI_Leave_Management_APP`

---

## Architecture

```mermaid
flowchart LR
    Client[MCP Client<br/>(Claude Desktop / other)] -->|MCP Protocol<br/>stdio| Server[FastMCP Server<br/>main.py]
    Server -->|get_leave_balance| Tools[Tool Functions]
    Server -->|apply_leave| Tools
    Server -->|get_leave_history| Tools
    Tools --> MockDB[(In-memory<br/>employee_leaves dict)]
    Tools --> Server --> Client
```

---

## Tools Exposed

| Tool | Description |
|------|-------------|
| `get_leave_balance` | Check remaining leave days for an employee |
| `apply_leave` | Apply for specific dates (deducts balance) |
| `get_leave_history` | Retrieve leave history |
| `get_greeting` | Personalized greeting resource |

---

## How to Run

### Option 1: With Claude Desktop (as in the Codebasics course)

1. Install [Claude Desktop](https://claude.ai/download).
2. Install uv: `pip install uv`
3. In this folder:
   ```bash
   uv sync
   uv run mcp install main.py
   ```
4. Fully quit and restart Claude Desktop.
5. You should see the LeaveManager tools available.

**Example queries:**
- "How many leave days does E001 have?"
- "Apply leave for E001 on 2025-04-17 and 2025-04-18"
- "Show leave history for E001"

### Option 2: Without Claude Desktop

Claude Desktop is only one possible MCP client. The server itself does not depend on it.

**Quick ways to test / use the server:**

1. **Run the server directly** (stdio mode):
   ```bash
   uv run python main.py
   ```

2. **MCP Inspector** (great for testing):
   ```bash
   npx @modelcontextprotocol/inspector uv run python main.py
   ```

3. **Other MCP clients** — Cursor, Continue, Cline, or any tool that supports MCP can connect to this server.

4. **Python client or LangGraph** — Use the `mcp` library or LangChain/LangGraph MCP adapters to call the tools from your own code.

5. **Direct function calls** — For pure learning, you can import and call the tool functions directly since they are normal Python functions.

---

## Learning Outcomes

- Creating an MCP server with FastMCP
- Defining tools with type hints and docstrings
- In-memory state management
- Using the server with Claude Desktop **or** other MCP clients

---

**Note:** This is a learning example with mock data. For production you would replace the dict with a real database.
