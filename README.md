# GenAI Projects Lab

**Hands-on repository** containing the **actual exercise and project files** from the course materials, reorganized with industry-style documentation, architecture diagrams, and clear explanations.

Original raw dump: [bode_casics_aigen](https://github.com/yash9614/bode_casics_aigen)

---

## Structure

```
01-foundations/          → LLM calls, parameters, prompts
02-vector-db/            → ChromaDB, embeddings, metadata
03-exercises/            → Numbered exercises with solutions
04-projects/             → End-to-end projects (RAG, agents, MCP)
05-crewai/               → CrewAI crash course notebooks + code
06-agents-course/        → Structured agent course (course-gen-ai-main)
```

Each folder contains:
- The **real code / notebooks** copied from the source
- A detailed `README.md` with objectives, architecture (Mermaid), key concepts, and how to run

---

## Key Projects (start here)

| Project | Folder | What you build |
|---------|--------|----------------|
| Real Estate RAG Tool | `04-projects/real-estate-rag` | Streamlit app: URLs → Chroma → Groq answers |
| E-commerce Chatbot | `04-projects/ecommerce-chatbot` | Semantic router (FAQ + SQL + small-talk) |
| Leave Management MCP | `04-projects/leave-management-mcp` | MCP server for Claude Desktop |
| Cab Booking MCP | `04-projects/cab-booking-mcp` | MCP + Google Maps integration |
| CrewAI Agents | `05-crewai` | Email agents, crews, tools, memory |

---

## Recommended Learning Order

1. `01-foundations` — understand LLM calls & parameters
2. `02-vector-db` — ChromaDB basics
3. `03-exercises` — practice (prompt engineering, vector DB, fine-tuning)
4. `04-projects` — build the real apps
5. `05-crewai` + `06-agents-course` — multi-agent & advanced agents

---

## Setup

Most projects use:
- Python 3.11+
- `pip` or `uv`
- `.env` file with `GROQ_API_KEY` (and others as needed)

```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

Never commit API keys.

---

## Source & Attribution

Files are reorganized from the course dump for learning. Many solutions carry copyright notices from Codebasics Inc. / LearnerX. Use for personal education.

Start with any project README and run the code.
