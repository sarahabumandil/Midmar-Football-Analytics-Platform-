# Midmar-Football-Analytics-Platform-

```text
midmar/
├── .env.example                          frontend variables (VITE_API_URL, VITE_BACKEND_PORT)
├── .gitignore                            ignores .env, venv, dist, videos, node_modules
├── .github/
│   └── workflows/
│       └── ci.yml                        CI: lint, test and build on every push
├── README.md                             project overview, setup, API reference
├── ROADMAP.md                            13-month phase plan
├── TASKS.md                              issue-level task breakdown
├── components.json                       shadcn/ui configuration
├── eslint.config.js                      lint rules
├── index.html                            Vite HTML entry
├── package.json                          frontend dependencies and scripts
├── package-lock.json
├── postcss.config.js
├── tailwind.config.ts                    Tailwind theme
├── tsconfig.json
├── tsconfig.app.json
├── tsconfig.node.json
├── vite.config.ts                        dev server, /api proxy, "@" aliases
├── vitest.config.ts                      test runner config
│
├── docs/
│   └── .gitkeep                          put demo.gif and screenshots here
│
├── public/
│   └── placeholder.svg
│
├── scripts/                              root-level helper scripts
│   ├── create_issues.sh                  bulk-create GitHub issues from TASKS.md
│   ├── import-players-from-csv.js        import players from a CSV file
│   └── smoke-check-server.js             quick backend health check
│
├── src/                                  React + TypeScript frontend
│   ├── main.tsx                          app entry
│   ├── App.tsx                           routes and providers
│   ├── App.css
│   ├── index.css                         global styles / Tailwind layers
│   ├── vite-env.d.ts
│   │
│   ├── Components/
│   │   ├── AdminRoute.tsx                blocks non-admins from admin pages
│   │   ├── ProtectedRoute.tsx            blocks logged-out users
│   │   ├── NavLink.tsx
│   │   ├── dashboard/
│   │   │   ├── PerformanceChart.tsx
│   │   │   ├── RecentActivity.tsx
│   │   │   └── RiskOverview.tsx
│   │   ├── layout/
│   │   │   ├── Header.tsx
│   │   │   ├── MainLayout.tsx            page shell (header + sidebar + content)
│   │   │   └── Sidebar.tsx
│   │   └── ui/                           shadcn/ui building blocks
│   │       ├── accordion.tsx
│   │       ├── alert-dialog.tsx
│   │       ├── alert.tsx
│   │       ├── aspect-ratio.tsx
│   │       ├── avatar.tsx
│   │       ├── badge.tsx
│   │       ├── breadcrumb.tsx
│   │       ├── button.tsx
│   │       ├── calendar.tsx
│   │       ├── card.tsx
│   │       ├── carousel.tsx
│   │       ├── chart.tsx
│   │       ├── checkbox.tsx
│   │       ├── collapsible.tsx
│   │       ├── command.tsx
│   │       ├── context-menu.tsx
│   │       ├── dialog.tsx
│   │       ├── drawer.tsx
│   │       ├── dropdown-menu.tsx
│   │       ├── form.tsx
│   │       ├── hover-card.tsx
│   │       ├── input-otp.tsx
│   │       ├── input.tsx
│   │       ├── label.tsx
│   │       ├── loading-spinner.tsx       custom
│   │       ├── menubar.tsx
│   │       ├── navigation-menu.tsx
│   │       ├── pagination.tsx
│   │       ├── player-avatar.tsx         custom
│   │       ├── player-card.tsx           custom
│   │       ├── popover.tsx
│   │       ├── progress.tsx
│   │       ├── radio-group.tsx
│   │       ├── resizable.tsx
│   │       ├── risk-badge.tsx            custom (injury risk level)
│   │       ├── scroll-area.tsx
│   │       ├── select.tsx
│   │       ├── separator.tsx
│   │       ├── sheet.tsx
│   │       ├── sidebar.tsx
│   │       ├── skeleton.tsx
│   │       ├── slider.tsx
│   │       ├── sonner.tsx
│   │       ├── stat-card.tsx             custom (dashboard numbers)
│   │       ├── switch.tsx
│   │       ├── table.tsx
│   │       ├── tabs.tsx
│   │       ├── textarea.tsx
│   │       ├── toast.tsx
│   │       ├── toaster.tsx
│   │       ├── toggle-group.tsx
│   │       ├── toggle.tsx
│   │       ├── tooltip.tsx
│   │       └── use-toast.ts
│   │
│   ├── contexts/
│   │   └── AuthContext.tsx               login state and token handling
│   │
│   ├── hooks/
│   │   ├── use-mobile.tsx
│   │   └── use-toast.ts
│   │
│   ├── lib/
│   │   ├── analysisVideo.ts              video-analysis helpers
│   │   └── utils.ts
│   │
│   ├── pages/
│   │   ├── Landing.tsx                   public home page
│   │   ├── Index.tsx
│   │   ├── Login.tsx
│   │   ├── Signup.tsx
│   │   ├── Dashboard.tsx
│   │   ├── Players.tsx
│   │   ├── MarketValue.tsx               market-value prediction page
│   │   ├── InjuryPrediction.tsx          injury-risk prediction page
│   │   ├── VideoAnalysis.tsx             upload and view analyzed match video
│   │   ├── Profile.tsx
│   │   ├── Admin.tsx
│   │   ├── NotFound.tsx
│   │   └── admin/
│   │       ├── ActivityLogs.tsx
│   │       ├── Analytics.tsx
│   │       ├── Reports.tsx
│   │       └── Settings.tsx
│   │
│   ├── services/                         all backend calls
│   │   ├── api.ts                        base HTTP client and endpoints
│   │   ├── playerService.ts
│   │   ├── teamPlayerService.ts
│   │   └── mockAIService.ts              mock predictions for offline UI work
│   │
│   └── test/
│       ├── setup.ts
│       └── example.test.ts
│
├── server/                               Node.js + Express backend
│   ├── .env.example                      MONGODB_URI, JWT_SECRET, PORT, PYTHON_API_URL ...
│   ├── README.md
│   ├── package.json
│   ├── package-lock.json
│   ├── server.js                         entry: app setup, routes, DB connect
│   ├── test-signup.js                    manual signup test
│   │
│   ├── config/
│   │   └── database.js                   MongoDB connection
│   │
│   ├── controllers/
│   │   ├── accountController.js
│   │   ├── adminController.js
│   │   ├── aiController.js               calls the Python service
│   │   ├── analyticsController.js
│   │   ├── authController.js
│   │   ├── matchController.js
│   │   └── playersController.js
│   │
│   ├── middleware/
│   │   ├── asyncHandler.js
│   │   ├── auth.js                       JWT and role checks
│   │   └── errorMiddleware.js
│   │
│   ├── models/                           Mongoose schemas
│   │   ├── ActivityLog.js
│   │   ├── IdMapping.js
│   │   ├── InjuryPrediction.js
│   │   ├── MarketValuePrediction.js
│   │   ├── Match.js
│   │   ├── Player.js
│   │   ├── PlayerAggregate.js
│   │   ├── PlayerMatchStat.js
│   │   ├── PlayerResetLog.js
│   │   ├── ReportEmailRequest.js
│   │   ├── Team.js
│   │   ├── User.js                       bcrypt hashing
│   │   └── UserPreference.js
│   │
│   ├── routes/
│   │   ├── account.js
│   │   ├── admin.js
│   │   ├── ai.js                         predictions and video analysis
│   │   ├── auth.js
│   │   ├── dashboard.js
│   │   ├── matches.js
│   │   ├── players.js
│   │   ├── reports.js
│   │   └── setup.js
│   │
│   ├── services/
│   │   ├── activityLog.service.js
│   │   ├── adminInit.service.js          creates the first admin account
│   │   ├── ageSync.service.js
│   │   └── club.service.js
│   │
│   ├── scripts/                          one-off maintenance scripts
│   │   ├── check-users.js
│   │   ├── clear-users.js
│   │   ├── find-user.js
│   │   ├── fix-email-index.js
│   │   ├── remove-username-index.js
│   │   └── smoke-check-server.js
│   │
│   ├── uploads/
│   │   └── .gitkeep                      uploaded match videos go here (ignored by git)
│   │
│   └── python-api/                       Flask AI service (the current one)
│       ├── app.py                        Flask routes: market value, injury risk, video
│       ├── football_pipeline.py          video detection and tracking pipeline
│       ├── run_football_video_analysis.py  CLI entry for video analysis
│       ├── extract_features.py
│       ├── create_training_columns.py
│       ├── training_columns.py
│       ├── save_columns.py
│       ├── check_feature_importance.py
│       ├── setup.py
│       ├── start-api.js                  launcher used by npm run dev:python
│       ├── requirements.txt              now includes torch and ultralytics
│       ├── models/
│       │   ├── football_model_integrated.pkl
│       │   ├── goalnet.pt                video model weights
│       │   ├── player_value_model.pkl
│       │   ├── training_columns.pkl
│       │   └── xgboost_model.pkl
│       └── output_videos/
│           └── .gitkeep                  annotated results go here (ignored by git)
│
└── python-api/                           old duplicate of the AI service (candidate to delete)
    ├── app.py
    ├── check_feature_importance.py
    ├── create_training_columns.py
    ├── extract_features.py
    ├── save_columns.py
    ├── setup.py
    ├── start-api.js
    ├── training_columns.py
    ├── requirements.txt
    ├── README.md
    ├── INSTALL.md
    ├── INSTALL_AFTER_PYTHON313_REMOVAL.md
    ├── FIX_PIP_INSTALL.md
    ├── FIX_PIP_NO_INDEX.md
    ├── FIX_PROXY_ISSUE.md
    ├── PYTHON_VERSION_ISSUE.md
    ├── START_PYTHON_API.md
    └── models/
        ├── player_value_model.pkl
        ├── training_columns.pkl
        └── xgboost_model.pkl
```
