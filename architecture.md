.
├── src
│   ├── application
│   │   ├── usecases
│   │   │   ├── SingleAnalysisUseCase.ts
│   │   │   ├── PairAnalysisUseCase.ts
│   │   │   └── ...
│   │   └── services
│   │       └── LLMOrchestrator.ts  // フォールバックロジックやLLM切り替えなど
│   ├── domain
│   │   ├── entities
│   │   │   ├── PalmReadingAnalysis.ts
│   │   │   ├── User.ts
│   │   │   └── ...
│   │   ├── valueObjects
│   │   │   ├── AnalysisLine.ts
│   │   │   ├── ChatMessage.ts
│   │   │   └── ...
│   │   ├── services
│   │   │   └── FortuneTeller.ts
│   │   ├── repositories (将来的にDBを扱う場合)
│   │   │   └── ...
│   │   └── ...
│   ├── infrastructure
│   │   ├── llm
│   │   │   ├── LLMService.ts         // インターフェース
│   │   │   ├── BedrockService.ts     // 実装
│   │   │   ├── GeminiService.ts      // 実装
│   │   │   └── ...
│   │   ├── http
│   │   │   └── ...
│   │   ├── db (将来的にDB関連クライアント等)
│   │   │   └── ...
│   │   └── ...
│   ├── interfaces
│   │   ├── controllers
│   │   │   └── PalmReadingController.ts
│   │   ├── routes
│   │   │   └── palmReadingRoutes.ts
│   │   ├── validators (Zod schemas)
│   │   │   └── chatRequestSchema.ts
│   │   └── ...
│   └── ...
├── docs
│   ├── diagrams
│   │   ├── domain-class-diagram.mmd
│   │   ├── data-flow.mmd
│   │   ├── context-map.mmd
│   │   └── ...
│   └── architecture.md
├── .env
├── package.json
└── README.md
