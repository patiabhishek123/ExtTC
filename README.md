# tc-red-flag/

├── extension/        # Browser extension (frontend)
├── backend/          # API + LLM logic
├── shared/           # Shared types & constants
├── docs/             # Architecture & pitch docs
├── README.md
└── .gitignore


## extension/

├── manifest.json
│
├── content/
│   ├── extractText.js        # DOM scraping logic
│   ├── highlightClauses.js   # Highlight risky text
│   └── index.js              # Entry for content scripts
│
├── background/
│   ├── index.js              # Service worker
│   └── apiClient.js          # Calls backend
│
├── popup/
│   ├── popup.html
│   ├── popup.js
│   └── popup.css
│
├── assets/
│   ├── icons/
│   └── logo.png
│
└── utils/
    ├── heuristics.js         # Detect T&C pages
    └── sanitize.js           # Clean extracted text


## backend/

├── src/
│   ├── server.js             # Express/Fastify entry
│   │
│   ├── routes/
│   │   └── analyze.route.js
│   │
│   ├── controllers/
│   │   └── analyze.controller.js
│   │
│   ├── services/
│   │   ├── chunker.service.js
│   │   ├── llm.service.js
│   │   ├── riskAggregator.service.js
│   │   └── summarizer.service.js
│   │
│   ├── prompts/
│   │   └── redFlag.prompt.txt
│   │
│   ├── utils/
│   │   ├── cleanText.js
│   │   └── deduplicate.js
│   │
│   └── config/
│       ├── env.js
│       └── llm.js
│
├── tests/
│   └── analyze.test.js
│
├── package.json
└── README.md


## shared/

├── types/
│   └── redFlagReport.ts
│
└── constants/
    ├── riskLevels.js
    └── keywords.js


## docs/

├── architecture.md
├── prompt-design.md
├── threat-model.md
└── demo

