# アプリケーションアーキテクチャ

## ディレクトリ構造

```
.
├── src
│   ├── application          // ユースケースのオーケストレーションや、LLMフォールバック処理など**アプリケーションロジック**を担当
│   │   ├── usecases
│   │   │   ├── SingleAnalysisUseCase.ts
│   │   │   ├── PairAnalysisUseCase.ts
│   │   │   └── ...
│   │   └── services
│   │       └── LLMOrchestrator.ts  // フォールバックロジックやLLM切り替えなど
│   ├── domain               // **エンティティ/値オブジェクト/ドメインサービス**を定義し、ビジネスルールを保持
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
│   ├── infrastructure       // LLMとの連携、DB接続など**外部I/O**を扱う実装を集約
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
│   ├── interfaces           // Controller, Route, バリデーション(Zod)など、**外部からの入出力**を扱う層
│   │   ├── controllers
│   │   │   └── PalmReadingController.ts
│   │   ├── routes
│   │   │   └── palmReadingRoutes.ts
│   │   ├── validators (Zod schemas)
│   │   │   └── chatRequestSchema.ts
│   │   └── ...
│   └── ...
├── docs                     // マーメイド(Mermaid)で書いたUML図・DFD・コンテキストマップなどを配置してバージョン管理
│   ├── diagrams
│   │   ├── domain-class-diagram.mmd
│   │   ├── data-flow.mmd
│   │   ├── context-map.mmd
│   │   └── ...
│   └── architecture.md
├── .env
├── package.json
└── README.md
