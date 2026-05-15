Structure

AI-Research-Assistant/
├── backend/                           # FastAPI Backend
│   ├── agents/                        # Multi-Agent System
│   │   ├── __init__.py
│   │   ├── agent_state.py            # Shared state for LangGraph
│   │   ├── critic_agent.py           # Validates response quality
│   │   ├── editor_agent.py           # Refines final output
│   │   ├── langgraph_nodes.py        # LangGraph node definitions
│   │   ├── langgraph_workflow.py     # Workflow graph construction
│   │   ├── orchestrator.py           # Main workflow orchestrator
│   │   ├── research_agent.py         # Document retrieval agent
│   │   └── summarizer_agent.py       # Summarization agent
│   │
│   ├── db/                            # Database & Storage
│   │   ├── conversation_memory.py    # Legacy memory (deprecated)
│   │   ├── conversations.db          # SQLite database
│   │   ├── faiss_index.bin           # FAISS vector index
│   │   ├── faiss_index_documents.pkl # Document metadata
│   │   ├── faiss_index_meta.pkl      # Chunk metadata
│   │   ├── faiss_store.py            # FAISS operations
│   │   ├── memory_store.py           # Legacy memory store
│   │   ├── multi_doc_store.py        # Multi-document FAISS manager
│   │   ├── sqlite_memory.py          # SQLite conversation memory
│   │   └── documents/                # Per-document FAISS indexes
│   │       └── [doc_name]/           # Individual document stores
│   │           ├── index.bin
│   │           ├── metadata.pkl
│   │           └── info.pkl
│   │
│   ├── logs/                          # Application Logs
│   │   ├── agents.log                # Agent workflow logs
│   │   ├── api.log                   # API request logs
│   │   ├── database.log              # Database operation logs
│   │   └── parser.log                # Document parsing logs
│   │
│   ├── models/                        # Data Models
│   │   └── schemas.py                # Pydantic request/response schemas
│   │
│   ├── utils/                         # Utility Modules
│   │   ├── document_parser.py        # Multi-format document parser
│   │   ├── embeddings.py             # OpenAI embedding generation
│   │   ├── logger.py                 # Logging configuration
│   │   └── pdf_parser.py             # Legacy PDF parser
│   │
│   ├── config.py                      # Configuration loader
│   ├── main.py                        # FastAPI application & routes
│   └── requirements.txt               # Python dependencies
│
├── frontend/                          # Next.js Frontend
│   ├── components/                    # React Components
│   │   ├── AgentGraph.tsx            # Workflow visualization
│   │   └── ChatBox.tsx               # Chat interface
│   │
│   ├── pages/                         # Next.js Pages
│   │   ├── _app.tsx                  # App wrapper with providers
│   │   ├── index.tsx                 # Main chat interface
│   │   └── history.tsx               # Conversation history view
│   │
│   ├── styles/                        # Stylesheets
│   │   └── globals.css               # Global TailwindCSS styles
│   │
│   ├── next-env.d.ts                 # Next.js TypeScript declarations
│   ├── package.json                  # Node dependencies
│   ├── package-lock.json             # Lockfile
│   ├── postcss.config.js             # PostCSS configuration
│   ├── tailwind.config.js            # TailwindCSS configuration
│   └── tsconfig.json                 # TypeScript configuration
│
├── venv/                              # Python Virtual Environment
│
├── .env                               # Environment variables (gitignored)
├── .gitignore                         # Git ignore rules
├── PROJECT_ANALYSIS.md                # Project documentation
└── README.md                          # This file
