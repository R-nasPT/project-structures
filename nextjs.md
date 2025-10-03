```
📁 src/
├── 📁 app/                                       # App Router (route handlers + UI entry points)
│   ├── 📁 (auth)/                                # Route group - Authentication
│   │   ├── 📁 login/
│   │   ├── 📁 register/
│   │   └── 📁 layout.tsx
│   ├── 📁 (marketing)/                           # group routes (landing page, blog, etc.)
│   │   ├── 📁 about/
│   │   ├── 📁 pricing/
│   │   └── 📄 layout.tsx
│   ├── 📁 (dashboard)/                           # group routes (protected routes)
│   │   ├── 📄 layout.tsx
│   │   ├── 📄 page.tsx
│   │   └── 📁 orders/
│   │       ├── 📄 page.tsx
│   │       ├── 📄 loading.tsx
│   │       └── 📄 error.tsx
│   ├── 📁 api/                                   # Route handlers (API endpoints)
│   │   ├── 📁 auth/
│   │   ├── 📁 webhooks/
│   │   └── 📁 orders/
│   │       └── 📄 route.ts
│   ├── 📄 not-found.tsx
│   ├── 📄 page.tsx
│   └── 📄 layout.tsx
│
├── 📁 features/                              # 🎯 Feature-based modules
│   ├── 📁 auth/                              # 🔐 Authentication feature
│   │   ├── 📁 components/
│   │   │   ├── 📄 login-form.tsx
│   │   │   └── 📄 signup-form.tsx
│   │   ├── 📁 hooks/
│   │   │   ├── 📄 use-auth.ts
│   │   │   └── 📄 use-login.ts
│   │   ├── 📁 schemas/                       # 📋 Validation schemas
│   │   │   ├── 📄 login-schema.ts
│   │   │   └── 📄 register-schema.ts
│   │   ├── 📁 services/
│   │   │   └── 📄 auth-service.ts
│   │   ├── 📁 store/
│   │   │   ├── 📄 auth-store.ts
│   │   │   └── 📄 auth-slice.ts
│   │   └── 📁 types/                         # 🧬 Feature-specific types
│   │       └── 📄 auth-types.ts
│   │
│   ├── 📁 dashboard/                         # 📊 Dashboard feature
│   │   ├── 📁 components/
│   │   ├── 📁 hooks/
│   │   ├── 📁 helpers/
│   │   ├── 📁 services/
│   │   ├── 📁 store/
│   │   └── 📁 types/
│   │
│   └── 📁 marketing/                          # ⚙️ App Settings feature
│       ├── 📁 components/
│       ├── 📁 constansts/
│       ├── 📁 hooks/
│       ├── 📁 services/
│       └── 📁 types/
│
├── 📁 shared/                                # 🔄 Reusable components and utilities
│   ├── 📁 components/
│   │   ├── 📁 ui/                            # 🧱 Basic UI building blocks - Reusable everywhere
│   │   │   ├── 📄 button.tsx
│   │   │   ├── 📄 input.tsx
│   │   │   ├── 📄 select.tsx
│   │   │   ├── 📄 checkbox.tsx
│   │   │   ├── 📄 modal.tsx
│   │   │   ├── 📄 badge.tsx
│   │   │   ├── 📄 card.tsx
│   │   │   ├── 📄 textarea.tsx
│   │   │   ├── 📄 switch.tsx
│   │   │   ├── 📄 breadcrumb.tsx
│   │   │   └── 📄 index.ts
│   │   │
│   │   ├── 📁 composite/                     # 🔗 Combined UI components - Enhanced functionality
│   │   │   ├── 📄 search-box.tsx
│   │   │   ├── 📄 file-upload.tsx
│   │   │   ├── 📄 filter-bar.tsx
│   │   │   ├── 📄 date-picker.tsx
│   │   │   ├── 📄 confirm-dialog.tsx
│   │   │   └── 📄 index.ts
│   │   │
│   │   ├── 📁 widgets/                       # 🎯 Purpose-specific components - Business logic included (component เฉพาะจุดประสงค์)
│   │   │   ├── 📄 status-badge.tsx
│   │   │   ├── 📄 role-chip.tsx              # 🔐 Show user role + color + permission indicator
│   │   │   ├── 📄 currency-display.tsx       # 💵 Show currency + format + symbol
│   │   │   ├── 📄 attachment-section.tsx
│   │   │   ├── 📄 stat-card.tsx              # 📊 Show statistics + icon + trend + comparison
│   │   │   └── 📄 index.ts
│   │   │
│   │   ├── 📁 wrappers/                      # 📦 Layout containers - Structure and spacing
│   │   │   ├── 📄 section-panel.tsx
│   │   │   ├── 📄 page-header.tsx
│   │   │   └── 📄 index.ts
│   │   │
│   │   ├── 📁 common/                        # ⚡ Common utilities - States and notifications
│   │   │   ├── 📄 loading-spinner.tsx
│   │   │   ├── 📄 error-boundary.tsx         # ⚠️ ไม่ค่อยจำเป็น
│   │   │   ├── 📄 error-fallback.tsx
│   │   │   ├── 📄 not-found.tsx
│   │   │   └── 📄 index.ts
│   │   └── 📄 index.ts                       # 📦 Export barrel
│   │
│   ├── 📁 constants/
│   │   ├── 📄 routes-constants.ts
│   │   ├── 📄 app-constants.ts
│   │   ├── 📄 roles-constants.ts
│   │   ├── 📄 regex-constants.ts             # ✍️ Regular expressions
│   │   ├── 📄 storage-constants.ts           # 🗝️ Keys for localStorage / sessionStorage
│   │   └── 📄 index.ts
│   │
│   ├── 📁 helpers/                           # 🛠️ Helper functions
│   │   ├── 📄 auth-helpers.ts
│   │   ├── 📄 business-helpers.ts
│   │   ├── 📄 api-helpers.ts                 # 🌐 API-related helpers
│   │   ├── 📄 ui-helpers.ts                  # 🎨 UI-specific helpers
│   │   └── 📄 index.ts
│   │
│   ├── 📁 hooks/                             # 🪝 Shared custom hooks
│   │   ├── 📄 use-analytics.ts
│   │   ├── 📄 use-copy-to-clipboard.ts
│   │   ├── 📄 use-permissions.ts
│   │   └── 📄 index.ts
│   │
│   ├── 📁 lib/                               # 📚 Third-party configs
│   │   ├── 📄 icons.ts 
│   │   ├── 📄 logger.ts                      # 📝 Logging setup
│   │   └── 📄 index.ts
│   │
│   ├── 📁 schemas/                           # 📂 Shared data schemas (validation, API shapes, form structures)
│   │   ├── 📄 common-schema.ts
│   │   ├── 📄 api-schema.ts
│   │   ├── 📄 form-schema.ts
│   │   └── 📄 index.ts
│   │
│   ├── 📁 services/                          # 🔌 Shared services
│   │   ├── 📁 api/
│   │   │   ├── 📄 api-client.ts
│   │   │   ├── 📄 endpoints.ts
│   │   │   ├── 📄 interceptors.ts
│   │   │   └── 📄 index.ts
│   │   ├── 📁 storage/
│   │   │   ├── 📄 local-storage.ts
│   │   │   ├── 📄 session-storage.ts
│   │   │   └── 📄 index.ts
│   │   └── 📄 index.ts
│   │
│   ├── 📁 store/                             # 🏪 Shared state stores
│   │   ├── 📄 common-store.ts
│   │   ├── 📄 cache-store.ts
│   │   ├── 📄 ui-store.ts
│   │   └── 📄 index.ts
│   │
│   ├── 📁 utils/                             # 🔧 Utility functions
│   │   ├── 📄 format-utils.ts
│   │   ├── 📄 date-utils.ts
│   │   └── 📄 index.ts
│   │
│   └── 📁 types/                             # 🧩 Shared business types
│       ├── 📄 api-types.ts
│       ├── 📄 common-types.ts
│       ├── 📄 env-types.ts
│       └── 📄 index.ts
│
├── 📁 core/                                  # 🏗️ Core app infrastructure
│   ├── 📁 layout/                            # 📐 App layout components
│   │   ├── 📁 header/
│   │   ├── 📁 sidebar/
│   │   ├── 📁 footer/
│   │   └── 📄 index.ts
│   ├── 📁 store/                             # 🗄️ Global state management
(Redux)
│   │   ├── 📄 index.ts
│   │   └── 📄 root-reducer.ts
(Zustand)
│   │   ├── 📄 app-store.ts
│   │   └── 📄 index.ts
│   └── 📁 providers/                         # 🔧 App-wide providers
│       ├── 📄 query-provider.tsx
│       ├── 📄 theme-provider.tsx
│       └── 📄 auth-provider.tsx
│
├── 📁 assets/                                # 📁 Static assets
│   ├── 📁 images/
│   ├── 📁 icons/
│   ├── 📁 fonts/
│   └── 📁 videos/
│
├── 📁 config/                                # ⚙️ Configuration files
│   ├── 📄 env.ts
│   ├── 📄 database-config.ts
│   ├── 📄 auth-config.ts
│   ├── 📄 navigation-config.ts
│   └── 📄 index.ts
│
├── 📁 types/                                 # 📘 Global types (augmentation, env)
│   ├── 📄 next-auth.d.ts
│   ├── 📄 global.d.ts
│   ├── 📄 env.d.ts
│   └── 📄 next.d.ts
│
└── 📁 styles/                                # 🎨 global styles, tailwind.css
│   └── 📄 globals.css
│
└── 📄 middleware.tsx                         # 🚀 App entry point
```
