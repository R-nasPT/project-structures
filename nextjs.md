# Next.js App Router Project Structure

> A scalable, enterprise-grade folder structure for Next.js applications using App Router with modern patterns. 

## 📁 Recommended Structure

```
📁 src/
├── 📁 app/                                   # 🚀 App Router (route handlers + UI entry points)
│   ├── 📁 (auth)/                            # 🔑 Route group - Authentication
│   │   ├── 📁 login/
│   │   ├── 📁 register/
│   │   └── 📁 layout.tsx
│   │
│   ├── 📁 (marketing)/                       # 🌐 group routes (landing page, blog, etc.)
│   │   ├── 📁 about/
│   │   ├── 📁 pricing/
│   │   └── 📄 layout.tsx
│   │
│   ├── 📁 (dashboard)/                       # 🔒 group routes (protected routes)
│   │   ├── 📄 layout.tsx
│   │   ├── 📄 page.tsx
│   │   └── 📁 orders/
│   │       ├── 📄 page.tsx
│   │       ├── 📄 loading.tsx
│   │       └── 📄 error.tsx
│   │
│   ├── 📁 api/                               # 🛠️ Route handlers (API endpoints)
│   │   ├── 📁 auth/
│   │   ├── 📁 webhooks/
│   │   └── 📁 orders/
│   │       └── 📄 route.ts
│   │
│   ├── 📄 not-found.tsx                      # 🚫 Global 404 page
│   ├── 📄 error.tsx                          # 💥 Global error page
│   ├── 📄 page.tsx                           # 🏠 Home page
│   └── 📄 layout.tsx                         # 🎨 Root layout
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
│   └── 📁 marketing/                         # ⚙️ App Settings feature
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
│   │   ├── 📄 error-fallback.tsx
│   │   └── 📄 index.ts
│   │
│   ├── 📁 store/                             # 🗄️ Global state management
│   │   ├── 📄 index.ts
│   │   ├── 📄 root-reducer.ts                # For Redux
│   │   └── 📄 app-store.ts                   # For Zustand
│   │
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
├── 📁 styles/                                # 🎨 global styles, tailwind.css
│   └── 📄 globals.css
│
└── 📄 middleware.ts                          # 🛡️ Next.js middleware
```

## 🎯 Key Principles

### 1. **App Router First**
From Next.js 13 onwards, the App Router has been the primary routing system, with file-based routing conventions.
- **Route Groups** `(folder)` - Organize routes without affecting URL structure
- **Layouts** - Shared UI that persists across routes
- **Loading States** - Automatic loading UI with `loading.tsx`
- **Error Handling** - Error boundaries with `error.tsx`
- **API Routes** - Server-side endpoints in `app/api/`

### 2. **Feature-Based Organization**
Each feature is self-contained with its own components, hooks, services, and types. This makes features easier to maintain, test, and scale independently.

### 3. **Clear Separation of Concerns**
- **`app/`** - File-based routing and API endpoints (Next.js App Router)
- **`core/`** - Application infrastructure (layouts, providers, global state)
- **`features/`** - Business logic organized by domain
- **`shared/`** - Reusable components and utilities
- **`config/`** - Application configuration

### 4. **Component Hierarchy**
Components are organized by complexity and purpose :
- **`ui/`** - Basic building blocks (Button, Input, Card)
- **`composite/`** - Combined components (SearchBox, FileUpload)
- **`widgets/`** - Business-logic components (StatusBadge, StatCard)
- **`wrappers/`** - Layout containers (SectionPanel, PageHeader)
- **`common/`** - Utility components (LoadingSpinner)

### 5. **Server and Client Components**
From Next.js 13 onwards, Next.js defaults to Server Components, providing better performance.
- Server Components fetch data directly
- Client Components use `'use client'` directive
- Proper separation improves bundle size and performance

---

## 📝 File Examples

### App Router - Route Groups and Layouts

#### Page Component (`app/(dashboard)/orders/page.tsx`)
```tsx
import { OrdersList } from '@/features/orders/components/orders-list';
import { getOrders } from '@/features/orders/services/orders-service';

export default async function OrdersPage() {
  // Server Component - fetch data directly
  const orders = await getOrders();

  return (
    <div className="orders-page">
      <h1>Orders</h1>
      <OrdersList orders={orders} />
    </div>
  );
}
```

#### Error Handling (`app/(dashboard)/orders/error.tsx`)
```tsx
'use client';

import { useEffect } from 'react';
import { ErrorFallback } from '@/shared/components/common/error-fallback';

export default function Error({
  error,
  reset,
}: {
  error: Error & { digest?: string };
  reset: () => void;
}) {
  useEffect(() => {
    console.error(error);
  }, [error]);

  return (
    <ErrorFallback
      error={error}
      reset={reset}
    />
  );
}
```

---

## 🎯 Features - Business Logic Modules

Each feature is a self-contained module following the same structure.

### Standard Feature Structure

```
features/[feature-name]/
├── components/              # Feature-specific components
├── hooks/                   # Custom hooks for business logic
├── schemas/                 # Validation schemas (Zod/Yup)
├── services/                # API calls and data fetching
├── store/                   # Feature-specific state
├── types/                   # TypeScript definitions
├── constants/               # Feature-specific constants
└── helpers/                 # Feature-specific utilities
```

### Example Feature

#### Auth Feature Service (`features/auth/services/auth-service.ts`)
```typescript
import { api } from '@/shared/services/api/api-client';
import type { LoginCredentials, AuthResponse } from '../types/auth-types';

export const authService = {
  login: async (credentials: LoginCredentials): Promise<AuthResponse> => {
    const response = await api.post<AuthResponse>('/auth/login', credentials);
    return response.data;
  },

  logout: async (): Promise<void> => {
    await api.post('/auth/logout');
  },

  getCurrentUser: async () => {
    const response = await api.get('/auth/me');
    return response.data;
  },
};
```

---

## 🔄 Shared Components

### Component Categories

#### 🧱 `ui/` - Basic Building Blocks
Pure UI components with no business logic.

```tsx
// shared/components/ui/button.tsx
import type { ButtonHTMLAttributes } from 'react';

interface ButtonProps extends ButtonHTMLAttributes<HTMLButtonElement> {
  variant?: 'primary' | 'secondary' | 'ghost';
  size?: 'sm' | 'md' | 'lg';
}

export function Button({ 
  variant = 'primary', 
  size = 'md',
  className = '',
  children,
  ...props 
}: ButtonProps) {
  return (
    <button 
      className={`btn btn-${variant} btn-${size} ${className}`}
      {...props}
    >
      {children}
    </button>
  );
}
```

#### 🔗 `composite/` - Combined Components
Components that combine multiple UI elements.

```tsx
// shared/components/composite/search-box.tsx
'use client';

import { useState, useEffect } from 'react';
import { Input } from '@/shared/components/ui/input';
import { Button } from '@/shared/components/ui/button';

interface SearchBoxProps {
  onSearch: (query: string) => void;
  debounce?: number;
  placeholder?: string;
}

export function SearchBox({ 
  onSearch, 
  debounce = 300,
  placeholder = 'Search...',
}: SearchBoxProps) {
  const [value, setValue] = useState('');

  useEffect(() => {
    const timer = setTimeout(() => {
      onSearch(value);
    }, debounce);

    return () => clearTimeout(timer);
  }, [value, debounce, onSearch]);

  return (
    <div className="search-box">
      <Input 
        value={value}
        onChange={(e) => setValue(e.target.value)}
        placeholder={placeholder}
      />
      {value && (
        <Button 
          variant="ghost" 
          onClick={() => setValue('')}
        >
          Clear
        </Button>
      )}
    </div>
  );
}
```

#### 🎯 `widgets/` - Business Logic Components
Components with domain-specific logic.

```tsx
// shared/components/widgets/status-badge.tsx
import { Badge } from '@/shared/components/ui/badge';

type Status = 'pending' | 'approved' | 'rejected';

const statusConfig = {
  pending: { color: 'yellow', icon: '⏳', label: 'Pending' },
  approved: { color: 'green', icon: '✓', label: 'Approved' },
  rejected: { color: 'red', icon: '✗', label: 'Rejected' },
} as const;

interface StatusBadgeProps {
  status: Status;
}

export function StatusBadge({ status }: StatusBadgeProps) {
  const config = statusConfig[status];
  
  return (
    <Badge variant={config.color}>
      <span>{config.icon}</span>
      <span>{config.label}</span>
    </Badge>
  );
}
```

---

## 📊 Component Decision Tree

```
Need to create a component?
│
├─ Basic UI element? (Button, Input, Card)
│  └─ ✅ Place in shared/components/ui/
│
├─ Combines multiple UI elements? (SearchBox, FileUpload)
│  └─ ✅ Place in shared/components/composite/
│
├─ Has business logic? (StatusBadge, StatCard)
│  └─ ✅ Place in shared/components/widgets/
│
├─ Layout/Structure purpose? (SectionPanel, PageHeader)
│  └─ ✅ Place in shared/components/wrappers/
│
├─ Utility/State component? (LoadingSpinner, ErrorBoundary)
│  └─ ✅ Place in shared/components/common/
│
└─ Feature-specific? (LoginForm, OrderCard)
   └─ ✅ Place in features/[feature]/components/
```

---

## 🚀 Benefits

### ✅ **Scalability**
- Feature-based organization scales with your app
- Route groups organize without affecting URLs
- Easy to add new features independently
- Clear boundaries between modules

### ✅ **Maintainability**
- Related code grouped together
- Consistent patterns across codebase
- Easy to locate specific functionality
- Self-documenting structure

### ✅ **Code Reusability**
- Shared components and hooks prevent duplication
- Features can be easily extracted or reused
- Common patterns are centralized
- Component hierarchy promotes composition

### ✅ **Developer Experience**
- Predictable file locations
- Type-safe with TypeScript
- Modern React patterns
- Easy to onboard new developers

---

## 🎨 Naming Conventions

### Files and Folders
- Use **kebab-case** for all files and folders in Next.js:
  - Components: `user-profile.tsx`, `product-card.tsx`
  - Services: `auth-service.ts`, `orders-service.ts`
  - Hooks: `use-auth.ts`, `use-orders.ts`
  - Utils: `date-utils.ts`, `format-utils.ts`
  - Constants: `routes-constants.ts`, `app-constants.ts`
  - Types: `auth-types.ts`, `api-types.ts`

### Next.js Special Files
- Use **lowercase** for Next.js convention files:
  - `page.tsx` - Route page
  - `layout.tsx` - Layout wrapper
  - `loading.tsx` - Loading UI
  - `error.tsx` - Error boundary
  - `not-found.tsx` - 404 page
  - `route.ts` - API route handler

### Route Groups
- Use **parentheses** for route groups: `(auth)`, `(dashboard)`, `(marketing)`

### Constants
- Use **UPPER_CASE** for constant variables: `API_BASE_URL`, `MAX_FILE_SIZE`

---

## 📚 Additional Tips

### Import Organization
```tsx
// 1. React and Next.js
import { useState } from 'react';
import { useRouter } from 'next/navigation';
import Image from 'next/image';

// 2. External libraries
import { useQuery } from '@tanstack/react-query';
import { z } from 'zod';

// 3. Internal imports - grouped by source
import { Button } from '@/shared/components/ui/button';
import { SearchBox } from '@/shared/components/composite/search-box';
import { useDebounce } from '@/shared/hooks/use-debounce';

// 4. Feature imports
import { useOrders } from '@/features/orders/hooks/use-orders';
import { ordersService } from '@/features/orders/services/orders-service';

// 5. Types
import type { Order } from '@/features/orders/types/order-types';

// 6. Relative imports (only when necessary)
import { OrderCard } from './order-card';
```

### Server vs Client Components

```tsx
// ✅ Server Component (default)
// app/(dashboard)/orders/page.tsx
import { ordersService } from '@/features/orders/services/orders-service';
import { OrdersList } from '@/features/orders/components/orders-list';

// This component runs on the server
export default async function OrdersPage() {
  // Direct async/await - no need for useEffect or useState
  const orders = await ordersService.getAll();

  return (
    <div>
      <h1>Orders</h1>
      <OrdersList orders={orders} />
    </div>
  );
}

// ✅ Client Component (when needed)
// features/orders/components/orders-list-client.tsx
'use client';

import { useQuery } from '@tanstack/react-query';
import { ordersService } from '../services/orders-service';
import { OrderCard } from './order-card';
import { LoadingSpinner } from '@/shared/components/common/loading-spinner';
import { ErrorFallback } from '@/shared/components/common/error-fallback';

export function OrdersListClient() {
  const { data: orders, isLoading, error } = useQuery({
    queryKey: ['orders'],
    queryFn: () => ordersService.getAll(),
  });

  if (isLoading) {
    return <LoadingSpinner />;
  }

  if (error) {
    return <ErrorFallback error={error} />;
  }

  return (
    <div className="orders-grid">
      {orders?.map(order => (
        <OrderCard key={order.id} order={order} />
      ))}
    </div>
  );
}
```

### Barrel Exports
Use `index.ts` files to create clean import paths:

```typescript
// features/orders/components/index.ts
export { OrdersList } from './orders-list';
export { OrderCard } from './order-card';
export { OrderFilters } from './order-filters';
export { OrderDetails } from './order-details';

// Usage
import { OrdersList, OrderCard } from '@/features/orders/components';
```

---

## 🧪 Testing Structure

### Testing Setup

```
__tests__/
├── e2e/                      # End-to-end tests (Playwright)
│   ├── auth.spec.ts
│   ├── orders.spec.ts
│   └── dashboard.spec.ts
│
├── integration/              # Integration tests
│   ├── api/
│   │   ├── orders.test.ts
│   │   └── auth.test.ts
│   └── features/
│       └── orders/
│           └── orders-service.test.ts
│
└── unit/                     # Unit tests
    └── shared/
        ├── components/
        │   └── ui/
        │       └── button.test.tsx
        └── utils/
            └── format-utils.test.ts
```

---

## 🎉 Conclusion

This Next.js structure provides a solid foundation for building modern, scalable web applications. Key takeaways :

* **Feature-based** organization keeps related code together
* **Clear component hierarchy** (ui → composite → widgets → wrappers)
* **Separation of concerns** across core, features, shared modules, and the application layer
* **Type-safe** throughout with TypeScript
* **Consistent patterns** make the codebase predictable
* **Easy to maintain** and extend as the app grows

Remember: This structure is a guideline that should be adapted to your specific needs. Start with the basics and expand as your application grows.

**Happy coding with Next.js! 🚀**
